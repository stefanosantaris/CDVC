About

===============================================================================

This is a Java implementation of the framework presented in the paper "Similarity 
Search Over The Cloud Based on Image Descriptors' Dimensions Value Cardinalities, 
ACM Transactions on Multimedia Computing, Communications and Applications, Antaris, S.,
Rafailidis, D.".The goal is to perform an efficient similarity search strategy over the 
windows azure cloud infrastucture based o the dimensions value cardinalities of image 
descriptors. Using this code, one can re-execute the experiments described in our paper. 


Datasets

===============================================================================

Experimental evaluation has been performed on seven publicly available datasets of
image descriptor vectors. You can download the first 3 datasets (CIME 240k-64d, CEDD-240k-144d, 
SURF-240k-5000d) from http://www.imageclef.org/wikidata. 

The other 2 datasets of the TEXMEX collection (SIFT 1M-128d, GIST-1M-960d) can be 
downloaded from http://corpus-texmex.irisa.fr.

For the very large-scale experiments we have used the GIST-80M-348d dataset of the 
Tiny Image Collection and the SIFT-1B-128d of the TEXMEX collection, were you can 
download these datasets from http://horation.cs.nyu.edu/mit/tiny/data/index.html and
http://corpus-texmex.irisa.fr, respectively.

In order to conduct the experiments each dataset file should contain an image descriptor
vector per row and each descriptor should be comma separated. Each of the seven used 
datasets should be converted appropriately in order to re-run our experiments.


Usage

===============================================================================

Our framework has been implemented using the Windows Azure SDK 2.1. All framework's 
componenents are implemented in Java and the experiment were conducted using the Windows
Azure Emulator. In our implementation, the local storage and queue services were used. In
case of Windows Azure subscription exists, the storageConnectionString variable on each 
of our framework's components need to be modified.


In our repository, we provide the sourcecode of the proposed framework components.In order to
run our code, you need to perform the following steps :

1) download and install the Windows Azure SDK in your computer
2) install the Windows Azure plugin for Eclipse to appropriate configure and include the windows azure 
libraries on each of our implemented components. 
3) create Windows Azure Deployment projects for each of our framework's components. Each component is 
deployed to the windows azure emulator as a worker role. In doing so, you need to define in the
Windows Azure Deployment project the number of instances that each worker role is executed over 
the cloud. 
4) modify the number of numberOfDVCExtractorNodes variable in CDVC_Scheduler component according to the
deployed instances of the DVC Exctractor worker roles instances. 
5) modify the number of numberOfImageSorterNodes variable in PriorityIndexer component according to the
deployed instances of the Image Sorter worker roles instances.

We provide in our repository a CDVC_Initializer project which constitutes the user interface of our 
framework. CDVC_Initializer should not deployed to the cloud but it should include the windows azure
libraries since it interacts with the windows azure blob storage and queue service. Since the framework's 
components have been deployed to the cloud, you need to execute the CDVC_Initializer to execute our
experiments. 




