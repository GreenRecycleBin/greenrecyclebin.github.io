---
layout: post
title: "Polaroid Camera with Famo.us"
description: "Polaroid Camera with Famo.us"
category: technology
tags: [famo.us, javascript, ui, framework, animation, polaroid-camera]
---
{% include JB/setup %}
I've been playing with the [Famo.us framework](https://famo.us/) lately. If you
haven't heard, Famo.us aims to help you develop modern, performant and complex
UIs for any screens.

[Famo.us University](https://famo.us/university) is the official place to learn
more about Famo.us. The website lets you live code in Famo.us without installing
anything. I've finished Famo.us 101 and 102 lessons and I am excited to start
new mini-lessons under the "Components" section.

The first project,
"[Polaroid Slideshow](https://famo.us/university/famous-101/slideshow)", helps
you architect and design a simple Famo.us app. After finishing it, you will have
a working polaroid camera app. Photos will be coming out of the camera, shaking
while being developed, before falling to the ground when touched.

I've also extended the project so that you can choose multiple photos or take
them if you use a mobile device. When the user chooses their photos, I need to
hide the old slideshow view, which contains all the slides/photos. However, it
is not possible to remove a surface from a context/container. This is because
the render tree is immutable and therefore does not support deletion. I ended up
following the approach described by
[DrClick's comment](https://github.com/Famous/core/issues/7#issuecomment-40530707)
on Famo.us' GitHub issues page. When I need to change the photos, I'll hide the
old slideshow view, and add the new slideshow view to the existing slideshow
container.

I've monitored the app performance using Chrome's task manager, alternating
between choosing new photos and taking them, and it doesn't exhibit any memory
leaks. Famo.us seems to be able to re-use the DOM elements and releases memory
previously held by views that are now hidden. If you have a better approach,
I'd be interested to hear your opinions.

You can play with the app [here](http://cdn.rawgit.com/GreenRecycleBin/polaroid-camera-with-famo.us/master/index.html).
I'd recommend using Chrome on iPad if you use a mobile device. The
[source code](https://github.com/GreenRecycleBin/polaroid-camera-with-famo.us)
is on GitHub. Hope you enjoy the app! Leave me a comment if you have any
questions.

**Suggested Reading**

[The Famo.us Render Tree](https://famo.us/guides/dev/render-tree.html)
