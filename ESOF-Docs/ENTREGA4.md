#Relatório ESOF - 4ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)

  In this report we will perform an analysis over the project and their verification and validation methods, we will analyse the methods utilized by the development team and contribute with our opinions about it, aswell as utilize our own tools to perform that analysis and verify if the project is being correctly validated. //can shoudl add more//

##Software Testability and Reviews

Being developed by a large community, **Youtube-DL** testing can be a mess sometimes. Starting with the unity testing: it's implementation is a good signal on its own. Given the software modularity, the unit testing structure it's easy to define, but also bearing in mind that many of the tests rely on external servers, it's almost as easy for one of them to break since the urls are forcibly hardcoded. This could be a problem as the url extractor could be working for a specific website but, beacause of a "defective" url, the software hould fail the test.

It's very easy to identify and separate the tests. Some of the most basic are the _download_,_url_,_infoExtractor_ and _http_ tests which are easy to understand and very straightforward. Major bugs in the more fault prone functions of **Youtube-DL** (mainly extractors) can be cought running this, but it's not so easy to run them quickly and specifically for a single combo of _url/extractor_.


  
##Test Statistics and analytics
  Static
  Group review
  
  Dynamic
    software testing
    Unit testing
    Coverage
##Bug


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
2016/12/...

