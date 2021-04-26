---
title: "Step two: customize and add content"
subtitle: Tailor the style of the site according to your preference and get ready to populate your content.

# Summary for listings and search engines
summary: Change colors, fonts, and put your content on the site.

# Link this post with a project
projects: []

# Date published
date: "2021-04-23T00:00:01Z"

# Date updated
lastmod: "2021-04-23T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: ''
  focal_point: ""
  placement: 1
  preview_only: false
   

authors:
- admin

tags:
- Academic


categories:
- Demo

---



## About this tutorial


This is the first part of the tutorial to create a website using
[Hugo](https://gohugo.io/) and [RStudio](https://www.rstudio.com). We
are going to use a particular flavor of Hugo templates called
[Wowchemy](https://wowchemy.com/) (previosuly know as academic Hugo).

With Wowchemy, the default option is to deploy the site using a
subscription based service called [Netlify](https://www.netlify.com/).
The process is very well explained on their
[documentation](https://wowchemy.com/docs/getting-started/install/).

As advocates for free technology we are going to opt for a second way to
modify and deploy your website using your own PC and [Github
Pages](https://pages.github.com/).

In this iteration we are going to proceed with the some of the most
basic and common ways to modify your website.

The following sections are based on the documentation of [Wowchemy](https://wowchemy.com/docs/getting-started/get-started/). Some materials, like schematics, are a direct reproduction of the materials found on [Wowchemy](https://wowchemy.com/docs/getting-started/get-started/). We offer a reinterpretation and examples.

Notice that the modifications that are possible are many. In this tutorial we are going to mention only the most basic, however, the limit of how much you can achieve is much higher than what we will cover. To see all the possibilities please checkout the [official documentation](https://wowchemy.com/docs/)  

## Understanding the structure of the website

Behind the scenes, the tools that build your website are a collection of [Markdown](https://en.wikipedia.org/wiki/Markdown) files that are the vessel for the content you want to display. By default, the template you acquired through the Github repo should have a structure similar to the shown below.


* 📄 LICENSE.md
* 📄 README.md
* 📄 academic.Rproj - (optional) For RStudio users, otherwise can be deleted
* 📁 assets
  - 📁 media
    - 📄 icon.png - (optional) add your website icon here
    - 📄 logo.png - (optional) add your logo here
* 📁 config
  - 📁 _default
    - 📄 config.yaml - define your site name and URL
    - 📄 languages.yaml - edit this for non-English or multilingual sites
    - 📄 menus.yaml - define your site menu
    - 📄 params.yaml - personalize your site
* 📄 config.yaml - (optional) a dummy file for RStudio compatibility - non-RStudio users can delete
* 📁 content
  - 📁 authors - user profiles
    - 📁 admin - your username (can rename)
  - 📁 home - your homepage - personalize the homepage with widgets
  - 📁 post
  - 📁 publication
  - 📁 talk
* 📁 data
  - 📄 page_sharer.toml - (optional) customize social sharing buttons
* 📄 netlify.toml - (optional) defines Hugo version for deploying with Netlify
* 📁 scripts - (optional) scripts to maintain the template repository - can be deleted
* 📁 static
  - 📁 admin - (optional) your Netlify CMS admin panel
* 📄 update_academic.sh - (optional) a script to help update Academic
* 📄 view.sh - (optional) a script to view your site locally

Yes! I know it is a lot! But for the sake of editing content in your website, and changing the appereance inside the pre-established parameters of the template, you should only be concerned with two directories:

* 📁 config
* 📁 content

The first one allows to change the general parameters, e.g., template of colors and font you are using. The second is where the most of the work is done and the editing of the site content is due.

## Choosing a color and font configuration

[Wowchemy](https://github.com/wowchemy/wowchemy-hugo-modules/tree/main/wowchemy/data/themes) provides twelve different color templates and five [font configurations](https://github.com/wowchemy/wowchemy-hugo-modules/tree/main/wowchemy/data/fonts). 

* themes: `1950s, apogee, coffee, cyberpunk, dark, earth, forest, minimal, mr_robot, ocean, rose, and strawberry.`
* fonts: `classic, minimal, mr_robot, cyberpunk, rose, and native.`


You can choose as you prefer. To do it you can edit the file:

* 📁 config
  - 📁 _default
    - 📄 config.yaml

There are several parameters that control the appeareance of the site in this file. To choose the color theme, and font you will need change the following options:

    # Appearance
      theme: minimal
      day_night: true
      font: ''
      font_size: L

For example one can choose the color theme [Mr. Robot](https://github.com/wowchemy/wowchemy-hugo-modules/tree/main/wowchemy/data/themes) with the font `rose`, and size `medium` you have to change the code to:

    # Appearance
      theme: mr_robot
      day_night: true
      font: 'rose'
      font_size: M

If you are more of a risk lover (like me), you can create download a template from  [Wowchemy's repo](https://github.com/wowchemy/wowchemy-hugo-modules/tree/main/wowchemy/data/themes), you can rename it and  put it in the folder: 

* 📁 data
  - 📁 themes
    - 📄 test_theme.toml

In there you can modify color options, among others(mind your changes!) using HTML color codes. You can do something similar to create your own font. Download a font file from the [repository](https://github.com/wowchemy/wowchemy-hugo-modules/tree/main/wowchemy/data/fonts). Rename it and paste it in:

* 📁 data
  - 📁 themes
    - 📄 test_theme.toml
  - 📁 fonts
    - 📄 test_font.toml  

 After you are done, you can change the `./config/_default/config.yaml` so it reflects:
 
     # Appearance
      theme: test_theme.toml
      day_night: true
      font: 'test_font'
      font_size: M

## Managing the sections and pages of your site

### Content Structure
The majority of the edits and change will have place in the files that are located in the `content` folder. By default you have the following structure. 

* 📁 content
  - 📁 admin (*used to host site using netlify*)
  - 📁 authors (*contains the authors metadata*)
  - 📁 event (*used to create a page for an event*)
  - 📁 home (*home page where you show case all the site*)
  - 📁 post (*blog like page where posts can be populated*)
  - 📁 project (*used to create a project page*)
  - 📁 publication (*used to list all publications*)
  - 📁 slides  (*used to show slides as desired*)     

Each folder in the `content` directory represents a page in your website as long as a file named `index.md` with a coherent header is placed on the folder. Some of them are pages associated with widgets that are placed in the home page. Wowchemy uses a set of widgets to populate the html content.  The list of widgets available can be found on the [documentation](https://wowchemy.com/docs/getting-started/page-builder/). Alternatively you can [create your own widget](https://wowchemy.com/docs/getting-started/page-builder/#create-a-new-widget) (requires a bit more effort and programming knowledge!). 


#### Creating a page

To create a page in your site simply create a folder (e.g. `test`), in the `content` directory and create an `index.md` file with a coherent header:

    ---
    title: An example title
    summary: Here we describe how to add a page to your site.
    date: "2018-06-28T00:00:00Z"
    
    reading_time: false  # Show estimated reading time?
    share: false  # Show social sharing links?
    profile: false  # Show author profile?
    comments: false  # Show comments?
    
    # Optional header image (relative to `assets/media/` folder).
    header:
      caption: ""
      image: ""
    ---

    Add your **content** here...


You can add this new page to the top Menu by modifying the file `config/_default/menus.yaml` by creating an entry:

    [[main]]
      name = "My new page"  # A link title for your page.
      url = "test/"  # The URL of your page.
      weight = 50  # The position of your page in the menu.



#### Removing pages

In order to remove pages you can either remove the associated folder of the page. Or you can edit the `active` option on the header:

    ---
    title: An example title
    summary: Here we describe how to add a page to your site.
    date: "2018-06-28T00:00:00Z"
    
    active: false

    ---

    Add your **content** here...

### Edit your home page

By far the most important page on your site is the home page. This one it self is a complex object. This is a page that host several widgets. Hence it is called a [`widget page`](https://wowchemy.com/docs/content/landing-pages/). This means that it holds widgets in it as sections of the site. Each sections is stored as an `<file.md>` with an appropiate header. The default structure of the home section is the following:

* 📁 home
  - 📄 about.md
  - 📄 accomplishments.md
  - 📄 contact.md
  - 📄 demo.md
  - 📄 experience.md
  - 📄 featured.md
  - 📄 index.md
  - 📄 posts.md
  - 📄 projects.md
  - 📄 publications.md
  - 📄 skills.md
  - 📄 tags.md
  - 📄 talks.md                   

#### Creating and removing sections

According to your needs and preferences you can choose which of this sections to retain. For example, if you are not into blogs, you can choose to remove such section deleting the `posts.md` file. 

To create new sections you can add a new file `content/home/<your_section>.md` that must have a header and content as shown:

    ---
    # An example widget.
    widget: <widget option>
    
    # This file represents a page section.
    headless: true
    
    # Order that this section appears on the page. (higher weight = later in the section)
    weight: <weight>
    
    # Section title
    title: Example title
    
    # Section subtitle
    subtitle: Example subtitle
    
    # Section design
    design:
      <your design options>
    ---
    
    Add Your Markdown content Here

You can include a link to the section by adding an entry in the file `config/_default/menus.yaml` as follows:

    [[main]]
      name = "Click bait"  # A name for the link.
      url = "/#<your_section>"  # URL of the section.
      weight = 10  # Position of the link in the menu

To understand each widget and wheter to use it on your section or not we recommend browsing through each [widget type description](https://wowchemy.com/docs/getting-started/page-builder/).


## Previewing your site

Every time you make an edit on the markdown files and save it the active server you are using. In the case of RStudio, the `blogdown::server_site()` should update automatically by refreshing the page. Usually, when you change images or aesthetics options you should  `blogdown::stop_server()` and start it again to see the changes implemented. 