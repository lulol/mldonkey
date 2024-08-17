# MLDonkey: cross-platform multi-network peer-to-peer daemon

[![Build](https://github.com/ygrek/mldonkey/actions/workflows/workflow.yml/badge.svg)](https://github.com/ygrek/mldonkey/actions/workflows/workflow.yml)

A lot of documentation (wiki) and user forums were previously hosted at http://mldonkey.sourceforge.net, but were shut down on August 21, 2023,
see [issue #90](https://github.com/ygrek/mldonkey/issues/90) for the details and links to the data dumps (help needed to restore them to the usable form).

[GitHub Discussions](https://github.com/ygrek/mldonkey/discussions) serves as a replacement for the forum for the time being.

Build
=====

Supported OCaml versions are >= 4.03 and < 5.0, see mldonkey.opam for canonical information.

GTK2 GUI (`./configure --enable-gui=newgui2`) builds only in specific configuration when lablgtk2 packages
are installed in `$(ocamlc -where)/lablgtk2`. This happens to be true on Debian when building with packaged (system) ocaml :

    sudo apt install ocaml camlp4 libnum-ocaml-dev liblablgtk2-gnome-ocaml-dev

It is known to not work with opam - this is the goal for the next release (only gui is affected, core itself builds fine in opam).

`./configure --enable-batch --enable-gui=newgui2` (ie download and build lablgtk2 locally) only works with old OCaml versions (e.g. 4.05.0)
because it is using very old lablgtk2.  Upgrading to the newer lablgtk2 is the goal for the next release
