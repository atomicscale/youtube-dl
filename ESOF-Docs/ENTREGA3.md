#Relatório ESOF - 3ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)


##Introduction to Software Architecture and the 4+1 Architectural View Model

##Logical View

To keep the structure simple, youtube-dl has separate folders for the different kind of implementations. Within the repository there is a folder called youtube_dl which contains all of the source-code. Within that folder there are subfolders called downloader, extractor and postprocessor. The related initializers can be found in __init__.py for the given subfolder and next to that every subfolder contains a common.py which holds the interface that is implemented by all implementations. For instance, each extractor implements the functions declared in the base class in extractor/common.py. The filenames of the different implementations are clear, for example the extractor for YouTube videos is located in a source file called extractor/youtube.py. A graphical overview can be found in Figure 3.

##Development View

##Deployment View

##Process View
