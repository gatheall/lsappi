## Introduction

This script lists information about software installs as recorded in _application info files_ by [install-app](https://github.com/gatheall/install-app).

**lsappi** requires Perl 5 along with the following Perl modules:

* `Carp`
* `Date::Format`
* `Getopt::Long`
* `XML::Twig`

If your system does not have these modules installed already, visit [CPAN](http://search.cpan.org/) for help.  Note that `Date::Format` and `XML::Twig` are not included with the default Perl distribution so you may need to install them yourself. Also note that `XML::Twig` itself requires the [Expat XML parser library](http://expat.sourceforge.net/).


## Installation

* Retrieve [the script](lsappi) and save it locally.
* Verify ownership and permissions on the script. It doesn't contain any sensitive information _per se_ but probably only `root` will be able to run it because of the need to access application info files.
* Edit the script and set `$ENV{PATH}` and `$apps_dir` according to your environment.  Also, you may wish to adjust the location of the perl interpreter in the first line as well as other variable initializations to suit your tastes.


## Use

For each application name or application info file specified on the commandline, **lsappi** will read the application info file and report which version is currently installed, who installed it, and when. If you'd rather report on all installs, not just the latest, use the `-a` option.  Finally, there is also a `-d` option to generate some admittedly limited debugging messages while running.

Examples:

| Invocation | Meaning |
| ---------- | ------- |
| `lsappi openssl apache` | lists information about the latest installs of OpenSSL and Apache. |
| `lsappi -d openssl apache` | same as above but displays debugging messages as well. |
| `lsappi -a openssl` | lists information about all installs of OpenSSL. |
| `lsappi /var/local/apps/*.xml` | lists information about the latest installs as found in all application info files. |


## Known Bugs and Caveats

Currently, I am not aware of any bugs in this script.

If you encounter a problem using this script, I encourage you to enable debug mode (eg, add `-d` to your commandline) and examine the output it produces before contacting me.  Often, this will enable you to resolve the problem yourself.


## Copyright and License

Copyright (c) 2004-2016, George A.  Theall.
All rights reserved.

This script is free software; you can redistribute it and/or modify it under the same terms as Perl itself.
