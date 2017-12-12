# Avoiding dependency hell in multi-project builds when using gradle

This repo demonstrates a way do use gradle files to help manage dependencies and keep them in sync in projects with subprojects and sub-modules

# Why?

It is common practice to structure your project so items are packaged by features rather than layers. For example, if you were using mvp, you would place your login view with your login presenter, as opposed to bundling all your views together and your presenters together.
There is a number of reasons for why this is good practice, one of the main reasons is to help avoid context switching and searching for files. A good article explaining some other reason why this is good and how this can be implemented can be found here https://overflow.buffer.com/2017/10/13/package-feature-modularised-android-projects/

In large or complex projects this can be taken a step further and layers of features can be broken into sub-projects or modules, a good description of how to create multiproject builds can be found here: https://docs.gradle.org/current/userguide/multi_project_builds.html

These modules often have common dependencies and managing the versioning of these can become challenging and time consuming in large projects especially when there is dependency conflicts (I'm looking at you Mockito)

# Solution

This can be fixed by creating a file for all your dependencies and then using this in the individual sub-projects

# Article Coming Soon

I am currently working on an article that describes this process but for now this process can pretty much be seen in this repo

# Basic steps

1 - create dependencies.gradle

2 - declare this file in the root build.gradle file

3 - add a variable to access the rootProject extensions in the subproject

4 - create a variable containing the map of dependecies

5 - compile the dependencies

6 - profit
