#Relatório ESOF - 4ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)

##Introduction

  In this report we will perform an analysis over the project and the verification and validation methods. We will analyse the methods used by the development team and contribute with our opinions about it, aswell as utilize our own tools to perform said analysis and verify if the project is being correctly validated.
  
  At first, we will evaluate the testability of the code in the context given and the implications of the organizations of the tests to the review of the code by de developers.
  
  At second we will try to find test statistics and analytics, using tools like [codacy](https://www.codacy.com/) aswell as using tools such as [PyCharm](https://www.jetbrains.com/pycharm/) for test running. 
  
  Finally we will explain how we found and solved a bug after analyzing Youtube-dl's **issues page**, why we choose that bug and how can you find new bugs in cases like this.

##Software Testability and Reviews

Being developed by a large community, **Youtube-DL** testing could become a mess. The developers went with unit testing exclusively: it's implementation is a good signal on its own. Given the software modularity, the unit testing structure it's easy to define, but also bearing in mind that many of the tests rely on external servers, it's almost as easy for one of them to break since the urls are forcibly hardcoded. This could be a problem as the url extractor could be working for a specific website but, because of a "defective" url, the software should fail the test.

It's very easy to identify and separate the tests and the results of each one of them. Some of the most basic are the _download_, _url_, _infoExtractor_ and _http_ tests which are easy to understand and very straightforward. Major bugs in the more fault prone functions of **Youtube-DL** (mainly extractors) can be cought running the _download_ test individually for each extractor but you have a "full test" where all the extractors are tested.

The pertinence of aproaches to some aspects sepcific to some extractor can be questioble. We can see this in tests as _age restriction_ wich exists only to check Youtube and Youporn and many Youtube related tests that can be small crumbs of old versions from the time when **Youtube-DL** only had the ability to download Youtube videos (_youtube signature_ and _youtube lists_). A different aproach could be the integration of the age restriction and playlists in the \_TEST variable of the default template wich is in the README file to be used by developers. That way the test would cover many more than one or two websites from seven hundred avaliable, and therefore, would be much more usefull.

Even though the code is being submmited from many different developers, the guidelines and the templates defined in the README file allow for the testing to be made the same way. So the testing of **Youtube-DL** is homogeneous.
  
##Test Statistics and analytics

 In the process of reviewing the software testability and project quality in the previous section, we ran the testing method developed by the team aswell as our own tests and tools to verify the condition of the project itself. In this section of the reports we will analyze these results and critise them in any way we find necessary.
  
  Using the knowledge we aqcuired in class to begin this review we easily concluded that any sort of **static verification methods** won't be effective since the code is logically organized in a very simple structure that leaves very few room for structural reviews, from a code perspetive as we came to discover most of the [project issues](https://github.com/rg3/youtube-dl/issues) are related to specific websites from which the software is trying to download.
  
  This is where **Software Testing** becomes relevant, here the developers have layed out some **Test Cases** as mentioned before
some of them became obsolete and are no longer relevant by several reasons, such as missing url or even geo restrictions. Here is an example of a test that is no longer valid because the website no longer exists.

  
  The team unit test strategy 
  Dynamic
    software testing
    Unit testing
    Coverage
    
##Bug
  
  While running the testing methods for the extractors of the websites provided we found that some of them didn't work. This was mainly because the website was redesigned, rendering the old extractor useless or simply because the authentication method changed. One which caught our attention, was **fusion.net**. Apparently, the link provided in the test area was still valid and the website had no authentication method, which was strangely unusual.
  
  //imagem do link para o fusion
  
  We searched the issue tracker and found that this was never reported, neither anyone had tried to fix it:
  
  //imagem do tracker
  
  We then tried to reproduce the bug and we managed to be able to get some information using **Youtube-dl**'s debbuger:
  
  //imagem do bug
 
 After this attempt, we decided to investigate what the problem was and we searched for the **fusion** extractor, named **fusion.py**. We noticed it used another extrator named **oolaia.py** and that the problem was 
  



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
2016/12/04
