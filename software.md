# Necessary Software

This guide will assume its reader essentially has no software beyond factory defaults and VSCode downloaded upon start. To get the TezLab mobile app successfully running on a simulator, much needs to be downloaded and set up.

**Assumed**: MacOS operating system.

## Setting Up TezLab Repos

Create a local directory on your machine to house the repositories you're about to clone. Navigate into that directory.

- To clone tesla-web, open a terminal window and run `git clone https://github.com/BrooklynRunningCompany/tesla-web`.
- To clone tesla-mobile, run `git clone -b main https://github.com/BrooklynRunningCompany/tesla-mobile`. Currently, most changes to tesla-mobile are pushed to `main`, but this may change in the future, which would alter the cloning command; this should be self-explanatory should that time come, though.

## Homebrew

Homebrew is a comprehensive package manager that makes further software installation as seamless as it can be (which, unfortunately, isn't all that seamless).

To download Homebrew, you can follow the instructions [here](https://brew.sh/) or simply run the following in a new terminal window:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
From there, just follow the instructions in your terminal.

## Gradle

Gradle helps automate builds for such languages as C and JavaScript, and will be necessary when you ultimately run the iOS simulator for TezLab. Follow the instructions at [this link](https://gradle.org/install/) to install.

*Note*: If you opt to manually download, I recommend keeping the ZIP file and its contents in your Downloads folder or migrating it to some other self-created folder; copying the `/opt/gradle` strategy they reference can lead to permission headaches.

## Node.js

[Node.js](https://nodejs.org/en) is a JavaScript runtime environment that allows developers to run apps external to their browsers. Follow the instructions at the link at the beginning of this section to install both `node` and `npm`, the latter of which is a Node package manager.

During my time grappling with Node installations, I often found that my machine would "forget" that npm existed. It's possible that as you open new terminals and continue to try this whole process, your terminal will tell you `npm: command not found`. In these frustrating cases, a temporary fix is to simply run `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash` and `nvm install 20` again; this should remind your machine that Node and npm are indeed installed.

A more permanent fix (at least so far) is to [download nodenv](https://github.com/nodenv/nodenv), a Node version manager. Part of the installation instructions include piping nodenv into your ~/.zshrc file, which customizes your shell with scripts behind the scenes so you don't have to keep "reinstalling" Node.

Additionally, there's a possibility that the version of Node on which the app runs is not the most current one[^1]; if so, reference [this doc](https://github.com/BrooklynRunningCompany/tesla-mobile/tree/main?tab=readme-ov-file#readme), which may be private.

[^1]: That being said, at the time of writing this documentation, I'm running Node v20.14.0 and npm v10.7.0 and was just able to successfully build the app for the first time.

## Cocoapods

[Cocoapods](https://www.cocoapods.org/) helps manage the multiplicitous dependencies upon which TezLab is built, and hence, you will need it to successfully build and run the app. You can do so by running:
```
sudo gem install cocoapods
```
Later, when actually building the app through your terminal, you'll want to navigate to `tesla-mobile/ios` and run `pod install` to install all the dependencies in the TezLab Podfile.

Do note that many difficulties can arise downstream after `pod install`. In lieu of the classic "turn it off, then turn it back on again" strategy, one effective debugging technique is the following:
```
cd ios // assuming you're already in tesla-mobile
pod deintegrate
pod install
cd ..
```

## Ruby

By far the most finicky of the tools mentioned here, Ruby has the potential to leech hours from your day and developing experience. With luck, this guide will at least partially alleviate those difficulties.

If you're looking for a paid way to manage Ruby versions, [Ruby on Mac](https://www.rubyonmac.dev/) is the tool for you. If you're on more of a budget, though, here are the steps to follow:

- First, [install RVM](https://rvm.io/), the Ruby Version Manager. `\curl -sSL https://get.rvm.io | bash -s stable` will do the trick. Next, follow these Xcode instructions before returning to the Ruby ones below.

##### Initial Xcode Setup

There's a decent chance that installing Xcode before configuring Ruby to the current TezLab specifications isn't necessary, but it worked for me. Here are a few brief instructions to get the bare bones of Xcode set up:

- [Download Xcode](https://developer.apple.com/xcode/).
- `cd` into `tesla-mobile`
- Run `xcode-select --install`. This will install Xcode's Command Line Tools, which will come in handy during future development.
- Just to ensure you're not running into any directory conflicts, set the active developer directory by running `sudo xcode-select --switch /Library/Developer/CommandLineTools`.
- Sanity check: `xcode-select -p` should return `/Library/Developer/CommandLineTools'.

### Back to Ruby
- Run the following code:
```
export LDFLAGS="-L$(brew --prefix openssl@1.1)/lib"
export CPPFLAGS="-I$(brew --prefix openssl@1.1)/include"
export PKG_CONFIG_PATH="$(brew --prefix openssl@1.1)/lib/pkgconfig"

rvm install 2.7.4 --with-openssl-dir=$(brew --prefix openssl@1.1)
```
This will configure Ruby, setting it and you up for the installation using rvm. Upon writing this, TezLab is built on Ruby 2.7.4, which is approaching end of life; for       future users, replace 2.7.4 (in this instance and any subsequent ones) with whatever version with which TezLab operates.

- Run `rvm use 2.7.4 --default`. This will set Ruby version 2.7.4 (or whatever version you use) as the default, which can always be overridden with additional invocation of the `--default` flag.
- Sanity check again! `which ruby` will show you where your current version of Ruby is (and, by extension, what). Here's some example output, showing that v2.7.4 is being used on my machine: `/Users/Jacks-Macbook-Pro/.rvm/rubies/ruby-2.7.4/bin/ruby`. (You can also run `ruby -v` to see what version is running)

A quick fix to unexpected output, especially immediately following the download of some new piece of software, is to open a new terminal before entering your next command. Make sure to cd into the proper directory once you do, though (this isn't necessary in all cases, but is good practice for when it is required)!
