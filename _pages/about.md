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
</style>

<div class="row">
  <div class="column" style="background-color:#FFF;">
    <!-- modify this form HTML and place wherever you want your form -->
    <form id="my-form" action="https://formspree.io/f/xnqwyrwj" method="POST">
      <label>Email:</label>
      <input type="email" name="email" />
      <label>Message:</label>
      <input type="text" name="message"/>
      <button id="my-form-button">Submit</button>
      <p id="my-form-status"></p>
    </form>
  </div>
  <div class="column" style="background-color:#FFF;">
    <div class="google-maps">
      <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d12091.578127255476!2d-74.1793225!3d40.7423462!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xb97c287a2ef95f43!2sNew%20Jersey%20Institute%20of%20Technology!5e0!3m2!1sen!2sus!4v1637423286669!5m2!1sen!2sus" width="100%" height="300" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0">
      </iframe>    
    </div>
  </div>
</div>




<!-- Place this script at the end of the body tag -->
<script>
    var form = document.getElementById("my-form");
    
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
          status.innerHTML = "Thanks for your submission!";
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
