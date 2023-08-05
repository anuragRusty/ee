<script>
    import India from "../assets/india.svg";
    const currentYear = new Date().getFullYear();
    
  </script>
  
<div class="container">
    <footer>
         <div class="box contacts">
            <ul>
                <h2>Contacts</h2>
                <li><b>Dr. Dummy Person</b></li>
                <li>Head, Department of Electrical Engineering</li>
                <li> Phone: +91010101010</li>
                <li>Email: hod@ee.email.com</li>
            </ul>
        </div>
         <div class="box quic-links">
           <ul>
            <h2>Quick Link</h2>
            <li>ERP</li>
            <li>Central Library</li>
            <li>Timetable</li>
            <li>Information</li>
            <li>Electrical Engg. Society</li>
            <li>Check Email</li>
           </ul>
        </div>
        <div class="box about">
         <h2>The Institute</h2>
         <p>
            Chaibasa Engineering College is a technical undergraduate college focused on the tertiary study of engineering and natural sciences, located near Chaibasa town in the West Singhbhum district in the Kolhan division of India.
         </p>
        </div>
        <img class="india" alt="india" src={India}>
    </footer>
    <p class="footer-text">© {currentYear} Department of Electrical Engineering, CEC Chaibasa</p>
</div>
  
<style>

    
    h2{
        padding-left:10px;
    }

    p{
        padding-left: 10px;
    }

    .india{
        width: 300px;
        height: 300px;
    }

.container {
    background-color: 	#0F52BA;
    color:#f2f2f2;
    display: flex;
	flex-direction: column;
    width: 100%;
    margin-top: auto;
    justify-content: flex-start;
}

.box{
    width: 300px;
}

footer{
  display: flex;
  padding: 20px 0;
  gap: 30px;
  justify-content: flex-start;
}

footer > div {
    border-right:1px solid white;
    border-radius: 0px;
}


ul {
    margin: 0;
    padding: 0;
    list-style: none;
    gap: 10px;
  }

  ul li{
    padding: 10px;
  }

.footer-text{
    text-align: center;
    font-size: medium;
}

@media (max-width: 768px){
    footer{
        display: block;
    }

    footer > div {
    border:none;
}

.box{
    width: auto;
}
}
</style>