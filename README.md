# Hello Gutenberg
This repository takes the "build your first Gutenberg block" exercise
and turns it into a custom package installable by Composer.

The goal of this repo is to determine whether I can define a consistent
architecture for custom Gutenberg blocks that, when required in a client
project, I can install into a desired directory in order to have the block
load inside WordPress.

The block structure might look something like this:

* assets/
    * block.js
    * editor.css
    * style.css
* src/
    * \<ClassNameOfBlock>.php
* composer.json

The Composer file will need to require a custom Composer installer that
will recognize a type of `wordpress-block` and install those types into
the correct directory from the resource that requires it. It will also
have a dependency on a library or libraries that define interfaces for
registering blocks, so that the resulting plugin or theme that requires
the package can leverage that interface in order to activate each of
those required blocks with ease.
