This repo is for review of requests for signing shim.  To create a request for review:

- clone this repo
- edit the template below
- add the shim.efi to be signed
- add build logs
- commit all of that
- tag it with a tag of the form "myorg-shim-arch-YYYYMMDD"
- push that to github
- file an issue at https://github.com/rhboot/shim-review/issues with a link to your branch

Note that we really only have experience with using grub2 on Linux, so asking
us to endorse anything else for signing is going to require some convincing on
your part.

Here's the template:

-------------------------------------------------------------------------------
What organization or people are asking to have this signed:
-------------------------------------------------------------------------------
Vercot-Serva (https://www.vercot.com/~serva/default.html)

-------------------------------------------------------------------------------
What product or service is this for:
-------------------------------------------------------------------------------
PXE Server Serva 32/64

-------------------------------------------------------------------------------
What's the justification that this really does need to be signed for the whole world to be able to boot it:
-------------------------------------------------------------------------------
Serva is a well know PXE server

-------------------------------------------------------------------------------
Who is the primary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name: Patrick Masotta
- Position: Serva Developer
- Email address: masottaus@yahoo.com
- PGP key, signed by the other security contacts, and preferably also with signatures that are reasonably well known in the linux community: PM_PubCert.der

-------------------------------------------------------------------------------
Who is the secondary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name:
- Position:
- Email address:
- PGP key, signed by the other security contacts, and preferably also with signatures that are reasonably well known in the linux community:

-------------------------------------------------------------------------------
What upstream shim tag is this starting from:
-------------------------------------------------------------------------------
15 + 39b8345 

-------------------------------------------------------------------------------
URL for a repo that contains the exact code which was built to get this binary:
-------------------------------------------------------------------------------
https://github.com/rhboot/shim

-------------------------------------------------------------------------------
What patches are being applied and why:
-------------------------------------------------------------------------------
only changed DEFAULT_LOADER pointing to Serva's Boot Managers
DEFAULT_LOADER=\\\\BM\\\\PXESERVA\\\\EFI64\\\\pxeserva.efi
DEFAULT_LOADER=\\\\BM\\\\PXESERVA\\\\EFI32\\\\pxeserva.efi

-------------------------------------------------------------------------------
What OS and toolchain must we use to reproduce this build?  Include where to find it, etc.  We're going to try to reproduce your build as close as possible to verify that it's really a build of the source tree you tell us it is, so these need to be fairly thorough. At the very least include the specific versions of gcc, binutils, and gnu-efi which were used, and where to find those binaries.
-------------------------------------------------------------------------------
Debian GNU/Linux 9.3 (stretch)
GNU Binutils for Debian 2.28
gcc version 6.3.0 20170516 (Debian 6.3.0-18+deb9u1)
gnu-efi 3.0.8

-------------------------------------------------------------------------------
Which files in this repo are the logs for your build?   This should include logs for creating the buildroots, applying patches, doing the build, creating the archives, etc.
-------------------------------------------------------------------------------
build_Serva_Shim_x64_15+39b8345.log
build_Serva_Shim_ia32_15+39b8345.log

-------------------------------------------------------------------------------
Add any additional information you think we may need to validate this shim
-------------------------------------------------------------------------------
--
