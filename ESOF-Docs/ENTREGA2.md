#Relatório ESOF - 2ª Entrega

![youtube-dl image](https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images1/youtube-dl.jpg)


##Requirements Elicitation

This report has the goal to explain how the requirements for the project were born and how the team decided which method to use to implement new features. This basicly means the process of **requirement elicitation**, which in [requirements engineering](https://www.interaction-design.org/literature/book/the-encyclopedia-of-human-computer-interaction-2nd-ed/requirements-engineering) is an essential practice and consists in the collection of requirements from users, customers and personnel related with the project in any way in order to make them feasible functions of the software.
**A requirement is a documented necessity that the software must perfom.**

As stated in the previous **[report](https://github.com/atomicscale/youtube-dl/edit/master/ESOF-Docs/ENTREGA2.md)**, we talked with one of the founding developers, which explained us how the project was born as a very simple script, and how it expanded as soon as the users began requesting new features to be added.

<p align="right">
    <img src="https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images2/contributions.png" /alt>
    <em>It's possible to notice the increase in the contributions around the begging of 2013</em>
</p>

###The Scope

When we contacted the developers of Youtube-dl, specifically [Ricardo Gonzalez](https://github.com/rg3) one of the very first things he told us was that the initial idea for the project was a very simplistic one with a very simple goal: The ability to download videos from Youtube in a very straightforward fashion. This meant there was no software process model and therefore no prototyping nor requirement elicitation. Although this means our project is a little off to what we study in our Software Engineering lessons, we will shape this very unorganized process into the concepts we are familiarized with.

After Youtube-dl's **user count increased** the developers entered inadvertently into the process of Requirements Engineering. To put it into perspective, we can look at the original idea of **Downloading a video** as the "vaguely defined problem, and then through the **[Issues List](https://github.com/rg3/youtube-dl/issues)** on Github, users began requesting new websites to be added to the software capabilities that would be qualified as the actual "Requirement Engineering".

<p align="center">
	<img src="https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images2/issues.png" />
</p>

This was followed by an attempt at **implementation by the developers** themselves or through the public **[Pull Requests](https://github.com/rg3/youtube-dl/pulls)** on github.

<p align="center">
	<img src="https://github.com/atomicscale/youtube-dl/blob/master/ESOF-Docs/images2/pullrequests.png" /> 
</p>

The decision making process about the implementation of new features is now mostly controlled by a couple of developers that maintain a common vision for the project and are mostly focused on implementing **functional requirements**. These functional requirements were born mostly of **brainstorming** sessions and requests from users. We are unsure of the actual step by step process of decision making for this, however we are led to believe they follow a centralized idea and go through very basic processes of **elicitation, analysis and negotiation, specification and validation.**

As they do explain in their developer oriented [F.A.Q](https://github.com/rg3/youtube-dl#developer-instructions) :

> Pull Requests and new Features: Only post features that you (or an incapacitated friend you can personally talk to) require. Do not post features because they seem like a good idea. If they are really useful, they will be requested by someone who requires them.

> Issues and Developers Team: The youtube-dl core developer team is quite small. While we do our best to solve as many issues as possible, sometimes that can take quite a while. To speed up your issue, here's what you can do: First of all, please do report the issue at our issue tracker. That allows us to coordinate all efforts by users and developers, and serves as a unified point.

> User Count and earlier development strategy: Unfortunately, the youtube-dl project has grown too large to use personal email as an effective communication channel.


###Specific Requirements and Features

As the software in question started as a side project on [Ricardo Gonzalez](https://github.com/rg3) free time, the specificity of the requirements was very fluid, as it was implied in the previous [chapter](#the-scope).
Although, there were a few **nonfunctional requirements** well specified in the beginning:
	
	* Had to be reliable, always on (more reliable than websites or browser extensions)
	* Portability through OS's
	* Interface simplicity

These were the main bullet points behind [Ricardo's](https://github.com/rg3) first draft of the software in terms of quality. Making something that would run locally eliminates the reliability problem as it is always accessible. In order to be portable he wrote it in Python. The first version, which was around 100 lines long, ran virtually in any OS/hardware combination very smoothly. For the front-end he chose the command line as a GUI would be overkill for such a simple task and could harm the growth of Youtube-dl. Only a URL of the video was necessary as an argument at the time.

As we write this, many features were added but the same quality principles are being maintained by the development team.

In the beginning of the **requirements engineering process** the only **functional requirements** were:
	
	* Download a Youtube video from the URL inserted by the user as an argument.
	* Playlist transfer capability

As the process evolved, the main stakeholder group (in this case, end users) increased drastically as stated [before](#the-scope) and with them another set of **features** started to be requested through the issue tracker on github:

	* Support for website X (where X can be one of 700+ websites supported)
	* Video post-processing (quality, metadata, audio)
	* Website login capable (for websites wich require a user account/ marking videos as seen on Youtube)

With the new development team taking over after [Ricardo](https://github.com/rg3) the analysis and specification of new requirements became easier. Although, to prevent any copyright infringement, the validation process is still strict as the supported website list could enter a gray area in legal terms.








