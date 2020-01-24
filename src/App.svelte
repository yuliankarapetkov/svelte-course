<script>
    import ContactCard from './ContactCard.svelte';

    let name = 'Yulian';
    let title = 'Software Developer';
    let imageUrl = 'https://avatars0.githubusercontent.com/u/6671521?s=220&v=4';
    let description = 'Some description';

    let contacts = [];

    function addContact() {
        const contact = { name, title, imageUrl, description };

        contacts = [
            ...contacts,
            contact
        ];
    }
</script>

<style>
  #form {
    width: 30rem;
    max-width: 100%;
  }
</style>

<div id="form">
  <div class="form-control">
    <label for="name">Name</label>
    <input type="text" bind:value={name} id="name" />
  </div>
  <div class="form-control">
    <label for="title">Title</label>
    <input type="text" bind:value={title} id="title" />
  </div>
  <div class="form-control">
    <label for="imageUrl">Image URL</label>
    <input type="text" bind:value={imageUrl} id="imageUrl" />
  </div>
  <div class="form-control">
    <label for="description">Description</label>
    <textarea rows="3" bind:value={description} id="description" />
  </div>
</div>

<button on:click="{addContact}">
    Add contact
</button>

{#each contacts as contact, index}
    <h2>#{index + 1}</h2>
    <ContactCard {...contact} />
{:else}
    No contacts here yet. :(
{/each}
