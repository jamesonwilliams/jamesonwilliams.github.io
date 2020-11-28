---
layout: post
title:  "Adventures Setting Up a Static Website on GitHub Pages"
date:   2020-11-27 21:56:21 -0600
categories: webdev
---

Well, I think it was about an hour or two ago when I was like:

> So you want a staticly hosted serverless website for free, huh?

(Joe Burns, my dudes?)

Anyway. Here we are. Look at us go. (Us = _The Royal We_ = me alone
slouched over on my laptop.)

As a banner-level point, this has been a remarkably simple experience.

I won't attempt to create a "tut" (tutorial) here, but IIRC, these were
some of the salient steps to it all:

### Create a repo for your site on GitHub.

My repo is named
[`jamesonwilliams.github.io`](https://github.com/jamesonwilliams/jamesonwilliams.github.io).
It lives in my personal GitHub account.

Next, you'll have to fiddle with its settings. You'll have to set the
Domain Name to your vanity domain, and then go futz about with your DNS
provider. This involves a few trips back forth. Run `dig` to check your
work.

Set the content directory to `"docs"`, and make `main` the default
branch, etc.

### Checkout your new repo, and install Jekyll into it

If you're like me, you don't know what Jekyll even _is_ at this point.
You also don't really know much about Ruby, Gemfiles, Bundler, or any of
that.

Well, it's pretty much just:
```bash
# Clone your repo
git clone git@github.com:jamesonwilliams/jamesonwilliams.github.io.git
cd jamesonwilliams

# Make a directory in which to install the docs site.
mkdir ./docs && cd ./docs

# Install Jekyll
jekyll new .
```

That's really about it. I saw a bunch of pages with lots of steps,
talking about installing different versions, futzing about with
Bundler, and all other kinds of noise. But I say unto ye: futz that
noise. At least for now.

You probably do want to check your work, though. Which is fairly easy to
do.

```bash
jekyll build
jekyll serve --watch
```

Note above that you have to "compile" your website each time. If you
have been running a dynamic webpage for a long time, like Wordpress on a
LAMP or something, this will be a mental shift for you.

The `serve` will make the content available via `http://127.0.0.1:4000`.

Anyway, once you're satisfied, just save the content and push it to your
repo. That's all. Then it will go live!

```bash
git add .
git commit -m "My initial Jekyll install."
git push origin --set-upstream main
```

### Cats of a Different Color

Well, when I had set out to write this blog earlier on, I'd promised not
to make a "tut." Indeed, I was just trying to get some technical content
in triple backticks so that I can checkout the formatting in a second.

Let's see how it looks, shall we, bruv? Oi.

Anyway. I do have some things I'll need to resolve, from here, I could:

1. I'm writing this in `vim`, and there's no spell check. It would be
   nice to be writing this in a WYSIWYG of some kind.

2. Eventually, I'll need to embed video, audio, images, etc. into these
   posts. I don't really want too many individual steps to that. I want
   to kind of drag and drop them and have them "do the right thing."
   I'll also need to setup content repository for my own stuff.

3. Theming. Arguably, was that the entire point of this? I want a
   dope-arsed theme.

4. Import legacy content from an old Wordpress blog? Yea, maybe.

5. Wire jamesonwilliams.com up. Ideally, it would work like a CNAME for
   nosemaj.org. GitHub refers to nosemaj.org as an "apex domain," since
   it doesn't have a host. It only supports a single apex domain though,
   and you're looking at it, baby.

I guess that's it for now. I'm going to post this, and see how it looks
rendered.
