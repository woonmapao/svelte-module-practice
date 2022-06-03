<script>
    import Header from "./UI/Header.svelte";
    import MeetupGrid from "./Meetups/MeetupGrid.svelte";
    import Ripple from "./UI/Ripple.svelte";
    import TextInput from "./UI/TextInput.svelte";
    import Button from "./UI/Button.svelte";

    let title = "";
    let subtitle = "";
    let address = "";
    let email = "";
    let description = "";
    let imageUrl = "";

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
        },
    ];

    function addMeetup() {
        const newMeetup = {
            id: Math.random().toString(),
            title: title,
            subtitle: subtitle,
            description: description,
            imageUrl: imageUrl,
            contactEmail: email,
            address: address,
        };
        meetups = [newMeetup, ...meetups];
    }
</script>

<Header />
<Ripple />

<main>
    <form on:submit|preventDefault={addMeetup}>
        <TextInput id="title" label="Title" bind:value={title} />
        <TextInput id="subtitle" label="Subitle" bind:value={subtitle} />
        <TextInput id="address" label="Address" bind:value={address} />
        <TextInput id="imageUrl" label="Image Url" bind:value={imageUrl} />
        <TextInput id="email" label="E-Mail" bind:value={email} />
        <TextInput
            id="description"
            label="Description"
            bind:value={description}
        />
        <Button type="text" caption="Save" />
    </form>
    <MeetupGrid {meetups} />
</main>

<style>
    main {
        margin-top: 5rem;
    }

    form {
        width: 30rem;
        max-width: 90%;
        margin: auto;
    }
</style>
