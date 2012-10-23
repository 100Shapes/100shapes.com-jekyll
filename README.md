100Shapes – We build apps
=========================


Hey, we're 100shapes. We build apps and websites. This is the conversion engine we're using to build our own site at [100shapes.com](www.100shapes.com).

First things first: we're not hosting the site with GitHub Pages. We'd like to, but we like being able to run custom plugins more. This repository holds our engine only – the thing that converts markdown to html.

The engine we're using is [`Jekyll`](https://github.com/mojombo/jekyll/) written in Ruby. We've choosen it because there's a massive community and it seems to just work.

Jekyll works by passing any markdown files within `posts/` through a series of templates to create a `site/` directory. `site/` is the directory that holds our site. Every time a new post is added, we need to regenerate it.

Getting set up
--------------

 In order to run it locally, you need to have Jekyll installed. It's a Ruby gem, so install it how you want. We recommend installing Ruby's `RVM` and `bundler` first so that you can have a gemset just for this site.

Once you're using your gemset, Install `bundler` so that it can manage your gems:

	gem install bundler

`bundler` is cool because it looks at at gems you've got listed in the `Gemfile` and installs them for you. Grab everything you need with:

	bundle install

You've now got everything you need, so run the site server:

	jekyll --server


Where are all the posts?
------------------------

Once you clone this repo, you'll notice it doesn't include `posts/`. That's because they live on our Google Drive in `blog/`. You need to symlink that directory here:

	cd :project_dir/
	ln -s :path/to/Google\ Drive/blog/ _posts

**Note:** Remember to escape the spaces.

When it works, you'll see `_posts/` and Jekyll can do its thing.


The Posts and the Media Problem
-------------------------------

So our blog has lots of media (it's image heavy). We can't put all this into the repo – we need to use an Amazon S3 account to host it instead.

Ideally, we'd like the have this structure:

	blog/
		:post_1_title/
			2012-10-20-:post-1-title.md
			dogs.jpg
			dogs_large.jpg
			script.js
			script.coffee

		:post_2_title/
			2012-10-20-:post-2-title.md
			cats.jpg
			script.js
			script.coffee
			cats_vid.m4a

The problem is that `blog/` is symlinked into the project as `_posts/` so that Jekyll can use it. However, Jekyll only converts files in `_posts` which have a filename like:

	2012-10-20-my-post-title.md

Everything else is ignored, even the directory structure. This is because it eventually builds the directory based on the categories you specify in the posts.

We have no way to tell Jekyll to copy everything over.


### Unsuccessful Things

- I created a `post_assets/` on our drive and tried symlinking it into `assets/` within the project root. Jekyll ignored it.
- I tried symlinking to `post_assets/` directly from the project root. Jekyll ignored it

It seems Jekyll ignores symlinks except when `posts/` is itself, a symlink.

### More Suggestions

- Abandon Jekyll and use Python's Pelican – it's less fussy about what it chooses to convert.

How do I write posts?
---------------------

Duplicate a post from `_posts/`, rename it, and edit. Posts are organised into directories in `site/` based on the categories you include in the post's Metadata.


How do I publish?
-----------------



Outstanding Tasks
-----------------

Stuff we still need to do:

- Responsive layouts
- Wire-up S3 account for assets
- Google Analytics
- Discuss comments Proof of Concept
- Share buttons
- Tag/Category pages
- Gravatar authors for profile pictures
- Wire-up DNS to point to s3 bucket

