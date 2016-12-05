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

 In the process of reviewing the software testability and project quality in the previous section, we ran the testing method developed by the team aswell as our own tests and tools to verify the condition of the project itself. In this section of the reports we will analyze these results and critisize them in any way we find necessary.
  
  Using the knowledge we aqcuired in class to begin this review we easily concluded that any sort of **static verification methods** won't be effective since the code is logically organized in a very simple structure that leaves very few room for structural reviews, from a code perspetive as we came to discover most of the [project issues](https://github.com/rg3/youtube-dl/issues) are related to specific websites from which the software is trying to download.
  
  This is where **Software Testing** becomes relevant, here the developers have layed out some **Test Cases** as mentioned before
some of them became obsolete and are no longer relevant by several reasons, such as missing urls or even geographical restrictions. Here is an example of a test that is no longer valid because the website no longer exists.

![testfailed image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/file1.png)

![testfailed image2](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/file2.png)

If we run all the tests provided by the team we will get a result similar to this one:

![testfailed image3](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/testfailed.jpg)

These failures are most of the time caused by 404 errors or denied permission errors, it was through here that we came across the bug we later solved.

Being a command line applicaton some of the testing process is very streamlined, issues regarding interaction between modules are rare however issues within a specific extractor are where bugs concentrate.

Unit testing is this way a process that is quite similar to system testing, the **Unit Tests** the project conducts are very similar to **System testing** since in this context  they execute they evaluate the functionalities of the software diagonally crossing all major modules, but utilizing a specific [extractor](https://github.com/atomicscale/youtube-dl/tree/master/youtube_dl/extractor).

This makes the process of evaluating test coverage difficult, as we can see from these screenshots:
	
![coverage image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/pre-coverage.png)

![coverage result](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/pos-final-coverage.png)

This happens because a specific lines of code are only called in specific websites so this means to do an accurate **system test**, with the current structure we would have to download a video from every supported website, this makes the whole process tedious and complex and to implement an efficient testing process difficult.

We have no reason to believe **Integration Testing** is used in this project since it was stated several times by members of the project they are no longer working on introducing new modules, or even a GUI, focusing only on website support.
**Acceptance testing** functions a little bit through the issue list, and Github interaction of users reporting if websites are functional or not.

We also used [Codacy](https://www.codacy.com/) to review the code and get some statistics about it's organization.

 ![codacy](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/codicy.png)
 
 
 
 Codacy's evaluation of the files in the project, from A - F:
 ![codacy1](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/project_quality.png)
 
 Codacy's evaluation of the severity of bugs in the issue list:
 ![codacy2](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/severity.png)
  
 Here we see the files that raise the most issues within the community and their grading according to **Codacy** classification system, as we said before they concentrate around requests and problems with the extractor files.
 
 ![codacy2](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/issueslist.jpg)
    
##Bug
  
  While running the testing methods for the extractors of the websites provided we found that some of them didn't work. This was mainly because the website was redesigned, rendering the old extractor useless or simply because the authentication method changed. One which caught our attention, was **fusion.net**. Apparently, the link provided in the test area was still valid and the website had no authentication method, which was strangely unusual.
  
  ![fusionnet image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/Fusion-website.png)
  
  We searched the [issue](https://github.com/rg3/youtube-dl/issues?utf8=%E2%9C%93&q=fusion) tracker and found that this was never reported, neither anyone had tried to fix it.
  
  We then tried to reproduce the bug and we managed to be able to get some information using **Youtube-dl**'s debbuger:
  
  ![prebug](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/pre-bug.png)
 
 After a carefull analysis of the Bug trace call , we found out that the the file **ooyala.py** was throwing the error  **list index out of bug** , the conclusion was that the object was empty , so this meant that the **fusion extractor** was not calling this extractor correctly.
 The fusion extractor is rather simple and understanding the works was efficient, the problem in this extractor was that the regular expression used to search the webpage was not matched therefore the **ooyala extractor** call was passed with empty arguments.
 So to fix this we inspected the website html to find the regular expression and the tag that matched the video info we wanted.
  
  ![solved](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/pos-fix.png)
  
  ![posbug](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images4/after-bug-fix.png)
  
  After we implemented the fix, we submited a [pull request](https://github.com/rg3/youtube-dl/pull/11364), in order to integrate it into the main core. We are still waiting it to be reviewed and approved by **youtube-dl**'s team.

## Informações
    
    
      Autores:
      
          Bruno Marques (up201405781@fe.up.pt)
          Número de horas despendidas: 10
          Contribuição: 25%
          
          João Ferreira  (j.jofe2@gmail.com)
          Número de horas despendidas: 10
          Contribuição: 25%
          
          Simão Lúcio (simaolucio@gmail.com)
          Número de horas despendidas: 10
          Contribuição: 25%
          
          Vitor Esteves(up201303104@fe.up.pt)
          Número de horas despendidas: 10
          Contribuição: 25%
          
          
Faculdade de Engenharia da Universidade do Porto - MIEIC
2016/12/04
