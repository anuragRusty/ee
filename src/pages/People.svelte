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
  ];
</script>

<div class="container" in:slide>
  {#each Peoples as people}
    <div class="people">
      <div class="profile-pic" />
      <p class="profile-name">{people.name}</p>
      <p>{people.about}</p>
    </div>
  {/each}
</div>

<style>
  .container {
    display: flex;
    flex-wrap: wrap;
    color: #f2f2f2;
    gap: 10px;
    padding-bottom: 10px;
  }

  .people {
    width: 32.5%;
    aspect-ratio: 1/1;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background-color: #0f52ba;
  }

  .profile-pic {
    width: 60%;
    height: 60%;
    border-radius: 50%;
    background-color: white;
  }

  .profile-name {
    font-size: larger;
  }

  @media only screen and (max-width: 600px) {
    .container {
      flex-direction: column;
    }

    .people {
      width: 100%;
    }
  }
</style>
