<script>
  import { slide } from "svelte/transition";
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
</script>

<div class="container" in:slide>
  {#each Peoples as people}
    <div class="people">
      <div class="profile-pic" />
      <div class="profile-name">{people.name}</div>
      <div class="profile-about">{people.about}</div>
    </div>
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
    background-color: #0f52ba;
  }

  .profile-pic {
    width: 70%;
    height: 70%;
    border-radius: 50%;
    background-color: white;
  }

  .profile-name {
    font-size: 30px;
    margin-bottom: 5px;
  }

  .profile-about{
    font-size: small;
    font-style: italic;
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
