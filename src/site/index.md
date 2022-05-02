---
title: Trent Bagshaw
subtitle: If I've pointed you at this then I'm asking you for 5 minutes of your life you'll never get back, so thank you! I'm a [Digital Transformation](https://en.wikipedia.org/wiki/Digital_transformation) (DX) and [Customer Experience](https://en.wikipedia.org/wiki/Customer_experience) (CX) professional who finds it hard to describe what I do and how I got here for a potential employer. I've only just spun this up (30th April 2022) because I haven't actively looked for a new role in fifteen years or so. Currently an unfinished work in progress based on a project scaffold by <a href="https://twitter.com/philhawksworth">Phil</a>, thanks Phil!
layout: layouts/base.njk
---
## What do I do for a living? Specifically what do I do well?
This is a question I've had trouble with for a long time because what I'm good at didn't really exist 20 years ago. At least not in the way that it works now or the speed at which it changes. Doctor, plumber and accountant are all roles that we inherintly just *understand*. Even modern jobs in the IT space like computer programmer are somewhat understood even if you don't know exactly what that person does on a day-to-day basis.

This might be better worded as "What do you do *well* while you are employed?" as I've had lots of different jobs but I've always gravitated towards DX and CX regardless of KPIs and role descriptions. What I do well is identify and permanently remove or reduce **process friction** for people, using (mostly) digital technology. I'd also like to think that I'm good at other things including communication, problem solving and computer "savvy".

## I've answer a question with a made-up term. What is process friction?
Process friction means something that gets in the way of you moving towards your goals. More speficially, it's something that gets in the way of your ability, experience, and expertise that you use to achieve those goals. In the business world it's called "business friction" and in your personal life I'm honestly not sure what it's called. Struggling to remember all of the passwords you have (assuming you are doing what you're supposed to do and having unique passwords for the 300 accounts in your life) and failing to log in to services quickly because you forgot one of them is an example of process friction. LastPass or 1Password is an example of a digital tool that can remove the process friction and allow you to log in. It removes the process friction by eliminating something you are probably not an expert in (remembering 300 unique passwords) and allowing you to more quickly achieve your goal (binge watching Netflix).

## What are some examples of process friction that you've resolved?
I worked in a call centre between 2003 and 2007 while at university where my role was answering the phone and providing customer service. Paperwork (faxing, tracking performance) was a major component of each day which with the Microsoft Office suite available seemed like a waste of time. So I created paperless systems that removed the need for paperwork in either by using existing systems and VBA (the MS Office scripting language). It saved each call centre worker ~15 minutes per day and the administrative staff about 2 hours a day. The process friction

## Below this line is all scaffold

From this point we should already have:

- [Eleventy](https://11ty.io) with a skeleton site
- A date format filter for Nunjucks based on [Luxon](https://moment.github.io/luxon)
- A tiny CSS pipeline with PostCSS
- A tiny inline JS pipeline. (<a href="#" class="btn-log">Test a console.log message</a>)
- JS [search index](/search.json) generator
- [Netlify Dev](https://www.netlify.com/products/dev) for testing [Netlify redirects](https://netlify.com/docs/redirects/)
- Serverless (FaaS) development pipeline with [Netlify Dev](https://www.netlify.com/products/dev) and [Netlify Functions](https://www.netlify.com/products/functions)



## Post pages

The pages found in in the posts

<ul class="listing">
{%- for page in collections.post -%}
  <li>
    <a href="{{ page.url }}">{{ page.data.title }}</a> -
    <time datetime="{{ page.date }}">{{ page.date | dateDisplay("LLLL d, y") }}</time>
  </li>
{%- endfor -%}
</ul>

## Links from an external data source

These links were sourced from [hawksworx.com](https://www.hawksworx.com/feed.json) at build time.

<ul class="listing">
{%- for item in hawksworx.entries.slice(0,5) -%}
  <li>
    <a href="{{ item.link }}">{{ item.title }}</a>
  </li>
{%- endfor -%}
</ul>


## Prerequisite

- [Node and NPM](https://nodejs.org/)

## Running locally

```bash
# install the dependencies
npm install

# External data sources can be stashed locally
npm run seed

# It will then be available locally for building with
npm run start
```

## Add some Netlify helpers
Netlify Dev adds the ability to use Netlify redirects, proxies, and serverless functions.

```bash
# install the Netlify CLI in order to get Netlify Dev
npm install -g netlify-cli

# run a local server with some added Netlify sugar in front of Eleventy
netlify dev
```

A serverless functions pipeline is included via Netlify Dev. By running `netlify dev` you'll be able to execute any of your serverless functions directly like this:

- [/.netlify/functions/hello](/.netlify/functions/hello)
- [/.netlify/functions/fetch-joke](/.netlify/functions/fetch-joke)

### Redirects and proxies

Netlify's Redirects API can provide friendlier URLs as proxies to these URLs.

- [/api/hello](/api/hello)
- [/api/fetch-joke](/api/fetch-joke)




