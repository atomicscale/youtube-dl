#Relatório ESOF - 5ª Entrega


![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)

##Introduction
In this last assignment we have as goal to evolve a feature in our project and document the process of doing so, while discussing **Software Maintainability** and the importance of software evolution.

In our lectures we studied the importance of software evolution, yet it was interesting to apply that to an open source project, because as we know software evolution for an organisation is essential in order to maintain bussiness competitiveness and is used as a more rentable way to continue evolving. Here we can observe a software in constant evolution process with no direct bussiness goals, and whose evolution follows the needs of the community. **Change requests** are many times called uppon by the users, or sometimes even implemented by them, leaving to the project owners to perform an **Impact analysis** and accept or not the implementation.

##Better Code Hub
After running the analysis on [Better Code Hub](https://bettercodehub.com) we found it did a pretty good job, obtaining 6 out of 10 on the metric system used.
This metrics, which will be explained in the following sections, evaluate repository's code quality based on the writing, organization and legibility using a grading system from 0 to 10.

![bettercode](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/initial.png)

###Write Short Units of Code

**This was one of the four metrics Youtube-DL didn't follow.**

Some of the most important functions on this code, such as Youtube's information extractor, contain well over 200 lines of code (249 in this case), which is way more than the 15 line recommended and the 30 line limit that violate Better Code Hub's guideline.

Besides some examples that we can find that are way over the line limit, we still think that, due to Youtube-DL's size and the amount of different contributors, the amount of times this happens is still quite small and we believe this could be easily updated by the main developers.

![shortunits](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/shortunits.png)

###Write Simple Units of Code

**This was one of the four metrics Youtube-DL didn't follow.**

This metric is based on the Mccabe Code Complexity Metric or [Cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity) which measures the number of linearly independent paths through a program's source code.

![simpleunits](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/simpleunits.png)

It's easier here to understand why Youtube'DL didn't pass the test.
If you can look at this segment of code, it's clear that the amount of If's ElIf's and for's here originates a number of branches way over the 5 maximum expected in this metric.

![extractelif](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/extractelif.png)

We also found out that this was a common practice in most extractors but not in the other sections of the code. Again, we little updates here and there we think it would be easy to fix this up.

###Write Code Once

**This was one of the six metrics that Youtube'DL did follow.**

Although Better Code Hub did offer us some refactoring candidates, more than 90% of the code is well written and does comply with what is expected.
Again, most of the information that is duplicated can be found in the extractors and this is due to Youtube-DL's extractor template that most developers use to add new websites.

![writecodeonce](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/writecodeonce.png)

###Keep Unit Interfaces Small

**This was one of the six metrics that Youtube'DL did follow.**

Besides some functions in the InfoExtractor that receive over eight parameters, in the remainder of the code functions only use at most two. This again doesn't violate Better Code Hub's limit number of parameters per unit to at most 4.

![keepunitsmall.png](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/keepunitsmall.png)

###Separate Concerns in Models
**This was one of the six metrics that Youtube-DL did follow.**

This one was obvious even before we saw the results. The main feature of **Youtube-DL** as a python coding example is its modularity. The extractors, downloaders and other parsers are separated and are independent. This gives the community the ability to add support for more websites easily.

![separateconcerns](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/separateconcerns.png)

###Couple Architecture Components Loosely
**This was one of the six metrics that Youtube'DL did follow.**

Having loose coupling between top-level components makes it easier to maintain components in isolation, as stated in Better Code Hub guideline. This was accomplished by by minimising the amount of interface code. It is also possible to develop components in isolation, in other words, being able to change only the component itself without changing what you don't want.

![couplearch](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/couplearch.png)

###Keep Architecture Components Balanced


![keeparch](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/keeparch.png)
###Keep Your Codebase Small
**This was one of the six metrics that Youtube-DL did follow.**

As described in Better Code Hub's guideline, "Keeping your codebase small improves maintainability, as it's less work to make structural changes in a smaller codebase". Youtube-DL does follow this guideline and it obtained a 175 man-month result, which is about 14.5 man-years and way less than the 20 man-year limit. A **man-year** is a method of describing the amount of work done by an individual throughout the entire year.

![codebasesmall](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/codebasesmall.png)

###Automate tests

**This was one of the four metrics that Youtube-DL didn't follow.**

For large systems such as Youtube-DL and it's 89,817 lines of code (notice that the large system criteria means more than 10,000 lines of code) the total lines of code should be at least 50% of the total lines of production code. Apparently the lines of test code make up about 4% of the total code, 3,271 lines precisely, which falls short in a huge difference.

![automatetests](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/automatetests.png)

###Write Clean Code
**This was one of the six metrics that Youtube-DL did follow.**

The amount of code smells we can find in Youtube-DL is substantially low, which means the developers did a good job keeping the code structured and organized.

![writeclean](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images5/writeclean.png)

## The Feature Evolution Process

Finding a feature to add to **Youtube-DL** was not an easy task. First of all because (as we said in the first report) the project does not aim to download videos from a single platform which involved a lot caution in order not to compromise the working status of all the url extractors. Then, we [noticed](https://github.com/yolonhese/youtube-dl#is-anyone-going-to-need-the-feature) that the present developer team was only accepting new features requested by the issue tracker on GitHub. Since we didn't noticed any feature missing from the software, the group decided to solve a request by a standard user. That way, even if only to a single user, it would be useful. 
Scrolling though the issue tracker the process of choosing what to implement was based on the opinion from one of the developers related to the issue relevance. So, being fans of the 4K resolution we took it personally to solve a [problem](https://github.com/rg3/youtube-dl/issues/11457) posted recently by the user [linglung](https://github.com/linglung). In **Youtube-DL** the users have the ability to find the first N Youtube videos based on the date of publishing and number of views. But since the Youtube extractor was created the platform grew to accommodate videos with specific HD or 4K resolutions and have properties as creative commons licensing indication. The goal is to implement a way to filter the auto downloading videos from the quick search by their resolution and licensing.

###**Identification of the files to edit**
After the identification of the feature to implement , it was time to find the source code necessary to edit to introduce the necessary changes for the requested feature.

So as one of the [lead maintainers](https://github.com/yan12125) said in the [issue](https://github.com/rg3/youtube-dl/issues/11457) :
>youtube-dl's search function is based on YouTube website's. 

So we logically tought that the file required to alter was the [youtube extractor.](https://github.com/rg3/youtube-dl/blob/master/youtube_dl/extractor/youtube.py)
This file is very content dense so finding if we should create a new class extractor or edit one was hard, but luckily the user that requested the feature mentioned that there was a similar feature already implemented.
> How to search any videos based on FEATURES filter such as 4K, Creative commons or 3D? i can see youtube-dl has ability to sort by upload date, min view etc but i can't find for features. e.g : **ytsearch:Chritsmas videos :creative commons**

With this we arrived at the following blocks of code 
```
class YoutubeSearchIE(SearchInfoExtractor, YoutubePlaylistIE):
    IE_DESC = 'YouTube.com searches'
    # there doesn't appear to be a real limit, for example if you search for
    # 'python' you get more than 8.000.000 results
    _MAX_RESULTS = float('inf')
    IE_NAME = 'youtube:search'
    _SEARCH_KEY = 'ytsearch'
    _EXTRA_QUERY_ARGS = {}
    _TESTS = []

    def _get_n_results(self, query, n):
        """Get a specified number of results for a query"""

        videos = []
        limit = n

        for pagenum in itertools.count(1):
            url_query = {
                'search_query': query.encode('utf-8'),
                'page': pagenum,
                'spf': 'navigate',
            }
            url_query.update(self._EXTRA_QUERY_ARGS)
            result_url = 'https://www.youtube.com/results?' + compat_urllib_parse_urlencode(url_query)
            data = self._download_json(
                result_url, video_id='query "%s"' % query,
                note='Downloading page %s' % pagenum,
                errnote='Unable to download API page')
            html_content = data[1]['body']['content']

            if 'class="search-message' in html_content:
                raise ExtractorError(
                    '[youtube] No video results', expected=True)

            new_videos = self._ids_to_results(orderedSet(re.findall(
                r'href="/watch\?v=(.{11})', html_content)))
            videos += new_videos
            if not new_videos or len(videos) > limit:
                break

        if len(videos) > n:
            videos = videos[:n]
        return self.playlist_result(videos, query)


class YoutubeSearchDateIE(YoutubeSearchIE):
    IE_NAME = YoutubeSearchIE.IE_NAME + ':date'
    _SEARCH_KEY = 'ytsearchdate'
    IE_DESC = 'YouTube.com searches, newest videos first'
    _EXTRA_QUERY_ARGS = {'search_sort': 'video_date_uploaded'}
```

After analyzing this we learned that the class **YoutubeSearchDateIE** is an extension of the class **YoutubeSearchIE**, and the only differences are the extra arguments .

Now that we pinpointed what to change we can proceed with the implementation of the feature.

----------
### **Implementation of the feature**

We read through the [**developers instructions**](https://github.com/rg3/youtube-dl#developer-instructions) carefully before starting.

We arrived at a tipping point :
**1-** we could implement a single class and with regular expressions extract the filters from the arguments.
**2-** we could create a class for each filter which would result in a different command for each class.

The consensus arrived was that although the correct way to implement this feature was the first one
with our limited skillset in **python** we decided to implement the alternative option.

This way the resulted code was 
```
class YoutubeSearchCCIE(YoutubeSearchIE):
    IE_NAME = YoutubeSearchIE.IE_NAME + ':creative_commons'
    _SEARCH_KEY = 'ytsearchcc'
    IE_DESC = 'YouTube.com searches by creative commons filter'
    _EXTRA_QUERY_ARGS = {'filters':'creativecommons'}


class YoutubeSearch4kIE(YoutubeSearchIE):
    IE_NAME = YoutubeSearchIE.IE_NAME + ':4k'
    _SEARCH_KEY = 'ytsearch4k'
    IE_DESC = 'YouTube.com searches by 4k filter'
    _EXTRA_QUERY_ARGS = {'filters':'4k'}

class YoutubeSearchHDIE(YoutubeSearchIE):
    IE_NAME = YoutubeSearchIE.IE_NAME + ':HD'
    _SEARCH_KEY = 'ytsearchhd'
    IE_DESC = 'YouTube.com searches by HD filter'
    _EXTRA_QUERY_ARGS = {'filters':'hd'}

```
 
--------------------

###Pull Request

It was created a pull request to the github project **youtube-dl**. During the implementation of this feature the group was closing monitoring the guidelines, to make sure we followed it. Altough the feature its simple and it could be more efficiently implemented its ready to use .

 





## Informações
    
    
      Autores:
      
          Bruno Marques (up201405781@fe.up.pt)
          Número de horas despendidas: 12
          Contribuição: 25%
          
          João Ferreira  (j.jofe2@gmail.com)
          Número de horas despendidas: 12
          Contribuição: 25%
          
          Simão Lúcio (simaolucio@gmail.com)
          Número de horas despendidas: 12
          Contribuição: 25%
          
          Vitor Esteves(up201303104@fe.up.pt)
          Número de horas despendidas: 12
          Contribuição: 25%
          
          
Faculdade de Engenharia da Universidade do Porto - MIEIC
2016/12/18
