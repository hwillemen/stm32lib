STM32 Cube library - CMSIS and HAL for C0 microcontrollers
=====================================================================================================

This repository contains a copy of STMicroelectronic's STM32 Cube firmware
library, with CMSIS-device and HAL code for the following microcontrollers;
STM32C0xx,

The ``vendor`` branch contains the original sources and is updated from
time-to-time when new versions become available.  The upstream sources are
provided as separate releases (and in separate archives) for each
microcontroller class (eg C0, WL, etc).  These are merged together here in
the "vendor" branch, because the idea of the HAL code is that it provides a
uniform interface to all microcontroller classes.  The commits in the ``vendor``
branch are tagged as appropriate with a tag that describes all the available
versions at that commit, for example ``C0-1.0.1+WL-1.1.0``.
The commit titles on the ``vendor`` branch should have the format ``import STM32CubeC0 v1.0.1`` or similar if applicable.

There are then working branches that branch at a given vendor tag and apply
minor patches to the vendor code, for example ``work-C0-1.5.0+G0-1.1.0``
The patches/commits that form a given working branch are reapplied (with
conflict resolution) to newer vendor tags to create the next working branch.
The commit title should clearly describe in short what has been fixed/improved/changed.

Original sources
================

The sources are obtained from ``http://st.com``, and also from the git
repositories found at ``https://github.com/STMicroelectronics/``.

Directories from the original sources are mapped into this repository according
to the following:
```
Drivers/CMSIS/Device/ST/STM32C0xx/Include -> as is
Drivers/CMSIS/Device/ST/STM32C0xx/Source  -> as is
Drivers/STM32C0xx_HAL_Driver/Inc ->          as is
Drivers/STM32C0xx_HAL_Driver/Src ->          as is
Documentations ->                            docs/STM32C0xx
```
And similar for the other microcontroller classes.
Be aware to not add a lot of large files to this repository/docs folder.
The following often needed documents are ok though:
```
Getting Started
Datasheets
Programming Manuals
```

Automation - future
================

With automation, the idea is to change formattting for all .c and .h files in a process before comitting:
- lines endings changed to unix style
- trailing spaces removed
- tabs expanded to 4 spaces
- non-ASCII chars converted to their ASCII equivalent

The included `fetch_from_upstream.sh` (run in bash) script can automatically copy and process
new source code from an STM git repository.
The calling format would be: `fetch_from_upstream.sh STM32C0 path/to/STM32CubeC0"
Where STM32CubeC0 is from https://github.com/STMicroelectronics/STM32CubeC0.git"

Listed repositories:
STM32C0    https://github.com/STMicroelectronics/STM32CubeC0.git
STM32WL    https://github.com/STMicroelectronics/STM32CubeWL.git
