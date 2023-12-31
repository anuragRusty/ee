<script>
    import {slide,scale} from "svelte/transition";
    import SearchBox from "../components/SearchBox.svelte";
   
    const newsArticle = [
  {
    title: "Scientists Discover New Species of Marine Life in the Depths of the Pacific Ocean",
    date: "31/12/23",
    show: false,
    info: "A team of marine biologists from the Ocean Exploration Institute has announced the discovery of a new species of deep-sea creatures in the Pacific Ocean. The fascinating creatures were found in the Mariana Trench at a depth of over 7,000 meters. The discovery sheds new light on the biodiversity of the ocean's most mysterious regions.",
  },
  {
    title: "Electric Car Manufacturer Breaks Record with 1000km Range on a Single Charge",
    date: "15/11/23",
    show: false,
    info: "In a groundbreaking achievement, an electric vehicle manufacturer has set a new world record by developing a car that can travel over 1000 kilometers on a single charge. The technological advancement marks a significant milestone in the electric vehicle industry and paves the way for longer-range and more practical electric cars.",
  },
  {
    title: "Global Summit Addresses Climate Change Crisis, Calls for Urgent Action",
    date: "07/10/23",
    show: false,
    info: "World leaders from over 150 countries gathered in a global summit to address the escalating climate change crisis. The summit aimed to find collaborative solutions to combat climate change and its devastating impacts on the environment and vulnerable communities worldwide. The participants emphasized the need for immediate and decisive actions to mitigate the effects of climate change.",
  },
  {
    title: "New Study Shows Link Between Screen Time and Mental Health in Adolescents",
    date: "22/09/23",
    show: false,
    info: "A comprehensive study conducted by researchers at a prominent university has revealed a concerning link between excessive screen time and declining mental health in adolescents. The study highlights the importance of monitoring screen usage in young individuals and raises awareness about the potential impacts of digital devices on mental well-being.",
  },
  {
    title: "Tech Giant Unveils Revolutionary Augmented Reality Glasses",
    date: "05/08/23",
    show: false,
    info: "A leading tech company has unveiled its latest innovation - a pair of cutting-edge augmented reality glasses that promise to transform the way people interact with technology. The glasses offer a seamless blend of the virtual and real worlds, opening up new possibilities in education, entertainment, and business applications.",
  },
  {
    title: "Artificial Intelligence Predicts Outbreak of Infectious Disease, Enables Timely Response",
    date: "18/07/23",
    show: false,
    info: "Researchers in the field of artificial intelligence have developed a sophisticated system capable of predicting the outbreak of infectious diseases with remarkable accuracy. The AI-based model uses vast datasets and machine learning algorithms to forecast potential epidemics, empowering health authorities to take proactive measures and prevent widespread transmission.",
  },
];

let searchText = "";
</script>
<SearchBox bind:searchText/>
<div class="container" in:slide>
  {#each newsArticle as article}
  {#if article.title.toLocaleLowerCase().includes(searchText.toLocaleLowerCase().trim())}
    <div class="news-container" transition:scale>
      <div class="news-header" on:click={() => article.show = !article.show}>
        <div class="title">{article.title}</div>
        <div class="date">{article.date}</div>
      </div>
      {#if article.show}
        <div class="info" transition:slide>{article.info}</div>
      {/if}
    </div>
    {/if}
  {/each}
</div>

<style>
  .container {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding-bottom: 10px;
    color: black;
  }

  .news-container {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 10px;
    background-color: #f2f2f2;
    border-radius: 3px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  }

  
  .news-header {
    display: flex;
    width: 100%;
    padding: 10px;
    align-items: center;
    gap: 20px;
  }

  .title {
    color: #333;
    font-size: 30px;
  }

  .date {
    font-size: 20px;
    color: #888;

  }

  .info {
    font-size: 1.2em;
    padding: 10px;
    color: #555;
  }

  @media (max-width: 768px) {
    .news-header{
      flex-direction: column;
      gap:10px;
    }
    .date{
      width:100%;
      text-align: left;
    }
  }
  
</style>