# Sphinx Example and Cheat Sheet

A simple example and cheat sheet for using Sphinx to document small Python modules.

reStructured Text cheat sheet: [https://davidstutz.github.io/sphinx-example/#index](https://davidstutz.github.io/sphinx-example/#index

Python documentation cheat sheet: [`module/__init__.py`](module/__init__.py)

## Installation

    $ sudo apt-get install python-sphinx
    $ sudo pip install sphinx
    # Depends on which version you prefer ...
    $ sudo pip3 install sphinx

## Quickstart

Sphinx offers an easy quickstart:

    $ mkdir docs
    $ cd docs
    # Quickstart, select yes for apidoc and mathjax and for splitting build and source.
    $ sphinx-quickstart
    $ sphinx

Choose to separate source and build directories, choose project name and version and the autodoc extension.

If the code/module to be documentation is accessable from the root directory, edit `docs/source/conf.py` as follows:

    import os
    import sys
    sys.path.insert(0, os.path.abspath('../../'))

Then the modules can be automatically documented using:

    $ sphinx-apidoc -f -o source/ ../
    $ make html

## Python 2.x

For modules or dependencies not supporting Python 3, `docs/Makefile` can ba adapted:

    SPHINXBUILD   = python -c "import sys,sphinx;sys.exit(sphinx.main(sys.argv))"
    
## License

BSD 3-Clause License

Copyright (c) 2016 David Stutz All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of David Stutz nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
