# dart-doc-syncer

A utility for syncing Dart examples for the Angular 2 docs (https://webdev.dartlang.org/angular).

Example sources are read from the [dart-lang/site-webdev repo](https://github.com/dart-lang/site-webdev) and written
to individual repos under [angular-examples](https://github.com/angular-examples).

Syncing a single example
------------------------

Run `dart_doc_syncer` to sync a single example folder. Use the example name as an argument
to the `--match` option. For example:

```
dart dart_doc_syncer --match architecture
```

Syncing multiple examples
-------------------------------

The `--match` option actually takes a regular expression as an argument.
To sync all examples you can use `.` as a "match-all" pattern:
```
dart dart_doc_syncer --match .
```

How to get the tools
--------------------

1. Clone the repo: `git clone git@github.com:angular/dart-doc-syncer.git`
2. Get the dependencies: `cd dart-doc-syncer; pub get`

Options
-------

```
dart ~/GITHUB/dart-doc-syncer/bin/dart_doc_syncer.dart --help

Syncs example applications.

Usage: dart_doc_syncer [options] [<exampleName> | <examplePath> <exampleRepo>]

-h, --help           show this usage information
-b, --branch         <branch-name>
                     git branch to fetch examples from
                     (defaults to "master")

-n, --dry-run        show which commands would be executed but make (almost) no changes;
                     only the temporary directory will be created

-f, --force-build    forces build of example app when sources have not changed
-k, --keep-tmp       do not delete temporary working directory (.tmp) once done
-p, --[no-]push      prepare updates and push to example repo
                     (defaults to on)

-m, --match          <dart-regexp>
                     sync all examples having a data file (.docsync.json)
                     and whose repo path matches the given regular expression;
                     use "." to match all

-u, --user           <user-id>
                     GitHub id of repo to fetch examples from
                     (defaults to "angular")

-v, --verbose        
```
