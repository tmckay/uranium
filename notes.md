# Testing Goals

Uranium needs to work in a variety of situations, so testing is key. Ultimately we should be looking at:

* 100% code coverage?
* full-stack tests
* coverage across all major versions of python:
  * 2.6
  * 2.7
  * 3.5
* uranium's warmup test needs to test installation of the uranium on disk,
  not from the repo.

# Known issues

* uranium version conflicts.
  * the uranium package currently lives in it's own sandbox, so
    version conflicts between uranium's requirements and the users
    will conflict.
  * We should maybe sandbox Uranium's own depedencies


# Potential Problems

## virtualenv does not copy over distutils

Distutils contains the code that helps package and download dependencies. If this is not copied over, it can
lead to the distutils on the system path being loaded, which results in an incorrect configuration, which finally
can cause eggs to be installed incorrectly (due to a misdetected root path)

# TODO

* does develop-eggs to a bad egg directory raise an error?
  * it should just warn
* support buildout plugins
* support buildout extensions?
* support inheritance
* make virtualenv relocatable at the end of the build process

## Tests TODO

* test to allow user paths in uranium script.
