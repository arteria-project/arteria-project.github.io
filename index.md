The Arteria Project
===================

## Why?
Handling sequencing data from massive parallel sequencing can be a daunting task! And while the process of handling sequencing data will share many of its characteristics across centers, the current norm is one center one solution. This creates a situation where reuse is difficult to achieve and the wheel is invented over and over again. This is a situation that we hope can be remedied in the form of the Arteria project.

## What is this?
The Arteria project provides components to automate analysis and data-management tasks at a next-generation sequencing center. It leverages a micro-service based architecture together with [StackStorm](http://stackstorm.com/) to create an event-driven automation system, which is both flexible and scalable.

Arteria has two main components:
 
##### Single responsibility micro-services
These provide different functionality, such as running the Illumina `bcl2fastq` program, check if a runfolder is ready to be analyzed, or removes data once certain criteria are met. The separation to responsibilities between services means that you can pick and chose which ones suite your particular workflow and infrastructure configuration.

The catalog currently includes:

[arteria-runfolder](https://github.com/arteria-project/arteria-runfolder)  
Manages the state of an illumina runfolder by monitoring the status files output by the instrument. I also allows for state to be changed via the REST interface.

[arteria-bcl2fastq](https://github.com/arteria-project/arteria-bcl2fastq)   
Provides a REST interface for Illuminas `bcl2fastq` software. Includes a simple scheduler to efficiently be able to handle running of multiple bcl2fastq instances on a single server.


[arteria-siswrap](https://github.com/arteria-project/arteria-siswrap)    
Wraps Sisyphus - the quality control and reporting software used by the SNP&SEQ Technology platform.

 
[arteria-checksum](https://github.com/arteria-project/arteria-checksum)    
Runs md5sum checking and lets you know whether all files have preserved their integrity.

##### StackStorm packs
StackStorms concept of packs means that it's easy to redistribute automation components, and stitch these toghether into workflows. The Arteria packs can be found here: https://github.com/arteria-project/arteria-packs

## Who can use it?
You can! We've open sourced the Arteria project under a [MIT licence](http://choosealicense.com/licenses/mit/), and we hope that more organizations and individuals will join us in developing Arteria in the future.

## Who are we?
The Arteria project originated in the [SNP&SEQ Technology Platform](http://molmed.medsci.uu.se/SNP+SEQ+Technology+Platform/?languageId=1) node of the [National Genomics Infrastructure](https://portal.scilifelab.se/genomics/) at [SciLifeLab](http://www.scilifelab.se/).

![](https://ngisweden.scilifelab.se/site/logo-white-background.png)
![](http://www.scilifelab.se/wp-content/uploads/2013/09/82047_logo-green.jpg)