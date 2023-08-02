<script>
    import {slide} from "svelte/transition";
   
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

</script>
<div class="container" in:slide>
    {#each newsArticle as article}
     <div class="news-container">
        <div class="news-header" on:click={() => article.show = !article.show}>
             <div class="title">{article.title}</div>
             <div class="date">{article.date}</div>
       </div>
       {#if article.show}
        <div class="info" transition:slide>{article.info}</div>
       {/if}
     </div>
     {/each}
</div>

<style>
    .container{
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
        padding-bottom: 10px;
        color:#f2f2f2;
    }

    .news-container{
        width: 100%;
        display: flex;
        flex-direction: column;
        background-color: #0f52ba;
        gap: 10px;
    }

    .news-header:hover{
        background-color: #0b2f58;
    }

    .news-header{
        display: flex;
        width: 100%;
        justify-content: space-between;
        font-size: 1.6em;
        margin-right: 10px;
    }

    .info{
      border-top: solid 2px #f2f2f2;
      font-size: 1.2em;
    }
    
</style>