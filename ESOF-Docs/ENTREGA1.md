# Relatório ESOF - 1ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)
## Description of the project

**Youtube-DL** is a command-line program to download videos from YouTube.com and a few more [sites](http://rg3.github.io/youtube-dl/supportedsites.html). 

It requires the **Python** interpreter, version 2.6, 2.7, or 3.2+, and it is not platform specific, so it should work on **Linux**, **Windows** or **Mac OS X**.If you want to convert video/audio, you'll need **avconv** or **ffmpeg**. On some sites - most notably **YouTube** - videos can be retrieved in a higher quality format without sound. It will detect whether **avconv**/**ffmpeg** is present and automatically pick the best option. By default **Youtube-DL** tries to download the best available quality.

Once the video is fully downloaded, use any video player, such as **mpv**, **vlc** or **mplayer** to reproduce your files.

## Development Process

In order to know more about the development process of this project, we decide to inquire some of the top contributors (past and present) to try and acquire a closer and more personal look on the way it was developed.

After meeting with the workgroup members we wrote an email directed to them and awaited response. We were later contacted by the project founder and one of the main contributors of **Youtube-DL** [Ricardo Gonzalez](https://github.com/rg3) .

He went on to explain that the project started as a very short script to download videos from **Youtube**, it had no process model to follow, and no long term development plan. So with lack of organization or any sort of software development process soon Ricardo ran into an unanticipated issue :**modularity**. After receiving some feedback he quickly realized adding support to new websites was crucial. This raised some problems as the application was conceived only to download videos from *youtube*.Ricardo started to separate the operation into modules like: the downloader and the info extractor. The second one would find metadata from the video URL and the first one would download it in the user selected format.


After some time, things kept evolving in the same direction. The new developers separated the earlier designed code into modules, improving future error spotting, practicality and made it easier to add user requested features as download options, even though none of these were projected features and the project never really did fit any concrete design process some correct decisions were taken in an organic way. Some features however continue missing such as the a validation activity or a defined evolution plan.

## Opinions, Critics and Alternatives 

After an extensive review of the project, we found that for an open-source project that started as a straightforward youtube downloader, surprisingly it evolved into a **multi website** video downloader with many more features than the ones it started with.

Interestingly enough, around the date when the original developer, Ricardo, stopped working on **Youtube-DL** the community took over and there was a _boom_. Fortunately this went well, but could result in inconsistencies or even some redundant pieces of code.Maybe an alternative approach would be to elaborate a transitional plan to be implemented by the new “core team” where the growth wouldn’t be so all over the place. Instead this would lead to a more organized and well thought development process.

In the opinion of the authors of this report, the development process of the application, even though it wasn’t structured from the beginning, took advantage of the best part of the open source community. The constant feedback from users and the help of new developers created a structure that was organically put together by the community. This worked well in this specific case as the final result it’s more mature and well structured than the initial prototype.


## Informações
    
    
      Autores:
      
          Bruno Marques (up201405781@fe.up.pt)
          Número de horas despendidas: 5
          Contribuição: 25%
          
          João Ferreira  (j.jofe2@gmail.com)
          Número de horas despendidas: 5
          Contribuição: 25%
          
          Simão Lúcio (simaolucio@gmail.com)
          Número de horas despendidas: 5
          Contribuição: 25%
          
          Vitor Esteves(up201303104@fe.up.pt)
          Número de horas despendidas: 5
          Contribuição: 25%
          
          
Faculdade de Engenharia da Universidade do Porto - MIEIC
2016/10/16
