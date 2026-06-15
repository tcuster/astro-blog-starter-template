---
title: "A Decent Laid Plan"
description: "Think before acting. Art: Lion Clan Samurai Tactician Akodo Dagurasu by John Donahue"
pubDate: "June 15 2026"
heroImage: "/Akodo_Dagurasu_by_John_Donahue.jpg"
---

## Yes, after I began, I made plans  
### So, showing up, like I did when I "started"  
That's what it's like in life. Whether doing a project, beginning a journey, or lifting weights, gotta do the bare minimum before we can do more.  

But surely you read my last blog...  

## Proof of concept
### Here it is not yet existing; directory structure  

```text
my-ssg/
├── main.go
│   ├── content/
│   │   │── index.md  
│   │   │── about.md  
│   ├── layouts/
│   │   │── page.html  
│   ├── public/
```

## Let me interject
### I'mma let ya finish
But I am not to quick to lock in my decisions iwthout reviewing the idea with a bit of scrutiny and criticism. Not too strict/rigid.

1. The main.go code will read what, when a,d where we tell it to. (in my vision) We use constants to hold the --locations-- details
2. The definisions of the constants belong in a --museum-- config file (more work;blogus interruptis: I'll do this after MVP is working)
3. LKGC aka Last known good config. (BI: again, something that can just wait until later, but I'm glad I wrote it down)
4. (BI)My notes get a bit off track. Basically, there can be a test/check to make sure the active config fulfills the schema requirements before build.

## Minimal feature set
### Breaking down the flow
Again, just planning a low-detail executable logical list of tasks that match the pattern for the desired project results

1. Read: Scan `content`  directory for .md files
2. Parse: Separate the metadata (Frontmatter) from the body text.
3. Convert: the Markdown body into HTML
4. Inject: send HTML and metadata into the HTML template from `layouts/`
5. Write: Save the final product as an `.html` file inside `public/` 

## That last one is a process
### I dove into it to get more
Info started sparking questions on

* how to do the write well and proper  
* how the metadata works  

## I continued to the next page of my notes
### Mostly samples of code/script
There seemed to be a reasonable value of exploring both ideas of the paper.
I wound up discovering the file overwrite convention that seems best practice.
Amazing how effective research can be.  
It's just make a tmp, test it, rename it at the OS level with code.  
The overwrite is lightning fast and super clean.  
  
The part that really tickled my brain was that when I went to look at the metadata schema it was fully written in TypeScript
People don't know yet, but my introduction to GoLang was taking a course on Data Structures and Algorithms.
The course, the in-class work, and the tests that made sure the work was correct were all only in TypeScript.

Not only did I have zero experience in GoLang, I had zero experience in TypeScript. Absolutely zero in both.
So, now, for this project I'm absolutely going to be taking typescript from this blog tool and rewriting it in Go. 
It is such a fun and wondnerful experience to learn.  
  
## Please, plan before you act and keep it simple, and 
### stay excited to make mistakes and learn in ways you never knew possible!

##### Shine on you crazy dogstars,
*Thomas Custer*  
  
P.S.  
Frontmatter example:  
```
---
title: "The True Start"
description: "Duck around and find out"
pubDate: "June 09 2026"
heroImage: "/rubber-ducky.jpg"
---
```

TypeScript Frongmatter Schema used on my blog posts:  
```
schema: z.object({
    title:z.string(),
    description: z.string(),
    pubDate: z.coerce.date(),
    updateDate: z.coerce.date().optional(),
    heroImages:zstring().optional()
})
```