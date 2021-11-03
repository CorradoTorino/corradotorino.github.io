---
layout: post
title: How to Setup your Blog in an Evening
thumbnail-img: /assets/img/2020-04-07-victoria-heath-MAGAXAYq_NE-unsplash-edited.jpg
share-img: /assets/img/2020-04-07-victoria-heath-MAGAXAYq_NE-unsplash-edited.jpg
tags: [blogging]
readtime: true
---
If you want to have a batteries-included blog without getting lost in the sauce, here’s my recipe. It uses open source ingredients, widely consumed in the blogging community. I obtained a standard, powerful and flexible solution, without spending much time and effort in implementation details.

My last and [first blog entry](https://corradotorino.github.io/2020-03-13-first-post/) was answering the question: why is it important for a software engineer to keep a blog? Now, I would like to highlight how incredibly simple and easy it is to setup one nowadays. In the past, creating and maintaining a blog was affordable by everyone with a minimum technical background and just some interest in the topic. But now, it is even simpler. I had one setup in an evening for free. The recipe that worked for me is a mix of:
- GitHub Pages
- Markdown
- Jekyll
- Beautiful Jekyll

I feel that with this combination I obtained a good result and was able to focus on just the content of the blog and not on the tools themselves.

## GitHub Pages

[GitHub Pages](https://pages.github.com) offers a way to create custom websites for GitHub users and projects. It is a well known product, with a long history and has been available since 2008. Its main benefit is simplicity. You have all the features of GitHub for free, such as:

- version control
- availability
- lot of documentation
- huge community support
- don't need any infrastructure or database

If you want a custom domain, it supports custom urls. And last but not least, as a software engineer you likely already have an account and have some repos on GitHub.

## Markdown

I really love Markdown, because it is so simple and intuitive. It is not a coincidence that it is nowadays a de facto standard for technical writing, especially for blogging. According to its creator [John Gruber](https://daringfireball.net/projects/markdown/): “*Markdown is a text-to-HTML conversion tool for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML (or HTML).*”

I found this lightweight markup language very powerful because I can write rich text format content extremely quickly compared to html. You can obtain nice, clean formatting without knowing anything about HTML or CSS. Moreover, as you can see in the next section, Markdown can be used in Static Site Generators such as Jekyll very easily, without worrying about JavaScript or Ruby.

Being a plain text format is a big advantage. It allows you to work smoothly with a version control system like Git. Finally, markdown is platform-agnostic, at least if you comply with the standard and do not extend it. Therefore, your content is not tied to the format of your editor.

Detractors of Markdown object that it is limited stylistically, in how you can display content. And that is absolutely true . However, this is an intentional design choice and probably the main reason why I like it, being a fan of the KISS principle.

## Jekyll

A dynamic website for a simple blog is just overkill. With a static website you can avoid all the overheads of a database and its infrastructure. So, you gain in maintenance, security, faster learning, versioning, and free hosting.

Of course, you can write your static website and its html on your own. However, you can count on allies that can make your life easier, for example: Jekyll. It is a static site generator. So, what does this mean? Simple: starting from a plain text as input, Jekyll is able to generate the html code of the entire static web site. In particular, the plain text can be Markdown. It will not surprise you that Jekyll was created to facilitate blog creation. And now, it is the most famous web static generator. Probably, because it is the engine behind GitHub Pages.

Again, simplicity and broad adoption are the reasons why I fell in love with this tool.

For example, I found it very useful that with zero effort you can [preview changes](https://help.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll) of your blog locally. In fact, you just need to install Ruby and Jekyll, a Ruby Gem, and then execute one command.

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

I promised a blog in just an evening, and I meant a battery-included blog: with a pleasant look and feel and all the functionalities that you can expect. So, It's time to meet the last of our ally: [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll#readme).

As defined by its creator, Dean Attali, *Beautiful Jekyll is a ready-to-use template to help you create an awesome Jekyll or GitHub Pages website quickly*.

When I discovered this project, I was very impressed: just cloning the repo and running it and I got a bunch of appealing features. It has a mobile-first look, it shines on both large-screen and small-screen (mobile) devices. It is highly customizable, for example you can change background colors, add images and avatars both in pages and in the navigation bar. You can share your posts easily on all the social media such as LinkedIn, Facebook, Twitter, RSS feed… Moreover, it has some cool features that I still haven’t tried like Google Analytics or the possibility to allow users to leave comments.

So, if you want to save time on styling and details, I absolutely recommend Beautiful Jekyll.

## Useful Links
1. [GitHub Pages](https://pages.github.com), to get your space
2. [Markdown by John Gruber](https://daringfireball.net/projects/markdown/), when Markdown was born
3. [Pros and Cons of Using Markdown for Technical Writing](https://hackernoon.com/pros-and-cons-of-using-markdown-for-technical-writing-34f277418a8a), some more details about Markdown
4. [Jekyll](https://jekyllrb.com/docs/), to get started
5. [Building a static website with Jekyll and GitHub Pages](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages), a detailed how-to guide to create this blog 
6. [Testing your GitHub Pages site locally with Jekyll](https://help.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll)