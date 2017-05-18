# Extras and Bonus Material

> Additional tools and information to help you on your journey

This file is full of extra tools and fun, optionl ways you can customize your environment to make it your own.

## Sublime Text Color Schemes and Themes

Everyone knows that Sublime Text is an ugly looking application. That's one of the very few downsides of using Sublime Texts vs. Atom but overall Sublime Text is a superior editor. Now that __you have Package Control installed__ you can install some cool themes and color schemes to customize the experience.

__*NOTICE - WARNING*__

You'll need Sublime Text 3 installed for most of these to work. To update, you can [download the latest version (v3) here](https://www.sublimetext.com/3).

### Sublime Themes

Themes will change the appearance of the GUI application and often come with syntax highlighting schemes to go with them. My favorite is the Glacier theme but you can choose whichever you like.

#### Finding themes

[There's a great list of themes with screenshots of each here](https://scotch.io/bar-talk/the-best-sublime-text-3-themes-of-2014). This page includes instructions on how to install them as well but we've also included instructions below as well.

A great looking theme (one that I use myself) is [Glacier](https://packagecontrol.io/packages/Theme%20-%20Glacier). This page will show you how to install the Glacier theme but please feel free to Google for "Sublime Text themes" and do your own research.

#### Installing themes

Most themes can be installed using the Package Control plugin that you should already have installed. Once you've found the thee you're interested in, installed it by following these instructions:

1. Press `Cmd + Shift + P` all at once to open up the menu
2. Type in "install" - at this point you'll see "Package Control - Install Package". Highlight that option and press enter or click on it.
3. Now you can search for packages. Search for the name of the theme package you found that you liked. Highlight it, then press enter. Now the theme is installed but you need to activate it.
4. To activate your new theme you'll need to click `Sublime Text` in your Mac's top most menu bar, hover over `Preferences - User`, then click it. A new file will open. Inside of that file you'll see some JSON written. You'll need to update that file. Here's an example:

If your preference file looks *something like this* (but not exactly):

```json
{
  "color_scheme": "Packages/Colorsublime - Themes/peacocks-in-space.tmTheme",
  "font_face": "Source Code Pro",
  "font_size": 13,
  "ignored_packages":
  [
    "Vintage"
  ]
}
```

Then you'll want to update the theme key by adding a line to the end of the file. Find the last setting in that file (before the final `}` character) and add a comma to the end of that line and press `Enter` to go to a new line. Now add this line of code to the file:

```
"theme": "theme-name.sublime-theme"
```

You'll need to replace `theme-name.sublime-theme` with whatever your chosen theme's instructions tell you. __Be sure to follow the documentation that's given to you before you ask questions to us.__ 9 times out of 10 the answer you're looking for is in the documentation (usually in the project's README file).

#### Sublime Color Schemes

Sublime comes with a nice selection of built in syntax coloring schemes. You can change your color theme by clicking `Sublime Text > Preferences > Color Scheme > Color Scheme - Default` and choose from the selection there. *I recommend starting with `Solarized Dark`. It's a very popular, common, and beautiful syntax highlighting scheme.

For those of you who want to branch out and explore more than just the defaults, [check out the ColorSublime Project](https://github.com/Colorsublime/Colorsublime-Plugin#installing)

First follow the installation instructions. __Do not do the manual install__. You already have Package Control installed so you can simply search for the ColorSublime plugin in package control and install it that way. You'll need to quit and reopen Sublime after the package has been installed.

Now you can install a theme by running:

```
Cmd + Shift + P
```

- Chooose "ColorSublime: Install Theme"
- Now search for the name of the theme you want to install and it will become available in your Sublime Text preferences

You can now just pick a different color scheme like normal.

[See the official instructions if you get stuck](https://github.com/Colorsublime/Colorsublime-Plugin#usage)


## Terminal Themes and Colors

Your terminal is not set up to be very colorful. We need to fix that. First off, let's download a terminal theme. You can choose from dozens of them [on this page](https://github.com/lysyi3m/osx-terminal-themes). To install the theme you want to *download* (not clone) the project from GitHub. Once downloaded, unzip the file and enter the `schemes` directory. Once you know which theme you want to try out, double click it and it will be automatically installed on your terminal. To make this your default theme click `Terminal > Preferences`. Now go to the "Profiles" tab. Find the theme you installed and like. Click on it. With the theme highlighted, click on the `Default` button at the bottom of the sidebar. This will make it so that all of your terminal windows will now use that theme by default.

You can customize your theme by changing the font and font-size. Menlo and Monaco at about 13 or 14pt are good starting points.

### Making sure your terminal is multi-colored

You'll notice that mine and Jim's terminal windows show different colors depending on the files and folder we work with. Someitmes your terminal theme will automatically enable colors. If not, schedule some time with us and we can help you make sure that your theme supports multiple colors so that all the text isn't all one color and hard to read.

## Clearing the terminal

Someimtes after you've done a lot of work in the terminal you want to start fresh and get rid of all the junk commands you've already written. There are two ways to do this.

### Method 1 - The not as cool way

If you enter the command `clear` your terminal window will scroll the old commands up so that they're out of your view and make it look like you have a fresh start. But its a lie. If you scroll up you'll see all the commands you've been running. Sometimes this is what you want. In cases where you want to separate commands related to certain ideas and want to separate them and look at them separately this is for you.

### Mehod 2 - Truly clearing the terminal

If you press `Cmd + k` in a terminal window it will clear out *all* of your commands and make it look as if you just opened the terminal.

## Editorconfig command

All of our projects will need an `.editorconfig` file in them. I have a special alias for creating a new editor config file in any directory I'm in by simply typing `editorconfig` in my terminal. The way to get this working goes like this:

1. Create a `.editorconfig` file in your Home folder (`touch ~./.editorconfig`). Open up that file and paste in your default editorconfig preferences
2. Open up your `~/.bashrc` file and add the following line to it:

```
alias editorconfig='cp ~/.editorconfig .'
```

This alias basically says "copy the `.editorconfig" file from my home folder to the folder I'm currently in.

## Apps to make your life easier

As developers we spend the vast majority of our time in the terminal. It's rate to use a GUI application but sometimes they can be very helpful. Here's a list of some tools we use to manage our web applications.

### Colored terminal

*See above - We can set this up for you before class or during office hours. Even though you may have set up a pretty terminal theme, you might not be getting the color coding that the terminal supports and allows by default. Your instructors have a code snippet you can use to enable this if it doesn't work by default.

Color coding helps you determine whether something is a file, is executable, and gives you an overall easier to read experience.


### DB Browser for SQLite

This tool will come in handy later on in the course when we start using databases. The [SQLite Browser](http://sqlitebrowser.org) allows you to open a database file and browse it visually instead of through the command line. 99% of your
SQLite databases are easier to browser visually rather than using the command line tool.

### Postman

[Postman](https://www.getpostman.com) is a tool that lets you create HTTP requests and explore and test local or remote APIs. This will come in handy later on in the course. This is basically a GUI application for the built in `curl` command. Instead of running something like `curl -i -X POST "user-id=1&session_id=af4Hd8vU&is_logged_in=1" http://localhost:3000` you can use the Postman GUI app to send GET, POST, PUT, PATCH, and DELETE requests to a local or remote URL. It lets you set the data you would send to a website through a form but through an easy to use GUI. I recommend learning cURL but Postman is very helpful in the beginnig of your journey into MV web applications.

### Robomongo

[Robomongo is a GUI application](https://robomongo.org) that allows you to explore a MongoDB database visually, similar to the DB Browser for SQLite. You can use the MongoDB command line tool but sometimes it's easier to explore a database using a GUI program when you're running more advanced commands.

### Sequel Pro

[Sequel Pro is a GUI application](http://sequelpro.com) that lets you explore a variety of remote or local databases visually. It works on most relational database egines (except SQLite) and is especially well suited to browsing local and remote MySQL repositories. Again, MySQL is super easy to learn on its own but sometimes you wanto so quickly get a visual idea of what's happening inside a database. Youll likely use Sequel Pro about 30% of the time and the rest of the time you'll use the built-in `mysql` command line tool.


