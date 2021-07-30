+++
Date = "7/30/2021"
title = "Contact Me"
+++

<form name="contact" method="POST" data-netlify-recaptcha="true" netlify-honeypot="bot-field" data-netlify="true">
  <p class="hidden">
    <label>Don’t fill this out if you’re human: <input name="bot-field" /></label>
  </p>
  <p>
    <label>Your Name: <input type="text" name="name" /></label>   
  </p>
  <p>
    <label>Your Email: <input type="email" name="email" /></label>
  </p>
  <p>
    <label>Message: <textarea name="message"></textarea></label>
  </p>
    </p>
  <div data-netlify-recaptcha="true"></div>
  <p>
  <p>
    <button type="submit">Send</button>
  </p>
</form>