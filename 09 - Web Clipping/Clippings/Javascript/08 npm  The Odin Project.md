---
title: "npm | The Odin Project"
source: "https://www.theodinproject.com/lessons/node-path-javascript-npm"
author:
published:
created: 2025-06-17
description: "The Odin Project empowers aspiring web developers to learn together for free"
tags:
  - "clippings"
---
In the previous lesson, we learned about ES6 modules and the syntax used for importing and exporting things between modules. As we build bigger, more complex applications, we may not want to write *everything* ourselves. We may want to import third party code to handle some things for us, which can range from helper functions other people wrote, to entire frameworks for us to build our application within. To find and import these third party packages with ease, we need the help of a package manager such as npm!

This section contains a general overview of topics that you will learn in this lesson.

- Understand what npm is.
- Understand the purpose of the `package.json` file.

**npm** (no capitals!) is a package manager - a gigantic repository of plugins, libraries, and other tools, which provides us with a command-line tool we can use to install these tools (that we call “packages”) in our applications. We will then have all our installed packages’ code locally, which we can import into our own files. We could even publish our own code to npm!

You may recall installing npm in the Foundations course in order to install the Jest testing framework to do the JavaScript exercises. Funnily enough, [npm does not stand for “Node Package Manager”](https://www.npmjs.com/package/npm#is-npm-an-acronym-for-node-package-manager), though you will often see it referred to as such.

If you are in the Full Stack Ruby on Rails pathway, you will have already been introduced to Yarn, another JavaScript package manager. For this course, we will be using npm.

As our applications get more complex and more and more files are needed (whether they are our own files or files from packages we’ve installed and imported), managing many of these dependencies can become rather troublesome, especially when packages get updated. This can get even more troublesome when we consider that we may end up sending *many* JavaScript files to the browser to download. In the next lesson, we will introduce bundlers, tools that lets us write multiple files that are better for us to work with, then bundle them together into fewer smaller files which will ultimately be sent to the browser instead.

npm revolves around a file called `package.json`. It’s a JSON file containing information about our project, such as its name or any dependencies and their version numbers. npm can read this file and do things such as install all of the listed dependencies with the correct versions, and running commands that you’ve set as an npm script (we will cover npm scripts in a later lesson).

For example, here is the `package.json` file for The Odin Project’s curriculum repo that houses all of the lesson files (including this lesson you are doing right now):

```json
{
  "name": "curriculum",
  "version": "1.0.0",
  "description": "[The Odin Project](https://www.theodinproject.com/) (TOP) is an open-source curriculum for learning full-stack web development. Our curriculum is divided into distinct courses, each covering the subject language in depth. Each course contains a listing of lessons interspersed with multiple projects. These projects give users the opportunity to practice what they are learning, thereby reinforcing and solidifying the theoretical knowledge learned in the lessons. Completed projects may then be included in the user's portfolio.",
  "scripts": {
    "lint:lesson": "markdownlint-cli2 --config lesson.markdownlint-cli2.jsonc",
    "lint:project": "markdownlint-cli2 --config project.markdownlint-cli2.jsonc",
    "fix:lesson": "markdownlint-cli2 --fix --config lesson.markdownlint-cli2.jsonc",
    "fix:project": "markdownlint-cli2 --fix --config project.markdownlint-cli2.jsonc"
  },
  "license": "CC BY-NC-SA 4.0",
  "devDependencies": {
    "markdownlint-cli2": "^0.12.1"
  }
}
```

There’s a lot of stuff here and we don’t need to understand it all yet. The point is that if you were to clone the curriculum repo, if you ran `npm install`, npm would read this `package.json` file and see that it needs to install the `markdownlint-cli2` package. Once this package is installed, you’ll be able to run any of the four npm scripts that use that package. The curriculum repo itself does not actually contain the code for the `markdownlint-cli2` package, as anyone cloning the repo can just run `npm install` to let npm grab the code for them.

In our own projects, as we use npm to install new packages (or uninstall any!), it will automatically update our `package.json` with any new details. We will see this in action in the next lesson when we introduce module bundling using a package called Webpack.

1. Read a bit more about npm, packages, and dependencies:
	1. [Installing packages with npm](https://docs.npmjs.com/downloading-and-installing-packages-locally).
	2. Read about [the `package.json` file](https://docs.npmjs.com/creating-a-package-json-file), the file that stores much of the information for our application.
	3. Any packages we install are called “dependencies”, but if any packages are only used during the development process and their code is not needed for the user-facing app (such as the Jest testing framework), we call them [development dependencies](https://dev.to/mshertzberg/demystifying-devdependencies-and-dependencies-5ege).
2. Here is a great little [history lesson about JavaScript and managing packages across multiple files](https://peterxjang.com/blog/modern-javascript-explained-for-dinosaurs.html). Only read up to “Using a JavaScript module bundler (webpack)”, as we will cover bundlers and webpack in the next lesson.

The following questions are an opportunity to reflect on key topics in this lesson. If you can’t answer a question, click on it to review the material, but keep in mind you are not expected to memorize or master this knowledge.

- [What is npm?](https://www.theodinproject.com/lessons/#npm)
- [What file does npm use that contains all information about dependencies?](https://docs.npmjs.com/creating-a-package-json-file)

This section contains helpful links to related content. It isn’t required, so consider it supplemental.

- It looks like this lesson doesn’t have any additional resources yet. Help us expand this section by contributing to our curriculum.

[Improve on GitHub](https://github.com/TheOdinProject/curriculum/edit/main/javascript/organizing_your_javascript_code/npm.md) [Report an issue](https://github.com/TheOdinProject/curriculum/issues/new?labels=Status%3A+Needs+Triage&lesson-link=https%3A%2F%2Fwww.theodinproject.com%2Flessons%2Fnode-path-javascript-npm&template=suggestion.yaml&title=npm%3A+%3CShort+description+of+your+suggestion%3E) [See lesson changelog](https://github.com/TheOdinProject/curriculum/commits/main/javascript/organizing_your_javascript_code/npm.md)

## Support us!

## The Odin Project is funded by the community. Join us in empowering learners around the globe by supporting The Odin Project!

[Learn more](https://www.theodinproject.com/support_us) [Donate now](https://opencollective.com/theodinproject/donate?amount=5)