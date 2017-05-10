# SuperNEMO-DBD.github.io

[![Build Status](https://travis-ci.org/SuperNEMO-DBD/SuperNEMO-DBD.github.io.svg?branch=develop)](https://travis-ci.org/SuperNEMO-DBD/SuperNEMO-DBD.github.io)

A testing template for a Jekyll-based website for SuperNEMO

# Developing Locally
The site can be developed locally by using the supplied `snjekyll` self-executing
Makefile. This sets up a local instance of Jekyll, so changes can be previewed
before submitting a PR to regenerate the actual website. The currently known
requirements are:

- Linux or macOS Platform
- Ruby 2 or better, including development headers and library
  - macOS/Home/Linuxbrew supply these
  - Linux systems may require the `ruby-dev` or similar package to be installed
- GNU Make >= 3.81

The resulting workflow should be:

```console
$ git clone https://github.com/supernemo-dbd/supernemo-dbd.github.io
$ cd supernemo-dbd.github.io
$ ./snjekyll serve
```

The last command will download and setup the local Jekyll instance, and
start a local isolated webserver at `http://127.0.0.1:4000`. Simply point
your favoured browser to this address to view the generated site.

The server runs in the foreground and watches the site sources for changes
(for example, `index.md`). When a file changes, the server will rebuild the
site automatically, so simply refresh your browser to see the resultant
regenerated site. For example, try making some changes to `index.md`
The server may be shutdown at any point using `Ctrl-C`.

Further information on tasks available from `snjekyll` can be seen by
running

```console
$ ./snjekyll help
```

## Known Issues
- No reliable check for existence of `ruby-dev{el}` package on Linuces
  - Will issue a warning, but nothing more
- The `xz` package installed by Home/Linuxbrew is not compatible with the
  `nokogiri` gem required by Jekyll, and will cause compiliation of
  the gem to fail
  - `snjekyll` will issue a warning about this, but will not take further action.
  - To work around this issue, either do `brew unlink xz` or remove Home/Linuxbrew settings
    from your environment. The latter may not be possible if you have Homebrew installed
    in `/usr/local`

## Contributing

Contributions to the website structure/build or content are welcome. To begin contributing:

1. [Create your own fork](https://github.com/SuperNEMO-DBD/SuperNEMO-DBD.github.io#fork-destination-box) of this repository in your GitHub account.
2. As Jekyll websites are constructed through Markdown and HTML, you can [edit the files on GitHub through your browser](https://help.github.com/articles/editing-files-in-your-repository/)
3. However, this will not allow you to build and view the website. To do this, you'll need to [have a fork and clone this onto your computer](https://help.github.com/articles/fork-a-repo/). You can then build and view the website following the instructions above.
4. To make and submit changes, you should [create a branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/) on your fork in which to make changes (for example, add a new publication). These branches should be made from the default "develop" branch, and seperate branches should be made for each distinct task. For example, one branch to "add new publication", and one for "enhance description of double beta physics". This is for clarity and ease of merging.
5. Once you are happy with your changes, the branch can be [submitted as a new Pull Request](https://help.github.com/articles/creating-a-pull-request/). The changes will be reviewed and tested before integration with the develop and hence master branch (from which the website is built and served). If you are asked to make changes, simply make these on the branch corresponding to the Pull Request and they'll be automatically added to the review.

### Reviewing Pull Requests

If you are interested in the content of a Pull Request and wish to preview the changes locally, you can do this by [creating a local branch and merging the PR onto it](https://help.github.com/articles/checking-out-pull-requests-locally/).


# TODO
More documentation, including:

- Working with the repo and making Pull Requests
- Jekyll data for collaborators and institutes



