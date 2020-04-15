# README

Members of the [OASIS Open Command and Control (OpenC2) TC](https://www.oasis-open.org/committees/openc2/) create and manage 
technical content in this TC GitHub repository (https://github.com/oasis-tcs/oc2arch/) as part of the TC's chartered work (the program of 
work and deliverables described in its [charter](https://www.oasis-open.org/committees/openc2/charter.php).

OASIS TC GitHub repositories, as described in [GitHub Repositories for OASIS TC Members' Chartered Work](https://www.oasis-open.org/resources/tcadmin/github-repositories-for-oasis-tc-members-chartered-work), 
are governed by the OASIS [TC Process](https://www.oasis-open.org/policies-guidelines/tc-process), 
[IPR Policy](https://www.oasis-open.org/policies-guidelines/ipr), and other policies. While they make use of public GitHub repositories, 
these repositories are distinct from [OASIS Open Repositories](https://www.oasis-open.org/resources/open-repositories), which are used 
for development of open source [licensed](https://www.oasis-open.org/resources/open-repositories/licenses) content.

## Description

All OpenC2 Profiles work within an implied architecture as well as a in a common language. The purpose of this repository is to develop a
specification of the standard architecture to guide all developers of Profiles. The OpenC2 Language Subcommittee is responsible for this specification.

This repository is organized with three branches:

 * The *_Working_* branch contains work product 
 material that is actively being developed, and 
 subject to potentially frequent and significant 
 change. Contributors to the work product should 
 target their inputs to the Working branch.

 * The *_Releases_* branch contains incremental 
 releases (i.e., Working Drafts [WDs]) of the work 
 product. The current contents of the Working 
 branch are merged into the Releases branch to 
 create a WD. 

 * The *_Master_* branch contains TC-approved 
[Committee Specification](https://www.oasis-open.org/policies-guidelines/oasis-defined-terms-2018-05-22#dCommitteeSpec) (CS) or [OASIS Standard](https://www.oasis-open.org/policies-guidelines/oasis-defined-terms-2018-05-22#dOASISstandard) 
versions of the work product. Until the first CS 
is approved, the Master branch will not contain 
a complete version of the work product.
## Contributions

As stated in this repository's [CONTRIBUTING](https://github.com/oasis-tcs/oc2arch/blob/master/CONTRIBUTING.md) file, contributors to this repository 
must be Members of the OASIS OpenC2 TC for any substantive contributions or change requests.  Anyone wishing to contribute to this GitHub project 
and [participate](https://www.oasis-open.org/join/participation-instructions) in the TC's technical activity is invited to join as an OASIS TC Member. 
Public feedback is also accepted, subject to the terms of the [OASIS Feedback License](https://www.oasis-open.org/policies-guidelines/ipr#appendixa). 

## Licensing

Please see the [LICENSE](https://github.com/oasis-tcs/oc2arch/blob/master/LICENSE.md) file for description of the license terms and OASIS policies applicable 
to the TC's work in this GitHub project. Content in this repository is intended to be part of the OpenC2 TC's permanent record of activity, visible 
and freely available for all to use, subject to applicable OASIS policies, as presented in the repository 
[LICENSE](https://github.com/oasis-tcs/oc2arch/blob/master/LICENSE.md). 

## Further Description of this Repository

*Any narrative content may be provided here by the TC, for example, if the Members wish to provide an extended statement of purpose.*

## Contact

Please send questions or comments about [OASIS TC GitHub repositories](https://www.oasis-open.org/resources/tcadmin/github-repositories-for-oasis-tc-members-chartered-work) to 
the [OASIS TC Administrator](mailto:tc-admin@oasis-open.org).  For questions about content in this repository, please contact the TC Chair or 
Co-Chairs as listed on the the OpenC2 TC's [home page](https://www.oasis-open.org/committees/openc2/).

## Preparation Note

Here is a customized command line which will generate HTML from this markdown file (named oc2arch-v1.0-csprd01.md):

pandoc -f gfm -t html oc2arch-v1.0-csprd01.md -c styles/markdown-styles-v1.7.3.css --toc --toc-depth=5 -s -o oc2arch-v1.0-csprd01.html --metadata title="Open Command and Control (OpenC2) Architecture Specification Version 1.0"

We are currently using pandoc 2.6 from https://github.com/jgm/pandoc/releases/tag/2.6.

This also requires the presence of a .css file containing the HTML styles (like styles/markdown-styles-v1.7.3.css).

