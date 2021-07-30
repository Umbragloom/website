+++
Date = "7/30/2021"
title = "Contact Me"
+++

<form method="POST">
  <label>Comments:
    <textarea name="comments"></textarea>
  </label>
</form>
After:

<form name="comments" method="POST" netlify-honeypot="hpfield" netlify>
  <div class="hpot">
    <label>Leave this field empty: <input name="hpfield"></label>
  </div>
  <label>Comments:
    <textarea name="comments"></textarea>
  </label>
</form>

// style.css
.hpot {
  display: none;
}
