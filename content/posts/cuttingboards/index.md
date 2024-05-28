+++
title = 'Building This Website'
date = 2024-05-27T16:58:11-07:00
draft = false
+++

<!-- I recently released my debut album, a labor of love!

<div style="text-align: center;">
    {{< figure src="/images/ESSAR_COVER.jpg" title="ESSAR" height=100 >}}
</div>

## {{< figure src="/images/ESSAR_COVER.jpg" title="ESSAR" height=100 >}}

{{< youtube matAawZcC9s >}} -->

## An experiment in web dev: hugo + vercel 

I coded up my own site - here's how and why. 

I wanted a newsletter dedicated to my projects so I could keep my professional network updated on my latest activities. Given this, I could only see it happening if my newsletter was something I could own. I've used Wordpress and Weebly for a long time, but have gradually witnessed more and more features put behind a paywall. Substack is new-ish (not guaranteed to last), Squarespace makes you pay for everything, and my Twitter account keeps getting spammed by bots. I was left a little lost... where on earth should I host my stuff? 

I'm approaching this from the decades long timeline. I want this to be one of those kinda crappy outdated sites you can encounter 10 years later, where you're surprised it's still up, but it hasn't crashed yet.

It made the most sense to download a framework, host my site locally, and depend on a few highly niche services that I'm confident I can replace if they go down (in this case, Github and Vercel - and Github isn't even necessary). Here's how I did it.

{{< figure src="/images/hugo.jpg" >}} 

I used Hugo, a HTML/CSS framework, to host my site. Hugo essentially delivers a wrapper over HTML and CSS and creates a pipeline between Markdown files (the bane of the content on a Hugo site) and the actual HTML/CSS encoding. I'll never have to touch the root code if I don't want to, but it's all mine to change if I desire.

This site is based on the [typo](https://github.com/tomfran/typo?tab=readme-ov-file) theme. After following the Hugo [quickstart](https://gohugo.io/getting-started/quick-start/) guide and adapting it for the [specific setup instructions](https://github.com/tomfran/typo?tab=readme-ov-file#1-setup) provided in Typo's Github Repository, I had a locally hosted website.
I learned that Hugo has markdown [shortcodes](https://gohugo.io/content-management/shortcodes/) that you can use to embed Youtube videos, images and more. The ease of this is crazy, because on some website providers these services are paywalled. I was surprised at how easy it actually is: Youtube's API is probably free for anyone to use, and here Hugo is making the code for that super easy while everyone else makes that a "premium service". Doing things yourself is so fun!

    brew install hugo
    hugo new site quickstart
    cd quickstart
    git init
    git submodule add --depth=1 https://github.com/tomfran/typo.git themes/typo
    git submodule update --init --recursive
    echo "theme = 'typo'" >> hugo.toml
    hugo server

{{< figure src="/images/vercel.jpg" >}} 

Hugo creates a "quickstart" folder enclosing the contents of your website. After converting this folder to a [Github repo](https://github.com/shxlpa/shilpsite), then trying and failing to turn it into a Github pages site, I gave up and looked into Vercel (way faster, can't recommend enough). All I had to do was install the Vercel CLI, run one command, then follow the resulting prompts:

    sudo npm install -g vercel
    vercel

{{< figure src="/images/vercelcode.jpg" >}} 

I now have a shiny new website in my hands. This thing is *clean*. There's a lot of aesthetic work to be done, and I still have to build in subscription functionality so that I can email my network every time I post. Luckily there are free APIs for that :)