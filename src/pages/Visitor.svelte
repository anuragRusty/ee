<script>
  import { slide,scale } from "svelte/transition";

</script>

<div class="container" in:slide>
<iframe transition:scale class="map" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3687.0619687672834!2d85.78902401495763!3d22.4643054852386!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3a1e25ddde342373%3A0x4ac680428662b09d!2sChaibasa%20Engineering%20College!5e0!3m2!1sen!2sin!4v1690776655923!5m2!1sen!2sin"  style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>

<div class="about">
<div class="heading">LOCATION</div>
<div transition:scale class="text"><p>Chaibasa Engineering College is located in the National Highway 75 connecting Chaibasa and Jaitgarh, 12 kilometres (7.5 mi) from the Chaibasa town in the West Singhbhum district in the Kolhan division. The campus covers an area of 14 hectares (35 acres). Students are awarded Bachelor of Engineering and Bachelor of Technology qualifications upon satisfactory completion of their studies.</p></div>
</div>
</div>

<style>
    .container{
       width:100%;
       display:flex;
       gap:10px;
       padding-bottom: 10px;
    }

   
    .map{
        width: 40%;
        aspect-ratio: 1;
        border-radius: 5px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    }

    .text{
      font-size: 20px;
      font-style: italic;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
      background-color: #f2f2f2;
    }

    p{
        margin: 10px;
    }


    .about{
        width:60%;
        height: auto;
        display: flex;
        gap:10px;
        flex-direction: column;
        align-items: center;
        color:#555;
        background-color: #f2f2f2;
    }

    .heading{
        width: 100%;
        text-align: center;
        color: #f2f2f2;
        font-size: 35px;
        font-weight: 100;
        background-color: #0f52ba;
    }

    @media (max-width: 768px)  {
        .container{
            flex-direction: column;
        }

        .map,.about{
            width: 100%;
            font-size: large;
        }
    }
</style>