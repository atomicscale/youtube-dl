#Relatório ESOF - 3ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)


##Introduction to Software Architecture and the 4+1 Architectural View Model
  In this report we continue our review of this project's software architecture, taking a look at the design choices the developers took overtime and hopefully getting a better understanding of how they influenced the project either in a positive or negative way.
  We payed close attention to the implementation of any architectural pattern in this project, an [architectural pattern](https://en.wikipedia.org/wiki/Architectural_pattern) is a great strategy for the development of a project since it provides a standardized solution for a recurring problem. In this manner we took a look at the architecture of **Youtube-dl** and 
  
##Logical View

  To keep the structure simple, **Youtube-dl** has separate folders for the different kind of packages. Within the repository there is a folder called youtube_dl which contains all of the source-code. Within that folder there are subfolders called **downloader**, **extractor** and **postprocessor**. 
 
 The related initializers can be found in **__init__.py** and each subfolder contains a **common.py** which holds the interface that is implemented by every class. For instance, each **extractor** implements the functions declared in the base class in extractor/common.py. The filenames of the different classes are clear, for example the extractor for YouTube videos is located in a source file called extractor/youtube.py. Here you can see Youtube-DL's [package diagram](https://en.wikipedia.org/wiki/Package_diagram):

![package_diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/PackageView.png)

##Development View

##Deployment View

##Process View

The process view is implemented through the usage of activity diagrams that allow the representation of data flow, the processing steps, etc. Th
