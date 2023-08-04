<script>
    import {slide} from "svelte/transition";
   
    const ABOUT = [
        {
         title:"ABOUT US",
         info:"Welcome to the EE Department website! We are a dynamic and forward-thinking department committed to excellence in education, research, and community engagement. Our department is dedicated to nurturing young minds, fostering a passion for learning, and empowering students to reach their full potential.",
        },
        {
         title:"MISSION",
         info:"Our mission is to provide a comprehensive and cutting-edge education that equips students with the knowledge, skills, and values necessary to thrive in an ever-changing world. We strive to create an inclusive and supportive learning environment that promotes critical thinking, creativity, and a spirit of inquiry.",
        },
        {
         title:"VISION",
         info:"Our vision is to be a leading center of academic excellence, recognized for producing outstanding graduates who make significant contributions to their respective fields and society at large. We aspire to be at the forefront of research and innovation, addressing real-world challenges and shaping the future through knowledge and collaboration.",
        },
        {
         title:"OUR TEAM",
         info:"At EE, we are proud to have a team of dedicated and accomplished educators who are passionate about their subjects and committed to student success. Led by our esteemed Head of Department, Mr. Subhadip Pan, our faculty members bring a wealth of expertise and experience to the classroom, ensuring a stimulating and transformative learning experience for our students.",
        },
        {
         title:"FACILITIES AND RESOURCES",
         info:"To facilitate holistic learning, we provide state-of-the-art facilities and resources for our students. From cutting-edge laboratories to well-stocked libraries, we offer an enriching environment that supports both academic and personal growth. Our commitment to leveraging technology ensures that students have access to modern tools and platforms to enhance their learning experience.",
        },
        {
         title:"JOIN US!",
         info:"We welcome students, faculty, researchers, and all stakeholders who share our passion for knowledge and growth. If you're interested in being part of our vibrant academic community or contributing to our vision in any capacity, feel free to reach out to us."
        }
    ];
</script>

<div class="container" in:slide>
 <div class="welcome">WELCOME TO EE DEPARTMENT!</div>
 <div class="info-container">
   {#each ABOUT as item}
   <div class="sub-info-container">
       <h2>{item.title}</h2>
       <div class="info">{item.info}</div>
   </div>
   {/each}
 </div>
</div>

<style>
    h2{
        color:#f2f2f2;
        text-align: center;
        color:#333;
        width: 100%;
    }
    .container{
        display: flex;
        flex-direction: column;
        gap: 10px;
        padding-bottom:10px;
    }

    .info-container{
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
        justify-content: space-between;
    }

    .sub-info-container{
        width: calc(33.3% - 10px);
        color: #555;
        font-size: larger;
        display: flex;
        flex-direction: column;
        align-items: center;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    }
    .welcome{
        width:100%;
        font-size: 45px;
        font-weight: 100;
        color:#f2f2f2;
        text-align: center;
        background-color: #0f52ba;
         box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    }

    .info{
        text-align: center;
        font-style: italic;
        margin-bottom: 10px;
    }

    @media (max-width: 768px){
       
        .welcome{
        width:100%;
        font-size: 35px;
        font-weight: 100;
        }

        .info-container{
            flex-wrap: nowrap;
            flex-direction: column;
            width: 100%;
            height: auto;
        }

        .sub-info-container{
            width: 100%;
            height: auto;
        }
    }
</style>