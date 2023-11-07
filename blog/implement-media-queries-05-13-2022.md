---
title: "Implementing media queries in my site"
date: 2022-05-13T12:44:22-07:00
draft: false
tags:
  - css
  - how-to
categories:
  - articles

---

_NOTE I have removed the feature from my site since I wrote this._

## Why I am writing this

I see a lot of sites, mine included, that dont look very good on small screens, while many people view them on mobile devices. I thought I would pitch in and move the needle on making the web better looking.

## 1. Assessing what is going on with my site currently

I recently added `list-tags` feature to my list pages.

This allows each each page entry in the list to show its tags, allowing someone to click on a tag, taking them to that taxonomy page. This allowing them to discover any related information based on tags I add in the frontmatter of the page.

The issue came up when I looked at my site on my phone.

![Imgur](https://i.imgur.com/GUJEd1al.jpg "Here is a screenshot of my site on my phone in portrait mode. Note the big column of text the tag becomes at a small screen size")

Up till now I hadnt been worrying too much about the mobile view, but I wanted to understand **media queries** better, so as to create a better user experience on devices other than my computer. I have, as yet, not made the site public so it has not been much of an issue, but in wanting to have more work out in the world, I decided it should.

## So, what are media queries?

Media queries allow you to change the styling, and in some cases, manipulate the dom based on how things like

- how big your screen is
- whether you are looking at on a screen or printing it out.

### mobile first development

The gist of this is to have the **default styling be based on the smallest mobile device**, and add media queries as you get larger.

I found a simple structure for doing "mobile first" development

Practically speaking, this means you have your default be based on the smallest screen size.

As it is best to **adhere to a ubiquitous standard** if you can. The ubuiquitous standard in thas case is bootstrap 4's media queries.

**tldr;**

- use `@media (min-width:...)` as opposed to `@media (max-width:...)`
<details>
  <summary> ASIDE: where I make my Hugo dev server available on my network </summary>

I then got my dev site available on my phone. I know it is easy enough to do with the browser, but I like seeing it update on both

I use Hugo, a static site generator. I used this command to show it on my phone while I test

```

hugo server --disableFastRender --buildDrafts --port 1314 --cleanDestinationDir --bind 0.0.0.0 --baseURL http://hostname

```

</details>

## 2. add the media queries to my css

I got the code below from the  [getbootstrap responsive breakpoints section](https://getbootstrap.com/docs/4.0/layout/overview/#responsive-breakpoints)

```css
// Extra small devices (portrait phones, less than 576px)
// No media query since this is the default in Bootstrap

// Small devices (landscape phones, 576px and up)
@media (min-width: 576px) {
  ...;
}

// Medium devices (tablets, 768px and up)
@media (min-width: 768px) {
  ...;
}

// Large devices (desktops, 992px and up)
@media (min-width: 992px) {
  ...;
}

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px) {
  ...;
}
```

## 3. Hide link tags at smallest size change the flex direction to row

This demonstrates using `flex-direction` to change from row to column

![after changing flex direction](https://i.imgur.com/XA0Ib3xl.png "now the rows become columns, and more readable")

Which in this case means to hide them by default and set visible via media query when it is larger
![descriptions](https://i.imgur.com/LNOHDrP.gif)

Remember the default is `display: none;` and the `display: flex;` is at the chosen media query breakpoint.

```css
.list-tags {
  display: none;
}

... @media (min-width: 576px) {
  .list-tags {
    flex-direction: column;
    display: flex;
  }
}

/* // Medium devices (tablets, 768px and up) */
@media (min-width: 768px) {
  .list-tags {
    flex-direction: row;
  }
}
```

What this does:

- at the smallest screen, the tags are not visible
- at the next size up they are visible and stacked in columns for better readability
- at the medium size (and up) they are now in rows

<figure>
<video controls width="720px">
    <source src="https://storage.googleapis.com/mwcw-blog-images/implement-media-queries-breaks.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
</figure>

## Conclusion

Having  spent most of my time on the backend, I wanted to learn a little more about media queries while implementing this little feature. I hope it helps make it easier to understand why and how to do it yourself.

At this point I will leave it up to a future aesthetic decision about how to change it. If you have any feedback feel free to click the `suggest changes` link above.
