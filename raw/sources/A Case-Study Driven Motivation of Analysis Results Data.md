---
title: "A Case-Study Driven Motivation of Analysis Results Data"
source: "https://www.youtube.com/watch?v=tOCsvU7yaJM"
author:
  - "[[R in Pharma]]"
published: 2023-12-20
created: 2026-04-30
description: "Workshop recorded as part of the R/Pharma Workshop Series (October 19, 2023)Instructors: Joana Marques-Barros (Idorsia), Lukas Widmer (Novartis), Mark Baillie (Novartis)Resources mentioned in the w"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=tOCsvU7yaJM)

Workshop recorded as part of the R/Pharma Workshop Series (October 19, 2023)  
Instructors: Joana Marques-Barros (Idorsia), Lukas Widmer (Novartis), Mark Baillie (Novartis)  
  
Resources mentioned in the workshop:  
\- https://joanacmbarros.github.io/ardm-website/  
\- https://www.cdisc.org/events/webinar/analysis-results-standards-hackathon-kick  
\- https://www.cdisc.org/standards/foundational/analysis-results-standards

## Transcript

**0:00** · I think we are sharing good looks perfect good um so that's very nice introduction thanks pH um so welcome everybody um we're here today on this

**0:15** · very first time we're actually running this workshop and my name is Joanna you'll be the one that you'll be hearing the most uh but we also have facilitating the workshop Lucas and Mark and they'll be more in the but in the backstage handling or questions uh I want to do just a tiny bit of housekeeping in addition to what Phil already said let me start the slideshow there we go so besides checking if you have

**0:43** · access then to the posit Cloud um and besides checking that you have the slider link and access to the zoom chat we also um would recommend to have some pen and paper or the digital version of it um it's it's good to have some place

**0:58** · to take notes we plan on making this Workshop a bit a bit of a thinking type of Workshop so this might be helpful um we we also know this is a 2hour well you should know this is a two-hour Workshop not too long but either way have some water coffee or tea whatever you need at already so to start

**1:23** · I would say let's move over to slido first because we think the best way to start is actually to get to know you a little bit um in fact getting to know what you know about analysis results data and about the analysis results data model so if you go over to slido I'm going to start now a series of polls I'm

**1:46** · going to um Joan I'm gonna add everybody real quick or just provide the uh user link just give me two seconds sure to do that here um yeah on top of that sorry about that forly forgot about this on the top right of the slide that you're seeing right now you have the QR uh image there if you want to join via smartphone on slider you can scan that if not you can go to slido.com put that number there or you will buy the link that uh is going to be posted in the J Zoom shot yep it just provided

**2:18** · it mishap but yeah plenty of ways of draing slid so I give a few minutes to join in you know can see that some people are already responding it's very

**2:48** · good okay so I'm going to start checking some of the results that we are having and I think you should all also be able to see some of the results that we're getting as soon as you finish the poll you should be able to see it also in real time have Lear 20 people that are responded so far and right now no is winning so not that many people know about okay no never mind it's 5050 now a perfect

**3:27** · split okay few more seconds because there's still quite a few people

**3:43** · responding okay seems like the not is picking up speed so not that many people well the majority of people here are not too familiar about analysis results data not a problem because we go over it obviously um experience with the with an

**4:00** · all results data or all's results data setes we see that not that many people have experience they're actually hoping on getting started today that's good to know and also quite a few people that heard about this before but didn't really use them and some that use them privately that's also good now about the analysis results data model we have also vast majority people do not know what this is not surprising it's even more of a well it's more and anything else to be

**4:32** · fair and then if we go to what you hope to learn from the workshop okay whether the analysis results data model could be applied to pharmacometrics okay basic concepts getting familiar with it basic understanding how to improve my statistical modeling workflow not sure well at least we're getting to know a bit about it so and how others are using analysis results data okay

**5:00** · that's good I'm going to stop then this poll now so it seems like um there's quite a few people that don't know what anal results data is even less people know what analys results data model are but people seem to be interested and curious and there's uh seems to be quite a bit enthusiasm thank you for responding to the poll we'll be running a few of these throughout today and it's really really

**5:28** · nice to see that you're participating okay so why are we even running this Workshop so first of all we got an invitation from the or Pharma committee and we are very thankful for that so when we got that invite it immediately kind of sparked a bit of it showed us that this could be a way for us to increase the visibility for the topic of analysis results data um and

**5:56** · also for the analysis results data model this this something that we worked on starting a couple of years ago and um specifically for the analysis results data model we think that the way to have this idea evolve is to actually hear from the community that would be using it so that's a key reason also for running this Workshop we are very very interested in hearing what you have to say about uh the ideas that we're putting forward here and we want to use

**6:29** · that idea those ideas to shape how the ardm should be I also want to make a bit of a disclaimer here some of you that said that know what analysis results data is and even what the analysis results data model is um I think some might might be

**6:48** · because uh you're aware of what cisk is doing in this area with the analysis results standard um the disclaimer here is that this is this Workshop should be viewed as something separate from cisk we are not proposing a standard we're not telling uh you that this is what we think is a good solution or what we think is a solution we are more interested in viewing um this for more

**7:14** · of a consumer level thinking about what is useful for us testing our ideas seeing them fail even and going back to the initial stage to the drawing board and change everything so there's really no barriers um it's more about building consensus

**7:34** · and see how to move forward um that's that's the key so now for the learning outcomes that we have prepared for this Workshop it's uh it's matching quite a lot of of what you answered in the survey so we really hope that by the end of the workshop those who don't know what analysis results data and analysis results data model or I hope that you then know a bit more about this um and

**8:05** · we hope as well that you can appreciate a bit the problems that the ardm tries to address and see if that actually fits uh some of the or benefit some of the areas that you work on and finally one of the last uh outcome learning outcomes is to understand how you actually start building your your own um ardm

**8:32** · so for the agenda today just for you to have an overview of what we're going to talk about um the first hour more or less it's going to be more of an INT introduction to the topic um and then we'll have a small break and this is then the second part is going to be focus more on the exercises um in in between we have um or

**8:54** · especially after each exercise you're going to have a questions um open questions basically so we will go over to slid and select a few and before the break and maybe a few times in in between the different areas of the first part you can also have some questions uh question and answer sessions okay so for to make sure that

**9:17** · everybody's on the same page um I'll do a brief introduction of what is analysis results data and what is the analysis results data model and then we'll go into more detail about the data model uh in a few minutes so about analysis Resorts data now I want you to think that every single time that you are um running an

**9:41** · analysis you're actually producing uh data but this takes the shape of results now normally when we think of um of results we tend to associate it more

**9:58** · with how we present the results so something like you have here on the left uh sorry on the right side on the data product on this plot this is what we associate results things or in this case products that we create to show the results to others plot tables for

**10:17** · example we normally don't think about the data sets for example the actual data that we have um when we run the analysis and this could be for example a similar data set as you see here on the left side um so like a data set um so if you start looking

**10:40** · at analysis results as data meaning as these data sets rather than these products these plots there's a few um questions that start coming up so one one thing is that you you might have to or or once you start formalizing the way that you view analysis results as this this sta there's a few things that c that have start coming up and one is you might have results

**11:14** · appearing and many different ways even though you're performing the same analysis this could be because uh you're using um different function could be that you're using um also so um different libraries different packages and different functions within those uh packages it could be because you're using a completely different programming language so the structure of your result

**11:42** · is going to change so you might have something that uh data sets that are resultant from your analysis that are they're resulting from your analysis that might have different column names that uh the structure itself of the data set changes might be in a more long format so that brings the question of why wouldn't you bring some um let's say harmonization to this why would why don't we have um a way of

**12:15** · making sure that if we run an analysis the results would always appear in a certain way because if we have that if you have let's say a standard around this uh we can then reuse the results because we know that they're going to be an expected form there always going to be an an expected um

**12:37** · coherent um structure that we can then exchange with others and that we can also build um tools that work on top of that structure so this is more or less what we mean when we talk about analysis results data and analysis results data sets um and to think when you think about the analysis results data model think about

**13:05** · it as a extension to to the nalys resorts data um is an extension and it goes a step so it goes a step further this is because if you think about the these data sets that I showed you before so these ones here you might think that um well they they all come from from the same analysis because I told you that they all came from the same analysis um but

**13:37** · you don't know exactly the details behind that analysis so you know they are different but they don't know why you don't know why they are different so what's missing here is contextual information information that allows you to fully understand how those results were created so that you can even be able to reproduce those results if needed so that's what the analysis results data model touches on and and capturing this uh contextual information

**14:10** · and you can can capture this by looking at everything that stems from the analysis so when you do an analysis you have the results like we said but you also have information about the analysis itself so you have like we mentioned the programming language that you run the analysis on uh you have

**14:34** · um the um libraries for example that you used functions the parameters that you specified in those functions you also have um you also uh can record information about the data that was input if you actually applied it to only apply that analysis to only a section of that data or for all the data if there was any filtering process done for example so the data model plans the idea

**15:06** · of it is to capture all of this information Define how to structure it so Define how we actually keep it the structure of the data sets let's say and standardizes how all the information links to one another um but we'll go bit more into detail uh

**15:28** · which a few more uh figures that make it easier to understand so this is the overall idea to have uh about analysis results data and the analysis results data model now this all seems very

**15:48** · complicated so one question that you might have is why should you care why why should you care about something that's so complicated um we'll go going into a few more reasons a it later um but first I want to talk you about talk to you about a situation that happened not that long ago um actually at a recent uh stats

**16:13** · conference and these were basically a group of people they were presenting the work that they did on um simulated um simulating realistic uh survival data or simulating realistic survival data and for that they would they needed as part of their study they needed to have Benchmark survival data so they went into the scientific

**16:42** · the repositories for scientific uh literature and they found um scientific papers that were uh that reported on U analysis survival analysis that were and all of the results that they found or the majority results that they found were actually presented as K Meer

**17:08** · plots so they didn't have the actual data they only have the figures so what they had to do to be able to get enough information for their benchmarks was what you're going to see here in this video um this is not a video of them this is a video of a that mimics a process that they had to do so for each plot of each scientific paper and these were like dozens of them they had to take a

**17:39** · screenshot go to an external software they had to then map the axis they had um then to map on top of it every single dot

**17:55** · that they that was part of the survival curve that was showing up and the only reason they had to do this is because again the results were stored and were presented just just as these plots there was no additional information about the actual data that

**18:14** · was used to produce these this product these plots and the reason why this happened is because it's it's in our mindset it's in our mindset to think that the result of an anal is going to be some kind of product it's going to be plot a table it's going to be a presentation that we do to somebody it's going to be a report and it's not it's actually the

**18:44** · data so can move forward now so myself Lucas and Mark met uh when I was doing a short-term program at es and one thing we all shared was that we thought reviewed analysis results as actual data and we saw that doing this was

**19:12** · already doing this was was first of all allowing us to have results that were machine readable and by default this was already lifting a lot of barriers because we could then start reusing results instead of repeating analysis and we could continue the

**19:34** · knowledge Discovery process because of this ability to reuse the results right think about metaanalysis for example if you could easily then perform that because you have actual data other than going through um again for example bunch of literature to find the results that you need and to extract them in a way that you can uh actually read them in your programs it was much easier to have them as data not as these

**20:06** · products so because there was a lot of ideas around this topic uh we decided that the best way to kind of wrap everything was to write a paper and this is when we also started thinking a little bit more about um this context that surrounds results and that we should keep this information as well to make sure that we can reproduce the results um so we wrote a paper and um you might

**20:40** · see that there's another author in that paper Simon he's not uh here today but he was a very important part of the yeah the thinking process that uh LED for us to think about the or DM um this Workshop is is going to just

**21:00** · touch just the surface of what we have on the paper so I if you find it interesting or if you have um additional questions or if you want to dig a little bit deeper I think this is a very good place to start um to have a look at the paper in in depth um as part of this

**21:18** · paper we also have a repository um with a code repository that has um um let's say suggestion for the analysis results data model or the first the first concept that we had um that's that is um more detailed than what we're going to do today so again highly suggest you to have a look at this

**21:47** · afterwards okay so we can now go a bit into more detail for the reasons why we would need an analysis results data model so we already mentioned that every single time you're doing an analysis you are producing data and the shape of results now we don't really think about it like that like I said we think about how we present results to others plots tables are very common ways um but we

**22:19** · also saw that if you focus on uh viewing results as these products it becomes very very difficult um if not impossible to reuse them and this wouldn't be a problem if we did not reuse them but we do even in clinical development you might be you might have result of the

**22:42** · analysis uh or you might have your analysis results and then from there you produce uh a plot and you put it in the CSR and then you want to have a different version of that plot you want to reformat it a bit want to match some colors uh and you want to add that plot to an internal presentation that you're going to give to another group but we normally don't have the date itself you would have to redo the analysis and then do the plot

**23:15** · again so if we have these these data products this plots instead of having the actual data if you want to reproduce something thing you're or you're left or if you want to reuse uh results you're kind of left with three options you saw the the

**23:35** · video that was one of them so if you only have access to the to the actual product let's let's let's say a plot it's the easiest uh way of thinking about this let's say you only have access to the plot which is what that group of people only had access to they could only have access to a k Meer and then not have any information about um the results themselves you had to reverse engineer the plot

**24:01** · like they did with that software toble to extract each data point the second option would be you might have access to some document that is detailing um the analysis that was

**24:20** · performed so you might try to just reproduce that analysis rewrite that analysis and see if you get the same results um since you can produce the same plot to verify if you have the same results but what what what tends to happen here uh and a lot of people don't fully understand it initially is that when we even when we document an analysis there is a lot of um small decisions that are

**24:54** · made that tend to not be recorded so these could be decisions that are made for example because of someone's expertise you might be an expert in a certain area might perform that analysis and you make some decisions and you don't necessarily log them in detail you

**25:12** · don't write them in a plan in detail because you think that well should be things that because you forgot or because you think that it's not too relevant to write because it should be obvious for example um you might have the case um

**25:30** · where um it's just because of the data you realize that there are some changes have to be done in the analysis and you adopt it but you don't fully record that in a plan so that means that you don't have the complete picture needed to fully redo

**25:46** · the analysis and get the same results right and all of this is assuming that you have access as well to the data that was used to to where the analysis was performed then you you have the third option it would be that you actually have a script that contains all the

**26:05** · steps of the analysis um you have access to the data that was uh that was analyzed so you think you're you're able to fully reproduce what you're doing but then of course if you don't have information about parkage versioning and the environment that was used you're going to have a lot of problems to try and reproduce that and of course we're all making we're continuously making um

**26:34** · improvements and all these areas but this is something that um still happens a lot okay so there's a lot of conditions that that we have to meet um so what we think is that again we have to Pivot our mindset reframe the target of the anal analysis to actually be a data source that you can reuse and that you can

**27:04** · easily access as well and if you start thinking about results then as data it it opens um opens the door to a lot of ideas that come from other areas like data management and data stewardship and um for example one of the key concepts of data management is to actually have data models that structure how the information um is um stored let's say

**27:36** · and what information is actually kept and how does that do that pieces of information relate to one another okay so um I don't know if there is a lot of questions if I should continue then we stop before the break think I think U most have just been comments about the video and paper uh so I think if you want to keep going okay fine okay now I'll go into the ardm

**28:09** · in more detail then so this figure that you're seeing here is uh one figure that comes from the paper actually um and when when we talk about an

**28:26** · analysis data model um we actually are referring to to this and you can see very easily that is not just the data model it has three pillars um so it has this standard input and this basically means that when you're performing in analys analysis the assumption that the assumption is that you're using um data that um or Source data that

**28:58** · uh follows an expected structure and this some something that we already have with the cisk standards like Adam and stdm then the second pillar here is the analysis standard and this is a bit more complex and I would say this is something that it's not um still still a bit not as polished

**29:26** · as as as the rest of our ideas uh and the but but the idea behind it overall is that you should be able an analysis standard is a way of abstracting an analysis into a collection of steps so think about when you're doing an analysis there's First Step which can be loading the data then you

**29:54** · have um for example selecting certain variables then you might fit a model and then you might do some Tiding at the end so the analysis standards would be then a collection of these steps of loading selecting um fitting and tidying and then the last part is the the data model and this is again what the workshop is also going to be focusing on and this is uh like I mentioned before is this um way way of

**30:28** · really formalizing which information we keep um relating to to an analysis and how to structure that and how to link all that information with with one

**30:44** · another uh okay good so before I'm moving to the next slide I want you this tends to help people when they're thinking about um how the data model works so normally let's just use it as an example that you have a database and that b database is going to be used to store um your results of your

**31:14** · analysis and you want to make that um as um fitting to your needs as possible so you want to make sure that the way you're storing your results is not allow not only allowing you to reuse them but to also reproduce them if needed so you're going to build a data model you're going to specify what information you're keeping about the analysis how to structure it and how to connect that information so think about that

**31:43** · your database is going to have four tables those four tables were defined by the data model as being a table for the study information called studies another table for demographic variables stores information from demographic variables a third table for the analysis Metadate so information about the analysis itself and then um another table that stores

**32:12** · the results this analysis results data set let's say specifically for descriptive analysis so you could have a different table as well that would store the results of another analysis like a survival analysis so your data model defines these four tables and it also defines what information should be kept

**32:37** · there so we see that for the studies we have a name and uh in this case an example of one of the arms for that study and it has an ID as well um a unique identifier then for the demographics You' have then the name of that variable

**32:56** · if it the unit if it's continuous or discrete and then we this example here we have the correspondent the expected correspondent correspondent column name in the itom data set and again a unique identifier for that specific demographic variable then we have the metadata for the analysis and you see that there's a little bit more information here collected about the person who run that analysis one that was run with after we

**33:27** · use uh was used um which package and then again we also have an ID and finally on the last table we have the results and this is where we started to link all the other three so each result also has a unique ID and you see here that you have a link to the analysis uh

**33:55** · metadata you have a link to the study ID uh and to the demographic variable ID exactly and then you have the actual results being stored so when you think about uh a data model being used think about something like this that you have a database that follows exactly what you modeled in the data model so keep this in mind for um the

**34:25** · exercises that will come later uh because this tends to be um um this tends to be very helpful for people another thing that tends to be helpful um and it helped us as well when we were writing the paper which is to think about a few principles and we specifically again in that paper we wrote These six principles so this helps you to guide help help

**34:56** · help us guiding um help us in um the having an clear outcome for the ardm so the first principle is searchable meaning the at the end goal is to have um a consistent way of searching over information of finding the results that we need uh of querying uh consistently uh via other in

**35:26** · be able to use other tools such apis again having a database that follows this this data model the second principle is uh non-redundant meaning if we have the results stored

**35:43** · and information as well about the analysis it shouldn't be any need to repeat an analysis unnecessarily if we have the results store then we can just reuse them and this is quite important because if you reuse results and if you know if you have enough information to understand their context how they were generated it means that you have a single source of Truth um that means that those result that analysis that generated those results could also have passed the validation process and the results that

**36:16** · you have shared that you have um um stored are actually again already validated in the products that you do with them different plots different tables they already coming from validated results so you don't need to validate things second time for example so you have this source of

**36:39** · Truth the third thing is a separation of concerns and you saw that the way the analysis results data model works is by separating every piece of information into their own let's say table just to make it a bit easier and this means that

**37:02** · you can separate the analysis then from the information that you have about the actual data itself and then the results or the study itself then the results but it also facilitates adding um additional information if needed so let's say that your original data model only has four tables but then you realize that you have different analysis that uh produce completely

**37:28** · different results that don't fit the tables that you already have so you have to add a few more and that's not a problem as long as you can link everything the fourth principle is rep

**37:45** · being reproducible uh again this goes into keeping enough contextual information about the result itself and that and specifically about the analysis that you can actually reproduce the entire workflow then interoperable meaning it shouldn't matter for example which programming language you're used you're using as long as you're able to um you should always be able to kind of format the result into the structure

**38:17** · that is defined by the model um so that means that it's easy for you t to have again this this unique location where you have results that might have come even from different um from different languages and they're still you're still you're still able to reuse them then the last um principle is

**38:46** · Community Driven so you probably realize by now that there's a lot of uh source of U there's a lot of ways that um there's a lot of variations into the way you can create a data model an analysis results data model so we really think that to evolve the data model and to shape it into a solution into a better solution and something that fits um the community then we should be

**39:17** · taking feedback from the community we should be able to uh build it in a way that incorporates the the different opinions but at the same time reaches a consensus as well so the idea here is that this is designed by and for the community um okay so that's i' say it for the

**39:46** · first part of the workshop I think now good time to have some questions before we go for let's say five minute break so I don't know if Mark and Lucas you find a few questions that came

**40:08** · up yes Joan can you hear me okay um yeah I can hear you yeah I think the first question is from um Karan and this maybe just a typo in the slides it's the question was from where was analysis meta data ID coming from in the last table so this is the the four tables prior to the principles yeah I think you know what you're mentioning I also realized so this this

**40:34** · sorry this should not be one M1 this should be a M1 coming from here that's that's well spotted thank you and I think Thomas picked that up as well so thanks Thomas um and then the second question is from Paulo is um you may not want to have everyone have full access to all information would you consider accessibility permissions as part of the ardm model uh yeah I think that that makes

**41:00** · complete sense um there's something as well that we have um highlighted a bit on the paper um because this having that type of permissions would enable you to share it for example with uh yeah with different parts of the company uh for example if you do it internally that might not have need to have access to certain details or even have access if you ended up storing as well um subject level uh data then you could keep that

**41:31** · uh from being accessible for certain people yeah that's definitely a good point here uh yeah sure go ahead Mark and this is again from Karen um you mentioned this model is following guidelines but it's separate from cisk am I understanding this correct also where do I find the latest guidelines on this so Lucas and I have um provided links to

**41:58** · the cisk AR but maybe you could comment on the first part around this being separate from cisk um yeah sure so this this is separate from cisk um so we're not following the same guidelines we actually started to work on this before the standard from cisk was published so there was no guidelines at at that time uh what we have is these principles that

**42:22** · kind of we kept this in the back of our mind when we thought about the erdm but there are no like solid um from our side at least there's no solid guidelines in sense of it has to be done in this way and and this is the

**42:39** · recommended way to do this and that so we don't have those guidelines uh at least we we don't have concrete ones um so this is completely separate from from cisk um and I think yeah exactly Mark and LU has already sent uh put post it on the chat the link for the standard uh from cisk and they they do give some guidelines into how and their view how they uh how this uh data model should um yeah should should take shape

**43:17** · basically okay so if there are no more questions I think I will continue uh let me start sharing the screen again there we go

**43:37** · perfect so let me move forward here so we have at break and now we move on to the case study and for our case study we are going to touch um on the capin my plot um so every every exercise is going

**43:53** · to be around this and we want to make also uh something clear is that the exercises are going to be they're not going to go into too much detail just because they can get very complex very fast so this is more like a starting guide um and uh they'll focus

**44:13** · on performing data analysis having um keeping in mind the idea of analysis results data and uh creating an analysis results data model in the process building a simple ardm and we will explore uh

**44:33** · the principle or the idea of the reusability of results and we had here if time permit the interoperable principle that that we um touch on before but we might not have sufficient time for that so we'll see how the two first exercises go so why are we focused on a k and wire plot um it this might seem um so first

**44:59** · of all the cap my part did have a bit of a rough start let's say it was not something that um uh was immediately uh accepted but nowadays it is very much U part of um is a very much

**45:19** · it's a a graphical display that appears um in many many uh types of indic ations to this place arrival data um and a lot of people think that the cin wire tends to follow very

**45:36** · specific um take normally takes a specific shape so there does there's not much variation to the plot but that's not actually true um so if you um start dissecting the capet Meer you can see that there are L of components that are part of it so you have for example let's see if I can have a here we go so you can have um the data

**46:10** · area where you actually would have then your results so this is where you have for example the survival estimate um then you have here in green um additional information that also come from your your results but they're displayed for example below the plot or annotated here above the plot you also can have um

**46:35** · additional analysis that you add to the plot work you have here so in this case an additional um inferential statistics the hazard ratio and um you have as well information on um details of the plot itself of um in terms of labels title and annotations so there is uh quite a bit more to it than a lot of people think

**47:10** · um so starting the first exercise I'll start first with the slides and then I'll move on to the um documents that I have in the cloud so I will start as well a poll very soon but I want you to have a look at this very very simple Capal Myer uh plot and I want you

**47:39** · to potentially get pen and papers to take some notes and I want you to think about three questions and they are now appearing on the slid and the slider polls also have the same figure I want you to think about if you want to reproduce that cap Meer plot um in assuming you're creating then this analysis results data model what

**48:07** · information do you need to keep to be able to reproduce it how would you categorize that information and then how would you actually structure the data model so these three questions are pull

**48:26** · as well in slider and um I want to hear what you think before we move uh to the actual exercise so this is part of the exercise but let's say before you we move to the cloud so I wanted to take a bit of time to think about

**48:54** · this you see that some people are responding it's very good thank you for

**49:15** · responding give it a a couple of minutes Jo as we wait there's another question from Karen that maybe you could pick up just as um at the end of the period or the responses just let me know when you want me to read it okay

**49:52** · okay okay I think maybe we can go to that question now because I see that a lot of people are responding and this is a open Text uh one so it might might take a bit longer if you want to go ahead and ask that question um so the general principle is

**50:09** · so is cisk willing to adopt these updates in the future so what's the relationship between the model you're presenting and the cisk model or the standard and as we start to adopt this what should we keep in mind should we focus on your model of principles or the see this standard and then just um

**50:28** · additional um with this working group are we working with their working group are they taking their guidelines or we taking their guidelines what's the kind of relationship between your work and the cisk working group um so cisk is aware of what we did uh we actually had some conversations with them um we are

**50:49** · not too involved in the guidelines that you're producing now um they are as far as I know taking feedback from others so they they even recently had a hackathon um so in terms of what guidelines you should keep I think the a good way of of

**51:13** · of using this Workshop is to have a um I would say an introduction to the actual way of constructing this data model and viewing things in a data as anal results data in a data model way because um at least I got we got this feedback a few times that with cisk um

**51:37** · it's a bit tricky to get started in the beginning um there's a lot of there's already a lot of guidelines um and it tends to be very difficult to start so view this as a simplified way of starting and I would say that's that's the the key thing of taking from from here and then given that cisk is uh

**52:00** · opening uh is open to suggestions even via these hackathons that they do um I would say use the feedback use use that opportunity to provide feedback uh based on um what uh what um what you experiment on with and if that answer everything that was asked okay so we have a bit of results

**52:36** · coming in from the poll and I think everybody I made sure that everybody could see the poll so as soon as you respond you should be able to see and we have quite a few answers now so key information to keep we have survival probability through time for both treatments the Legends the curves the Y

**52:56** · xais um survival probability they s randomization the medical and surgical groups so it seems like everybody is uh is is more or less on the same page then we have how would you categorize these items and then you have some people saying that by the data product by the

**53:19** · treatment categorize them through the grouped time series or by metadata and curve by groups stats columns struges okay results data treatment groups okay so we have we have some variation in how we would categorize this and then the last question how would you structure it some people are

**53:47** · saying provide the complete results for One path provide the difference uh for calculating this and provide the difference for calculating second curve input all raw data include all the meta well metadata and pull the data and process review the data model analysis data model okay then we have some people saying long table use a long format okay so there's a lot of there's a lot of variation so what what so let's go step

**54:21** · by step so the first question what is the key information to keep so having another look at the plot so when I when I look at this and again this is a very Optive way of viewing things because you saw that there was much more uh opinions and the

**54:37** · polls for me the first thing I see here are the curves right so these are the results of a a survival analysis they present the these are the estimates presented over time right they have an x value and a y value each data point here then I see the access labels a lot of people also pointed out and the title and the

**55:03** · legend and then when I start thinking a bit more about this remember I said we had the estimates presented over time that came from an analysis so there there's um there's some information already here that's that's that might be

**55:25** · that might be need to cap might be needed to to be captured but we're not fully seeing it now let's move on to the second question how would you categorize these items now for me again being very very Optive suggestion is okay these estimates presented over

**55:46** · time for me these are analysis results again from a survival analysis then I have the output like this plot has has some some information about it so has some metadata if you want to call it like that um again the title the labels and the legend and then remember we had these results that came from an analysis so we my my view we

**56:10** · should also make sure to store the metadata that's associated with these analysis so the information about how this analysis was done to be able to produce those results and then comes the third so the

**56:27** · analysis metadata so there comes the third uh a bit of a summary what we had so now comes the third question finally how would you actually structure the data model and by structure uh I mean how would you organize this information again thinking back to this example of these four tables how would you structure format these these tables and here it it helps to think about is

**56:59** · as think about the following concept it's helpful to think about tidy data in a sense that data there is easy to manipulate for example and then it also helps to think about tidy outputs and this is something that uh for example the broom package does it uh ties up different outputs uh

**57:23** · outputs of different models in a way that is consistent to forming following again a specific structure and it also helps to think about link data in the sense that it is machine we have data that's supposed to be machine readable machine readable data that has to be linked to to each other um to enable uh this

**57:48** · reproducibility so going to the actual uh exercise to resume again few seconds so it's \[Music\]

**58:16** · resumed there we go so if I go then to the first exercise it will start with the same same information that we had these three questions that we saw in the poll and then uh these initial thoughts that we also saw now when we think about the survival analysis results and this is going to be very specific to R um so we just we just restricted to to

**58:47** · that uh when it produces survival analysis you tend to have quite a lot of information that comes from it not just um the these estimates that are presented over time so you might have information immediately about standard errors confidence interval patients at risk number of events censoring and so on so on one hand you to reproduce that plot you just

**59:12** · need to capture a portion of this information of these results but on the other hand we also saw that the cou and Meer can have a lot of variation so it might it might um be that for a different output a different plot we might want to have the confidence band showing so it makes sense to capture as much information as we can now a question that immediately comes up with this is well how do I know

**59:45** · how much information do I have to capture if I don't know what I'm going to do in the future which outputs I'm going to produce um and this is where the structure of uh or yeah the structure uh enforcement that the data model does comes into play you have to think a bit about keeping this information in a way meaning in a structure in a format

**1:00:16** · that would make it easier to add additional information if needed so if you if if you end up needing to um include if if initially you didn't store the number of patients at risk and then you wanted to actually store this should be able to add this um and that that means that the way you structure your data model has to be flexible enough um so one way of doing is this

**1:00:47** · would be to have more of a long format of a table um this at least is what we found to be the more um um yeah more flexible so for example here let me just please quickly so for example here one way would be to

**1:01:10** · have a table that then stores your results from your survival analysis in this case I'm just going to call this this table this imaginary table in my database that's going to follow the data model it's going to be called the survival Rd table and it's going to keep

**1:01:28** · um it's going to have an ID it's going to have a description associated with that ID I have another column with a strata and then I have name and value and the the idea of having this as name and value is that you might have in each row name would be the number of events and then you would have um the the value corresponding to that and and then below you might have then the um the the the

**1:02:00** · day and then you have the value for that then you would have the estimate and then you have the value for that and it is a bit more flexible to add information then for the outputs

**1:02:16** · metadata um so the tables and U uh sorry the table the labels and the titles uh one could think of again repeating the ID and the description so should be consistent through all the tables to have a unique way of identifying um each piece of information that they store but also a description field that is more readable to humans so

**1:02:42** · it's uh easy to quickly understand uh what it's referring to and then I decided to put here um a field called text and another another one called type and this means that for example the type would um Keep information regarding if this is a title if this is a x label or y- axis

**1:03:09** · label and text would be the corresponding text to put in the title to put in the X label and the Y label location yes sorry there's just a request if you could increase the on size if possible yeah sure sorry about that this is not visible I'm really sorry okay is this

**1:03:38** · better would looks great okay thank you um okay so then additional information about location and position so if this should be in the for example for the for the title it should be uh placed in left hand side or the right hand side

**1:04:00** · and um position as well and then we have the weight which would be if you want to have certain labels bold or not and color if you want to color anything like we have in the in the example have the legend and each curve has a specific

**1:04:22** · color and then finally we mentioned that not only we have to store the results we also have to store the contextual information about the results that that means analysis metadata um and again this is a very very rudimentary suggestion there's a lot of a lot of other details that should be um kept about an analysis um but one way of viewing it

**1:04:47** · could be again you have an ID in a description you would keep information about the software that you use the versions of the software which libraries um and for examp the function call that you use to actually execute that or fit that model and one thing I did here because we have a very small uh data model to

**1:05:11** · not to not make it too large what I did is remember that the data model should also Define how all the information is linked so in this case I link I'm linking all the information in the anal this metadata so I have a field which should um where you should add the um ID

**1:05:33** · corresponding to the analysis results that are generated from this analysis and another ID that should correspond to the output metadata um that was that that's from um

**1:05:48** · an output that generated from the well the results of this metadata so if if we would look then into the way of how how all these tables um I think I didn't forget to run anything yeah so you would have let's say a data model that looks a little bit like this so you have your analysis metad dat table that has then links to the

**1:06:14** · survival uh Ard where the survival results are stored and then an output ID that links to um this outputs metadata uh table that stores information regarding the output so again this would be the second step would be actually populating this um and in this case we have already some data prepared in the project um it's following uh time to event um

**1:06:48** · standard and in this case we're just using a surf uh survival package to fit uh calculate the survival estimates and then we are doing some again nothing too complicated we're just using deply R functions and we are making sure this

**1:07:10** · information is stored in this these data sets which are repr where basically um are this these tables taking the shape of these table that I mentioned the very beginning and they are following how we specified um all the constraints

**1:07:28** · that we were specified in our data model before so we have the same for the outputs and then we have lastly same for the analysis metadata and in this case because we only have one analysis stored um or one

**1:07:44** · one um information regarding one analysis stored can just immediately query the output table as you see here and if we we we use this again very standard way of of extracting information using deply R again we extract information on the T title the labels The Legend and then we use ggplot to rebuild the plot that we had before and we are able to reproduce it without rerunning the analysis we just used the

**1:08:17** · the the data sets that we created that or following this data model that we specified at the very beginning um so before I have a couple of questions um and I would first ask if there's any questions as well in this chat and then I will put up some some polls

**1:08:52** · afterwards no specific questions in the chat no specific questions good so if there is no specific questions I will have some some myself to you so I'll I open another poll um with two questions let's go back

**1:09:15** · here and these questions are um so thinking about what you said at the very beginning your at the very beginning about what information would you keep uh and given what I just showed you is there anything that you think that is very very very important that for example I missed and that you definitely would have saved uh would make sure that the model captured that and also another question would be

**1:09:41** · compare in comparison to what what we have in the exercise would you use a different structure to store the data and uh maybe you want to share why you would use that different structure structure or what are the key things or key reasons why why U why you would choose something a bitly different so I see that some people are entering that's very

**1:10:17** · good have a couple of minutes so again if there's any other key information that you think that no this this should should have been definitely kept the model should be uh ensuring that this information is stored and um if you would choose a a different structure uh for the data for the

**1:10:52** · data okay we see that some people have responded um so one

**1:11:09** · one one uh answer is for example the reference to the paper where the plot is coming from and information about the analysis or which algorithm settings were used for the analysis okay so basically going into more detail about the analysis metadata makes sense what questions were asked during the analysis and what are what were the decisions this is a very good one so this basically means that you're staring

**1:11:37** · not only metadata about how the analysis was performed but also um information about discussions that happen around the analysis so that's I actually never thought about this but this is this is very very very good point actually some other people are saying data source of the source of the data yes that makes sense

**1:12:02** · um because if you think about when you perform an analysis it might be that it also it's very much associated with the data that you're using sry right which data you're analyzing and you can think about for example how we do analysis now nowadays when we have um different data cut offs so it might be that an analysis is associated associated with a data database let's say data C off dat and

**1:12:30** · the data itself is going to be updated on a different time and then the analysis might be the same and the results then are different right exactly the version of The Source data it's one of the answers on the poll let's move then to the second part would you use a different structure uh um to store the

**1:12:56** · data um some people are saying a long for or Nest object seems like a good approach yes um a linked graph database um that's so technically well the idea of the data model is that um it could you could choose how where you apply it um it could be that you apply it for a database that is relational but you could also apply it to a a graph database as well um but that that makes

**1:13:33** · sense okay so we had a few answers so that's very good um okay so I think this means we completed exercise one is there any questions on just a couple of questions in the chat um the first one on from Jeremy um if one plot needed to create

**1:13:57** · at least three tables results output analysis what do we do if we have many plots say four plots it seems hard to manage so many outputs example have four plots and 12

**1:14:13** · tables so okay so if one plot needs to create at least three tables so you mean that you're creating basically multiple outputs from the same results sorry I'm trying to

**1:14:32** · fully understand but I'm going to assume that's yeah okay yes good um yeah so it it it does seems that there's a lot of outputs that are being created and and they and that's the reality if you think about how how you perform this nowadays

**1:14:50** · um how you perform the analysis now nowadays you are actually producing a lot of outputs most of the times you don't really realize because um it just let's say standard practice you could put let's say a a threshold audit you could say if I am just in the exploration phase I might not keep all of this information stored

**1:15:15** · in the database that follows this data model that I specified but you could also say I'm just going to keep every information start and you can automatize that process so imagine that you just have your you just do your analysis and you produce different plots and again assuming that everything follows this data model um you um should be able to

**1:15:39** · have a set of standardized function that would help you then approximate your results to what needs to be stored in um in your database that follows the the data model um so yeah it's bit of a tricky thing because you could see this growing

**1:16:01** · exponentially if that answers your question um but I think we can go to a different question I think that there's

**1:16:17** · more I see that I check I can see here the question from uh karigan so the fields that you're using to capture different information or something we can look up in the guidelines and can use them to capture similar info for other applications also at what point in the analys you suggest starting this process uh as analysis needs can change

**1:16:46** · and seems that there will be a lot of rework and as this step is not actual product we might not have enough time to spend this activity um so in terms of the field that I'm using and if you can if you can look up any guidelines um um I wouldn't say

**1:17:06** · again for for anything of what I'm showing here this is a simplification of what we have in the paper so if you have if you want to know a bit more of what we suggest I would say have a look at the the paper because um that links to a repository and you have the creation of these type of tables there and they go into a bit more detail we actually made sure that that data that data model worked for I think reproducing uh a demographics table and

**1:17:37** · also I think cap the cap Meer so should fit for demographic analysis and a uh survival analysis but again these are not solid uh let's say um hard deadlines uh

**1:17:53** · guidelines these are are more suggestions at what point of the analysis you suggest starting this process um again that goes a bit to the question that Jeremy um asked in terms of do you keep do you record everything um that's that's a bit uh I would say

**1:18:16** · it's a point where it's a bit up to discussion on one hand you would have some groups of people who would say you should record everything you do um because you never know um what uh what might be useful to understand what changes happened in that analysis but we also got a very very um good uh comment from

**1:18:40** · one of the polls when somebody said that another piece of information to store about the analysis could be the discussions that happen around the analysis so maybe what we what one suggestion would be wait until you have let's say the let's say the analysis finalized and then Associated to that

**1:19:01** · would be uh a way of recording discussions that happened and that mutated that analysis until the shape that it's the last the last shape it it took so that would be a

**1:19:21** · suggestion and then I can see I'm just going to go through the chat and see the questions um you can see in question from Paulo there are many flags that are set to the FL the default like this color scheme of the plot do you recommend have all parameters explicit uh I would say yes this makes it uh obviously more difficult to model um but I do think

**1:19:52** · think that in a sense of keeping of ensuring that the data model has enough information at something can be reproducible and keeping in mind that some defaults even might change over time I would suggest that to keep all parameters uh and have them

**1:20:18** · explicit and then you have another question so maybe as regards to the first first question we could add if the proportionality of aards is valid or not between the groups so us not to be able to compare the results uh from uh

**1:20:34** · different analysis um yeah I think I understand your question and I think yeah that's information that if it's relevant to keep that it is relevant to keep then we should make sure that the data model also uh is recording it or is ensuring that that information is

**1:20:59** · kept okay seems like there all the questions so we're going to move on to the second exercise and in this case we

**1:21:14** · have um we're touching on the idea of reusing analysis results right because this is one of the key things about having a data model is that all information that you keep is uh all the results information that you keep can be then reused and you know the context that surrounds those results so you know that you're actually reusing the results that you think uh that you um that you

**1:21:37** · are reusing that you want to reuse so in this case I want you to think about the scenario I want to think that you know you had a request to produce to perform this this analysis survival analysis and you produce this kapl Meyer and you written up your work you finalized it you completed the submission that you had to do and then comes a request to

**1:22:01** · publish basically the same analysis but in a different venue and this venue has a set of recommendations so the plot that you produced before it doesn't fit that many recommendations right so here you have a a comment uh please can you modify modify your cap Myer plot to meet the current recommendations of the journal as spelled by mors and of course to make this a realistic scenario we have a deadline which is tomorrow tends to be like that so like I

**1:22:34** · said this is a very common scenario you we we want to use um the same analysis results but in a variety of venues because each venue might have like we in this specific case different requirements uh we might need to tailor our outputs uh or plot tables to fit the

**1:22:53** · the audience so it means that we have to um be able to reformat these these outputs to meet the specifications that are required so if you go then to um moris at all and if you check this

**1:23:10** · we see that there's a paper that um uh this group of people did and in in this this paper they run the survey and asked people what do they think a c and Meer plot should have um and they kind of summarized it into basically it should

**1:23:32** · have the this table below the plot uh with um the numbers at risk censored in the subject that experienced an event it should also have the confidence spans around the the curve the cap my curves desate so I have a question or a couple of questions for you again in the slid poll

**1:24:00** · uh the pole to of slid up um so my questions are given the analysis results data model that we start building in the first exercise can we fulfill this request without making a new analysis and second is there any information that we are missing and that we did not capture in our data

**1:24:28** · model okay and if we then go to the second is there any information missing that we didn't capture so a lot of people are saying that yes there is information that is missing that we did not capture but we can calculate that okay so if I go then the second exercise

**1:24:52** · let's resume again thank you for participating in the poll this is very very helpful to hear your opinions and to to hear your thoughts so again just the beginning like we saw before um one caveat that I want to put here is that typically what uh would happen is that

**1:25:23** · assuming we did not have anything like a data model assuming that we did not even have this mindset of thinking of analysis results as data a typical thing that would happen is a person would have to redo the analysis right and when you go to the point where you try to I mentioned this briefly before when you go to to a point where you try to rep rewrite an analysis that somebody

**1:25:49** · did and you don't have sufficient information or you you think you have sufficient information to uh rewrite that it's it's not un common that you end up introducing some errors so what we have here is a typical scenario where you would rerun your analysis it might be that the person re uh rerunning or reproducing sorry recreating that analysis would decide to use a specific

**1:26:20** · setting to calculate to to estimate the confidence intervals and that setting might deviate from what was actually done and the analysis that produced um that original product that original plot so this might be not this might not be um let's say an error that was introduced uh because of of an accident this might

**1:26:49** · be an error that is introduced because of a a different way of viewing how the analysis should be done so again having something like the anal results data model having a way of or just thinking about results as data would allow us to have results that we can reuse and we can bypass trying to reproduce recreate analysis that were done uh even when we don't have sufficient

**1:27:21** · information um so about the question of if we have enough information uh or if we're missing any information um in our um that we capture according to our data model we we have all the information that we required the only thing we don't have is the uh cumulative sums that would go to the table that's below the plot but this like a lot of you said is

**1:27:52** · not too problematic because we can calculate the missing information right so here I'm just loading again this survival Ard that we had I'm seeing that we have basically all the information we need um here I'm again applying the same code that we did before I didn't didn't write anything you I'm just applying the same code producing the same plot and then using

**1:28:13** · that plot as a basis uh and then starting to add the confidence bends so again same thing just confidence bends are added there's nothing new really to it besides the addition of the bun and then to add the table bu plot is like like we mentioned before we need to calculate the cumulative sum for um the number of

**1:28:37** · events and the sensory um this is not too problematic because it's something that we can derive from the results that we have so it's not necessarily a new analysis it's just a uh just derives on the results that we already have and um in this case

**1:28:57** · I just created a series of functions that I'm using to calculate then these sums and then a function that uh we can use to uh at the table below the plot and again assuming that if if you'd have this data model in production let's say uh even though it's a very very basic thing you could then have all of these uh functions um ready to be used when needed

**1:29:27** · because the data is always structur in the same way so we know exactly what you should expect so so these functions can be standard function that you just apply to your uh to the data that's stored in the data model according to the data model so in this

**1:29:47** · case this is just the functions and then um we then have the final plot which would then follow the recommendations that are uh part of uh mors at all and there's a bit of a curveball here we received an update to our

**1:30:08** · request so let's say that uh the same person came back and apparently they don't really care much about the recommendations anymore they prefer to have the sensor information in the lines uh and the estimat the survival curves and and not in the table but that's not much of a problem right because again we don't have to reproduce any analysis we just go back to the results we even have um standardized code that produces that plot and we can just remove that line

**1:30:42** · from the table and add the uh the lines the the sensoring uh to the estimates to the survival cures so again and the the the more

**1:30:59** · amazing thing very amazing part here is that we didn't have to redo we made two different plots and we didn't have to redo uh any analysis this is all all of this came from the information that we stored in this very simplified um um analysis results data

**1:31:20** · model so I have then one after question about this exercise sorry I went a bit too far and there's a poll appearing then on slido so what do you think that would

**1:31:39** · facilitate these tasks that we shown here in exercise to like adding the table below the pot assuming that you have already a data model in place what in your opinion think what do you think could facilitate this is there anything that we could could have included in the data model to facilitate this or even something that's external to the data model but can be used in collaboration with

**1:32:05** · it let's say take home questions so these are more open questions that um you can explore later and it probably will require a bit more time to think about them as well so what I'm going to do is that I'm going to skip uh not not a break but let's skip then to the closing part of the the workshop so I would say that there's a couple of uh takeaway messages from

**1:32:38** · today one of them by far is to really ingrain this idea of Shifting the target of um data analysis to become shift it away from these these data products and ensure that the target is actually having a reusable and accessible data source that you can um create by by uh first defining your

**1:33:08** · data model and making sure that this this follows your data model your analysis results data model and then the the other key message here is that again you saw that there's a lot of um there's a lot of things that are open there's a lot of questions that are open and it's it's not so clear what is the best way

**1:33:33** · of of storing certain pieces of information or even what information should be stored so it's key to understand that the way for this to evolve is to really hear everybody else and see if there's a way of finding it a consensus um so with with this in mind I have one last question for you again in the slido poll from your experience from what you what you um

**1:34:05** · also listened to today and what you did today in the exercises what do you think or what what are the key points that a person should follow uh when building an analysis results data model like Keith Keith like somebody would stop you in the hallway tomorrow and ask what how do I start building my analys results model what do I have to keep in mind which Step should I take what would you say to

**1:34:38** · them open question so need a few minutes for people to respond okay that we can spend less time formatting outputs and more time on the ardd that's that's true it's a good point reproducibility that anyone with an ardm should be able to take and

**1:35:07** · recreate what information is required to reproduce the result I think that's that's a very good uh that's a very good um uh key point because I think that that it tends to help when you look

**1:35:25** · at what you're trying to achieve first and then you kind of backtrack like what we did on the first exercise for example we looked at this at this thing that we wanted to reproduce this plot and then we backtracked we thought okay what what results are actually represented here what contextual information do I need to keep and we start building the data model like that a few more answers or store carefully all the metadata and

**1:35:58** · documentation Ure producibility capture decisions and think about extensibility to Future outputs that's that's also a very good point to make sure that when you when you're creating a data model and this is a tricky thing to do this why it requires normally a lot of um iterations over it is that it it should be flexible enough that um you can include new analysis and

**1:36:25** · include more information that is captured if you need to reformat than the data model determine critical aspects of data store using a defined data type to avoid data loss loss like toes versus lists I

**1:36:43** · said that's a very good point and provide results along with the data product for interpretability of vians and machines yes definitely think about future analysis to ensure correct metadata and you would say that there's a steep learning curve but then the advantages will come as this becomes more stable yes these are all very very very good points thank you thank you for sharing them with us so with this in mind we have five

**1:37:15** · minutes more or less just to wrap up I want to talk to you about just some some again we are missing a lot of people here for sure and I want you to tell us who those people are so we saw that there already some companies um cisk for example um is also part of this

**1:37:38** · but and and that our developing pieces of software are already taking into account these principles that we mentioned before so they are they already thinking about already analys results as data itself or they already thinking about which information do we need to capture to reproduce things what information we need to capture to make them reusable so these are here are very few

**1:38:06** · examples again we're for sure missing people so um tell us we are missing and I want to highlight one last thing here um which is the the omop common data model this is something that we looked at at the very beginning when we were um again writing this paper and and searching around the area this is a very good example of what can be achieved if you have a data model um that um is used by the community by

**1:38:39** · community so the omop Comm data model was um is a data model made to uh make sure that there's standards around how observational data stored and that they're able to easily reuse um the results and also make sure that everything is reproducible so they are like the key uh I would say the key example of what what we can have if if you're able

**1:39:13** · to U have consensus of what an analysis data model will look like so with this um I would say that you know if if you are interested in this topic if you have ideas on how to progress uh and if you're working on symol problems do reach out to us we quite interested and see if we can continue to uh build a community around

**1:39:42** · this building even a community of practice uh and see if you can also shape uh how um how we will use the analysis results data model in the future so thank you very much for your participation um thank you very much for um being so active in the polls I don't know if there's any questions left over in the chat but I'm happy to answer them before we fully finish

**1:40:19** · today okay don't see any questions okay yes Lucas put a link there to our website we plan on keeping it a bit more also up to dat and we will link everything there I think the paper is already linked on that website um

**1:40:46** · we'll also make sure the um uh public repository with all the materials that you saw here today on POS cloud cloud are also link there is also linked there um and yeah thank you much for again for participating and I hope you found this interesting