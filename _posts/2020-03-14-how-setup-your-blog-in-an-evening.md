---
layout: post
title: How Setup your Blog in an Evening?
image: /img/2020-03-13-glenn-carstens-peters-npxXWgQ33ZQ-unsplash-edited.jpg
tags: [blogging]
---
If you want to have a batteries included blog without getting lost in the sauce, I can share my recipe. It is flavored by open source ingredients, broadly consumed in the blogging community. I obtained a powerful and flexible solution, without spending effort in implementation details.

My last and first blog entry was answering the question: why is it important for a software engineer to keep a blog. Now, I would like to highlight how incredible simple and easy is to setup one nowadays. Already in the past, creating and maintaining a blog was affordable by everyone with a minimum technical background and just some interest on the topic. But now, it is even more simpler. I had setup one in an evening for free, without having experience on web development. The recipe that worked for me is a mix of:
- GitHub Pages
- Markdown
- Jekyll
- Beautiful Jekyll

I feel that with this combination I obtained a good result and had the possibility to focus on just the content of the blog and not on the tools itself.

## GitHub Pages

[GitHub Pages](https://pages.github.com) offer a way to create custom websites for GitHub users and projects. It is a well known product and with a long history, since is already available from 2008. Its main benefits is simplicity. You have for free all the features of GitHub, like:

- version control
- availability
- lot of documentation
- huge community support
- don't need any infrastructure or database

If you want your custom domain, it support custom urls. And last but not least, as a software engineer you likely already have an account and have some repos on GitHub.

## Markdown

I really love Markdown, because it is so simple and intuitive. It is not a coincidence that it is nowadays a de facto standard for technical writing, especially for blogging. According to its creator John Gruber: “*Markdown is a text-to-HTML conversion tool for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML (or HTML).*” [1]

I found very powerful this lightweight markup language because I can write rich formatted content extremely quickly compared to html. You can obtain nice and clean formatting without knowing nothing about HTML or CSS. Moreover, as you can see in the next section, Markdown can be used in Static Site Generators such as Jekyll very easily, without worrying about JavaScript or Ruby. 

Being a plain text format is a big advantage. It allows working smoothly with version control system as Git. Finally, markdown is platform-agnostic, at least if you attain to the standard and do not extend it. So, your content is not tied to the format of your editor.

Detractors of Markdown objects that it is limited stylistically, in how you can display content. And, it is absolutely true . However, this is an intentional design choice. And probably the main reason why I like it, being a fan of the KISS principle. 

## Jekyll

A dynamic website for a simple blog is just overkilling. With a static website you can avoid all the overhead of a database and its infrastructure. Then, you will gain in maintenance, security, faster learning, versioning, and free hosting. 

For sure you can write your static website and its html for your own. However, you can count on allies that can make your life easier, for example: Jekyll. It is a static site generator. What does it mean? Simple: starting from a plain text as input, Jekyll is able to generate the html code of the entire static web site. In particular, the plain text can be markdown. It will not surprise you that Jekyll was created to facilitate blog creation. And now, it is the most famous web static generator. Probably because it is the engine behind [GitHub Pages](https://en.wikipedia.org/wiki/GitHub_Pages).

Again, simplicity and broad adoption are the reasons  why I get in love with this tool.

For example, I found very useful that with zero effort you can preview locally the changes of your blog. In fact, you just need to install Ruby and Jekyll, a Ruby Gem, and then execute one command.

~~~
$ bundle exec jekyll serve
Configuration file: D:/Code/corradotorino.github.io/_config.yml
            Source: D:/Code/corradotorino.github.io
       Destination: D:/Code/corradotorino.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 2.988 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'D:/Code/corradotorino.github.io'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
~~~

## Beautiful Jekyll

I promise a blog in just an evening, and I'm meant a batterie included blog: with a pleasant look and feel and all the functionalities that you can except. So, It time to meet the last of our ally: Beautiful Jekyll.

As defined by its creator, Dean Attali, *Beautiful Jekyll is a ready-to-use template to make help you create an awesome Jekyll or GitHub Pages website quickly*.

When I discover this project, I was very impressed: just cloning the repo and running it and I get a bunch of appealing features. It has mobile-first look, it shine on both large-screen and small-screen (mobile) devices. It is highly customizable, for example you can change background colors, add images and avatars both in pages and in the navigation bar. You can share nicely your posts on all the social media as LinkedIn, Facebook, Twitter, RSS feed... Moreover, it has some nice features that I still not tried as Google Analytics or the possibility to allow users to leave comments. 

So, if you want save time on styling and details, I absolutely recommend Beautiful Jekyll.

## Useful Links
- [GitHub Pages](https://en.wikipedia.org/wiki/GitHub_Pages)
- [MarkdoWn by John Gruber](https://daringfireball.net/projects/markdown/)
- [Pros and Cons of Using Markdown for Technical Writing](https://hackernoon.com/pros-and-cons-of-using-markdown-for-technical-writing-34f277418a8a)
- [Jekyll](https://jekyllrb.com/)
- [Building a static website with Jekyll and GitHub Pages](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages)
- [Testing your GitHub Pages site locally with Jekyll](https://help.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll)
- [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll#readme)