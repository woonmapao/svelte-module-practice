<script>
    import { createEventDispatcher } from "svelte";
    import TextInput from "../UI/TextInput.svelte";
    import Button from "../UI/Button.svelte";
    import Modal from "../UI/Modal.svelte";

    let title = "";
    let subtitle = "";
    let address = "";
    let email = "";
    let description = "";
    let imageUrl = "";

    const dispatch = createEventDispatcher();

    function submitForm() {
        dispatch("save", {
            title: title,
            subtitle: subtitle,
            address: address,
            email: email,
            description: description,
            imageUrl: imageUrl,
        });
    }

    function cancel() {
        dispatch("cancel");
    }
</script>

<Modal title="Edit Meetup Data" on:cancel>
    <form on:submit|preventDefault={submitForm}>
        <TextInput
            id="title"
            label="Title"
            value={title}
            on:input={(e) => (title = e.target.value)}
        />
        <TextInput
            id="subtitle"
            label="Subitle"
            value={subtitle}
            on:input={(e) => (subtitle = e.target.value)}
        />
        <TextInput
            id="address"
            label="Address"
            value={address}
            on:input={(e) => (address = e.target.value)}
        />
        <TextInput
            id="imageUrl"
            label="Image Url"
            value={imageUrl}
            on:input={(e) => (imageUrl = e.target.value)}
        />
        <TextInput
            id="email"
            label="E-Mail"
            value={email}
            on:input={(e) => (email = e.target.value)}
        />
        <TextInput
            id="description"
            label="Description"
            value={description}
            on:input={(e) => (description = e.target.value)}
        />
    </form>
    <div slot="footer">
        <Button type="submit" mode="outline" on:click={cancel}>Cancel</Button>
        <Button type="submit" on:click={submitForm}>Save</Button>
    </div>
</Modal>

<style>
    form {
        width: 100%;
    }
</style>
