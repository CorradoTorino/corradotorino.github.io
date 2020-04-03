---
layout: post
title: How Setup your Blog in an Evening?
image: /img/2020-03-13-glenn-carstens-peters-npxXWgQ33ZQ-unsplash-edited.jpg
---

My last and first blog was answering the question: why is it important for a software engineer to keep a blog. Now, I would like to highlight how incredible simple and easy is to setup one nowadays. Already in the past, creating and maintaining a blog was affordable by everyone with a minimum technical background and just some interest on the topic. But now, it is even more simpler. I had setup one in an evening for free, without having experience on web development. The receipt that worked fine for me is a mix of:

- GitHub Pages
- Markdown
- Jekyll
- Beautiful Jekyll

I feel that with this combination I get the benefit of a powerful and flexible solution, without spending effort in implementation details. So, I could focus on just the content and not on the tools itself.

### GitHub Pages

[GitHub Pages](https://pages.github.com) offer a way to create custom websites for GitHub users and projects. It is a well known product and with a long history, since is already available from 2008. Its main benefits is simplicity. You have for free all the features of GitHub, like:

- version control
- availability
- lot of documentation
- huge community support
- don't need any infrastructure or database

If you want your custom domain, it support custom urls. And last but not least, as a software engineer you likely already have an account and have some repos on GitHub.

### Markdown

I really love Markdown, because it is so simple and intuitive. It is not a coincidence that it is nowadays a de facto standard for technical writing, especially for blogging. According to its creator John Gruber: “*Markdown is a text-to-HTML conversion tool for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML (or HTML).*” [1]

I found very powerful this lightweight markup language because I can write rich formatted content extremely quickly compared to html. You can obtain nice and clean formatting without knowing nothing about HTML or CSS. Moreover, as you can see in the next section, Markdown can be used in Static Site Generators such as Jekyll very easily, without worrying about JavaScript or Ruby. 

Being a plain text format is a big advantage. It allows working smoothly with version control system as Git. Finally, markdown is platform-agnostic, at least if you attain to the standard and do not extend it. So, your content is not tied to the format of your editor.

Detractors of Markdown objects that it is limited stylistically, in how you can display content. And, it is absolutely true . However, this is an intentional design choice. And probably the main reason why I like it, being a fan of the KISS principle. 

### Jekyll

A dynamic website for a simple blog is just overkilling. With a static website you can avoid all the overhead of a database and its infrastructure. Then, gaining in maintenance, security, faster learning, versioning, free hosting. 

Jekyll helps you to create a static website. It is a static site generator. Starting from a plain text as input, Jekyls is able to generate the html code of the entire static web site. In particular, the plain text can be markdown. Jekyll was created to facilitate blog creation and it is now the most famous web static generator, probably because is the engine behind [GitHub Pages](https://en.wikipedia.org/wiki/GitHub_Pages).

Again what I like of this tool is its simplicity. I found very usefull the possibility to preview the changes locally  the content with very los effort. You need just to install jekyl with its dependecny (Ruby) and then launch ....





place code example here



### Beautiful Jekyll

[GitHub Pages](https://pages.github.com/) are *powered by Jekyll*,

Get up and running *in seconds*.

ToDo: remark the importanece of open source

## References:

1-[Markdwon by John Gruber](https://daringfireball.net/projects/markdown/)

2 -[Pros and Cons of Using Markdown for Technical Writing](https://hackernoon.com/pros-and-cons-of-using-markdown-for-technical-writing-34f277418a8a)

3 -  [Jekyll](https://jekyllrb.com/)

4- [Building a static website with Jekyll and GitHub Pages](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages)

4- [Testing your GitHub Pages site locally with Jekyll](https://help.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll)