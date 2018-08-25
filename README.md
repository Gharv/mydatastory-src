# website_source

## Intro

In the following replace `username` with your github account name.

**Do not edit `username.github.io/` folder**

Since our website is basically a folder containing static files, it is much easier to deploy than websites that require dynamic server-side languages such as PHP or databases. All we need is to upload the files to a server, and usually your website will be up and running shortly. In this case the `username.github.io/` folder is where our website is held.  
Our website is rendered in this `username.github.io/` because of we set an option in the `website_source/config.toml` file with `publishDir: "../username.github.io"` So we need to setup a GIT repository with the name of our website `username.github.io`  and it must follow `username.github.io` otherwise github will not know to use it as a website. We will clone the GIT repository and have two repositories as shown below: 

```
website_source/
│
├── config.toml
├── content/
├── themes/
└── ...

username.github.io/
│
├── .git/
├── index.html
├── about/
└── ...
```

## Setup

1. Download [github desktop](https://desktop.github.com/)
2. Sign into github desktop
3. Click `Clone a repository`
4. Set the `Local path` to whatever directory you wish to save to. Make sure both of the following are cloned into the same `Local path`
5. Click `Clone` once you have selected the website repository for the website in this case `username/username.github.io`
6. Click `File` on the menu bar and select `Clone repository` and select the source of the website `username/username-src`
7. We have now cloned both repositories needed, now make sure at the top left Current repository is `website_source`
8. Click on the blue text in the middle of github desktop application labeled `open this repository`
9. A file explorer should open up and select the R Project file which should open up RStudio and you can begin step 1 in the Update Instructions below
10. Install `blogdown` package, to do this run `install.packages("blogdown")` in RStudio Console.
11. Install `hugo` with the following code `blogdown::install_hugo()` this will produce an error that looks like  

```
problem copying .\hugo.exe to C:\Users\username\AppData\Roaming\Hugo\hugo.exe: No such file or directory
```  

To fix this we need to go to this folder path and create the `Hugo` folder in this case we would navigate to `C:\Users\username\AppData\Roaming\` and right click in file explorer and create a new folder then name it `Hugo`.  

12. Install the `hugo` package again by running `blogdown::install_hugo()`


## Update Instructions

Once the directories are set up as shown above go into the `website_source` directory, then to add a post:  

1. Click `Addins` drop down in RStudio menu > Click `New Post` under BLOGDOWN (this requires blogdown package installed)
2. Fill out appropriate details and use .Rmd format
![](https://bookdown.org/yihui/blogdown/images/new-post.png)
3. Add a description to the header like shown below, if this is not added the description will default to the first 200 words of your post.
```
---
title: "My Post"
description: "Summary of the post to show on front page."
---
```
4. Write out post, take advantage of Rmd syntax with this [pdf](https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)
5. In the R Console inside RStudio run `blogdown::serve_site()` to see preview of your post in the Viewer panel.
6. Once satisfied with your website run `blogdown::build_site()` this will render all the Rmd files into html files that will allow you to share the website.
7. Open GitHub Desktop, you should see changes in the repositories that you have changed
8. Type in a summary at the bottom left, then hit `Commit to master`
9. Click the `Push origin` button along the top to push changes to GitHub
10. Repeat this for both repositories

Now the website should be up and running, it may take a minute or two to update.

## Extra

The `config.toml` contains a lot of configuration options.  

Use `coverimage: "{url to image}"` in the yaml header of a post to specify a background image for the article title.

If you wish to change the layout or colors, you need to edit the `style.css` file in the `themes` folder the whole path is `themes/hugo-xmag/static/css/style.css`  

Blog posts are saved in `content/post` if you are having an issue or want to delete a post, just go there and delete the file.

**Do not edit `username.github.io/` folder**




