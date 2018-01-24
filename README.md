# Standard
Standard for process, revision control, project structure and coding standard

## Process
Release every 2 weeks -- Try to use the process follows [SAFe](http://www.scaledagileframework.com/) and [Spotify](https://labs.spotify.com/2014/03/27/spotify-engineering-culture-part-1/)

## Revision Control
Use Git and follow [Gitflow](http://nvie.com/posts/a-successful-git-branching-model/) branching model.

Hosted on
- [GitHub](https://github.com/)
- [GitLab](https://gitlab.com/)

## Project Structure
- `changelog` -- A log of all notable changes made to work project.
- `docs` -- Folder to store all documents that related with how to use and public for user ex. User manual, API reference (Library project).
- `release-notes` -- Release notes folder.
  - `release-[Version].md` -- Release file ex. `release-1.4.md`
- `src` -- Source code folder. Following the platform or programming language folder name to `src` ex. `Android`, `C#`, ... to `src`
- `LICENSE` -- License file. See [Licensing a repository](https://help.github.com/articles/licensing-a-repository/) and [Licenses](https://choosealicense.com/licenses/).
- `README.md` -- README file contains information about work project.
- `[Filename]-[Language Code].md` -- Files in the other languages, Language code is [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).

## Coding Standard
Use [Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/) and adapt for the other programming languages.
