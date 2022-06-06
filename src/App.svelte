<script>
    import Header from "./UI/Header.svelte";
    import MeetupGrid from "./Meetups/MeetupGrid.svelte";
    import Ripple from "./UI/Ripple.svelte";
    import TextInput from "./UI/TextInput.svelte";
    import Button from "./UI/Button.svelte";
    import EditMeetup from "./Meetups/EditMeetup.svelte";

    let meetups = [
        {
            id: "1",
            title: "Monmon Fanmeet",
            subtitle: "Met Monmon and only Mon",
            description:
                "In this meetup, you'll meet the glorious Monmon cat that teach you how to sleep!",
            imageUrl: "images/moncat.jpg",
            address: "Monmon Home",
            contactEmail: "Monmon.cat@business.com",
            isFavourite: false,
        },
        {
            id: "2",
            title: "Shopping with Mii",
            subtitle: "Walk and follow Mii evreywhere!",
            description:
                "In this meetup, you had to walk around and nothing else",
            imageUrl: "images/miicat.jpg",
            address: "Future Park Rangsit",
            contactEmail: "Mii.shoping@catmail.com",
            isFavourite: false,
        },
    ];

    let editMode;

    function addMeetup(e) {
        const newMeetup = {
            id: Math.random().toString(),
            title: e.detail.title,
            subtitle: e.detail.subtitle,
            description: e.detail.description,
            imageUrl: e.detail.imageUrl,
            contactEmail: e.detail.email,
            address: e.detail.address,
        };
        meetups = [newMeetup, ...meetups];
        editMode = null;
    }

    function cancelEdit() {
        editMode = null;
    }

    function toggleFavourite(e) {
        const id = e.detail;
        const updatedMeetup = { ...meetups.find((m) => m.id === id) };
        updatedMeetup.isFavourite = !updatedMeetup.isFavourite;
        const meetupIndex = meetups.findIndex((m) => m.id === id);
        const updatedMeetups = [...meetups];
        updatedMeetups[meetupIndex] = updatedMeetup;
        meetups = updatedMeetups;
    }
</script>

<Header />
<Ripple />

<main>
    <div class="meetup-controls">
        <Button on:click={() => (editMode = "add")}>New Meetup</Button>
    </div>
    {#if editMode === "add"}
        <EditMeetup on:save={addMeetup} on:cancel={cancelEdit} />
    {/if}
    <MeetupGrid {meetups} on:togglefavorite={toggleFavourite} />
</main>

<style>
    main {
        margin-top: 5rem;
    }

    .meetup-controls {
        margin: 1rem;
    }
</style>
