# Microbiome Green Revolution Website

This repository hosts the source code for the new website of the Microbiome Green Revolution (https://microbiomerevolution.org/). The website was developed using the style.scss template from the Yale DHLab website, with extensive modifications to its layout and structure.

## Developing

First download the application source:

```
git clone https://github.com/Microbiome-Revolution/Microbiome-Revolution.github.io
cd Microbiome-Revolution.github.io
```

### Mac Users
Follow [these instructions](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/#start-here-if-you-choose-the-long-and-manual-route) to ensure modern, non-System ruby on recent versions of OS X, especially on Apple Silicon (M1 chips).

Pay special attention to the section where you [detect, and if neccessary remove](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/#start-here-if-you-choose-the-long-and-manual-route), previous ruby virtual environments such as rvm, rbenv, and asdf.

Then:
```
brew install chruby ruby-install
ruby-install ruby-2.7.2
echo ". /usr/local/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo ". /usr/local/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-2.7.2" >> ~/.zshrc
```
Important: close and reopen the Terminal.app (all windows, not just your current one).
Verify you're on the right version of Ruby:
```
ruby -v
```
Then install the Ruby dependencies:

```
bundle install
```
On the Mac, use homebrew to install Node:
```
brew install node
```
Then install yarn and install the JavaScript dependencies:

```
npm install -g yarn
yarn install
```

Finally, you can start the development server by running:

```
bundle exec jekyll serve --incremental
```

## Additions
Please familiarise yourself with the css elements in the ["assets/css/style.scss"](assets/css/style.scss) file prior to making any changes or additions to the website. There are many elements that can be used included in the file, further than just those used in the website's current state. 

### New pages

To make an additional page on the website, you must make an html file in the main directory of the repository. We will use the ```about.html``` as an example, because of the existing changes that you can reference when adding your own page to the website!

If you are looking at keeping the same format as the existing pages, the dockstring at the top of your new page should look like this (e.g "About" page): 

```
---
title: About
layout: default
class: about-page
order: <numeric value>
caption:
---
```

The ```class``` and ```layout``` should remain the same if you want a consistent style across the website. Despite their naming including "about", they define how features should be displayed on any page that uses them, not just the "About" page. Only change this if you add a new class or layout for your page. The ```order``` feature defines the order in which the pages will be displayed in the header - this will need adjustment across all compiled pages if adding a page in between the existing ones.



### New Team Members

To add new team members to "The Team" page, you must have a square photograph of them placed in the ["assets/images/team"](assets/images/team) directory labeled as ```<firstname>_<lastname>.<jpg/png>```. 

Within the ["_team"](/_team) directory, you must make a markdown file labeled as ```<firstname>_<lastname>.md```, with the following dockstring and the person's information in a single line to form the description. This should be approximately 75-80 words to fit alongside their picture.
```
---
name: <firstname> <lastname>
role: <pick existing role or new role>
image: /assets/images/team/<firstname>_<lastname>.<jpg/png>
---

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut in venenatis neque...
```

