<script>
  import { slide,scale } from "svelte/transition";
    import SearchBox from "../components/SearchBox.svelte";
  const Peoples = [
    {
      name: "Anurag Singh",
      about: "Indie Game Dev",
    },

    {
      name: "Kumar Sourav",
      about: "Content Writer",
    },

    {
      name: "Balak",
      about: "Template modifier",
    },

    {
      name: "Dummy",
      about: "Dummy",
    },

    {
      name: "Dummy2",
      about: "About",
    },

    {
      name: "Dummy2",
      about: "About",
    },

    {
      name: "Dummy2",
      about: "About",
    },

    {
      name: "Dummy2",
      about: "About",
    },

    {
      name: "Dummy2",
      about: "About",
    },
  ];

  let searchText = "";
</script>

<SearchBox bind:searchText/>
<div class="container" in:slide >
  {#each Peoples as people}
  {#if people.name.toLocaleLowerCase().includes(searchText.toLocaleLowerCase().trim())}
    <div class="people" transition:scale>
      <div class="profile-pic" />
      <div class="profile-name">{people.name}</div>
      <div class="profile-about">{people.about}</div>
    </div>
    {/if}
  {/each}
</div>

<style>
  .container {
    display: flex;
    flex-wrap: wrap;
    color: #f2f2f2;
    gap: 10px;
    justify-content: space-between;
    padding-bottom: 10px;
  }

  .people {
    width: calc(25% - 8px);
    aspect-ratio: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background-color: #f2f2f2;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  }

  .profile-pic {
    width: 70%;
    height: 70%;
    border-radius: 50%;
    border:solid 2px #333;
  }

  .profile-name {
    font-size: 30px;
    margin-bottom: 5px;
    color: #333;
  }

  .profile-about{
    font-size: small;
    font-style: italic;
    color: #555;
  }

  @media (max-width: 768px)  {
    .container {
      flex-direction: column;
    }

    .people {
      width: 100%;
    }
  }
</style>
