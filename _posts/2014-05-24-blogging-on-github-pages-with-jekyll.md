---
layout: post
title: "Blogging on GitHub Pages with Jekyll"
description: "Blogging on GitHub Pages with Jekyll"
category: technology
tags: [github, github-pages, jekyll, jekyll-bootstrap, tutorial]
---
{% include JB/setup %}
In this blog post, I'm going to guide you through the process of setting up your
blog on [GitHub](https://github.com). We'll be using
[GitHub Pages](https://pages.github.com/) and [Jekyll](http://jekyllrb.com/).
Using these two tools, you can blog using
[Markdown](http://daringfireball.net/projects/markdown), manage your blog with
[git](http://git-scm.com/) and not worry about databases and hosting.

**Step 1: Setting up a repository for your blog on GitHub**

If you don't have a GitHub account yet, sign up [here](https://github.com/join).
Then, follow the steps described at [GitHub Pages](https://pages.github.com/).
Make sure your repository name is **&lt;username>.github.io**; otherwise it
won't work.

**Step 2: Writing your first blog post**

Firstly, clone the repository that you created in step 1.

    $ git clone https://github.com/<username>/<username>.github.io

Secondly, say hello to the world.

    $ echo 'Hello, world!' > index.html

Lastly, add, commit and push to GitHub to make it live.

    $ git add --all .
    $ git commit -m 'Initial commit'
    $ git push

GitHub Pages will take a couple of minutes to get around to serving your blog.
Subsequently, changes will be live pretty much instantly.

**Step 3: Setting up Jekyll on your local machine**

Jekyll is an active open-source project, and is updated frequently. Thus, it is
a good idea to use Jekyll to preview your blog locally before pushing it to
GitHub. We'll use the [github-pages gem](https://rubygems.org/gems/github-pages)
to bootstrap the GitHub Pages Jekyll environment locally.

    $ echo "source 'https://rubygems.org'\n\ngem 'github-pages'" > Gemfile
    $ echo '_site/' > .gitignore # Skip this if you want Jekyll Bootstrap
    $ bundle install
    $ git add --all .
    $ git commit -m 'Add github-pages gem'

You can then run `jekyll serve` to start up Jekyll locally. To learn more about
*Jekyll*, run `jekyll -h` or consult
[Jekyll's documentation](http://jekyllrb.com/docs/home/).

To make sure your blog looks the same locally and on GitHub Pages, remember to
update the *github-pages* gem and preview your blog before you push to GitHub.

    $ bundle update github-pages

**Step 4: Setting up Jekyll Bootstrap**

A blog usually need more than just plain HTML. You want to tag,
archive, and organize your blog posts. Furthermore, you want to engage
with your blog's readers by making it easy for every one to have online
discussions by commenting on your blog posts. Last but not least, you want to
make your blog posts standout through appropriate theme usage.
[Jekyll Bootstrap](http://jekyllbootstrap.com/) gives you a complete blog
scaffold with the above features built-in.

    $ git pull https://github.com/plusjade/jekyll-bootstrap/
    $ git add --all .
    $ git rm index.html
    $ git commit -m 'Use Jekyll Bootstrap'

Don't forget to customize your Jekyll Bootstrap setup and push to GitHub when
you're done. To learn mode about *Jekyll Bootstrap*, consult
[the documentation](http://jekyllbootstrap.com/usage/jekyll-quick-start.html).
Definitely check out the
[How Jekyll Works](http://jekyllbootstrap.com/lessons/jekyll-introduction.html)
section for a high-level overview on Jekyll's core concepts.

**Conclusion**

You should have a blog running on GitHub by now. I hope that this blog post has
been helpful. If you have any questions, please leave a comment. Happy blogging!
