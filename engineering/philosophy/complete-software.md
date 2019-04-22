---
description: 'Sometimes, software is just done.'
---

# Complete Software

With the plugins that we use across multiple projects and across timespans of more than a year, stability is more important than having the latest hotness. Stability gives us the confidence that things won’t break, and new things won’t suddenly appear.

Because this software is in use on real-world production sites \(either client sites or internally\), we can ensure stability. Any changes made will need to work with our existing setups. It also means we’re always watching for bugs that appear as part of our normal monitoring.

A low-level plugin like S3 Uploads is a great example of this philosophy: you expect the plugin to store uploaded files on S3, and **nothing else**. Additional functionality can easily be handled by new plugins, so there is no reason to add features to the main plugin. We don’t need UI for managing S3 settings, so adding it makes no sense for us. Because of this, it will never compete with a all-in-one solution like [WP Offload S3](https://deliciousbrains.com/wp-offload-s3/), and _that is OK_. Because we’re using it on every site we host, we can be pretty certain that there are no major bugs or edge-cases in it.

This stance may be confusing to some users. Maybe they want to use a plugin we develop, but it’s missing one tiny feature that they need. Unless this use case is crucial to our own needs as well, it’s unlikely we’d include this in the plugin. Instead, an ecosystem of extensions on top of the software should be encouraged instead. Generally speaking, making plugins more pluggable is a good idea. If others run into bugs, these should be fixed where possible. Rearchitecturing the software to fix an edge case is usually not a good idea though.

At first, these plugins may appear to be unmaintained. Seeing that a repository hasn’t had changes in the past year isn’t usually regarded as a good sign in open source. However, this is exactly what we’re striving to achieve with completion.

### Why not simply accept new features? <a id="why-not-simply-accept-new-features"></a>

Accepting PRs and adding new features isn’t free. Each new feature requires someone to maintain it and ensure it works correctly with other features when those are added. For code supplied by others, this also requires learning the code to ensure it does what it says on the box, and getting it up to the same quality as the rest of the plugin. In addition, every feature requires documentation and support resources, which are definitely not free.

New features are typically better handled in separate plugins which can be enabled as needed and follow their own updating process.

### What’s the alternative? <a id="whats-the-alternative"></a>

We can’t possibly write code to handle every potential use case, so instead we should encourage a large ecosystem around our plugins. To enable plugins to work coherently, we need to make sure they’re as extensible as WordPress core itself. In addition, we should have a resources page that lists other available plugins, and promotes them as much as possible.

