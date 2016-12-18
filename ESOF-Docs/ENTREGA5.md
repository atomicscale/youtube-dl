#Relatório ESOF - 5ª Entrega


![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)

##Introduction
In this last assignment we have as goal to evolve a feature in our project and document the process of doing so, while discussing **Software Maintainability** and the importance of software evolution.

In our lectures we studied the importance of software evolution, yet it was interesting to apply that to an open source project, because as we know software evolution for an organisation is essential in order to maintain bussiness competitiveness and is used as a more rentable way to continue evolving. Here we can observe a software in constant evolution process with no direct bussiness goals, and whose evolution follows the needs of the community. **Change requests** are many times called uppon by the users, or sometimes even implemented by them, leaving to the project owners to perform an **Impact analysis** and accept or not the implementation.

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
