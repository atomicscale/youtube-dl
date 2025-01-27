#Relatório ESOF - 3ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)


##Introduction to Software Architecture and the 4+1 Architectural View Model
  In this report we continue our review of this project's software architecture by taking a look at the design choices the developers took over the time and hopefully getting a better understanding of how they influenced the project either in a positive or negative way.
 
 We payed close attention to the implementation of any architectural pattern in this project: An [architectural pattern](https://en.wikipedia.org/wiki/Architectural_pattern) is a great strategy for the development of a project since it provides a standardized solution for a recurring problem. In this manner we took a look at the architecture of **Youtube-dl** and couldn't quite match any specific [architectural pattern](https://en.wikipedia.org/wiki/Architectural_pattern) however, we concluded that it implemented some sort of hybrid design. We believe that this maybe be a result of the change in command and redirection of the project after [Ricardo Gonzalez](https://github.com/rg3) left, and then a whole restructuring began.
  
  This hybrid stucture we observed comes from the fact that the whole program runs as a combination of modules that are executed thanks to a script, that script being **Youtube-dl** and makes it have some of the characteristics of a **Repository**. However the way it the inputs from several modules are transmited into others without a layered architecture, just a continuous data flow to execute the required funcionts leaves it much closer to a pipe and filters sort of architecture.
  So without neglecting any we believe this project follows this sort of hybrid between the two architectures.
  
##Logical View
  
  To keep the structure simple, **Youtube-dl** has separate folders for the different kind of packages. Within the repository there is a folder called youtube_dl which contains all of the source-code. Within that folder there are subfolders called **downloader**, **extractor** and **postprocessor**. 
 
 The related initializers can be found in **__init__.py** and each subfolder contains a **common.py** which holds the interface that is implemented by every class. For instance, each **extractor** implements the functions declared in the base class in extractor/common.py. The filenames of the different classes are clear, for example the extractor for YouTube videos is located in a source file called extractor/youtube.py. Here you can see Youtube-DL's [package diagram](https://en.wikipedia.org/wiki/Package_diagram):

![package_diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/PackageView.png)

##Development View
![Component Diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/Component%20Diagram.png)


Youtube-dl consists of 4 main components. These components and their relationships are visualized in [Component Diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/Component%20Diagram.png):
* **YoutubeDL**: the core of the application. This component is responsible for the overall process. It processes the input, parsed arguments from the command-line and information from assumptions made by youtube-dl itself.  
* **Extractors**: responsible for gathering the information about the video. The extractors are able to extract video-urls from webpages through analysis (regular expressions for instance). The extractors provide the information in a pre-defined format so that it can be processed further by the *YoutubeDL* component.  
* **Downloaders**: the downloaders are able to transfer a remote video to the local filesystem. Depending on the media-format this component will determine which downloader to use.
* **Post Processors**: responsible for any post-download operations that should be applied on the video. Think of embedding subtitles, extraction the audio, etc.

##Deployment View
The following diagram represents the relation between the software and hardware in the normal functioning of **Youtube-DL**.

![Deployment Diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/esof3_deployment.png)

**Youtube-DL** runs over any OS with the right Python libraries installed. Video files are downloaded trough HTTP requests between the user computer and the video server machine.

##Process View

The process view is implemented through the usage of activity diagrams that allow the representation of data flow, the processing steps, etc. This way, we present in the diagram ahead the Process View of the software in question. **Youtube-dl** functions as a center piece for several activities that execute a specific function, data flows from a couple extensions that check for user preferences and the website/download specifications, all the way to the core program, which will parse that information and execute the download.

![Process Diagram](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images3/viewdiagramfixed.png)

##Summary

It's important to let you know that both the diagrams and the ideas behind their making are solely based on the project interpretation's made by the authors. That said, it's possible that some of them may change in the near future (most likely, based on the project expasion route) and might have been different in the past.
We used the [draw.io](https://www.draw.io/) platform in the making of all our diagrams.

In the **logical view**'s package diagram we try to explain how the different packages interact with each other, their dependancies and how important **Youtube-DL**'s main package is.

In the **development view** package diagram we tried to have a better understanding at how the software components work with eachother and how it they evolve along with the software development.

In the **deployment view** we analyzed the hardware/software requirements interactions of the software looking over at how it behaves and what it needs to behave correctly from a machine standpoint.

And finally in the **process view** we saw how the software behaves and how data is transmited and flows within the internal stucture of the software, obtaining this way a better insight at how the developers mind organized and executed their vision.

## Informações
    
    
      Autores:
      
          Bruno Marques (up201405781@fe.up.pt)
          Número de horas despendidas: 8
          Contribuição: 25%
          
          João Ferreira  (j.jofe2@gmail.com)
          Número de horas despendidas: 8
          Contribuição: 25%
          
          Simão Lúcio (simaolucio@gmail.com)
          Número de horas despendidas: 8
          Contribuição: 25%
          
          Vitor Esteves(up201303104@fe.up.pt)
          Número de horas despendidas: 8
          Contribuição: 25%
          
          
Faculdade de Engenharia da Universidade do Porto - MIEIC
2016/11/21

