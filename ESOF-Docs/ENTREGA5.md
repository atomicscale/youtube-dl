#Relatório ESOF - 5ª Entrega


![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)

##Introduction
In this last assignment we have as goal to evolve a feature in our project and document the process of doing so, while discussing **Software Maintainability** and the importance of software evolution.

In our lectures we studied the importance of software evolution, yet it was interesting to apply that to an open source project, because as we know software evolution for an organisation is essential in order to maintain bussiness competitiveness and is used as a more rentable way to continue evolving. Here we can observe a software in constant evolution process with no direct bussiness goals, and whose evolution follows the needs of the community. **Change requests** are many times called uppon by the users, or sometimes even implemented by them, leaving to the project owners to perform an **Impact analysis** and accept or not the implementation.

##Better Code Hub
After running the analysis on [Better Code Hub](https://bettercodehub.com) we found it did a pretty good job, obtaining 6 out of 10 on the metric system used.
This metrics, which will be explained in the following sections, evaluate repository's code quality based on the writing, organization and legibility using a grading system from 0 to 10.

////////////IMAGEM INICIAL BETTERCODE

###Write Short Units of Code

**This was one of the four metrics Youtube-DL didn't follow.**
Some of the most important functions on this code, such as Youtube's information extractor, contain well over 200 lines of code (249 in this case), which is way more than the 15 line recommended and the 30 line limit that violate Better Code Hub's guideline.

Besides some examples that we can find that are way over the line limit, we still think that, due to Youtube-DL's size and the amount of different contributors, the amount of times this happens is still quite small and we believe this could be easily updated by the main developers.

////////////IMAGEM SHORT UNITS OF CODE

###Write Simple Units of Code

**This was one of the four metrics Youtube-DL didn't follow.**
This metric is based on the Mccabe Code Complexity Metric or [Cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity) which measures the number of linearly independent paths through a program's source code.

//IMAGEM SIMPLES UNITS OF CODE

It's easier here to understand why Youtube'DL didn't pass the test.
If you can look at this segment of code, it's clear that the amount of If's ElIf's and for's here originates a number of branches way over the 5 maximum expected in this metric.

//IMAGEM IF EXTRACTOR

We also found out that this was a common practice in most extractors but not in the other sections of the code. Again, we little updates here and there we think it would be easy to fix this up.

###Write Code Once

**This was one of the six metrics that Youtube'DL did follow.**
Although Better Code Hub did offer us some refactoring candidates, more than 90% of the code is well written and does comply with what is expected.
Again, most of the information that is duplicated can be found in the extractors and this is due to Youtube-DL's extractor template that most developers use to add new websites.

//IMAGEM WRITE CODE ONCE

###Keep Unit Interfaces Small

**This was one of the six metrics that Youtube'DL did follow.**
Besides some functions in the InfoExtractor that receive over eight parameters, in the remainder of the code functions only use at most two. This again doesn't violate Better Code Hub's limit number of parameters per unit to at most 4.

//IMAGEM KEEP UNIT INTERFACES SMALL

###Separate Concerns in Models

###Couple Architecture Components Loosely

###Keep Architecture Components Balanced

###Keep Your Codebase Small

###Automate tests

###Write Clean Code

## The Feature Evolution Process

Finding a feature to add to **Youtube-DL** was not an easy task. First of all because (as we said in the first report) the project does not aim to download videos from a single platform which involved a lot caution in order not to compromise the working status of all the url extractors. Then, we [noticed](https://github.com/yolonhese/youtube-dl#is-anyone-going-to-need-the-feature) that the present developer team was only accepting new features requested by the issue tracker on GitHub. Since we didn't noticed any feature missing from the software, the group decided to solve a request by a standard user. That way, even if only to a single user, it would be useful. 
Scrolling though the issue tracker the process of choosing what to implement was based on the opinion from one of the developers related to the issue relevance. So, being fans of the 4K resolution we took it personally to solve a [problem](https://github.com/rg3/youtube-dl/issues/11457) posted recently by the user [linglung](https://github.com/linglung). In **Youtube-DL** the users have the ability to find the first N Youtube videos based on the date of publishing and number of views. But since the Youtube extractor was created the platform grew to accommodate videos with specific HD or 4K resolutions and have properties as creative commons licensing indication. The goal is to implement a way to filter the auto downloading videos from the quick search by their resolution and licensing.



## Informações
    
    
      Autores:
      
          Bruno Marques (up201405781@fe.up.pt)
          Número de horas despendidas: 10
          Contribuição: %
          
          João Ferreira  (j.jofe2@gmail.com)
          Número de horas despendidas: 10
          Contribuição: %
          
          Simão Lúcio (simaolucio@gmail.com)
          Número de horas despendidas: 10
          Contribuição: %
          
          Vitor Esteves(up201303104@fe.up.pt)
          Número de horas despendidas: 10
          Contribuição: %
          
          
Faculdade de Engenharia da Universidade do Porto - MIEIC
2016/12/
