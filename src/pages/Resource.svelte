<script>
import {slide,fade} from "svelte/transition";
import OptionBox from "../components/OptionBox.svelte";
    import SearchBox from "../components/SearchBox.svelte";

const years = ["2019","2020","2021","2022","2023"];
const semesters = ["1","2","3","4","5","6","7"];

const subjects = [
    {
      name: 'Digital Electronics',
      selctedYear:"",
      selectedSem:"",
      selectedNotes:"",
      questionPapers: [
        {
          year: '2022',
          sem:"1",
          link: 'https://example.com/electrical-circuits-2022.pdf',
        },
        {
          year: '2021',
          sem:"2",
          link: 'https://example.com/electrical-circuits-2022.pdf',
        },
      ],
      notes: [
        {
          title: 'Basic Concepts',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Fundamental Concepts',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Intermediated Concepts',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Advanced Concepts',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },
      ],
    },

    {
      name: 'Analog Electronics',
      selctedYear:"",
      selectedSem:"",
      selectedNotes:"",
      questionPapers: [
        {
          year: '2022',
          sem:"1",
          link: 'https://example.com/electrical-circuits-2022.pdf',
        },
        {
          year: '2021',
          sem:"2",
          link: 'https://example.com/electrical-circuits-2022.pdf',
        },
      ],
      notes: [
        {
          title: 'Rectifer',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Filter',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Chopper',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Amplifier',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },
      ],
    },

    {
      name: 'Power Electronics',
      selctedYear:"",
      selectedSem:"",
      selectedNotes:"",
      questionPapers: [
        {
          year: '2022',
          sem:"1",
          link: 'https://example.com/electrical-circuits-2022.pdf',
        },
        {
          year: '2021',
          sem:"2",
          link: 'https://example.com/electrical-circuits-2022.pdf',
        },
      ],
      notes: [
        {
          title: 'Thrysistor',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Diodes',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Transistor',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },

        {
          title: 'Oscillators',
          link: 'https://example.com/electrical-circuits-basic-concepts.pdf',
        },
      ],
    },
  ];

  let searchText = "";

</script>
<SearchBox bind:searchText={searchText}/>

<div class="container" in:slide>
    <div class="sub-container-1">
    </div>
    {#each subjects as subject}
    {#if subject.name.toLocaleLowerCase().includes(searchText.toLocaleLowerCase().trim())}
     <div class="subject" transition:fade>
         <div class="qp">
            <h2>{subject.name}</h2>
            <h3>Previous Year Question Papers</h3>
            <div class="options">
              <OptionBox options={years} placeholder={"Select Year"} bind:selectedOption={subject.selectedYear} />
              <OptionBox options={semesters} placeholder={"Select Sem"} bind:selectedOption={subject.selectedSem} />
           </div>
         {#each subject.questionPapers as qp,i}
         {#if subject.selectedYear === qp.year && subject.selectedSem === qp.sem}
         <a class="links" href={qp.link}><button>Download</button></a>
         {/if}
         {/each}
      </div>

       <div class=notes>
        <h3>Short Notes</h3>
          <div class="notes-op">
        <OptionBox options={subject.notes.map((obj) => obj.title)}  placeholder={"Select Notes"} bind:selectedOption={subject.selectedNotes}/>
        </div>
        {#each subject.notes as n,i}
          {#if subject.selectedNotes == n.title}
          <a class="links" href={n.link}><button>Download</button></a>
          {/if}
         {/each}
       </div>
    </div>
    {/if}
    {/each}
</div>

<style>

    .container{
        display: flex;
        flex-wrap: wrap;
        gap:10px;
        padding-bottom: 10px;
    }

    .subject{
        width: calc(33% - 6px);
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        display: flex;
        flex-direction: column;
        gap:10px;
    }

    a{
       color:#333;
       margin-left: 0px;
       padding-left: 0;
    }

    button{
      font-size: large;
      color:#f2f2f2;
      background-color: #0f52ba;
      border: none;
      outline: none;
      border-radius: 3px;
    }

    .options{
      display: flex;
      gap:10px;
      margin-bottom: 10px;
    }

    .qp,.notes{
        margin-left: 20px;
    }

    .notes,.notes-op{
        margin-bottom: 10px;
    }

    h2 {
    font-size: 2rem;
    color: #333;
    }

    h3 {
    font-size: 1.5rem;
    color: #555;
    }

    @media (max-width: 768px)  {

        .container{
            flex-direction: column;
        }
        .subject{
            width: 100%;
        }
    }
</style>