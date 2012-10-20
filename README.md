# Welcome…

Hi, we're 100shapes. We build apps and websites.

## How do I write posts?

They are two ways:

- using a shell
- copying a file

If you're ok with the shell, run:

	rake post title="test post" date="2012-10-20"

Otherwise, duplicate a post from `_posts/` and edit it. 

## Local Development

This site is built using Jekyll and hosted on github. In order to run it locally, you need to have `jekyll` installed. It's a Ruby gem, so install it how you want. We recommend installing `RVM` and `bundler`, that way you can have a gemset just for this site.

Once you're using your gemset, Install `bundler` so that if can manage you gems:

  gem install bundler

When you've got `bundler`, install all the gems you need with

	bundle install

You've now got everything you need, so run the site with an autoreloading server:

  jekyll --server


## Outstanding Tasks

Stuff we still need to do:

- Responsive layouts
- Wire-up S3 account for assets
- Google Analytics
- Discuss comments Proof of Concept
- Share buttons
- RSS/Atom feeds
- Tag/Category pages
- Gravatar authors for profile pictures
- Wire-up DNS to point to 100shapes.github.com


# Usage

For all usage and documentation please see: <http://jekyllbootstrap.com>

## Version

0.2.13 - stable and versioned using [semantic versioning](http://semver.org/).

## Contributing 

This repository tracks 2 projects:

- **Jekyll-Bootstrap Framework.**  
  The framework for which users should clone and build their blog on top of is available in the master branch.
  
  To contribute to the framework please make sure to checkout your branch based on `jb-development`!!
  This is very important as it allows me to accept your pull request without having to publish a public version release.
  
  Small, atomic Features, bugs, etc.   
  Use the `jb-development` branch but note it will likely change fast as pull requests are accepted.   
  Please rebase as often as possible when working.   
  Work on small, atomic features/bugs to avoid upstream commits affecting/breaking your development work.
  
  For Big Features or major API extensions/edits:   
  This is the one case where I'll accept pull-requests based off the master branch.
  This allows you to work in isolation but it means I'll have to manually merge your work into the next public release.
  Translation : it might take a bit longer so please be patient! (but sincerely thank you).
 
- **Jekyll-Bootstrap Documentation Website.**    
  The documentation website at <http://jekyllbootstrap.com> is maintained in the gh-pages branch.
  Please fork and contribute documentation additions to this branch only.

The master and gh-pages branch do not share the same ancestry. Please treat them as completely separate git repositories!


## License

[Creative Commons](http://creativecommons.org/licenses/by-nc-sa/3.0/)
