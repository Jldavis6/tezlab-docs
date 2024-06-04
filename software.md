# Necessary Software

This guide will assume its reader essentially has no software beyond factory defaults downloaded upon start. To get the TezLab mobile app successfully running on a simulator, much needs to be downloaded and set up.

**Assumed**: MacOS operating system.

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

As an aside, it's possible that as you open new terminals and continue to try this whole process, your terminal will tell you `npm: command not found`. In these frustrating cases, simply run `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash` and `nvm install 20` again; this should remind your machine that Node and npm are indeed installed.

Additionally, there's a possibility that the version of Node on which the app runs is not the most current one; if so, reference [this doc](https://github.com/BrooklynRunningCompany/tesla-mobile/tree/main?tab=readme-ov-file#readme), which may be private.
