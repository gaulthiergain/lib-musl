musl for Unikraft
===================

This release provides a functional version of musl (compiles and
links) on Unikraft but some functions are not supported (especially
the ones related to threads). Furthermore, some functions can have
unexpected behaviour since they use musl internal thread support.

## Build

In order to avoid multiple definitions errors, the following libraries
MUST NOT BE INCLUDED with musl:

* `lwip->socket`
* `pthread-embedded`

## Known Issues

* At this stage, we noticed that there are some issues with `ioctl`
and buffering on stdin. We are currently investigating these issues.
As things stabilize, we will update this file to reflect this.
* Some syscalls need to be implemented. Please have a look at the
following map:
https://people.montefiore.uliege.be/gain/unikraft/syscalls.png for
futher information.
* Due to missing syscalls, there is some unexpected behaviour
concerning threads.

## Further information

Please refer to the `README.md` as well as the documentation in the
`doc/` subdirectory of the main unikraft repository.