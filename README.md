Vulkan tutorial
===============

This repository hosts the contents of [vulkan-tutorial.com](https://vulkan-tutorial.com).
The website itself is based on [daux.io](https://github.com/justinwalsh/daux.io),
which supports [GitHub flavored Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/).
A few changes were made to daux.io and its themes, which are included in
`daux.patch` and are licensed as [MIT](https://opensource.org/licenses/MIT). The
patch is based on commit `d45ccff`.

Use issues and pull requests to provide feedback related to the website. If you
have a problem with your code, then use the comments section in the related
chapter to ask a question. Please provide your operating system, graphics card,
driver version, source code, expected behaviour and actual behaviour.

Changing code across chapters
-----------------------------

It is sometimes necessary to change code that is reused across many chapters,
for example the `VDeleter` class or a function like `createBuffer`. If you make
such a change, then you should update the code files using the following steps:

* Update any chapters that reference the modified code.
* Make a copy of the first file that uses it and modify the code there, e.g.
`base_code_fixed.cpp`.
* Create a patch using
`diff -Naur base_code.cpp base_code_fixed.cpp > patch.txt`.
* Apply the patch to the specified code file and all files in later chapters
using the `incremental_patch.sh` script. Run it like this:
`./incremental_patch.sh base_code.cpp patch.txt`.
* Clean up the `base_code_fixed.cpp` and `patch.txt` files.
* Commit.

License
-------

The contents of this repository are licensed as [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/),
unless stated otherwise. By contributing to this repository, you agree to license
your contributions to the public under that same license.

The code listings in the `code` directory are licensed as [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/).
By contributing to that directory, you agree to license your contributions to
the public under that same public domain-like license.
