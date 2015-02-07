About

===============================================================================

This is a Java implementation of the CDVC framework, presented in "S. Antaris and D. Rafailidis, Similarity Search Over The Cloud Based on Image Descriptors' Dimensions Value Cardinalities, ACM Transactions on Multimedia Computing, Communications and Applications, http://dx.doi.org/10.1145/2716315". The source code reproduces the experiments described in our paper.


Datasets

===============================================================================

Our experimental evaluation was performed on seven publicly available datasets of image descriptor vectors. The first 3 datasets (CIME 240k-64d, CEDD-240k-144d, SURF-240k-5000d) are available at http://www.imageclef.org/wikidata. Also, the 2 datasets (SIFT 1M-128d, GIST-1M-960d) of the TEXMEX collection can be downloaded from http://corpus-texmex.irisa.fr. For the very large-scale experiments, we used the GIST-80M-348d dataset of the Tiny Image Collection and the SIFT-1B-128d of the TEXMEX collection, publicly available at http://horation.cs.nyu.edu/mit/tiny/data/index.html and http://corpus-texmex.irisa.fr, respectively. Each dataset file should contain an image descriptor vector per row and the dimensions of each descriptor should be comma separated. 


Usage

===============================================================================

Our framework was implemented using the Windows Azure SDK 2.1. The framework's components were implemented in Java and the experiments were conducted using the Windows Azure Emulator. In our implementation, the local storage and queue services were used. In case that Windows Azure subscription does exist, the storageConnectionString variable on each of our framework's component needs to be modified.

In our repository, we provide the source code of the proposed CDVC framework. In order to run our code, the following steps are required:

1) download and install the Windows Azure SDK in your computer;
2) install the Windows Azure plugin for Eclipse to appropriate configure and include the Windows Azure libraries in each of our implemented components; 
3) create Windows Azure Deployment projects for each of our framework's components. Each component is deployed to the Windows Azure Emulator as a worker role. Also, in the Windows Azure Deployment project you need to define the number of instances that each worker executes in the cloud; 
4) modify the numberOfDVCExtractorNodes variable in the CDVC_Scheduler component according to the deployed instances of the DVC Extractor worker instances; 
5) modify the numberOfImageSorterNodes variable in the PriorityIndexer component according to the deployed instances of the Image Sorter worker instances.

We provide in our repository a CDVC_Initializer project which is the user interface of our framework. CDVC_Initializer should not deployed to the cloud but it should include the Windows Azure libraries, since it interacts with the Windows Azure blob storage and queue service. Since the framework's components is deployed to the cloud, you need to execute the CDVC_Initializer to run our experiments.r component according to the
deployed instances of the DVC Exctractor worker roles instances. 
5) modify the number of numberOfImageSorterNodes variable in PriorityIndexer component according to the
deployed instances of the Image Sorter worker roles instances.

We provide in our repository a CDVC_Initializer project which constitutes the user interface of our 
framework. CDVC_Initializer should not deployed to the cloud but it should include the windows azure
libraries since it interacts with the windows azure blob storage and queue service. Since the framework's 
components have been deployed to the cloud, you need to execute the CDVC_Initializer to execute our
experiments. 




