
---
date: 2024-03-20
og: /img/nue-css-og.png
include: [ext/glow]
title: Nue CSS (preview)
desc: Nue brings a scaleable alternative to Tailwind, BEM, and CSS-in-JS
thumb: glow-thumb.jpg
---

# *__Nue CSS__ preview* A scaleable alternative to Tailwind, BEM, and CSS-in-JS [headline]

[author]

Here's a preview of Nue's approach to styling things on the web. The key difference to existing systems are *minimalism*, and extreme *re-usability*. The difference can be huge: you can build an entire website with the same amount of CSS that goes into a single *Tailwind* button. Or even crazier: three websites with a single *Tailwind Catalyst* button.

[image.big-scaled]
  small: /img/nue-css-hero.webp
  large: /img/nue-css-hero-big.webp
  size: 720 × 451

To understand what's happening here, we need to step back and look closer at what has happened to CSS in the past few years:


### *BEM:* Finding order to chaos
CSS is notoriously hard to manage. It takes years to get a hold of it. Between 2008 and 2014 there were several attempts to bring order: *OOCSS*, *BEM*, and *SMACSS*.

However, these systems failed due to their size and verbosity. Developers lost interest in naming patterns like `block-name__elem-name_mod-name_mod-val` or the 600 different class names introduced by Bootstrap, which was based on SMACSS.

[image.scaled "/img/css-history.png" size="720 × 83"]


### *CSS-in-JS:* Clean global namespace
In 2014, *Christopher Chedeau* from *Facebook* gave birth to the CSS-in-JS movement. The main idea was to get rid of global namespace pollution. He showcased Bootstrap as the key example of a bad design.

It was a huge success and developers started converting their CSS to JavaScript. We saw a flood of new CSS frameworks like [Vanilla Extract](//vanilla-extract.style/), [Styled JSX](//github.com/vercel/styled-jsx), and [Emotion](//emotion.sh)


### *Tailwind:* Inline styling
In 2017, *Adam Wathan* introduced [Tailwind](//tailwindcss.com/) — a new kind of CSS framework with a special styling language. The idea was to inline all styling inside a class attribute so that everything could be expressed with HTML only.

Developers loved it: it was an easy way to build good-looking user interfaces with a copy/paste mentality. Backend developers and junior frontend developers were able to build things without understanding how CSS cascade or specificity works.


## The tradeoffs
For the most part, CSS-in-JS and Tailwind worked nicely and frontend engineers were pleased. But it was far from roses.


### Massive codebases
We're not talking about "slightly more", or "just double the size". We're talking about a situation where a single button has more CSS than a complete, professionally designed website. And the codebases just keep on growing due to [the false beliefs](/blog/tailwind-misinformation-engine/) on how CSS works.

Large codebases can draw you down: small styling changes trigger large compilation chains, potentially involving hundreds of JavaScript files and NPM modules before the browser is hot-reloaded. What should take milliseconds, is suddenly taking seconds.


### Technical debt [debt]
Things work well if you can just copy/paste components and tweak settings, but it gets wild pretty easily. You end up with a codebase that only specialists can understand:

[image "/img/inline-styling.png" width="450"]
  caption: This sort of code is guaranteed technical debt.
  size: 450 × 460



### Single point of responsibility [blocker]
Today, JavaScript/React developers are responsible for everything. The components are modern-day "kitchen sinks" where content, layout, styling, and business logic are stuffed together.

Things that used to be separate, are now under the responsibility of a JavaScript developer. It's hard or impossible for content creators, designers, and CSS developers to participate.

The talent is inefficiently spread when React developers work on issues outside of their interests. Engineers are not necessarily the best designers and many of them *hate* CSS.

Your team could do so much better.




## What if...
What if we could break away from all these tradeoffs?

Start building websites that look perfect inside out. Where your codebase is ten times smaller and is made out of clean, simple components.

What if we get all the benefits of CSS-in-JS, but none of the problems? No trouble of naming things, nor worrying about cluttering the global namespace.

What if we could offload the burden from JavaScript developers and hand all design/UX work to people who are the absolute masters of that craft?

What would _that_ look like?



## 1. Cascading CSS architecture
Nue offers a more maintainable and scaleable alternative to Tailwind, BEM, and CSS-in-JS. It's a new way to *write and structure your CSS*. Here are the key differences:


### Your design is based on a design system [architecture]
Every Nue project starts with a design system. It's your "single source of truth":

[image.tall]
  small: /img/abstract-design-system.png
  large: /img/abstract-design-system-big.png
  size: 600 × 410

Design system is really a simple concept: you define the master look and feel in a central location and let all your pages inherit from that. Ideally, your design is just a single self-documenting CSS file that even non-technical people can understand. Here are three examples:


[site-list]

Nue makes sure your design is consistently applied across all the pages and components on your website. It automatically binds the correct CSS files to your pages depending on where the page resides. There is no need to tinker with path names with JS/CSS import statements.

[image.tall]
  small: /img/css-architecture.png
  large: /img/css-architecture-big.png
  size: 720 × 556



The design is fully separated from the HTML structure so that the system can be fully controlled by designers and UX developers. This way, non-technical people can create content so that the pages automatically inherit the correct design. And there is no way they can break the design system with local or inline styling.


## 2. A new, minimalistic way to write vanilla CSS [minimalism]
The key idea to leave out all class names that relate to styling and let external CSS take care of the element and/or component look and feel:

```
<!-- component name is all naming you need -->
<div class="gallery">
  <figure>
  <figure>
  <figure>
  ...
</div>
```

Naming things and minimalism go hand-in-hand. The more names you have, the more complex your design system API. In most cases, the component name is all the naming you need.

Simple means lean and well-organized CSS that is easy to maintain and scale. There's less room for errors: no global namespace issues, no local breaking points, and no consistency issues.

[.hero-quote]
  > “Less, but better”

  — **Dieter Rams** • The grandfather to Apple's design


The simpler you design the system, the better. The fewer colors, font weights, elements, components, and variants you have, the better.



## 3. No CSS-in-JS layer needed
When everything is based on a single source of truth, it's trivial to ditch the redundant CSS-in-JS layer in front of your design system, be it Tailwind, *CSS Modules*, or Vanilla Extract. This makes a simpler stack:

[table.small "| CSS-in-JS | Tailwind | Nue"]
  - - Key idea
    - Local scoping
    - Utility classes
    - Design system

  - - Styling with
    - JavaScript
    - JavaScript
    - CSS

  - - Conflict resolution
    - Class name obfuscation
    - Domain-specific language
    - Single source of truth

  - - Optimization
    - Tree-shaking + Bundling
    - One large CSS bundle
    - Minimalism + Code splitting + Page inlining


Done. Now let's see the benefits:


## Reach new levels of simplicity [size-graphs]
Sites made with Nue have extremely little CSS. For example, a basic Tailwind button has more styling than a complete Nue-powered website:

[size-compare a="sha" b="aimee-app"]


### It's easy to maintain
The combined amount of CSS in three Nue websites equals the size of a single Tailwind Catalyst button:

[size-compare a="catalyst" b="all"]



### Keep things in control
Design-system-powered websites stay lean as the site grows:

[size-compare a="dialog" b="mona-editor"]


[.hero-quote]
  > One line of CSS is easier to maintain than a hundred lines.

  — **Nue Best Practice**

Talk about maintainable CSS!



## Create motherfu!!ng fast websites
[motherfuckingwebsite.com](//motherfuckingwebsite.com/) is a developer meme from *Barry Smith* to demonstrate the power of minimalism. It's a text-only website that does not use CSS at all. Needless to say: it's motherfucking fast:

[image.tall]
  small: /img/mf-perf.png
  large: /img/mf-perf-big.png
  href: //pagespeed.web.dev/analysis/https-motherfuckingwebsite-com/jjbk58sczm
  caption: Click image for details
  width: 650

A surprising fact is that minimal, inlined CSS gets you to the same performance levels with _zero compromises on design_:


[image.tall]
  small: /img/nue-css-perf.png
  large: /img/nue-css-perf-big.png
  href: //pagespeed.web.dev/analysis/https-aimee-app-nuejs-org/qllf5ab934
  caption: Click image for details
  width: 650

No matter what sort of Turbo-Infuced-Rust-Bundler &trade; you use to optimize the irrelevant, nothing beats a tiny TCP packet that has everything to render the landing page.

Talk about performance!



## Scale like the best
Nue breaks you out from the [single point of responsibility](#blocker) and offloads the burden from the JavaScript/React engineer for the more talented:

[image.tall "/img/without-js-bottleneck.svg"]
  width: 600


Separation of concerns equals scalability: marketers and technical writers proceed with content, designers and UX developers focus on the user experience, and JavaScript developers perfect the [back of the frontend](//bradfrost.com/blog/post/front-of-the-front-end-and-back-of-the-front-end-web-development/). The same applies for one person projects too — all the UX talent just comes from one head.

Talk about scalability!



## Stand the test of time
CSS is the styling language of The Web

[image "/img/standard-styling.png" width="500"]

Any developer with a background in CSS can maintain the codebase. And when you come back later, even years later, the codebase is still sound and clear. There is no fear of [technical debt](#debt) because the CSS you write today is valid forever.

Talk about timeless web design!



## We're building the web framework of the future
Nue is a framework for future generations, who demand more from their development stack. Nue CSS was an important step towards our ultimate goal [the perfect web framework](/blog/perfect-web-framework/):


[nue-roadmap]


### *Stay tuned:* Nue Design System
Our next release is an actual design system: the kind of stuff that is currently employed in large, design-focused companies only, but we'll make it available for everyone. I'm hoping to get a chance to talk with *Brad Frost* and get involved in the development of a [global design system](//bradfrost.com/blog/post/a-global-design-system/). It's important. It's the next big thing in CSS development:

[image "/img/css-future.png" width="650"]



### *Then:* Templates
Think complete website templates with marketing, documentation, registration, e-commerce, and blogging areas. Or copy/pasteable components ala Shadcn and Tailwind, with a ten times smaller codebase and seamless integration to your design system.

Become the next *Stripe*, *Linear*, or *Apple* — with the speed levels of a mother-effing website.

These perfected templates will likely have a one-shot price tag because we want to secure the development of Nue for years to come without depending on 3rd party demands.


### Join our mailing list
Receive an email when the next milestone is ready. And give us your thoughts! I read them all with care and I answer all questions.

<br>

[join-list]


## Get started with Nue
Experience the power of Nue hot-reloading and modern CSS:

``` sh
# Install Bun (if not done yet)
curl -fsSL https://bun.sh/install | bash

# Install Nue
bun install nuekit --global

# Start with a template
bun create nue@latest
```

Choose *Aimee website template, Sofa Company website*,  or *Mona Editor website* from the list — ie. one of the first three options:

[image]
  small: /img/create-nue.png
  large: /img/create-nue-big.png
  width: 550

Enjoy!
