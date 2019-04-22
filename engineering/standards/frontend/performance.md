---
description: Considerations on frontend performance.
---

# Performance

### Initial Render <a id="initial-render"></a>

The time till initial render is one of the most important performance measurements \(see more in [perceived performance](https://engineering.hmn.md/standards/frontend/best-practices/#perceived-performance)\). Initial render is the time between a user starting to load the page and the browser’s first draw.

Time to initial render can be reduced by avoiding unnecessary JavaScript libraries and reducing blocking assets in the HTML header.

### Creating a Performance Budget <a id="creating-a-performance-budget"></a>

Before spending time optimising a site’s performance, it’s useful to create a performance budget. A performance budget serves as a living marker to judge and test a website against.

Creating a performance budget involves taking a company’s user base, competitors, and KPIs and building out a matrix of metrics and measured pages that can be used for the duration of a project to ensure it is on track.

Each Performance budget will end up a little different, but generically the following steps will be involved:

* Find out the client’s key performance indicators and goals for the site
* Find, from the client’s analytics, what the most viewed pages on the site are
* Find, from the client’s analytics, what the most used and important devices and networks are
* Get the 3 most comparable competitors to test against
* Based on the above gathered information, determine what 3-5 metrics are worth tracking against the 3 top-visited types of pages, and what those metrics are on the 3 closest competitors.
* From this data, create the desired goals for the 3-5 metrics

The result of the above work can be used throughout a project \(and during the lifetime of a site\) as a measure to ensure that performance is where it should be.

#### Related Reading <a id="related-reading"></a>

* [Performance Budget Builder](http://bradfrost.com/blog/post/performance-budget-builder/)
* [How to Make a Performance Budget](http://v3.danielmall.com/articles/how-to-make-a-performance-budget/)

