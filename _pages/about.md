---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

PhD candidate, Computer Science & Engineering


### Contact

<style>
* {
  box-sizing: border-box;
}

/* Create two equal columns that floats next to each other */
.column {
  float: left;
  width: 50%;
  padding: 10px;
  height: 300px; /* Should be removed. Only for demonstration */
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}
  
/* button */
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800;900&display=swap');

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

.container{
    width: 100%;
    height: 50vh;
    background: #e3ebfe;
    display: flex;
    justify-content: center;
    align-items: center;
}

button{
    width: 120px;
    height: 40px;
    border: none;
    outline: none;
    background: #2f2f2f;
    color: #fff;
    font-size: 14px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 3px 10px -5px rgba(0,0,0,0.4);
    position: relative;
    overflow: hidden;
    cursor: pointer;
    margin: 2px 1px;
}

.check-box{
    width: 40px;
    height: 40px;
    border-radius: 20px;
    box-shadow: 0 0 6px -2px rgba(0,0,0,0.5);
    position: absolute;
    top: 0;
    right: -20px;
    opacity: 0;
}

.check-box svg{
    width: 20px;
    margin: 10px;
}

svg path{
    stroke-width: 3;
    stroke: #fff;
    stroke-dasharray: 34;
    stroke-dashoffset: 34;
    stroke-linecap: round;
}

.active{
    background: #24D040;
    transition: 1s;
}

.active .check-box{
    right: 0;
    opacity: 1;
    transition: 1s;
}

.active p{
    margin-right: 125px;
    transition: 1s;
}

.active svg path{
    stroke-dashoffset: 0;
    transition: 1s;
    transition-delay: 1s;
}
</style>

<div class="row">
  <div class="column">
    <!-- modify this form HTML and place wherever you want your form -->
    <form id="my-form" action="https://formspree.io/f/xnqwyrwj" method="POST">
      <label>Your email:</label>
      <input type="email" name="email" />
      <label>Your message:</label>
      <input type="text" name="message" rows="3" maxlength="3000" style="height:150px;"/>
      <button id="my-form-button">
            <p id="btnText">Send message</p>
            <div class="check-box">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="10 10 50 50">
                    <path fill="transparent" d="M14.1 27.2l7.1 7.2 16.7-16.8" />
                </svg>
            </div>
      </button>
      <!-- <button id="my-form-button">Submit</button> -->
      <p id="my-form-status"></p>
    </form>
  </div>
  <div class="column">
    <div class="google-maps">
      <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d12091.578127255476!2d-74.1793225!3d40.7423462!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xb97c287a2ef95f43!2sNew%20Jersey%20Institute%20of%20Technology!5e0!3m2!1sen!2sus!4v1637423286669!5m2!1sen!2sus" width="100%" height="300" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0">
      </iframe>    
    </div>
  </div>
</div>




<!-- Place this script at the end of the body tag -->
<script>
    var form = document.getElementById("my-form");
    const btn = document.querySelector("#my-form-button");
    const btnText = document.querySelector("#btnText");
  
    btn.onclick = () => {
      btnText.innerHTML = "Thanks";
      btn.classList.add("active");
    };
    
    async function handleSubmit(event) {
      event.preventDefault();
      var status = document.getElementById("my-form-status");
      var data = new FormData(event.target);
      fetch(event.target.action, {
        method: form.method,
        body: data,
        headers: {
            'Accept': 'application/json'
        }
      }).then(response => {
        if (response.ok) {
          status.innerHTML = "Will get back to you soon.";
          form.reset()
        } else {
          response.json().then(data => {
            if (Object.hasOwn(data, 'errors')) {
              status.innerHTML = data["errors"].map(error => error["message"]).join(", ")
            } else {
              status.innerHTML = "Oops! There was a problem submitting your form"
            }
          })
        }
      }).catch(error => {
        status.innerHTML = "Oops! There was a problem submitting your form"
      });
    }
    form.addEventListener("submit", handleSubmit)
</script>


