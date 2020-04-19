# Contribute

Thank you for contributing to Armory! Armory is an open source project and depends on contributions of the community. Even if you just fix a spelling issue or a add a docstring to a function, any help is greatly appreciated!

**There are multiple ways you can make Armory better:**
- **Help developing**:

  If you have an idea for a new feature or found a bug you can fix (also take a look on the [currently opened issues](https://github.com/armory3d/armory/issues?q=is%3Aopen+is%3Aissue)), feel free to implement that feature or fix that bug by yourself and open a new [pull request](#creating-a-pull-request).

  Also, check out the excellent [Best practices for engine contributors](https://docs.godotengine.org/en/stable/community/contributing/best_practices_for_engine_contributors.html) document published by Godot engine.
- **Engage in the community**:

  Every active user helps to spread the word about Armory:
  - [Armory Forums](https://forums.armory3d.org/)
  - [Discord Channel](https://discordapp.com/invite/axq6qWV)
  - You can add the hashtag [#armory3d](https://twitter.com/hashtag/armory3d) to your tweets about Armory
- **[Improve this wiki](#contributing-docs)**:
  
  For new users, the wiki is an important place to get information about Armory, so it is important that this place is kept up to date and improved.


## Creating a pull request

- Install [Git](https://git-scm.com/download/win)
- Click the `Fork` button on [GitHub](https://github.com/armory3d/armory):

  !["Fork" button](https://github.com/armory3d/armory_wiki_images/raw/master/dev/contribute/fork_button.jpg)
- Pick a location, open a command line here and clone **your forked** repository
  ```batch
  git clone https://github.com/my_username/armory
  ```
  You need to fork the repository only once, but if you don't know how to use Git, it is the best to fork it everytime you want to open a new pull request. The old fork gets overwritten then.

- Apply your changes, then open a command line in your forked repository and push the changes
  ```batch
  git add .
  git commit -m "My armory patch description"
  git push origin master
  ```
- Create a [new pull request](https://github.com/armory3d/armory/compare?expand=1) by clicking `compare across forks` and selecting your fork as the "head repository":

  ![Create a new pull request](https://github.com/armory3d/armory_wiki_images/raw/master/dev/contribute/new_pull_request.jpg)
  ![Compare accross forks](https://github.com/armory3d/armory_wiki_images/raw/master/dev/contribute/compare_across_forks.jpg)
  ![Compare changes](https://github.com/armory3d/armory_wiki_images/raw/master/dev/contribute/compare_changes.jpg)

- Thanks for contributing!

> You can also use a Git GUI client for the Git related tasks if you don't want to work from a command line. [Here](https://git-scm.com/downloads/guis) is a list of many clients.

## Local Armory setup

When working on Armory patches, it is useful to setup the SDK locally and apply your modification there.

> **Note**: Disable `Armory Project - Flags - Cache Build` to always recompile the project when you hit `Play`. There is no need to compile Armory itself, you will see the changes in action instantly. However, if you changed a Python script for the Armory add-on, you must restart Blender for the changes to take effect. 

#### Armory

- Fork and clone the [armory repository](https://github.com/armory3d/armory) into `blend_location/Libraries/armory`, it will automatically get picked up for that project

#### Iron

- Fork and clone the [iron repository](https://github.com/armory3d/iron) into `blend_location/Libraries/iron`, it will automatically get picked up for that project

### HaxeBullet

- Setup and Update Guide [HaxeBullet Documentation](haxebullet)

#### Full SDK

Alternatively, you can clone the whole SDK at once.

- Clone [armsdk](https://github.com/armory3d/armsdk) into `blend_location/armsdk`, it will automatically get picked up for that project - this lets you have a fully self-contained and portable project setup

- You can also point Armory to use the armsdk [at specific location](gitversion?id=manual-clone)

If you contribute more regularly, it might be helpful to create a local setup that lets you easily change between Armory versions. Every Git repository can have multiple "remote repositories" connected to it.
If you cloned the forked Armory SDK, there will automatically be a remote called `origin` pointing to your fork. You can add another one pointing to this armory repository. To do this, open a command line in your local repository and write:
```batch
git remote add upstream https://github.com/armory3d/armory.git
```
`upstream` will then be the new name of that remote, you can give it any name you want.

A tutorial about working with remotes can be found [here](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes). Note that a GUI client for Git can make it much easier to work with remotes.

Each submodule of the Armory SDK can also point to different remotes, so you can easily keep track of all your forks across the Armory project structure.

## Contributing docs

Docs can be edited directly on this GitHub wiki! Just click on `Edit` at the top of the article you want to edit. If you want to add or edit images, please open a pull request with the new/edited images [here](https://github.com/armory3d/armory_wiki_images) and embed them via link in your article. GitHub does not currently allow non-repository members to edit images in wiki articles.

## Building API docs

API docs are built using [dox](https://github.com/HaxeFoundation/dox). After building an empty project with Krom target selected, follow the instructions at dox [readme](https://github.com/HaxeFoundation/dox#usage).

Detailed build instructions can be found [here](https://github.com/armory3d/armsdk/tree/master/api).
