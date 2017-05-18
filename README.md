# SuperNEMO-DBD.github.io

[![Build Status](https://travis-ci.org/SuperNEMO-DBD/SuperNEMO-DBD.github.io.svg?branch=master)](https://travis-ci.org/SuperNEMO-DBD/SuperNEMO-DBD.github.io)

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
The server may be shutdown at any point using `Ctrl-C`. This mode
is best used to check the look and interactive behaviour of the site.

Basic structure and linking tests of the site can be run by building the site and then
running the `test` target

```console
$ ./snjekyll build
$ ./snjekyll test
```

This runs the [html-proofer program](https://github.com/gjtorikian/html-proofer)
for basic validation of the generated pages. It can only be run using the
build/test cycle, and will fail if run on pages built with `./snjekyll serve`.

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

1. [Create your own fork](https://help.github.com/articles/fork-a-repo/) of this repository in your GitHub account.
2. To make and submit changes, you should [create a branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/) on your fork in which to make changes (for example, "add a new publication"). Seperate branches should be made for each distinct task. For example, one branch to "add new publication", and one for "enhance description of double beta physics". This is for clarity and ease of merging.
3. As Jekyll websites are constructed through Markdown and HTML, you can [edit the files on GitHub through your browser](https://help.github.com/articles/editing-files-in-your-repository/)
4. However, this will not allow you to build and view the website. To do this, you'll need to [clone your fork locally](https://help.github.com/articles/fork-a-repo/). You can then build and view the website following the instructions above.
5. Use the instructions above to build, check and test the site for interactive use and structural integrity.
6. Once you are happy with your changes, submit the branch [as a new Pull Request](https://help.github.com/articles/creating-a-pull-request/). The changes will be checked for conflicts and a build/test will be run using [Travis CI](https://travis-ci.org/SuperNEMO-DBD/SuperNEMO-DBD.github.io/) and reported back to the PR page. If these checks reveal issues, review them and add commits as needed to the branch for your Pull Request. Retesting
will then occur automatically.
7. Once all the checks are passed, the PR will be merged to the `master` branch for publication.

### Reviewing Pull Requests

If you are interested in the content of a Pull Request and wish to preview the changes locally, you can do this by [creating a local branch and merging the PR onto it](https://help.github.com/articles/checking-out-pull-requests-locally/).


# TODO
More documentation, including:

- Working with the repo and making Pull Requests
- Jekyll data for collaborators and institutes



