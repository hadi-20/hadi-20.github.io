---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Computer Science & Engineering

My research interests are Machine Learning and Software Development. I have been researching video analytics systems for embedded devices, image processing using deep learning, and graphic applications for mobile devices.

<br />
<br />


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
.pushable {
    position: relative;
    border: none;
    background: transparent;
    padding: 0;
    cursor: pointer;
    outline-offset: 4px;
    transition: filter 250ms;
  }
  .shadow {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 12px;
    background: hsl(0deg 0% 0% / 0.25);
    will-change: transform;
    transform: translateY(2px);
    transition:
      transform
      600ms
      cubic-bezier(.3, .7, .4, 1);
  }
  .edge {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 12px;
    background: linear-gradient(
      to left,
      hsl(105deg 60% 16%) 0%,
      hsl(105deg 60% 32%) 8%,
      hsl(105deg 60% 32%) 92%,
      hsl(105deg 60% 16%) 100%
    );
  }
  .front {
    display: block;
    position: relative;
    padding: 6px 21px;
    border-radius: 12px;
    font-size: 0.9rem;
    color: white;
    background: hsl(105deg 60% 40%);
    will-change: transform;
    transform: translateY(-4px);
    transition:
      transform
      600ms
      cubic-bezier(.3, .7, .4, 1);
  }
  .pushable:hover {
    filter: brightness(110%);
  }
  .pushable:hover .front {
    transform: translateY(-6px);
    transition:
      transform
      250ms
      cubic-bezier(.3, .7, .4, 1.5);
  }
  .pushable:active .front {
    transform: translateY(-2px);
    transition: transform 34ms;
  }
  .pushable:hover .shadow {
    transform: translateY(4px);
    transition:
      transform
      250ms
      cubic-bezier(.3, .7, .4, 1.5);
  }
  .pushable:active .shadow {
    transform: translateY(1px);
    transition: transform 34ms;
  }
  .pushable:focus:not(:focus-visible) {
    outline: none;
  }
</style>




<div class="row">
  <div class="column">
    <!-- modify this form HTML and place wherever you want your form -->
    <form id="my-form" action="https://formspree.io/f/xnqwyrwj" method="POST">
      <label>Your email address:</label>
      <input type="email" name="email" />
      <label>Your message:</label>
      <textarea name="message" rows="4" cols="10" wrap="soft"></textarea>
      
      <button id="my-form-button" class="pushable">
        <span class="shadow"></span>
        <span class="edge"></span>
        <span class="front">
          send message
        </span>
      </button>
      
      
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
          status.innerHTML = "Thanks, will get back to you soon.";
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


