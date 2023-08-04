<script>
    import Email from "../assets/email.svg";
    import Linkedin from "../assets/linkedin.svg";
    import Phone from "../assets/phone.svg";
    import {slide} from "svelte/transition";

    const HEAD = {
       name:"Dr. Dummy Person",
       email:"hod@email.com",
       linkedin:"https://www.linkedin.com/?original_referer=",
       phone:"818181818",
    }

    const WEB_TEAM = [
       {
       name:"Dummy Guy",
       email:"dummy@email.com",
       linkedin:"https://www.linkedin.com/?original_referer=",
       phone:"818181818",
      },

      {
       name:"Dummy Guy",
       email:"dummy@email.com",
       linkedin:"https://www.linkedin.com/?original_referer=",
       phone:"818181818",
      }
    ];
</script>

<div class="container" in:slide>
  <div class="head">
    <div class="hod">
        <div class="profile-pic-hod"></div>
        <div class="name-head">{HEAD.name}</div>
        <i style="margin:5px;">Head of Department</i>
        <div class="contact contact-head">
            <a href="mailto:{HEAD.email}"><img alt="icon" class="icon" src={Email}></a>
            <a href="tel:{HEAD.phone}"><img alt="icon" class="icon" src={Phone}></a>
            <a href={HEAD.linkedin} target="_blank"><img alt="icon" class="icon" src={Linkedin}></a>
        </div>
    </div>
  </div>
  <div class="web-team-leads">
    <div class="banner">WEB TEAM LEADS</div>
    {#each WEB_TEAM as member}
     <div class="member">
        <div class="profile-pic-member"></div>
        <div class="name">{member.name}</div>
        <i style="margin:2px;">Student</i>
        <div class="contact">
            <a href="mailto:{member.email}"><img alt="email" class="icon icon2" src={Email}></a>
            <a href="tel:{member.phone}"><img alt="phone" class="icon icon2" src={Phone}></a>
            <a href={member.linkedin} target="_blank"><img alt="linkedin" class="icon icon2" src={Linkedin}></a>
        </div>
     </div>     
     {/each}
  </div>
</div>

<style>

    .container{
        display: flex;
        padding-bottom: 10px;
        gap:10px;
        color:#f2f2f2;
    }

    .head {
        width: 50%;
        aspect-ratio: 1;
        display: flex;
        flex-direction: column;
        gap:10px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    .hod{
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
    }

    .web-team-leads{
        width: 50%;
        aspect-ratio: 1;
        display: flex;
        flex-direction: column;
        gap:10px;
    }

    .banner{
        width: 100%;
        height: auto;
        font-size: 35px;
        font-weight: 100;
        color:#f2f2f2;
        text-align: center;
        background-color: #0f52ba;
    }

    .member{
        width: 100%;
        height: 50%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
    }

    .profile-pic-hod{
        margin: 10px;
        width: 75%;
        aspect-ratio: 1;
        border-radius: 50%;
        border:solid 2px #333;
    }

    .profile-pic-member{
        margin: 10px;
        width: 30%;
        height: 60%;
        border-radius: 50%;
        border:solid 2px #333;
    }

    .name{
        font-size: 30px;
        color:#333;
    }

    .contact{
        display: flex;
        gap:5px;
    }

    .name-head{
        font-size: 40px;
        color:#333;
    }

    .icon{
        width: 50px;
        height: 50px;
        border-radius: 50%;
    }

    .icon2{
        width: 30px;
        height: 30px;
    }

    i{
        color: #555;
    }

    @media (max-width: 768px) {
        .container{
            flex-direction: column;
        }

        .web-team-leads, .head{
            width: 100%;
            height: auto;
        }
        .member , .head{
            width: 100%;
            aspect-ratio: 1;
        }

     .profile-pic-member, .profile-pic-hod{
        margin:10px;
        width: 65%;
        height: 65%;
        border-radius: 50%;
        background-color: #f2f2f2;
     }

     .name-head{
        font-size: 30px;
    }

     .icon2,.icon{
       width: 35px;
       height: 35px;
     }
    }
</style>