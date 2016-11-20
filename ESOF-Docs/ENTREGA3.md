#Relatório ESOF - 3ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)


##Introduction to Software Architecture and the 4+1 Architectural View Model
  In this report we continue our review of this project's software architecture, taking a look at the design choices the developers took overtime and hopefully getting a better understanding of how they influenced the project either in a positive or negative way.
  We payed close attention to the implementation of any architectural pattern in this project, an [architectural pattern](https://en.wikipedia.org/wiki/Architectural_pattern) is a great strategy for the development of a project since it provides a standardized solution for a recurring problem. In this manner we took a look at the architecture of **Youtube-dl** and couldn't quite match any specific [architectural pattern](https://en.wikipedia.org/wiki/Architectural_pattern) however what we concluded was that it implemented some sort of hybrid design. We believe that this maybe be a result of the change in command and redirection of the project after [Ricardo Gonzalez](https://github.com/rg3) left, and a whole restructuring began.
  This hybrid stucture we observed comes from the fact that the whole program runs as a combination of modules that are executed thanks to a script, that script being **Youtube-dl** and makes it have some of the characteristics of a Repository.
  
##Logical View
  
  To keep the structure simple, **Youtube-dl** has separate folders for the different kind of packages. Within the repository there is a folder called youtube_dl which contains all of the source-code. Within that folder there are subfolders called **downloader**, **extractor** and **postprocessor**. 
 
 The related initializers can be found in **__init__.py** and each subfolder contains a **common.py** which holds the interface that is implemented by every class. For instance, each **extractor** implements the functions declared in the base class in extractor/common.py. The filenames of the different classes are clear, for example the extractor for YouTube videos is located in a source file called extractor/youtube.py. Here you can see Youtube-DL's [package diagram](https://en.wikipedia.org/wiki/Package_diagram):

![package_diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/PackageView.png)

##Development View
![Component Diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/Component%20Diagram.png)


Youtube-dl consists of a couple of components. These components and their relationships are visualized in [Component Diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/Component%20Diagram.png).
The main components are: 
* **YoutubeDL**: the core of the application. This component is responsible for the overall process. It processes the input, parsed arguments from the command-line and information from assumptions made by youtube-dl itself.  
* **Extractors**: responsible for gathering the information about the video. The extractors are able to extract video-urls from webpages through analysis (regular expressions for instance). The extractors provide the information in a pre-defined format so that it can be processed further by the *YoutubeDL* component.  
* **Downloaders**: the downloaders are able to transfer a remote video to the local filesystem. Depending on the media-format this component will determine which downloader to use.
* **Post Processors**: responsible for any post-download operations that should be applied on the video. Think of embedding subtitles, extraction the audio, etc.

##Deployment View
![Deployment Diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/Component%20Diagram.png)


##Process View

The process view is implemented through the usage of activity diagrams that allow the representation of data flow, the processing steps, etc. Th
