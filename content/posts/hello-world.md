---
title: "Hello World"
date: 2023-10-05T20:50:58+01:00
draft: false
toc: false
images:
tags: 
  - autobiography
---

I've been wanting to start a blog for years, but I haven't been able to mainly for three reasons:

__Software__:

I have tried time and again to set up a simple blog using GitHub pages and Jekyll but, have failed.
This is a summary of my most recent attempt trying to start a blog using Jekyll developing on Windows Subsystem for Linux (WSL2).

- `gem install jekyll bundler`

Having mindlessly copied and run the command from the GitHub pages Jekyll setup guide, I had my doubts on whether it would work since I wasn't sure Ruby was installed. Turns out, I may have tried and failed to set up a blog earlier this year since Gem was already installed, and now it gave me a different error this time:

```sh
ERROR:  Error installing jekyll:         ERROR: Failed to build gem native extension.
```

There were way too many similar issues but none seemed to vibe with me. This made me quickly give up, and try the jekyll wiki for installing on WSL2. Following the tutorial, Ruby installed fine as it suggested using a different Ubuntu repository, it was downgraded by Ruby install from 2.7 to 2.5 for some reason. 2.7 anyway makes me anxious, so I didn't mind. However, I hit a new snag - an error complaining the installed Ruby version was too old. I would have had to pin a lot of dependencies, which didn't seem right. So, as a last resort, I tried using the asdf-vm package manager to install the latest Ruby.

```sh
asdf plugin install python
asdf install ruby latest
asdf global ruby latest
```
Surprisingly, only after restarting my terminal, I had a shiny new Ruby 3.2.2 install. Jekyll also installed perfectly, with no errors. All I had to do next was enable the GitHub pages v228 plugin in the gem file and use bundle install to download and install it. But, as predicted, I ran into another error:


```sh
❯ bundle install
Fetching gem metadata from https://rubygems.org/..........
Resolving dependencies...
Could not find compatible versions

Because GitHub-pages >= 228 depends on Jekyll = 3.9.3
  and Gemfile depends on jekyll ~> 4.3.2,
  GitHub-pages >= 228 cannot be used.
So, because Gemfile depends on github-pages ~> 228,
  version solving has failed.
```

Which was solved simply by:

```sh
cd ..
rm -rf archkudo.github.io
```

I started looking for other options and remembered seeing praise for Hugo on HackerNews. So, I decided to give it a go. Installing it was as easy as `apt install hugo`. But when I built the site, it was serving empty pages. After some digging, I realised it had to do with the theme. I had set it correctly in `hugo.toml` as the official Get Started wiki said, but turns out it needs to go in the config.toml file instead. Now, I have a local version of the blog running smoothly, and if you're reading this blog, I managed to host it on `gh-pages` too!

__Topics__:

Earlier, I could never figure out what to write about. It always felt like I was just writing for the sake of it. I could've written about technology, computer science, new things I learned, or even about myself, but it all had its downsides. For example, I didn't want to write about a new technology I was learning because I didn't want to lose focus. And writing about myself felt like I was just ranting, which I didn't want to do either.
2022, also marked the year when I became interested in pursuing a master's which after a lot of soul-searching my purpose which sparked my interest in the biology of ageing. Now a year later, I have another thing to write about which is neither about how I solved some rare bug, which already had a Stackoverflow answer since 2010 nor about my opinions of why I don't fancy any language except Clojure (even though I use Python for every new project I start). That being I'm no longer scared of reading academic articles and wish to write about them.

__Motivation__:

Lastly, the infliction point to start writing this blog is that I did poorly in my recent MSc dissertation report. I delayed it till the very end, had a few personal setbacks and a cold next thing I knew I was writing the conclusion twenty minutes before the deadline and missed adding citations to my work and in barbaric English without a pass through grammarly or chatgpt. Not only did this destroy my chance of getting 1:1 which I had put so much effort into maintaining throughout the year, but I believe I also lost the trust of my reviewers, particularly my supervisor and have been living in the guilt ever since.
As much as that mistake hurt, it made me realise how bad I was at writing and how I could actually write 15,000 words when I tried. This blog is my way of getting better at writing and making sure I don't make the same mistake again, especially if I want to stay in academia, which I definitely do.

__What's next?__:

I've always had things I wanted to write about, and now I finally have a reason to do it. I hope this blog will be proof of whether I can stick to it with my goal of writing at least one post on each of the following topics:

1. Summarizing my dissertation
2. Review of the paper "Hallmarks of ageing"
3. My experience living in the UK for the past year
