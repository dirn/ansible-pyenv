pyenv
=====

[![Build Status](https://travis-ci.org/dirn/ansible-pyenv.svg?branch=master)](https://travis-ci.org/dirn/ansible-pyenv)

An Ansible role to install [pyenv](https://github.com/yyuu/pyenv).

Requirements
------------

This role works on OS X and Debian-based OSes. If using OS X, make sure you have
[Homebrew](http://brew.sh/) installed before running the role. If you're looking
for a role to handle it for you, check out
[dirn.homebrew](https://github.com/dirn/ansible-homebrew).

Role Variables
--------------

Several variables are available to configure the role.

To set where pyenv will be installed:

    pyenv_root: ~/.pyenv

To set the location of your projects:

    pyenv_project_root: '~'

> This is useful if you want a different version of Python than you use
> elsewhere.

To specify the name of the run commands file that will initialize pyenv:

    pyenv_runcom: ~/.bashrc

To specify which versions of Python to install:

    pyenv_versions: []

To specify the default versions of Python available:

    pyenv_default_versions: []

To specify alternative default versions of Python available inside your projects
root:

    pyenv_project_versions: []

> This is useful if you want a different version of Python than you use
> elsewhere.

To install [virtualenv](https://github.com/yyuu/pyenv-virtualenv) and
[virtualenvwrapper](https://github.com/yyuu/pyenv-virtualenvwrapper):

    pyenv_virtualenv: true

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: dirn.pyenv
          pyenv_runcom: ~/.zshrc
          pyenv_versions:
            - 2.7.9
            - 3.4.3
            - pypy-2.5.0
            - pypy3-2.4.0
          pyenv_default_versions:
            - 2.7.9
            - pypy-2.5.0
          pyenv_project_versions:
            - 3.4.3
            - pypy3-2.4.0

License
-------

MIT

Author Information
------------------

This role was created by [Andy Dirnberger](https://github.com/dirn).
