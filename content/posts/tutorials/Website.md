---
title: Personal Website with Hugo and Netlify!
date: 2021-07-28T12:19:00-0400
draft: false
description: "Setting up Hugo, hosting to Github/Gitlab, deploying with Netlify and Netlify CMS."
tags:
 - Linux
 - Tutorial
 - WebDev
---

# Static websites are amazing!
----

Building your own website, and hosting it is easier than ever nowadays.
Especially with things such as WIX, WordPress and Squarespace. But I wanted
a bit more of a personal technological feel behind it to justify having one.

# Why do this?
----

There are a lot of reasons to host your own website. My reasons are below:

1. I wanted somewhere I could post what ever I wanted. 

2. I wanted to learn a little of both the frontend and backend development
   that went into WebDev and website management. 

3. It looks good to potential employers, as well being able to act as a simple
   portfolio for projects and things you are passionate about. 

# How to get started.
----

RESEARCH is your best friend. Look into YouTube videos, Read the documentation
from the [Hugo](https://gohugo.io/getting-started/quick-start) website and research other
peoples code bases if they have them available to you.

# So where do I even begin??
----

## First Steps!
The first thing to do once you've done your research is to install Hugo. For my
example I will be doing this on Linux. There are a plethora of resources on how
to handle this if your on Mac or Windows. **COUGH** ***RTFM***

From your terminal make sure whatever system you are using has git installed or
Homebrew if you go that route. For me as I'm using Arch Linux, I can just
install Hugo directly from the Arch Linux community repository by using the
following command in my terminal.

```bash
$ sudo pacman -Syu hugo
```
Then you should verify the install with the following:

```bash
$ hugo version
```

Your Command line should show the version number of Hugo if it was installed
correctly. If it does congrats you have the Hugo Framework installed.

Next steps are to create a new site! 

```bash
hugo new site "sitename"
```

The above command will create a new Hugo site in a folder called "Sitename", you can 
replace Sitename with your desired name. Within this folder will be the files, folders, and items needed to run your site.

The main file you currently need is the `config.toml` file. This is the base configuration of your site. For example mine is below:

```vim
baseurl = "/"
languageCode = "en-us"
theme = "terminal"
paginate = 5

[params]
  # dir name of your main content (default is `content/posts`).
  # the list of set content will show up on your index page (baseurl).
  contentTypeName = "posts"

  # ["orange", "blue", "red", "green", "pink"]
  themeColor = "red"

  # if you set this to 0, only submenu trigger will be visible
  showMenuItems = 5

  # show selector to switch language
  showLanguageSelector = false

  # set theme to full screen width
  fullWidthTheme = false

  # center theme with default width
  centerTheme = true

  # set a custom favicon (default is a `themeColor` square)
  # favicon = "favicon.ico"

  # set post to show the last updated
  # If you use git, you can set `enableGitInfo` to `true` and then post will automatically get the last updated
  showLastUpdated = true
  #enagleGitInfo = true
  
 # Provide a string as a prefix for the last update date. By default, it looks like this: 2020-xx-xx [Updated: 2020-xx-xx] :: Author
   updatedDatePrefix = "Updated"

  # set all headings to their default size (depending on browser settings)
  # it's set to `true` by default
  # oneHeadingSize = false


[languages]
  [languages.en]
    languageName = "English"
    title = "[Mathie@josh]#"
    subtitle = "A simple, retro theme for Hugo"
    owner = ""
    keywords = ""
    copyright = ""
    menuMore = "Show more"
    readMore = "Read more"
    readOtherPosts = "Read other posts"
    missingContentMessage = "Page not found..."
    missingBackButtonLabel = "Back to home page"

    [languages.en.params.logo]
      logoText = "[Mathie@josh]#"
      logoHomeLink = "/"
      
    [languages.en.menu]
      [[languages.en.menu.main]]
        identifier = "about"
        name = "About"
        url = "/about"
            
    [[languages.en.menu.main]]
        identifier = "projects"
        name = "Projects"
        url = "/posts/projects"
        
    [[languages.en.menu.main]]
        identifier = "blog"
        name = "Blog"
        url = "/posts/blog/"
          
    [[languages.en.menu.main]]
        identifier = "art"
        name = "Art"
        url = "/posts/art/"
        
    [[languages.en.menu.main]]
        identifier = "tutorials"
        name = "Tutorials"
        url = "/posts/tutorials/"   

```
This configures the base navigation section of your website. In my example, I have the sub folders Tutorials, 
Art, Blog, Projects, and the About Me pages. This takes you to the sub pages and content for each. This is 
also where you can have links to your social media, as well as where you can set certain parameters required
by your theme. 

Congrats you have the start of a website, if you havent set anyhting up yet in the `config.yml` its going to be 
pretty bland starting off. 

## Make it ***STAND OUT***

From here you should add a theme. There are HUNDREDS of themes
you can install. the best place to go is, you guessed it, the [Hugo
Themes](https://themes.gohugo.io) page. 

For my website I went with the Amazing [Terminal
Theme](themes.gohugo.io/themes/hugo-theme-terminal/) from panr on
[Github](https://github.com/panr/hugo-theme-terminal).

This is where Git comes in, you need to clone the theme into your websites
folder. For the Terminal Theme, panr recommends using a git submodule (as does the Hugo dev team), which
allows you to use the updates made to the repo, without causing any harm to the master branch of the repository 
once you start making changes to it. To do this type the following into your terminal:

```bash
$ cd sitename #to move into your hugo root folder.
$ git submodule add https://github.com/panr/hugo-theme-terminal.git
themes/terminal
```

This will install all files you need to utilize the theme on your
website, in a dedicated theme folder within your root folder of your website. 

From here just follow the documentation to set up the theme and your ready to
go and start making posts. 

# Post and post and post!!

Now its time to start making some glorious, glorious content! You can manually
create content files for example typing `content/<CATAGORY>/<FILE>/<FORMAT>`
and provide metadata in them, however I would recommend the `new` command to do
a few things for you (like add title and date):

```bash
$ hugo new posts/"your-posts-title"
```

This will create a new .md file for you to edit. Hugo utilizes markdown syntex
for your websites content. Below would be the example of what will be in your new post that you can open in any text editor:

```vim
---
title: "Your Posts Title"
date: 2019-03-26T08:47:11+01:00
draft: true
---
```

This will make whatever you put in "Your Posts Title" the title of your first post, then 
display the date of the post. The next line `draft: True` is important, this sets the post 
as a draft that will not be posted to your site, until it is ready. 

# Check it out!
---

So after you've set up your website, chosen a theme that you enjoy (or made your own), and posted your 
first piece of content you can start the hugo server and view the local copy of your website in any browser! 
Type the following into your command line:

```bash
$ hugo server -D
```
Your terminal will output something similar to the below:

```bash
$ ▶ hugo server -D

                   | EN
+------------------+----+
  Pages            | 10
  Paginator pages  |  0
  Non-page files   |  0
  Static files     |  3
  Processed images |  0
  Aliases          |  1
  Sitemaps         |  1
  Cleaned          |  0

Total in 11 ms
Watching for changes in /Users/bep/quickstart/{content,data,layouts,static,themes}
Watching for config changes in /Users/bep/quickstart/config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

This will load the hugo server for you,and all you need to do is navigate to http://localhost:1313/ 
and view your website!! The -D option loads any drafts that you have so you can view them before posting!

From here you can continue to configure your theme by updated the themes `config.taml` file. Here you 
can set a base url if you have a domain ready, replace the title for your webpage, as well as many other 
options!

---

But ***"Wait!"*** you say, ***"My website isn't online now is it?"*** The answer to that is yes, your correct 
its not online, and canont be accessed on the web. This is where Netlify and Github come in handy!

# Git Commit!

So you've made your site, configured it to your hearts content, and seen what it will look like from your browser, now your ready to 
get yourself setup online. For this we will transition our website's root folder into a Git folder! On your commandline `cd` ,or change directory, 
into the root folder of your website (Should be something like: `~username/home/mywebsite/` if you made it in your home folder)
then run the following commands:

```bash
$ git init
```

This will intialize the folder as a git repository waiting to be pushed to GitHub/GitLab. Go to your GitHub/GitLab create a new repo, and copy the supplied `git remote add` and `git push` commans from the `...or push an existing repository from the command line` section, then commit the changes to the staging area and commit them to GitHub/GitLab:

```bash
$ git add . #this adds all files in the root folder to the staging area.
$ git commit -m "Your commit message here" #This is the commit message that you should use to keep track of changes you have made to your git folder, this is useful if you are working in groups.
```

Then push the local Git repo to your repository on Github/Gitlab:

```bash
$ git remote add origin https://your-github's-repository-address.git
$ git push -u origin master
```

Congrats you have now begun the process of keeping all data on Github/Gitlab for version control!

# Netlify to the rescue!

Next steps are to deploy your website on ***Netlify***. Head over to [Netlify](https://netlify.com) and create an account. You can also use your Github login details if you feel like that would make it easier. Once your logged in you'll see an option `New site from Git:` click this and you will be asked to choose your git provider, Either Github or GitLab, Choose which ever site you used. From here you'll be asked to install Netlify on your personal GitHub/GitLab account, Choose the repository where your website is then you'll be asked to verify your build settings. For this set the build command as `hugo` and what directory you need to publish, for us this is the `public` directory where all our content is stored. After this is confirmed click the `Deply site` button at the bottom of the page.

Your website will not be correctly displayed if you proceed to the URL shown on the in the site overview since it does not match the `baseUrl` setting value in the `config.toml` file. Therefore, click on the `Deploy settings` in the site overview. Then select the `Site details` under the `General` tab. In the `Site details` tab, click on the `Change site name:` button, this will cause a pop up to show up, from here set it to whatever your `baseUrl` setting was.

# ***CONGRATUALTIONS***

You now have your own personal website with the Netlify hosting page, that is manually updated once you make new posts to your website on whatever device your Git folder is in! Now on to setting up Netlify CMS so you can edit, update and push content remotely!

---

#CMS's are great!

CMS's or Content Managment Systems, are fantastic backend utilities that allow for a larger group of people to work and maintain a website. This allows the users that are logged in and authorized on the CMS to make posts or content to the website, and await review from an admin before releaseing and pushing the content to the webpage. For a static website built on Hugo, NetlifyCMS is one of the best options. For a personal website this is certainly overkill, Unless you would like to be able to work on your website from anywhere

We should first understand the basic app file structure used by Netlify CMS. As we are using Hugo, Netlify will store all CMS files, at the root of your site in a static `admin` folder, in this case with Hugo it is stored in the `/static` folder. 

To get this set up simply do the following in your Root folder of your website:

```bash
$ cd /static
$ mkdir /admin && cd /admin # The && is a logical AND function.
$ touch index.html && touch config.yml
```

The first file `admin/index.html`, is the base entry point for the Netlify CMS admin interface. This allosws users set up in the CMS to navigate to `yoursite.com/admin/` to access the CMS and start publishing content. On the code side, this is a very basic HTML starter page that loads the Netlify CMS JavaScript file. In the `index.html` file you can place the following: 

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Content Manager</title>
</head>
<body>
  <!-- Include the script that builds the page and powers Netlify CMS -->
  <script src="https://unpkg.com/netlify-cms@^2.0.0/dist/netlify-cms.js"></script>
</body>
</html>
```
---

The second file `admin/config.yml` is the heart of the CMS instillation. Since im already utilizing Netlify for hostin and unthentication, the backend configuration is fairly straightforward. For GitHub and GitLab repositories, you should start your `config.yml` file with the following lines:

```yml
backend:
  name: git-gateway
  branch: master # Branch to update (optional; defaults to master)
```

This specifies your backend protocol and your publication branch. Git Gateway is an open source API that acts as a proxy between authenticated users of your site and your site repo. 

By default, saving a post in the CMS interface pushes a commit directly to the publication branch. However, you can enable the **Editorial Workflow**, which adds an very nice intuative interface for drafting, reviewing, and approving posts. To do this, add the following line to your Netlify CMS `config.yml`:

```yml
# This line should *not* be indented
publish_mode: editorial_workflow
```

Great now the admins set up on your account can review and approve posts that your writters are making! But they be able to post images sadly. We can easiy fix this.  If you already have an images folder in your project, you could use its path, possibly creating an uploads sub-folder, for example:

```yml
# These lines should *not* be indented
media_folder: "static/images/uploads" # Media files will be stored in the repo under static/images/uploads
public_folder: "/images/uploads" # The src attribute for uploaded media will begin with /images/uploads
```

If you're creating a new folder for uploaded media, you'll need to know where your static site generator expects static files. In the configuration above adds a new setting, `public_folder`. While `media_folder` specifies where uploaded files are saved in the repo, `public_folder` indicates where they are found in the published site. Image `src` attributes use this path, which is relative to the file where it's called. For this reason, we usually start the path at the site root, using the opening `/`.

If public_folder is not set, Netlify CMS defaults to the same value as media_folder, adding an opening / if one is not included.

After this we need to set up something called collections. Collections define the structure for the different types of content on your site. For example a magority of my posts all have a title, publish date, description, tags, and a body. I can also post a featured image and list an author if i wanted to. For my website, my `config.yml` file in the `adnmin` folder has the following:

```yml
 - name: "projects"
    label: "Project Posts" 
    folder: "/content/posts/projects"
    create: true
    slug: "{{year}}-{{month}}-{{day}}-{{slug}}"
    fields:
      - {label: "Title", name: "title", widget: "string"}
      - {label: "Publish Date", name: "date", widget: "date"}
      - {label: "Featured Image", name: "cover", widget: "image", required: false}
      - {label: "Decription", name: "desciption", widget: string"", required: true}
      - {label: "Tags", name: "tags", widget: "list", required: false}
      - {label: Author, name: author, widget: hidden, default: Joshua Mathie}
      - {label: "Body", name: "body", widget: "markdown"}
```

This is set up for every type of post that I could want to utilize. This might look quite confusing, and not going to lie it is, so let me break it down for you. 

| ITEM   | DESCRIPTION                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| name   | Post type identifier, used in routes. Must be unique.                                                                                                                                                                                                                                                                                                                                                                                            |
| label  | What the admin UI calls the post type.                                                                                                                                                                                                                                                                                                                                                                                                           |
| folder | Where files of this type are stored, relative to the repo root.                                                                                                                                                                                                                                                                                                                                                                                  |
| slug   | Template for filenames. {{year}}, {{month}}, and {{day}} pulls from the post's date field or save date {{slug}} is a url-safe version of the post's title. Default is simply {{slug}}.                                                                                                                                                                                                                                                           |
| fields | Fields listed here are shown as fields in the content editor, then saved as front matter at the beginning of the document (except for body , which follows the front matter). Each field contains the following properties:  - label: Field label in the editor UI. - name: Field name in the document front matter. - widget: Determines UI style and value data type (details below). - default(optional): Sets a default value for the field. |

---

PHEW that was alot to take in huh? Get conmfy were not done yet!

Next we need to set up authentication. Thankfully because we are using the Netlify platform already this is relatively easy to do as they offer a nuilt-in authorization service they call Identify.


1. Go to Settings > Identity, and select Enable Identity service.
2. Under Registration preferences, select Open or Invite only. In most cases, you want only invited users to access your CMS, but if you're just experimenting, you can leave it open for convenience.
3. If you'd like to allow one-click login with services like Google and GitHub, check the boxes next to the services you'd like to use, under External providers.
4. Scroll down to Services > Git Gateway, and click Enable Git Gateway. This authenticates with your Git host and generates an API access token. In this case, we're leaving the Roles field blank, which means any logged in user may access the CMS. For information on changing this, check the Netlify Identity documentation.


Once thats done the backend has been setup to handle authentication, now you just need a frontend interface. Don't worry were almost done. Netlify Identify has a nice widget that we can install as a drop-in for this purpose. To include the widget just add the following in 2 places"

```yml
<script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
```

These need to be added to the `<head>` of your CMS index page located at `/admin/index.html`, as well as the `<head>` of your sites main index page. Depending on how your site generator is set up, this may mean you need to add it to the default template, or to a "partial" or "include" template. If you can find where the site stylesheet is linked, that's probably the right place.

Whe a user logs in with the Metlify Identify widget an access token redirects to the site homepage. In order to complete the login and get back into the CMS, we need to redirect the user back to the `/admin/` path. This can be accomplished by adding the below script right before the closing `body` tag of your sites main index page:

```html
<script>
  if (window.netlifyIdentity) {
    window.netlifyIdentity.on("init", user => {
      if (!user) {
        window.netlifyIdentity.on("login", () => {
          document.location.href = "/admin/";
        });
      }
    });
  }
</script>
```

## CONGRATULATIONS AGAIN

Your site is now fully configured and ready for you to start using the CMS and draft, review, and post content independant of your base install on your PC. Just don't forget to invite people to post if your doing this!

# Enjoy your website!

-----

All thanks to [Hugo](http://gohugo.io), [Netlify](http://www.netlify.com), and [Netlify CMS](http://www.netlifycms.org) for posting their amazing tutorials on setting this all up. 
