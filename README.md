# SuperNEMO-DBD.github.io

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

# TODO
More documentation...


