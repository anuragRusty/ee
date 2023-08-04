<script>
  import { slide } from "svelte/transition";

  const HEAD = {
    name: "Dr. Dummy Person",
    title: "HEAD OF DEPARTMENT",
  };
</script>

<div class="container" in:slide>
  <div class="head">
    <div class="head-pic"></div>
    <div class="name-title">
      <div class="name">{HEAD.name}</div>
      <div class="title">{HEAD.title}</div>
    </div>
  </div>
  <div class="reach-me">REACH ME</div>
  <div class="contact">
    <div class="sub-contact">
      <div class="contact-details">
        <div>Phone (Head's Cabin): +91-3187238282262</div>
        <div>Phone (EED Office): +91-3217238261</div>
        <div>FAX: +998123890138</div>
        <div>Email: hod@ee.email.com</div>
      </div>
      <div class="about">
        Department of Electrical Engineering,
        Chaibasa Engineering College, Kelendi, Jhinkpani, Chaibasa, Kelende,833215 JHARKHAND, INDIA.
      </div>
    </div>
  </div>
</div>

<style>
  .container {
    width: 100%;
    aspect-ratio: 4/1;
    display: flex;
    gap: 10px;
    flex-direction: column;
    padding-bottom: 10px;
  }

  .head {
    width: 100%;
    height: 80%;
    display: flex;
    gap: 10px;
    justify-content: space-between;
    align-items: center;
  }

  .head-pic {
    width: 50%;
    height: 100%;
    background-color: #f2f2f2;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    background-color: #fff;
  }

  .name-title {
    width: 50%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
  }

  .name {
    font-size: 70px;
    color:#333;
  }

  .title {
    font-size: 20px;
    font-style: italic;
    color: #555;
  }

  .reach-me {
    width: 100%;
    font-size: 35px;
    font-weight: 100;
    text-align: center;
    color:#f2f2f2;
    background-color: #0f52ba;
  }

  .contact {
    width: 100%;
    height: 40%;
    font-size: medium;
    display: flex;
    flex-direction: row;
    gap: 10px;
    background-color: #fff;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
  }

  .sub-contact {
    width: 50%;
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }

  .contact-details,
  .about {
    width: 100%;
    height: 50%;
    padding: 10px;
  }

  .about {
    border-left: 2px solid #555;
    padding: 20px;
    border-radius: 0px;
  }

  @media (max-width: 768px) {
    .container {
      aspect-ratio: unset;
    }

    .head {
      height: auto;
      flex-direction: column;
    }

    .head-pic {
      width: 100%;
      aspect-ratio: 2/1; 
    }

    .name-title {
      width: 100%;
      text-align: center;
      padding: 10px 0;
    }

    .name {
      font-size: 40px;
    }

    .title {
      font-size: 16px;
    }

    .reach-me {
      font-size: 25px;
      padding: 10px 0;
    }

    .contact {
      height: auto;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-size: small;
    }

    .sub-contact {
      width: 100%;
      align-items: center;
      padding: 10px;
      flex-direction: row;
    }

    .about {
      border-left: 2px solid #f2f2f2;
      padding: 10px;
    }
  }
</style>
