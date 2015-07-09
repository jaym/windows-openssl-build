# windows-openssl-build

[![Build status](https://ci.appveyor.com/api/projects/status/o50q1jusjr8pyv4x/branch/master?svg=true)](https://ci.appveyor.com/project/jdmundrawala/windows-openssl-build/branch/master)

This repo contains the build recipes needed to build openssl for Windows. It uses
[knap-build](https://github.com/oneclick/knap-build) and [knap-recipes](https://github.com/oneclick/knapsack-recipes).
Creating a GitHub release on this repo will trigger AppVeyor to build OpenSSL and add the files to that release.

## Building Locally

To build, you need a working [DevKit](http://rubyinstaller.org/add-ons/devkit/) along with Ruby. 
You can install Ruby from [RubyInstaller](http://rubyinstaller.org/downloads/). Once both are installed,
you will need to make sure that you have a working `tar.exe` in your path. This can be acheived by copying
`bsdtar.exe` from mingw. For example, `cp C:\Ruby21\DevKit\mingw\bin\bsdtar.exe C:\Ruby21\DevKit\bin\tar.exe`.

Now, you will need to activate DevKit. Assuming you are using powershell, this can be done by running
`C:\Ruby21\DevKit\devkitvars.ps1`. This will add the GCC compiler toolcahin to your path.

The final steps are easy. First, set the version of OpenSSL you want to build in the `OPENSSL_VERSION` file.
This file must have a corresponding `knapfile` in `knap-build/recipes/openssl`. After that `bundle exec rake build`.

You can find the artificats in `knap-build/var/knapsack/packages/openssl/`

## Publishing through AppVeyor

To have AppVeyor publish the artificats in a GitHub Release, make sure your changes are merged into master
and create a release through the Releases tab. Name it the version of OpenSSL you are wanting to build so that
we can easily tell what it is. Once you do this, it will kick off a build on AppVeyor. If this job succeeds, it
will publish the artificats and you will be able to see them on the release.
