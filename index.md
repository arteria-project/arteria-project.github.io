The Arteria Project
===================

[![Join the chat at https://gitter.im/arteria-project/arteria-project](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/arteria-project/arteria-project)

## Why?
Handling sequencing data from massive parallel sequencing can be a daunting task! And while the process of handling sequencing data will share many of its characteristics across centers, the current norm is one center one solution. This creates a situation where reuse is difficult to achieve and the wheel is invented over and over again. This is a situation that we hope can be remedied in the form of the Arteria project.

## What is this?
The Arteria project provides components to automate analysis and data-management tasks at a next-generation sequencing center. It leverages a micro-service based architecture together with [StackStorm](http://stackstorm.com/) to create an event-driven automation system, which is both flexible and scalable.

Arteria has two main components:
 
##### StackStorm packs
StackStorm's concept of packs means that it's easy to redistribute automation components, and stitch these toghether into workflows. The Arteria packs can be found here: [https://github.com/arteria-project/arteria-packs](https://github.com/arteria-project/arteria-packs). This provides an excellent starting point for building your own Arteria system.

##### Single responsibility micro-services
These provide different functionality, such as running the Illumina `bcl2fastq` program, check if a runfolder is ready to be analyzed, or remove data once certain criteria are met. The separation of responsibilities between services means that you can pick and chose which ones suite your particular workflow and infrastructure configuration.

The catalog of services of general interest currently includes:

[arteria-runfolder](https://github.com/arteria-project/arteria-runfolder)  
Manages the state of an illumina runfolder by monitoring the status files output by the instrument. It also allows for state to be changed via the REST interface.

[arteria-bcl2fastq](https://github.com/arteria-project/arteria-bcl2fastq)   
Provides a REST interface for Illumina's `bcl2fastq` software. It includes a simple scheduler to efficiently manage multiple bcl2fastq instances on a single server. 
 
[arteria-checksum](https://github.com/arteria-project/arteria-checksum)    
Runs md5sum checking and lets you know whether all files have preserved their integrity.

## Who can use it?
You can! We've open sourced the Arteria project under the [MIT licence](https://choosealicense.com/licenses/mit/), and we hope that more organizations and individuals will join us in developing Arteria in the future.

## Publications, Presentations, Blog posts, etc

We have a paper out describing Arteria which can be found here. [https://academic.oup.com/gigascience/article/8/12/giz135/5673459](https://academic.oup.com/gigascience/article/8/12/giz135/5673459)

[Roman Valls](https://twitter.com/braincode) has written two excellent blog posts related to Arteria which can be found here:

 - [Event driven automation for DNA sequencing centers with StackStorm and Arteria at UMCCR](https://blogs.nopcode.org/brainstorm/2018-03-12-umccr-arteria/)
 - [Productionalising cancer reporting](https://blogs.nopcode.org/brainstorm/2018-03-13-umccr-pcgr/)

We have been featured by StackStorm:

 - [Genomics Sequencing, StackStorm, and Reading the Source Code of Biology](https://stackstorm.com/2016/11/15/genomics-sequencing-stackstorm-reading-source-code-biology/)
 - [Case study of SciLifeLab](https://stackstorm.com/case-study-scilifelab/)

Arteria has been presented at Scientific conferences:

 - [Poster from AGBT 2017](https://drive.google.com/open?id=1Unc6FlwEaRigt1FmBFxm1Le7bAgUzT6C)
 - [Beyond Cron and Bash](https://docs.google.com/presentation/d/1qe_b9EwUuKw0HDgT-4l_2J_Vj5ROelcoUIdQCsOlnkQ/edit?usp=sharing) - presentation at the [Conference of Software Research Engineering in Manchester 2016](https://ukrse.github.io/conf2016)

## Who are we?
The Arteria project originated in the [SNP&SEQ Technology Platform](https://snpseq.medsci.uu.se/) node of the [National Genomics Infrastructure](https://portal.scilifelab.se/genomics/) at [SciLifeLab](http://www.scilifelab.se/). It has since been adopted at the [Clinical Genomics Uppsala at SciLifeLab](https://www.scilifelab.se/facilities/clinical-genomics-uppsala/), and the [University of Melbourne Centre for Cancer Research](https://mdhs.unimelb.edu.au/our-organisation/institutes-centres-departments/the-university-of-melbourne-centre-for-cancer-research)

![](https://ngisweden.scilifelab.se/site/ngisweden_logo.png)
![](https://www.scilifelab.se/wp-content/uploads/2013/09/82047_logo-green.jpg)
