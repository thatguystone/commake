# commake: a common Makefile

A lot of my projects use the same Makefile layout, but each tends to vary
slightly from all the others. There's no reason for this (except, perhaps, for
the pain of using submodules).

commake provides a simple, boilerplate Makefile that provides clean rules for
compiling a typical C/C++ project. It helps generate your *.o's and provides
consistent and reliable variables for installing files, running valgrind,
generating pkg-config files (*.pc), creating archives (*.a), creating shared
objects (*.so), and linking binaries.

## Usage

commake provides a helper script (`update`) to manage itself in all your
repos. This obviously depends on your repos being available locally (something
I would recommend doing anyway).

```bash
# You may call the update script directly, with the base directory to search in
# for files to update
./update ../../

# Or you may set the env var COMMAKE_BASE and forget the argument
export COMMAKE_BASE=~/Code
./update
```

## Where's the submodule?

While you're more than welcome to use this as a submodule, I personally don't,
for 1 simple reason: I forget to update all of my projects. The point of
commake is keeping things consistent and up-to-date, and submodules don't play
nicely with that.

`git subtree` also has the same problem as submodule, so I don't use that,
either.
