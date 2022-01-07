---
category: adobe-analytics
title: This Blog
description: Trying to share my thoughts about analytics engineering while
  staying abreast of current web development trends
---
In addition to being a place to share my experience as an analytics engineer, this is also what the good folks at egghead.io would call a "digital garden" — a space to cultivate web application development skills.

This blog uses:
- Nuxt.js
- TailwindCSS
- Netlify CMS

## Why Nuxt?
We use Vue at work. Coming from an Angular shop, I'm fairly new to Vue, although I've already had some opportunities to get familiar with it. We use it in most of our Launch extensions, and we also use it to build internal utility apps for things like migrating Launch properties and GTM containers.

Nuxt is a "meta-framework", in that it's built on top of another framework (Vue) and incorporates other frameworks (Tailwind), but tries to solve for a lot of common patterns that arise when building Vue apps: how do I optimize for production? What's the best Vue config for things like postcss and eslint? Nuxt attempts to abstract much of the arcane nuances of these tools and centralize tooling in a single config file.

Nuxt also has a Content module, which makes it similar to other static site generators (Hugo, Eleventy) in terms of being able to write content in e.g. Markdown and have routing dynamically generated based on directory structure. There are a lot of other benefits to the Content module which I'm trying to learn more about.

## Why Tailwind?
In terms of CSS frameworks, I'm most familiar with Bootstrap. While I don't have much experience with Tailwind, it's gotten a lot of traction in recent years, hence why I'm trying to get familiar with it. So far I'm a little skeptical: I get that the idea is to have it automatically build a bunch of "utility classes" based on what you think you'll need, but that means you'll inevitably end up with a bunch of unused CSS. So Tailwind necessitates other tools, like PurgeCSS, to get rid of those unused classes. I'm practically tearing my hair out trying to get these two things to work the way I want. Part of the process I suppose.

## Netlify CMS
When I first started, I figured I could maintain all of my content manually without having to deal with a CMS. However I reached a point where writing content in VSCode (or Typora) was getting kludgy. I looked into Sanity, a popular headless CMS, but it seems like overkill for what I'm trying to do: all of your content is stored as Portable Text, a proprietary format that can easily be exported to Markdown, HTML, React, whatever. This seems to make sense if you're writing content that will be consumed in different ways. I only need Markdown though, and to write in plain Markdown requires extra tooling in Sanity. Also, Sanity's gotten to be pretty big, so you need a monorepo with separate apps for Sanity Studio and the blog itself. Then you're looking at bringing in more tooling like Lerna or Turborepo. So I looked into alternatives.

Unlike Sanity, Netlify CMS (an OSS offshoot of Netlify) uses git to manage the publishing workflow, which I was already doing, albeit very manually. I prefer this approach. It has a much smaller footprint and seems way more intuitive. Best of all, it supports writing in Markdown out of the box with no additional configuration! Bravo, Netlify CMS team.