<script>
  import Research from "../assets/research.svg";
  import Head from "../assets/head.svg";
  import Acad from "../assets/acad.svg";
  import Award from "../assets/award.svg"
  import Carousel from "svelte-carousel/src/components/Carousel/Carousel.svelte";

</script>

<div class="container">

  <div class="upper">

   <div class="image-slider">
    <Carousel autoplay autoplayDuration={2000}>
    <div id="slide-1" class="slide" style="background-size:100% 100%; background-image: url(https://images.unsplash.com/photo-1466853817435-05b43fe45b39?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2198&q=80);"></div>
		<div id="slide-2" class="slide" style="background-size:100% 100%; background-image: url(https://images.unsplash.com/photo-1506744038136-46273834b3fb?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2370&q=80);"></div>
		<div id="slide-3" class="slide" style="background-size:100% 100%; background-image: url(https://images.unsplash.com/photo-1434725039720-aaad6dd32dfe?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2842&q=80);"></div>
    </Carousel>
   </div>

    <div class="left">
      <div class="image" style="background-color:#0F52BA;">
        <img alt="research" src={Research} style="width:90%; height:90%; padding:20px;">
      </div>
      <div class="image" style="background-color:#0F52BA;">
        <img alt="research" src={Award} style="width:90%; height:90%; padding:10px;">
      </div>
      <div class="image" style="background-color:#0F52BA">
        <img alt="research" src={Acad} style="width:90%; height:90%; padding-top:20px;">
      </div>
      <div class="image" style="background-color:#0F52BA;">
        <img alt="research" src={Head} style="width:90%; height:90%; padding-top:20px;">
      </div>

    </div>

  </div>
  <div class="lower">

    <div class="box box2" style="background-color:#EF6262; ">
      <h2>ABOUT THE DEPARTMENT</h2>
      <p style="text-align:center; font-size:larger">
        Welcome to the Department of Electrical Engineering. <br>
       Visit these pages to discover more about the department, <br>
       our study programme and research activities, and find out whom to contact at EE.
      </p>
    </div>
    <div class="box" style="background-color:#F3AA60;">
      <h2>NEWS</h2>
    </div>
    <div class="box" style="background-color:#7A9D54;">
      <h2>EVENTS</h2>
    </div>
    <div class="box" style="background-color:#9681EB;">
     <h2>VISION</h2>
     <p style="text-align:center; font-style:italic; font-size:22px;" >
      “Academic Excellence in <br> 
       Power, Control, <br>
       Instrumentation and <br>
       Signal Processing.”</p>
    </div>
  </div>
</div>

<style>

  h2{
    padding-bottom: 10px;
    display: flex;
    justify-content: center;
    border-bottom: #f2f2f2 solid 2px;
  }

  .image{
    display: flex;
    justify-content: center;
  }
    .container {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 10px;
  color:#f2f2f2;
    }

  .upper {
    display: flex;
    gap: 10px;
  }

  .image-slider {
    width: 50%;
  }

  .left{
    flex: 1;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  .left .image {
    height: 250px;
    background-color: #94B49F;
  }

  .lower {
    display: flex;
    gap: 10px;

  }

  .lower .box {
    min-height: 200px;
    flex-grow: 1;
    background-color: #AAC4FF;
  }

  .box2{
    width: 400px;
  }

  

  

  @media only screen and (max-width: 600px){


  .box2{
    width: auto;
  }

    .upper {
      flex-direction: column;
    }

  .image-slider {
    height: 350px;
    width: 100%;
  }

    .left{
    display: grid;
    grid-template-columns: 1fr;
    gap: 10px;
  }

 .lower {
    flex-direction: column;
  }
}
</style>