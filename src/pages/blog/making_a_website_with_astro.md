---
layout: '../../layouts/MarkdownBlogPostLayout.astro'
title: 'Making my personal site with Astro'
author: 'kobijet'
desc: 'How I made my portfolio and blog website using Astro, the problems I faced, and the things I learned.'
pubDate: 12-27-2024
longDate: 'December 2024'
platforms: ["desktop", "mobile"]
tags: ["web", "astro", "node", "html", "css"]
---

Howdy!

Welcome to my journey building the beautiful site you're using today! I appreciate you taking the time to check it out.

## A bit of a background...

Although my background is in game design, my path didn't begin there. When I started school, I had my heart set on being a web designer. Eventually also a cybersecurity analyst, and at another point a network administrator. Then finally, game designer. I have always admired the beautiful websites people create and loved the countless tools and utilities people build as web apps. Games, tools, and content are all on the table. The possibilities are truly limitless!

That leads us to today. I am in a position where I am looking to expand my online presence, professionally speaking, and I figured the best place to start is with my personal landing page: my website.

## The research process

Before thinking about code, or even touching Miro, I spent plenty of time browsing through other portfolio and blog websites for inspiration. I found this handy list compiled by emmabostian on GitHub with plenty of software developer and designer portfolios for artistically emulating.

[emmabostian's list on GitHub](https://github.com/emmabostian/developer-portfolios)

A few pages I noted:
- __omargpax__: bento style design with engaging mechanics
- __nev flynn__: beautiful tile design with smooth animations and good colors
- __dean tate__: seo legend, simple but powerful website

Looking at this list, it reinforced for me that having a good website is a balance of art and science--very much like video games. 

## The tenants of a good portfolio

You need the right amount of creativity so as to make your website interesting enough, yet also enough knowledge to know what people do, what works, and what tools to use. Luckily, my diverse background in school and my commitment to being chronically-digital makes pretty easy work of this.

All these websites share some things in common:  
- Information is quick to read
- Websites should be beautiful to look at
- Portfolios should be high-speed

To make sure that people can find me, I am also making it a goal to optimize my website for search engines. On top of single-page apps being slow, they also don't provide amazing SEO since most of the content is dynamically rendered. It doesn't leave web crawlers much data to use to rank you in the search results.

Finding the tools went quick. I have always used React in the past for my front-end and something like Express to route pages, but I've been seeing one framework in particular crop up in various places. I've lived single-page application land for far too long, and so I decided it time to dive into the multi-page app world of Astro.

## Astro's Advantages

Astro works by pre-rendering content and serving static files, and only dynamically rendering components or pages when you specify them as server or client-rendered.

Astro uses a unique architecture, something they call "islands." An island is a component that needs to be hydrated apart from the rest of the page. It can either be client-side for adding interactivity to the UI or server-side for dynamically changing content separate from the rest of the page. This is cool because you needn't worry you're wasting time rendering components/content you shouldn't be, and instead only handle the stuff that you explicity deem to have interactivity or dynamic content.

One of the other patterns that I appreciate is the way you can use markdown files to write content, then display it using reusable templates. Similar to how React-Router has the <outlet> element to render content within other pages or components, you simply use the aptly named <slot> component in Astro. Once you have your layouts and content written up, you can use Astro's API to do some super-cool stuff really quick, like render a dynamic list of all the posts containing certain tags or create an RSS feed for your viewers to subscribe to. 

When you're all finished, Astro builds your source code into static pages that can then be served, fast and easy.

### Lighthouse
Oh, Lighhouse. The bane of every developer's existence... Never able to achieve those perf-

Well would you look at that...

<img src="/kobijet-org_lighthouse.png" alt="Perfect 100's across all categories for this website on PageSpeed Insights" />

Astro is out here killing it! And without hardly a headache on my end.

### Largest Contentful Paint
Largest Contentful Paint is 0.4s on desktop and 2.1s on mobile. Google recommends that websites should strive for 2.5s or less. According to [this data from the Astro dev team](https://astro.build/blog/2023-web-framework-performance-report/) (I know, it's Astro... but they're all I could find), ~73% of the Astro websites they checked passed this metric, compared to other popular frameworks like Next.js, Svelte, and Remix, all falling below the 55% mark.

### Cumulative Layout Shift
The worst category is Cumulative Layout Shift with a 0.12 on mobile devices; I'll accept 0.018 on desktop, I suppose... From [the same Astro post](https://astro.build/blog/2023-web-framework-performance-report/) we're able to see that Astro's websites passed nearly 85% of the time, compared to the next highest being Remix or Svelte 10 points lower.

The reason for this would be I use a column layout on mobile devices, therefore if my picture on the homepage takes any extra time to load, it will cause a shift in the layout. I'm sure if I used Astro's \<Image> or \<Picture> components instead of regular old \<img> tags, that would save the time. I didn't know these components existed when I set off on this project, but I will definitely refactor the source to optimize speed.

## Conclusion

For content-focused websites, there's no competition to Astro. In testing, and thus far in deployment, Astro has been amazing. I am confident that the sky's the limit when it comes to this framework. It's lightweight, and since many content-focused sites contain mostly static data anyway, it's inherently quick. By being able to leverage reusable HTML/CSS layouts with markdown storing the content, and use components that can either be server-rendered or client-rendered upon specification, powerful content-driven experiences can be created quickly. 

I mean, take this website for example. I created it in a day, having never made an Astro project before, and it's received almost all 100's on PageSpeed. None of my Next/React projects even comes close. On top of that, I don't even think I'm fully utilizing all the features has, as the afforementioned <Image> and <Picture> tags. Astro allows you to make API endpoints as well, though I need to read into this more, so I believe the possibility of full apps with Astro is completely possible.