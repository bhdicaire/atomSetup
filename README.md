# Settings for Atom

Keeping my text editor configuration is *nice*. I recently did a reinstall of my operating system and I had the entire ~/.atom folder backed up. I installed Atom, replaced the .atom folder, but I was getting a bunch of errors all the time. :sweat:

You learn lessons, a lot of the hard way. Fortunately, I did not lost anything — Atom stores all settings files inside the ~/.atom/ directory. In order to restore the atom setup, you only need the .coffee, .cson, .json and .less files AND a list of installed packaged (e.g. apm list --installed --bare > packages.list).

## Backup strategy

Based on my experience, you should never rely on one backup method. I make copy on the computer, on site and to the cloud. The more backups you have, the better, but two to three should be fine for most.

The identified aasets are:
* Atom's and package settings
* Installed packages
* User keymaps, styles, and snippets
* User init script

### Using a distributed version control system

Use a public or private Git repo and store the contents of your local ~/.atom folder in there.

You can then keep it up to date using git push (to upload changes) and git pull (to download changes). Syncing the configuration using git clone will provide a manual replication strategy for several computers. I'm using a makefile to track the installed packages and update the git repository.

You can ignore the following files/directories (e.g. .gitignore):
`* storage
* compile-cache
* dev
* .npm
* .node-gyp

The thing that you may be concerned about is your userId being inside your config.cson file. Don't worry about my repository, I removed mine &#57358;.

### Using the Sync Settings Plugin for Atom

[Sync Settings for Atom](https://atom.io/packages/sync-settings) is a plugin by [Geno Roupsky](https://github.com/groupsky). It stores the configuration in a single public or private [gist](https://gist.github.com/). You trigger a synchronization from the Command Palette: ⌘ ⇧ P ( macOS) or ^ ⇧ P (Linux/Windows).

You'll need to store a [Github's personal access token](https://github.com/settings/tokens/new) into the plugin settings next to the gistID. You can fork my current config with my public [GIST](https://gist.github.com/bhdicaire/3fbd3803ee3127dc24e919c6e5a1ed01)

The sync Settings configuration are stored in Atom's config.cson and are *NOT* included in the Gist. For the paranoid out there, you should disable the Exception Reporting and Metrics plugins.

Click on Menu "Open Your Config" to edit Atom's config.cson
Use these keys:
  "sync-settings":
    gistId: "b3025...88c41c"
    personalAccessToken: "6a10cc207b....7a67e871"

### Using Time Machine (Mac OS X)

If everything else fail, I might have a working copy on my local Time Machine (e.g. ¯\_(ツ)_/¯ )

## Author

Benoît H. Dicaire, http://github.com/BHDicaire, @BHDicaire, BH@Dicaire.com, http://BHDicaire.com/

### About

I help organizations facing difficult strategic decision-making.

I am a freelance security expert and a keynote speaker in French and English. Over the last 25 years, I have led consulting engagements for well-known companies throughout North America.

I'm [available for hire](http://dicaire.com/).  I’d be pleased to discuss your requirements.
