<script>
    import {slide} from "svelte/transition";
    const events = [
      {
        title: "Event Title 1",
        date: "September 10, 2023",
        description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ac tristique urna. Quisque fermentum vitae risus a pharetra.",
        imageSrc: "event1.jpg",
      },
      {
        title: "Event Title 2",
        date: "October 15, 2023",
        description: "Aenean malesuada metus at tortor auctor, vel fermentum lectus viverra. Sed iaculis, velit id efficitur aliquet, sapien nunc congue elit.",
        imageSrc: "event2.jpg",
      },
      {
        title: "Event Title 3",
        date: "December 17, 2023",
        description: "Dolor sit amet, consectetur adipiscing elit. Nulla ac vel fermentum lectus viverra. Sed iaculis, velit id efficitur aliquet, sapien nunc congue elit.",
        imageSrc: "event2.jpg",
      },
    ];
  </script>

<div class="container" in:slide>
    {#each events as event}
      <section class="event">
        <img src={event.imageSrc} alt={event.title}>
        <h2>{event.title}</h2>
        <p class="date">Date: {event.date}</p>
        <p class="description">{event.description}</p>
        <a href="#" class="btn">LEARN MORE</a>
      </section>
    {/each}
</div> 

  <style> 
    .container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
      padding-bottom: 10px;
    }
  
    .event {
      display: flex;
      width: calc(33% - 20px);
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #f2f2f2;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
      border-radius: 5px;
      padding: 20px;
      margin: 10px;
      text-align: center;
    }
  
    .event img {
      max-width: 100%;
      border-radius: 5px;
      margin-bottom: 10px;
    }
  
    h2 {
      font-size: 24px;
      margin-bottom: 10px;
    }
  
    .date {
      font-style: italic;
      color: #666;
      margin-bottom: 10px;
    }
  
    .description {
      margin-bottom: 20px;
    }
  
    .btn {
      background-color: #0f52ba;
      color: #f2f2f2;
      border: none;
      font-size: 1.5em;
      border-radius: 5px;
      text-decoration: none;
      display: inline-block;
      transition: background-color 0.3s ease;
    }
  
    .btn:hover {
      background-color: #0b2f58;
    }
  
    @media (max-width: 768px) {
      .event {
        flex-basis: 100%;
      }
    }
  </style>
  

  