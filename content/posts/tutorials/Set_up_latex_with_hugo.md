---
title: "Setting up LaTeX to show on Hugo site."
date: 2025-10-20T20:09:35-04:00
tags:
- Hugo
- Latex
- Tutorial
description: "Shows how to set up LaTex to display on a Hugo static website."
math: true
---

I've been interested in LaTeX for years, and never really had a use case beyond
a few simple thing, such as writing a pamphlet/leaflet, or my resume. When I
found out that you could get LaTeX, specifically MathTeX/KaTeX to show in a hugo
website. I figured i'd give it a try and see how well it works. I'm going to use
Katex as i've read it can be implemented a little faster than standard MathJaX. 

# Setup

There are a few simple steps that need to take place for LaTeX to integrate
with you're Hugo Site.


1. Set up a KaTeX partial.
2. Reference it somewhere it can be seen everywhere.
3. Active the partial.

## Create the Partial.
---

1. Its best to set up a KaTex partial to access everywhere on your site. We will call
   this `katex.html`and we will store this where your other partials are store. In my example
   these are at `mywebsitename/layouts/partials/helpers/`.
2. You will need to import the required files. these can be found from the
   [KaTeX site](https://katex.org/docs/browser.html). You should add the
   following to the katex.html file you just made. Make sure this matches what
   ever information is available on the [KaTeX documentation](https://katex.org/docs/browser.htm)l

``` bash
 <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.25/dist/katex.min.css" integrity="sha384-WcoG4HRXMzYzfCgiyfrySxx90XSl2rxY5mnVY5TwtWE6KLrArNKn0T/mOgNL0Mmi" crossorigin="anonymous">

    <!-- The loading of KaTeX is deferred to speed up page rendering -->
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.25/dist/katex.min.js" integrity="sha384-J+9dG2KMoiR9hqcFao0IBLwxt6zpcyN68IgwzsCSkbreXUjmNVRhPFTssqdSGjwQ" crossorigin="anonymous"></script>

    <!-- To automatically render math in text elements, include the auto-render extension: -->
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.25/dist/contrib/auto-render.min.js" integrity="sha384-hCXGrW6PitJEwbkoStFjeJxv+fSOOQKOPbJxSfM6G5sWZjAyWhXiTIIAmQqnlLlh" crossorigin="anonymous"
        onload="renderMathInElement(document.body);"></script>

```

## Integrate this into your website.
---

It important to integrate this into something that is commonly accessed in all
of your site. the ```header``` or ```footer``` or ```head``` are perfect places.

1. Create a ```footer.html``` or ```header.html``` or ```head.html``` in the same partials folder
   at ```layouts/patrials```. Note if doing this in a ```footer.html``` this
   will overide the ```footer.html``` provided by the theme you are using.
2. Add the following to your prefered partial. I will be adding this to my
   ```head.html```:

```css
{{ if .Params.katex}}{{ "helpers/partial/katex.html" . }}{{ end }}
```

3. Now that this is referenced you should be able to reference the use of KaTeX
   for each of mark down files seperatly. This makes it so you don't have to
   use KaTeX JS and CSS file for posts that it's not needed in.

## Using the Katex Partial

Now we can start using the KaTeX partial in pages that need it. All we need to
do is add the following to the front matter of any markdown file on our site.

partial
```bash

---
math : true 
---

```

Now this should allow the KaTeX partial to be used on any page with that in the
front matter. 

The following

$$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$

Is an integral

If you wanted to have inline equations you should add the following to your
partial: 

```bash
<script>
    document.addEventListener("DOMContentLoaded", function() {
        renderMathInElement(document.body, {
            delimiters: [
                {left: "$$", right: "$$", display: true},
                {left: "$", right: "$", display: false}
            ]
        });
    });
</script>

```

This will provide inline equations with single dollar signs. $\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$

Now you can add in large extravagent math equations to your hearts fancy:

$$F(x)= A_0 + \sum_{n=1}^N\left[ A_n\cos{\left(\frac{2\pi nx}{P}\right)}+B_n\sin{\left(\frac{2\pi nx}{P}\right)}\right]$$

