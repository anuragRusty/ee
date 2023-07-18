<script>
import { slide,fade } from 'svelte/transition';
import Logo from "../assets/logocec.svg";

let isDesktop = window.screen.width>600;
let isMobile = false;

const navItems = ["HOME","RESEARCH","PROGRAMME","FORMER FACULITY","CEC"];
const menuItems = ["HISTORY","HEAD","PEOPLE","AWARDS AND RECOGNITION","STAFF","ACADEMIC PROGRAM","PUBLICATION","CONTACT","ABOUT"]
let currItem = navItems[0];

function handleNavClick(item){
     currItem = item;     
}

function handleMenuClick(item){
  currItem = item;
  isMobile = false;
}

</script>

<div class="container">
  <header>
   <div class="logo">
    <img alt="logo" src={Logo}>
    <div class="logo-text">
      <div class="coll-name">Chaibasa Engineering College</div>
      <div class="dep-name">Electrical Department</div>
  </div>
</div>
<nav>
  <ul>
    {#each navItems as item,i}
    <li on:click={() => handleNavClick(item)}>{item}{#if i < navItems.length-1} {" | "} {/if}
    </li>
    {/each}
  </ul>
</nav>
  </header>
  <div class="menu-bar">
   {#if !isDesktop} <div transition:fade class="menu-title" on:click={() => isMobile = !isMobile}><div>MENU</div>&#9776;</div> {/if}
   {#if isDesktop || isMobile}
    <ul transition:slide>
      {#each menuItems as item }
        <li on:click={() => handleMenuClick(item)}>{item}</li>
      {/each}
    </ul>
    {/if}
  </div>
  {#if currItem !== "HOME"}
  <div class="curr-item-bar" transition:slide>{currItem}</div>
  {/if}
</div>

<style>
  .container{
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    margin-bottom: 10px;
  }

  .logo{
    display: flex;
    padding: 0;
  }

  .coll-name {
    font-size: 35px;
  }

  .dep-name{
    font-size: larger;
  }

  .curr-item-bar{
    margin-top:-10px;
    background-color: 	#0F52BA;
    width: 100%;
    /* height: 50px; */
    font-size: 35px;
    font-weight: 100;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #f2f2f2;
  }

  header{
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center; 
  }

  nav{
    padding-top: 15px;
    font-size: 20px;
  }

  nav ul li{
   text-decoration: none;
   color:black;
  }

  nav ul li:hover{
    color:#007bff;
  }

  .menu-title{
    display: flex;
    cursor: pointer;
    justify-content: space-between;
    padding: 10px;
    border-bottom: 1px solid white;
  }

   ul {
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    gap: 10px;
  }

  .menu-bar{
  width:100%;
  background-color: 	#0F52BA;
  color: white;
  }

  .menu-bar ul li{
      padding: 10px;
  }

  .menu-bar ul li:hover {
    background-color: #0b2f58; 
  }

  
.menu-bar ul {
  justify-content: space-between;
}

  @media only screen and (max-width: 600px){
    header{
      flex-direction: column;
    }
    ul{
      flex-wrap: wrap;
    }

    nav ul li{
      font-size: smaller;
    }

    .coll-name {
    padding-top: 20px;
    font-size: medium;
  }

  .dep-name{
    padding: auto;
    font-size: small;
  }
  
    .menu-bar{
    padding: 0;
    }

    .menu-bar ul{
      display: block;
    }
   
   .menu-bar ul li{
      border-bottom: 1px solid white;
    }
    nav{
    padding-top: 10px;
    font-size: smaller;
  }
  }

</style>


  
  
  
  
  
  
  