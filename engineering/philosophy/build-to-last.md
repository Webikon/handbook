---
description: Projects need to be built to last so they can be maintained for years to come.
---

# Build to last

### Documentation <a id="documentation"></a>

Documentation should be scattered liberally amongst the code, as well as extra documentation in documents. This is something that benefits both short and long projects.

Long-running \(multi-year\) projects need to be maintainable for a long time, and may cycle through different developers on the same pieces of code over time. The nature of this means that documentation ends up saving both you and everyone else time, as future developers don’t need to follow up with the original author of the code.

However, even shorter projects need documentation. For new developers on a project, a getting started guide can be crucial, and helps the project be adaptable as requirements or timelines change. These projects also tend to have more people working on them at once, so documentation can be critical to collaboration. Time constraints make it even more important to avoid unnecessary back-and-forth over code, especially with colleagues working across timezones.

Short projects might also turn into long-running projects; follow-up work might appear after shipping the initial build of a site, and we need to pick up the project again. Documentation ensures we can pick up where we left off easily.

### Over- and under-engineering <a id="over-and-under-engineering"></a>

As engineers, we look at a lot of things and immediately see the problems with them. We also have a tendency to see problems that don’t exist to anyone else. Overengineering is a common time sink on all types of projects, and it’s important to always be mindful of this.

Short projects can be under heavy time constraints. While we don’t believe in pumping out sites as fast as possible, we don’t want to take forever to deliver on projects. It’s up to us to make the call as to whether we need to spend a day rewriting a system, or do the simplest thing that works. Time constraints help here, as they can force you into doing minimal work, but should never mean that you skip spending time on those parts that are worth it.

Long-running projects can suffer from overengineering, as a result of spending so much time on a single project. Often, we’ll look at code and want to rewrite it from scratch because we know the hacks that got it running in the first place. There’s also an element of not-invented-here syndrome. Focusing on shipping is important to not lose sight of the goal, especially when you can simply bump the issue to the future and reconsider it then.

It’s up to engineers to decide how much time a problem is worth. Good design now might save you countless hours down the road, but the code might also be ripped out tomorrow as requirements change. Use your time judiciously.

Don’t be afraid to pull out the string and glue to hold a project together. It’s possible that today’s solution won’t scale up in 6 months, but if you need to launch the site tomorrow, your time is better spent fixing the bugs than scaling for users that don’t yet exist. Don’t overengineer it.

