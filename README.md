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


How do I write posts?
---------------------

Duplicate a post from `_posts/`, rename it, and edit. Posts are organised into directories in `site/` based on the categories you include in the post's Metadata.


How do I publish?
-----------------

Setup the s3 vars, then run `jekyll-s3`.


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

