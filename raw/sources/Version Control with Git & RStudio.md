---
title: "Version Control with Git & RStudio"
source: "https://www.youtube.com/watch?v=qJWoNcbu98M"
author:
  - "[[R in Pharma]]"
published: 2023-12-20
created: 2026-04-30
description: "Workshop recorded as part of the R/Pharma Workshop Series (October 17, 2023)Instructors: Christina Fillmore (GSK), Alexandra Lauer (Merck KGaA), Lyn Taylor (Paraxel), Irene Vassallo (Incyte)Resourc"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=qJWoNcbu98M)

Workshop recorded as part of the R/Pharma Workshop Series (October 17, 2023)  
Instructors: Christina Fillmore (GSK), Alexandra Lauer (Merck KGaA), Lyn Taylor (Paraxel), Irene Vassallo (Incyte)  
  
Resources mentioned in the workshop:  
\- https://camis.shinyapps.io/git-app/  
\- https://github.com/PSIAIMS/git-training  
\- https://colorado.posit.co/rsc/Team\_Code\_Collaboration\_RStudio\_Git/git\_clinical\_presentation.html  
\- https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository  
\- https://github.com/asavarim/git-training

## Transcript

**0:00** · hi everyone I changed my screen um so hi everyone my name is Christina and I am going to talk to you today a bit a little bit about Version Control and G so

**0:18** · um so who are we and why are we here um it's a good start so basically my name is are you sharing your screen by chance I'm sharing my screen in my head does that make sense well unfortunately we won't be able to see it but we can see it now perfect sorry back to you so um yes today we're gonna talk

**0:43** · about um Version Control and G with our studio if these things don't sound interesting to you then you don't have to be here you know this doesn't sound right you're might not be in the right place but um so today we're going to talk about that now who are we and what are we talking about uh why are we talking about it really so my name is Christina Filmore I'm a data scientist here at GSK um so I work a lot on kind

**1:08** · of building out solutions for the far my pharmaceutical colleagues in biostatistics um I also am very involved in PSI which is the pharmaceutical stats Industry Group within kind of generally Europe although primarily the UK and some other places um and as part of that group I am part of the r kind of a r group called as and we co-run I co-run

**1:34** · with Lynn um something called Chas which is a project for comparing statistical results in um different softwares and so comparing St whatever um and so in doing that we've have a get repo that is for that and part of that developing that gpro repo and doing that we realized how much there was a need for doing kind of a basic git training which is how we came to be today um so that's the long

**2:03** · story short of that so that's who I am now Lynn do you want to introduce yourself as well yep sure um so I'm Lyn Taylor um I'm a statistician at par EXL um I worked on the r validation Hub project um for I think around like sort six years or so and got really involved with R in Pharma and how we can encourage the use of R within the pharmaceutical Industries and how problems like Val ation can be overcome and then like uh Christina said I've

**2:35** · then become more recently involved with a fuse project called CIS which is comparing analysis method implementations in software and through that we need to collaborate together and that's why we've ended up looking at collaborations repositories and that requires Git Version Control and I've found that with my background in statistics I've never actually been taught git or the sort of way that g

**2:59** · Works differently to other version control that I've been used to in the past so that's how this has kind of come across and hopefully you'll all enjoy it today Alex do you wantan to go next sure so my name is Alexandra lower I go by my short name Alex uh so please feel free to do that as well um yeah I am a biostatistical Analyst at mark kga and um I attended PSI conference this year where I met Lyn and Christina and

**3:30** · um from from my background I am a member of the r tables for regulatory Sol working group and I'm also a biostatistical analyst so tables um my working group um participation that kind of led me to um Version Control and as kind of that that third part of my profession I'm also co-leading the um our user group at Merc

**3:58** · um together with a colleagues so I encounter the problem that a lot of times bi statistic by statisticians or statistical programmers are not familiar with Version Control um whenever I pushed a a project to them and said hey have you tried out that package they came across an issue and were like okay

**4:17** · this and that is not implemented and they were simply not aware of what to do when I said hey have you tried to open up an issue so all of that kind of resonated with Lynn and Christina when we met at the conference and yeah we are now super excited to present this workshop with you and I hope you like it Irene please hello and welcome so my name is aren and I am a senior statistician at

**4:44** · Insight um I'm mainly work on clinical so clinical trial but a lot of my work is also focused on uh helping the transition to start to video use R um for clinical development and clinical submission and and I love G so I

**5:01** · actually really hope you will enjoy this U Workshop was quick perfect so with that let's get into it um enough that's why we're here basically we all love get we all know why we like like it so we're here to teach you to love it maybe a little bit as well so how this is going to work is we're going to have a short little intro and then this it's basically going to be

**5:25** · kind of the the tale of two halves the first half is all going to be in theory this is going to be not necessarily using it directly but building that Foundation there are a lot of exercises um both for the theory part and the Practical part so we this is very interactive we would love you to take part and be um interactive as Phil said please do use the chat box to ask for questions and also um kind of the only

**5:51** · other thing is as we do the exercises once you finish an exercise do raise your hand I'll remind you every time but just in case I forget to remind you there's my first reminder so with that let's oh and one final thing the final thing is our environments as Phil said we are using posit Cloud today um so you can use

**6:12** · posit Cloud for the Practical exercises we're doing this primarily because git is already installed in posit which is very convenient for us when trying to explain to you how to use a system that we know is already installed in the other thing we're doing is we are using a shiny app for all of the theoretical exercises so Lynn is going to put that in the chat box I think she's she has done it um and so basically we're going

**6:37** · to go through this app for every exercise for all of our theoretical exercises in order to give you an example um give you a chance to kind of get used to using get and understanding how things are happening behind the scenes okay so what is get why are we here today so get is a Version Control System you may have heard of it that like described that way it works kind of as you'd

**7:02** · expect it helps you track your versions but it's a little bit unique um so it was created by lus toal who helped help him make Linux so the guy who made Linux needed to have some way of tracking all his versions as he was making it and the traditional Version Control Systems of just checking one thing in and checking one thing out and having things super super linear just weren't cutting it for him so he needed something slightly fancier so he made this um which is a really great system system um now you

**7:32** · probably have also heard things like GitHub or gitlab or maybe even bitbucket um all of these things are not quite git but are very similar the difference is basically that git is going to be on your computer it's going to be running locally that's what's going to track the versions whereas GitHub etc etc are in

**7:51** · the cloud service based systems that help you manage these get repositories so that you can share them with your friends and colleagues Etc um because stuff on your computer needs to get out into the world how it gets out into the world is going to be things like GitHub so for this um for this Workshop today sorry we are going to be using GitHub but most of what we're teaching you is pretty agnostic to any system um and generally

**8:22** · you can switch it out for gitlab which I think is the biggest one I hear about as an alternative but I know that some companies also use bit um so let's get some down some Basics basic terminology when we think of kind of get

**8:39** · the most basic one is going to be a repository so you'll hear people call it a repo as well but basically it's the collection of code you want to track together this is going to be a folder it's just a folder on your computer and anything you want to track together is going to live in that folder so it's spe

**8:55** · made special by like having a secret little G folder in there in your f folder that helps track everything but basically when you put things in a in a repo you want to group things together that you want to keep get track together so things like if you're doing a study you maybe want to put all your study code in a single repo or maybe you're writing up a paper for submission and you want to put all of that in a single repo just how you would normally do your

**9:21** · kind of project management things that go should go together should stay together things that go together in a repo will be tracked together so the next thing to talk about is a commit so a commit is the saved version of your folders um of your files or what's in

**9:36** · your project so there are a couple of things that make commits a little bit unique compared to maybe a check-in checkout or like a snapshotting system first of all it tracks changes so rather than tracking tracking the whole file every time it's only looking at the changes from what happened last time to this

**9:56** · time this makes it pretty efficient in terms of how the file storage but it also allows us to do some fun things which we'll talk about later um but basically it's only looking at the the changes the line by line changes you've done in your file the next thing that

**10:11** · makes commits a bit unique is you can commit multiple files into a single commit let's just say that you created a variable and you accidentally spelled it wrong except for you put that variable in five different files well what you can do is you can just go through and change the variable everywhere and change it in all the files and have one commit and be like I forgot how to spell

**10:32** · and then you can change it and put them all together but sometimes when you're making commits you want to group things together into a single commit because you know you're all doing the same thing so those are some kind of the basics of doing that now now that we have some really basic understanding of things that are happening in git let's go to a case study sometimes it's easiest to learn about the stuff with the reason why you might want to learn it so today throughout the workshop we're going to use the case study of camil camil here is our lovely statistician um she got to you know

**11:03** · start her week she had a coffee she had a laptop ready she's excited because this week is the week she's putting things out for publication so she starts doing some analysis and she makes some graphs that's what happens Monday Tuesday comes along she then submits to journal A she's having a great time she'll like you know what actually Journal B is probably a good idea too so she does more analysis makes some more graphs does all the changes she needs to do because not all Jour have the same publication standards so does some more changes in into her graphs in order to submit to journal B then Friday she fit

**11:38** · Smits to journal B has a great week shuts down her computer and enjoys her weekend unfortunately she comes back on a Monday morning to the unfortunate email from journal A being like we have some questions and we would like you to make some changes well that does not

**11:56** · help her mood she needs to change her code but she's actually already changed it so much from when she submitted it to journal A so she's going to have to go back she has to find it she has to figure out where she stored it and also she doesn't want to undo all of the work she's done for Journal B so what's she going to do well before we get into solving her problem we're gonna make you do an exercise um so the first exercise is

**12:22** · actually about committing um and so Christina let me just interrupt one minute before we explain the exercise the um shiny app is now got a 503 service un available oh no yeah and I like tried it but it's not come back up so okay I think you refresh the page it's working okay for me um it happened at first and then I just refreshed it once or twice and then it came back so you might uh so maybe you shut your browser yeah

**12:50** · it's still doing it for me it's working for me who knows back okay sorry Christine I just wanted everyone was panicking and I was like um it's not back for me yet but I'll keep trying okay um it's probably because we're all refreshing the page

**13:12** · repeatedly um so so if you want to go back to the slide sorry screen no it's fine we're gonna come here you should be on this thing that says committing um it should look like this if it's not pink it's probably not in the right place um but what you're going to do is you're going to work through question one two and three here um each question has an

**13:33** · has like an explanation of what you should be doing so what you're going to do is we're going to have 10 minutes so I guess that's almost I can do 42 3:28 my time which 28 pass whatever that is to wherever you are um and then we will resume so if you

**13:56** · have any questions just go into the chat feel free to ask and again remember please do raise your hand when you are done new emojis oh that's funny okay well I will slowly Fade Into the background and let me know if y That's

**14:12** · great oh we're getting a bunch of Thumbs Up in so cool wonderful so I'm just gonna work through the exercise it might feel weird doing exercise so far early in the day but it's nice to learn in a Hands-On way particularly with Git because I think if you just see things in slides it makes sense but then when you come to do it the terminology things can get confusing so hopefully you find this a really hands-on experience to help get some of the terminology into

**14:35** · your mind so that when you see this in the future and we're not here you'll know what you're doing um so we're starting really basic we're going to do a first commit and you need to change the code in some way so I'm just going to replace the my name with my name and I'm going to put a commit message so I'm just going to say personalized oops I'm going to spell it right personalized the

**15:00** · print and click commit and immediately we see that the diagram has changed so we've got the first commit here and then we've got one with a personalized the print so that's it for the first exercise if there's any questions I'll try and watch the chat as well in case anything comes up that you want me to go over

**15:23** · again and then question two so this is just practicing making commits so if you hover over these dots you'll see this one is my first commit this one's my next commit and this is my final commit and we're going to try and replicate this network diagram so first of all my

**15:42** · first commit and I press commit and I've got my first commit made so for the second one this is my next commit and I hit it again and again you can hover over these it shows you the commit messages and you can see that that's creating the same as this one and finally the final

**16:08** · commit and hopefully you got this message saying you've matched the network graph now if you've typed something different in as the commits you won't have done you won't get that message but that's fine you can still move on to question three if you understand what we're doing it's very basic but you know we're at the start of the course and things will get a bit more complex also gives you good practice on getting used to our diagrams and and how some of the questions work so going on to question three this is Camille and as Christina

**16:40** · mentioned in the slides you can click over each one of her commits in this network diagram the first one she was exploring the blood pressure data she got this graph the second one she cleaned up the plot for journal A that was using this graph and in the third one she started looking into Journal B and changed the graph to be like this with splines on and then finally she

**17:06** · made a fourth commit and she changed the colors and tied up the graph for Journal B so what we want to do is to find the right one that's journal A because she's been requested from the journal to make changes and unfortunately the version of the code she's looking at is this one now which isn't the one that she wants to make edits to because it's very different to the one she submitted at a so we need to find the right one and

**17:33** · we can look at the text that's been added in it's a helpful text it would be even more helpful if her commit messages actually said what the changes she'd done to the uh program was because at the moment she's just gone version one version two version three and version four and that's making it very hard for me to find which is the version that I want to to use um and to make this

**18:02** · easier you can do something called a tag and so when I find this one which says the last reference to journal A in it I can now click tag and that will ask me to add a tag message which I'm going to put as Journal a um final version which is a much more

**18:24** · useful commit message that I'll be able to find this in future and I submit that and now this is tagged with hopefully a a more uh findable commit message um so that I can do that in future so Christina did you want to share again and we'll go back to the slides and just check for any new

**18:49** · comments yes trying to find where to get sharing back wonderful so oh great do you want me to just talk through this one which one this question

**19:14** · yeah we have one more slide so just to look at it graphically on this last slide uh we made a commit and this is starting a network graph and we saw the four commits as there was um each of those graphs that were done and then we identified um which one was the one that

**19:34** · she wanted to send to the journal so we've checked out each of these different commits by clicking on each one and that changed the code that you could see when you checked out those different commits and then we've tagged it um and

**19:49** · then we've put a commit message in there just so we can find it in future so yeah I think that's the end of that exercise yeah so yeah um there we go so let's so we did I made you do a bunch of things you probably had never done before uh while doing that so let's go back and explain a little bit of the the things that we did in the exercise so the first thing we're going to talk about is checking out so checking out is just a command and git used to move around um you can think of

**20:16** · wherever you're checked out as like where you are currently located in space on these graphs that we're showing so where each graph each dot represents a single commit um we're using these Network graphs because they're pretty commonly seen throughout using git um so it's just kind of what's around um so

**20:34** · the kit commit that you're currently on is referred to as the head um that's just kind of the nomenclature we're trying to avoid as much jargon as possible but that is jargon that will go run into if you don't um know much about it so there's that one there's still a lot of hands up is if you have you if

**20:53** · you done with the exercise great you can put your hand down if you have a real question can you put put the question in the chat and if not none of those things cool I'm seeing hands go down that's that's good um okay sorry anyway so

**21:09** · that's what checking out is so checking out is just where you are in space as you move out move around from place to place you need to check out the new place and then you go to the new place and that is the process in GitHub of moving around from your different commits the other thing we talked a little bit about was tagging um so tagging can be super useful um for identifying things in this case identifying the plot that was used for G um so but

**21:41** · um so now Camille knows where that that location is which is super helpful for her but she actually does need to do some updates so there's going to be a slight problem because a tag is associated with a commit it can be on any commit but it is the commit that's tagged um and so it can only be that one

**22:01** · commit in this case we need to do updates right journal A asked us to do some ask camil to do some updates so in order to do those updates she's going to have to use something other than just a tag to identify it which is really helpful but it's not quite enough so in this case we're going to need to use a different thing called a branch so so branching how it works is in G by

**22:28** · of standard we use we use our kind of primary Branch it's called Bane this is the primary the where everything typically is coming off of but you can Branch off anything but this branching allows us to make nonlinear changes to code so rather than having to just check something in and check it back out and check it in kind of a more linear Version Control System we're allowed to kind of make changes from wherever we want to do it so um by making changes by

**22:55** · what we're going to do is we're going to find a commit that we want to and then we're going to Branch off of that commit so in this case we've made Branch one and now we're going to add some changes to Branch one now these changes on Branch one are not going to be on Main Branch so in the case of Camille the updates that she made to journal B is not going to be for Journal B they won't be affected by the changes that she's making to stuff for journal A they're

**23:19** · kind of now entirely separate they're swimming in their own swim Lanes if you want to use the swim Lane analogy or they're like branches on a tree they're maybe from the same Source but they live in different spaces so you can have as many branches as you want so for instance maybe some she wanted to do another update later on with something earlier she could make Branch two um you

**23:40** · can have as many or as few commits On Any Given branch and there's no limit to the number of branches that you can have or the number of commits that can have branches off of them so if she wanted to make multiple branches from the same commit that would be fine it's there's really not a lot of rules when it comes to branching you're allowed to do basically whatever you want so with that being said now it's time to go back to the app so however you choose to be in the app whether through pit connect or through the app through the URL um we

**24:12** · are now going to change over from being see if it will open up for me maybe let's see if it will reload potentially not ah we're going to go to the making branches section so now we're going to do question one and question two of the making branches um as usual we'll be available for help

**24:31** · um so if you have a question please put it in the chat and when you're done do a thumbs up sign rather than raise your hand because now I know you can do a thumbs up and this one will also be about 10 minutes so s till so in other words for me it's

**24:51** · 53 and just regarding the question on um tags yeah normally you wouldn't tag every commit your commit message should identify what you have committed but for example if you're just at the point where something's being sent to a journal it might be useful to add a tag to that to help you locate it later on because you're gonna end up with loads and loads of commits um so hopefully

**25:14** · that answers that question yeah you'll also see them the place you're going to most often see them or at least I feel like I most often see them but I'm entirely Jaded by what I do as a data scientist um is that I see it on like when you see you tag you tend to tag releases of packages so if you're using an r package the version 1 whatever whatever is going

**25:37** · to probably be a tagged release or it probably should be a tagged release and say that that's the tag the commit and you're just using the app it's probably best just to restart that exercise so I go out and go back in again or um yeah reload the app

**26:05** · there's a question on if is there commonly agreed upon a best practice language for tagging or commit messages for example should be adverbs or actions Etc is just responding but yes uh typically you do probably want a verb um but the important thing is that it will make sense to you later um and it will be intuitive so things like changed

**26:32** · variable probably not super helpful because future you will not understand what variable you changed or why you did it so there is definitely kind of a a fine art to commit messages um that I don't necessarily if not perfected by any means um you usually want them to be quite short so you don't want them I think it's you get a kind of message being like consider having it less than 80 characters I want to say um so don't

**27:00** · write a thesis but like say you know updated adae for new safety flag or something like that might be a good commit message because you understand exactly what's

**27:17** · changed yeah a lot of times people feel like Version Control is for collaboration within a larger group but honestly most of the stuff you do for you and your future cell like at least that's my experience

**27:33** · like future Alex will have no clue what what Alex today did so keep good track and make sure that the commit messages are meaningful to you and just to answer a couple more of the questions you don't need to give a name to the new Branch it's just fixed as I think analysis to um and when you're tagging using get INR Studio I don't think there's any colors no it's just um it's just identified as a tag the color coding in our shiny app is just to um

**28:04** · help you see when we get to slides and things which ones are the tagged ones which ones are just committed are just

**28:23** · committed and I think tagging was on the commit one you don't need to tag anything in exercise the second exercise making branches maybe I should work through the exercise do you think Christina yep I okay so all we're doing is this is the

**28:46** · main branch this is our Network diagram we can see my first commit my next commit and my final commit like you saw in the previous example so we're going to make a branch and then we're going to add commits so two additional commits and if we picture ourselves being Camille and she was editing her graph this commit at this point could be um a

**29:13** · cleaned oh may maybe she wants to do something different so like uh revised for journal A or something so we can commit that and we've branched off the main uh Branch here we've created a new

**29:29** · branch and then she's carried on working on that and maybe she's added some color and \[Music\] formatting and we could be more specific about what formatting she's done but um

**29:47** · we add a second commit and we're working along this Branch now and that's fine we could carry on working along that brunch but maybe now she realizes that she's done something here that she didn't really need to do

**30:04** · and she thinks oh my goodness when was the last version I had that that had code that was more similar to what I want to do now maybe she's explored one wave and anal analyzing something but it's just you know not what she wants to do anymore she wants to go back to a version that um is more like where she wants to go now so she can change and and um can change branch and she can check out the main branch so the way to do that is change from your new Branch

**30:36** · back to your main branch and you can see this is now in bold indicating that we're back on our main branch again and if here she wants to um go back to where she was and add changes aligned to journal B's needs she can add that

**30:58** · commit there and now we're back on the main branch and this is working on sort of maybe Journal B's um specifics now at any point she can still navigate back and we call this a checkout to the new

**31:14** · branch and we can see here that this was actually revised for journal A and it starts to tell you what your codee's doing whether it's working on journal A whether it's working on Journal B um you know what you're exploring at that time and helps you locate the of code that you want so a commit has been added here and we've also got um the commit on the main branch as well so if we go to question

**31:43** · two we're back in the version of um finalizing things to journal B because we're the Bold one here's at the end this is the code on version four again you can check out each of these and have a look how the code changes just make this a bit smaller so you can see it on the screen maybe like that so that's version one of the code version two of the code we tagged this in our first example so

**32:10** · we know that this is the version that was uh cleaned up for journal A and so by checking out each of these um committed versions um we can then do a branch from the tagged out version and commit that it would have

**32:36** · asked you to do a commit message if you in the actual system but this is just an example and we can see that not just branching from the last version we can actually Branch from um any version of the code that we've committed or tagged and if she has more commits she can just keep committing along here and working along the the two sets of the branches so should we go back to the slides Christina

**33:18** · sure I swear by the end of this I'll actually be able to share slides in Zoom okay so a quick recap of the exercise made a branch we committed to the new branch and we've now tried checking out different branches so checking out is most like where you're mostly going to use checking out in your day-to-day life is between branches it is kind of the most common way um to just go about things so making branches is fun we

**33:47** · maybe have a lot of branches but realistically we probably want to bring back some of the changes we've made in the past so for instance in our main branch Branch one example potentially the things on Branch one would be useful to us we might want them we probably

**34:06** · don't want to be just making changes everywhere it's like having it's basically like having a billion versions of the code running around which we are trying to avoid that's why we're using git so what we're going to do is combine them back together to do that we use the git command called merging so we're going to just merge things together by checking out the branch you wanted to merge into so in this case we now see our little head has come onto Main and then we are going to merge in Branch one

**34:34** · so we'll say like the get command for it is get merge Branch one into main so great perfect most of the time that's how it will be it's quite easy to merge things in there won't be a problem but occasionally we have conflict conflict is never good we don't like conflict but what happens with conflict is that so git is tracking the changes per line right I

**35:02** · said that at the very beginning the thing that makes it get commit get a little bit unique and what makes the commits unique is it's tracking the changes in the file as opposed to the files themselves so what happens in when you have a merge conflict is basically

**35:19** · in Branch one and in Maine there's two file there's like a single file where the on the same line there's a change so two people two branches have changed the same file in the same place and git doesn't know how to resolve that fundamentally git is a bit dumb like it doesn't it seems really smart it's not um it is not going to keep track of things chronologically or anything like that so even though let's just say maybe

**35:47** · you haven't touched Maine for like a month and you've made all of your updates to Branch one and you're like why would you think git that it should be made should be in front of this or like this little commit bu bubble should happen first it's going to go like I don't know I'm not making decisions here so it needs to know how to resolve these things um so when you do get a conflict what will happen is it will complain about you saying whatever file has a conflict in it fix it please and in that

**36:21** · file you'll end up with something that looks like this you'll have kind of Three Special lines that have been added in the less than sign which then usually says head although sometimes it might say main um the equals line and then the other the

**36:39** · greater than sign so on the less than sign is it saying this is It's just telling you the branch that you were on um or whether you're at head so basically we've as you said before where you're currently located is usually called head so it's going to say you know head everything between the that line

**37:02** · where it says head and the equal sign comes from that one branch everything from the equal signs to the greater than signs come from the other branch and it's just telling you what branch things come from so let's just say you wanted to keep all the code oftentimes this I would say is the most common thing I do is I just need all the code um if that's the case all you have to do is delete the things that got it in there you're going to just get rid of the equal signs and the greater than and the less than and voila Presto you just commit this

**37:34** · change um and go forward and there's no problem but what if you didn't want that what if you're like oh you're totally right get like that's old code I don't want that so maybe let's say we were you know running our models with the lm4 package we were doing them an mmrm but now we're using the new mmrm package so we're going to get rid of everything that came from that lm4 stuff so in this

**38:00** · case it's only one line but you can imagine a scenario where potentially it's a large chunk of stuff all you're going to do is you're going to delete everything from the less than sign to the equal sign and then also just delete that greater than sign at the bottom and you'll end up with something like this so basically you're just going in there and directly editing the um code at the

**38:22** · end of that you're going to commit it and everything should go through without a problem it won't let you commit unless you've deleted those greater than and equals signs also they would just make your code not run so that's why you need to delete them but it adds them in so that it helps you know where the conflict is and it's easier for you to figure out exactly what it's complaining about so with that time for another exercise um we did say it was fairly Hands-On so um this one is going to be

**38:51** · again you're working through the app you're going to work on question having the merging branches section up here so

**39:07** · work through questions one and question two again do put any questions you have in the question box and do a thumbs up when you're ready to go and then we will continue so we have 15 minutes for this exercise which should mean 415 if I'm doing my maths correctly that's not what I would like to see but we'll get there cool so yeah that looks good so

**39:36** · the exercise here wants us to pull the updates we have made on the analysis Branch into Maine and to do this change the branch uh we change the branch to Main and then merge so we check out Maine going there ah you see that little dot that

**39:53** · outline moved here we're now back on Main and now we can merge that worked well if we undo the change for example and say hey uh go back to analysis 2 we check out analysis 2 and would like to merge that well that's not meaningful right because we would like for our changes that we did in the analysis 2 Branch to be reflected on Main so yeah just make sure to check

**40:19** · out Main and then merge from there that works smoothly so then we want to pull the updates we have made on the analysis Branch into Maine but this time there is a commit on Main already change to the main branch and merge to see what happens okay I wonder what so we'll try to merge

**40:43** · same as last time now oops there is a conflict so remember the conflict um description here basically tells you okay you have this highlighted content on head so everything from the less than

**41:00** · signs to the equals is a content of on the head and then um basically everything between the equal signs and the crater signs is on the analysis 2 Branch so we can either keep both of them or let's say we would like to keep only the changes on analysis to we delete all of these confusing less than equal and greater than signs and

**41:29** · commit that's perfect now we were successfully able to merge that's nice right so going back to the slides let's see where are they right here yeah uh what we did in

**41:48** · the exercise is we merged a branch into Maine and yeah we we checked out uh different commits and um resolve a merge conflict so that was nice right keep in mind that a merge conflict is nothing to be overly afraid of uh we now know how to resolve them we now know how to merge branches even though there might be a conflict and I think this is where you take back control Christina stop

**42:25** · sharing oh you're on mute

**42:44** · Christina there you go I'm so good at technology um anyway just a so now that we've done all of our merging let's have some quick R rules of th about kind of branching and merging generally branches are cheap

**43:00** · so feel free to make a lot of them there's no cost having lots of branches around necessarily um the thing you have to be aware of is that the longer a branch grows away from Maine whether it's that Maine grows really far in or the branch grows really far or both the harder it will be to merge them back in as we saw merging in one conflict is not a problem it's pretty easy but when you have 30 or 40 conflicts Suddenly It's a lot of work to do so really the goal is

**43:30** · always to minimize the number of conflicts you have um to do that the best kind of best practice is to branch make an update commit that update merge that Branch back to main delete your branch and then start a new Branch um so it's better to just kind of constantly have small little branches think of it more like Twigs rather than full-on branches we're going for a very bushy twig type tree rather than an oak or

**44:00** · something I don't know now we're we're really questioning my Arbor my Arboretum knowledge arum knowledge anyway so now we can go back to our case study so Camille was going to do all of the updates for journal A she had everything planned everything organized but then she got busy um and so now she actually needs some help in order to do the updates so to get that help syvia Sylvie

**44:26** · has joined um her team so sylv is going to do help Camille and to do with those updates to journal A for her which is great now remember the beginning of the course where we talked a little bit about git versus kind of GitHub and gitlab and those sorts of things that git is just on your local computer but not anywhere else so all of the work that camil has done up to this point is just on her computer she doesn't have it online in a place that she could share it EAS eily with Sylvie now a g project

**44:58** · is not really the sort of thing that you tie up and put into an email so she's going to need a way to share this with Sylvie so the best way to do this is these kind of cloud-based services like GitHub bit bucket bit bucket gitlab what have you um to do that what will happen is you will get a cloud-based service and have a repository in that service then you're going to be able to mirror your loc what's on your local computer onto the kind of into the cloud so in GP

**45:31** · we talk about things that are happening on your computer as local and things that are happening in the out in the cloud far away world as remote so what does that look like in practice how does that actually happen so to walk through this with camil Camille has everything on her computer right so she's done her tags all of that's good now she wants to get it to share it with svie so first thing she's going to do is she's is going to go into the cloud and create a repository in the cloud for her to push

**46:03** · to then she's going to push so push is just the git vernacular of saying mirror what's on my local computer onto the internet so she's mirroring what's close what's locally to her to the remote location of the cloud great once she does that sylv's able to come down and then she can clone or copy that repository to her local laptop so now Sy

**46:34** · has it on her laptop and Camille has it on her laptop and they have a combined place in the center on the internet where they can share with each other which is really good so now Sylvie has her on on has the code

**46:49** · on her laptop she's able to make some changes the first thing sylv is going to do is the thing that you guys did right where she makes a branch and then does some commits great so she has something that you guys just had in your exercise everything is going well but she wants to share the code with camil so the first thing she's going to do is she is going to push when she pushes now it

**47:12** · that new branch that she created gets pushed into the cloud and so it is also in the remote so now she has local version of that branch and a remote version of that Branch amazing great the next thing that's going to happen is camil actually wants to run this code she wants to be able to not just see it on the internet but see it on her computer so in order to be able

**47:33** · to run that code what Camille's going to do is she is going to pull that repository down now the eagle eyed of you will notice that she did not clone it down and she pulled it down and those are different words um and that's just because there's a little bit of get Nuance here but when you clone it you're copying the whole thing usually for the first time whereas pulling it is just going to pull the updates that have happened so because she already has all of has

**47:58** · the main branch and all of the commits with that she just needs to pull down the updates not necessarily the whole thing um so that is like the general workflow of working with remotes versus locally

**48:14** · so as with all of the other things we've done so far another exercise for you we did tell you it was going to be quite Hands-On um so we're going to do another exercise and maybe Phil will play some more jazzy music uh I say 10 minutes but so far everyone's been super Speedy so maybe closer to five um but again ask questions if you have any questions in the chat box we'll be around to help this time we're going to be working

**48:44** · through the remote section of this um app so it's the final section we're almost done with using the app you will have two questions question one and question two um and then and we will come back so yeah showing my new superpower how to share the screen sharing perfect so let's see we're finding branches now so uh we

**49:14** · have the remote this is the repository that is located in the cloud um local is what either we or in this case Camille and Sylvie will see on their local PCS so um yeah remotes main we see this

**49:32** · network graph here um it has two branches it has the main branch it has analysis 2 so remotes is definitely the cloud repository and we're going to main should be here yay this feels nice then local analysis too local is

**49:50** · the version that Camille or Sylvie pulled to their local PC so um it is no longer in the cloud they cloned it or they they pull changes from the remotes and now we're on their local PC and Analysis 2 is the analysis 2 Branch so here we fixed the book

**50:13** · correct so we're now able to distinguish between branches we know what is meant when people refer to the remote it is the cloud repository and your local version is just well in this case a mirror of the the cloud repository going to question two so

**50:33** · we're now walking through sy's workflow to make the updates for camil um first we're going to clone the repository um because so far it's only living in the cloud so the first thing in order to get this network C and all of the the changes and code versions to our local drive we clone this rep repository that's what we do now we need to check out the tag commit by clicking on it the tag commit is the bubble in

**51:04** · red or pink here so we're checking this out going here it says code V2 and from this we create a branch so we're branching up this Tech commit um and we add a commit on this new Branch saying hey yeah now we are in analysis 2 um we just have this change and this this Branch locally nothing is

**51:29** · visible in the cloud so far we can also add additional commits really doesn't matter and then once we finish and once once we're happy with the state of our code we can push that to remote this will make our changes be visible um to

**51:45** · um either Camille or Sylvie whoever we are not yes yeah correct so now everybody on the project team can see the new branch and the um edits that have been made in the analysis 2 Branch yeah so going back to the slides here what we did sorry

**52:12** · who that is not where I wanted to go um give me a second we located different branches that is what we did in the exercise um we clone the repo we created a branch and push changes back to the remote so no big deal honestly

**52:41** · right this was the the case study for Camille and Sylvie Sylvie is part of the project team now let's imagine some random stranger Edward is now entering the scene here's some person on the internet who's unrelated to the project

**52:57** · but he wants to contribute but camil wants to retain control of her original project and thus she would like to protect it from outside changes and prohibit Edward from branching off of it Edward is not able to do that in order to still be able to use camil's work as a starting point Edward might want to Fork off of camil's repo the fork is basically a direct copy

**53:23** · of camil's repo where Edward enjoys full ownership so there he can do whatever he wants and at a later point in time Edward can decide to open a so-called poll request or you will hear people refer to it as a PR and proposes changes to the original project now again this project was protected so there Sylvie or the project team around her have control

**53:50** · they see the changes proposed by Edward and can then decide which parts of the fork to merge into the original project or rather not so this is a really cool thing let's see how this works so we see the cloud repository right and we see Edward right here at the bottom Edward would like to clone the repository in order to apply his

**54:17** · changes but he's not able to do that because again this repository is protected so he can't do that in instead he creates the fork so again we're dealing with the protected repository but now he creates his Fork this creates an identical copy to that repository but now he has full ownership so he can do whatever he wants and from this new remote repository he pulls it uh the content to

**54:48** · his local computer and he can now continue working this is really just a copy of the protect um repository but he is now the owner so now from this one he is able to pull and apply his changes as he

**55:07** · wishes so yeah now Edward is making his changes on his local computer he's happy with a version of his code and he would like to push these changes back to his Fork again he can push to the pork because there he enjoys full ownership so no problem and for these changes in his Fork to be reflected in that protected repository

**55:31** · he opens pull request so the poor request is simply asking the owner in this case Camille or her project team um and it suggests the changes made by Edward you can see this is kind of grayed out so Camille can now approve or reject the changes so yeah after camil has reviewed

**55:53** · and approved at changes they merged into the repo cool stuff right so as a summary Forks allow for this kind of controlled collaboration outside of a designated project team and users can create Forks um which is just a copy of the remote um protected repo where they are the true owners and they can do whatever they want and hence um yeah they they

**56:22** · are able to apply all all changes they would like to apply so to promote their changes back to the original project they can then open poll requests soal PRS and the project maintainers can decide whether to approve the PRS or rather not this is a case you will likely encounter in the development areas of our packages right access is granted only to the designated team of the core developers but not to everybody in the outside world so if you are a user of

**56:52** · that package and you encounter for example a bug and you would like to propose a bug fix then you would create a fork of the P the package repository change the code parts that cause the buck and then open the poll request to suggest your changes with a buck fix to the um core team of

**57:12** · developers they can then go and review your code see if it makes change and merge your changes in or they can also reject them like whatever makes sense right here the owner of the original project is really in full control and yeah this basically concludes the theoretical part of the section we have learned how to read Network graphs we've learned a lot about commits branches pull push uh how to

**57:41** · clone a repository how to differentiate between our local repo and the remote and finally we'll learn about Forks good stuff right and now we'll have a 20 minutes break this part is going to be a Hands-On session um where you can follow what Irene is doing Irene now let's see if I manage to screen to share I know it's super hard right okay so this session has uh Alex

**58:13** · said is going to be very practical so the idea is that uh you follow along if you can so we will go as low as possible as needed and I seen that there were a lot of question uh that we said we would answer here if I forget something um just uh again rewrite it or let us know

**58:32** · and we will try to cover everything so managed to share but not to move the side no so what we will cover the idea is that we will for this course we chose GitHub as was said at the beginning other platform works exactly the same it's just this one that is the most used

**58:53** · so we decided to go for this and I we'll show you how to Fork a project and why we will have to Fork the project and not clone it and then uh we will have to do a little bit of setup because we will have to set the G identity in a way that you can actually commit and the system will be able to know who has commit and then we will have to link your uh environment that

**59:17** · you're using so deposit Cloud to your giab and then we will try to follow along and make commit push create branches merges and at the end to do a p request this is actually kind of what happens usually when you to work on an open- source project you will kind of follow along those kind of procedure so the prerequisite are that

**59:43** · you have access to posit Cloud but as this has been solved at the beginning with the app I think should be good and then that you have a GitHub account if you do not have one you can just follow along I will share my screen and basically it will be the same that you would be doing but so this is the

**1:00:03** · prerequisite GI account it's free and very should be very quick but if you don't aggress if you you don't want one you don't have to have one you can follow wrong but you can get one they're free and easy to get like posit Cloud takes about the same amount of time yeah good point and uh this course is based on G

**1:00:25** · integration with our studio so we will show you mainly how to work with the GUI with a little bit of exception for the terminal we will show you along but so if you have question just ask doesn't matter which system you want to to see so we will start with uh the project that actually we have kind of used uh or

**1:00:50** · or less through all of the examples so the link has been shared I think I think right now even uh Alex has shared it so you should click on it and we will just look how GitHub looks like where you can find information and then we would get the code and Fork it like this we will be able to start

**1:01:17** · working so you should be able to see the G um that was shared let us know if you have any issue and um as you can see this is a project that is located on PSI as so you can see where it sits in the remote in the cloud it it is a public

**1:01:43** · project so meaning you can see the code um this also meant you cannot unless you're part of the project you cannot just get it and um make changes so just one second I'm going to try to keep the the

**1:02:13** · up actually have I been can you hear me yeah we can hear you oh I actually could okay it went blank I no idea why and now I can actually even see the chat cool so um what I was saying is that this is a public project so as you're not part of it you will not be able to just get a code and make changes that's why you need to Fork instead of Cl it and um there was a question before you could see if someone had forked the project and actually yes you can you can always know how many Fork have been made

**1:02:46** · and a very um nice tools that is in GitHub you can go in inside and if you look at the Network you basically will see what has happened until now so here for instance it's a very simple project you have a main branch you have a second branch that hasn't been merged back and you know that there is only this location every Fork that will be you will be able to see it here so it you

**1:03:16** · have a good track or whatever has taking your code now if you go back to code um as we said before so if you would be part of the project you just copy the URL and you would be able to bring it down to your location by cloning it here we don't have the rights so if you try to do that it wouldn't work so you would have to perform a fork and you will have to do it here it's good if you're already link um log in into your GitHub

**1:03:49** · is when you click create a new Fork you will see see that here it already appears uh my GitHub because I'm linked and maybe will you will see the same otherwise you might have to log in the default is to only copy the main usually when you want to propose a change we want to change the main so we will leave it like this will only copy the main branch and will just be easier so just need to create a

**1:04:21** · fork might take you a little bit and then it should bring you into your own GitHub now as you see here I still know that I've been fored from a place but now it's located in my own remote it's my own place so I on this code I can do anything I want so and this is when you Fork you're now the owner you can do

**1:04:45** · everything and this means that at this point you have it on the remote so when you do a fork it goes from the cloud in a position yes and the network graph you need to go in inside here and then it's

**1:05:11** · Network actually this is nice because we know we took it from here but now the main branch is in mine so we can see that uh we have it what we would have to do now is to take this code and bring it into posit Cloud because we want to start working on it this means we will have to clone it down to your workspace um this means you will have to

**1:05:41** · copy here the URL the https and go back to your posit Cloud we start a brand new project so you will have to go on your workspace and you will have to click on new project from get

**1:06:06** · repository and you tell me if I need to stop because I don't manage to read the comment okay so this should clone your project from your own geub directly in here and will take a little bit but you should see the same um code that was in GitHub directly

**1:06:47** · here I see that there are a few question about thatt to create a fork it's in your Reginal git it's up here and I see that 29 have been created it's a good sign and I pa it

**1:07:10** · C so now we have our classical art studio and um everything has been brought down um as I was saying before we will do a lot of the action using the git guy that's here just on in

**1:07:29** · connection and tutorial and all of the main action are down here again this is this is to perform simple action you can more or less do everything complex things unfortunately they're not covered here so they have to be done on the terminal but in general for your normal workflow you should be able to just use that and uh perform everything so here you see that everything is white because nothing has changed now we are up to Main and

**1:08:01** · um if you want to explore and if you want to go to see what has happened to this project you can go in history and this is very similar with less fancy than what you see in uh GitHub so you have the chronological uh information of all of the commit have happened with the code so you can actually see what has changed and what has not change um you can by looking at the

**1:08:28** · color code so get tracks by line so anything that has changed it will know if this line has been modified or not and uh it will be readed if I've been deleted and it will be green if it been added like this you can see all of the changing and it's pretty nice because you can compare code here we only have main we only have one branch because we only clone that so right now is a very simple

**1:08:55** · structure as you see here can you go back and just show the foring one more time for people I think there's some people who are I think that happened quite quick okay so you need to go to the PSI aims G training that is the first link that was shared and it's here so you will have to click on the fork on here sorry and then create a new

**1:09:29** · one well I already created one so doesn't work sorry but that's the process and when you go through it it will and you and you click on Fork it should bring you to your own GitHub and you should be able to see the same uh in your own

**1:09:50** · GitHub and then just make sure that when you're going to make your new project in our in the posit Cloud that you're copying the URL from the forked version not from the PSI as version because if you go from as it will say you do not have access to do so and that's because

**1:10:08** · you're trying to clone something you don't have access to so remember how we were talking about the difference between forking and cloning that's when you're going to need to to clone your forked version and to the question if you create a new project you just go to your your workspace create a new project and then is new project from the git repository and in there you place \[Music\]

**1:10:42** · your let just see if uh there is any more question about it before we start with the with the next setup yeah I think it's it's getting your head around um forking the repository and that being your duplicate if you like of the repository but then in our studio you don't have that project visible so you have to go do new project and Link through to that fork that you've done to

**1:11:15** · tell um are what project you want to be working on and I think that might be where people got a little lost yeah just remember that the fork is always in the cloud so you're right to think of forking and cloning is very similar except for cloning takes it from the cloud to your computer and forking takes it from one place in the cloud to a different place in the cloud so we need to go from one place in the cloud to a

**1:11:43** · place that you own in the cloud and then from the place you own in the cloud to your computer so you're gonna Fork it and then you're GNA clone it okay think it looks like people have caught up it looks like we don't have questions iina you can go back go

**1:12:02** · forth so right now what I was showing you before in the history it's like um you can see that basically the only person that I work is actually Christina in this and you have her name everywhere and um G needs to

**1:12:18** · know who has made a change to be able to say who has committed a change so this is going to be a little bit painful because we will have to set up your git ID and then we will have to set up a secure connection between this that is you kind

**1:12:38** · of can consider this as your local machine it's just a your environment that you're using now just your local place and you will have to be able to link this with your ghub account because right now you just clone it down this is a it's a it's a public project still but you won't be able to push back changes unless you have security linked the to there are several way to do so and we have picked one that

**1:13:07** · in theory is the easiest so when you have this project open here you should see the file system on the bottom right and you should click on ged. R in here you will find the code that is actually needed to help help you set this stuff up uh this is a new instance so you will

**1:13:29** · have to install a few package so you can you can run line nine and it will instead two two package that will just physically help to set up your credential take a little bit of time see if everybody has found this

**1:13:51** · F done and at this point you will have to tell git who you are so in here you will have to write your username that's what then will happen will appear as your your name the person has done the commit and your email that is used for your giab account and these are the two main thing that will be needed to do to do this part

**1:14:22** · so

**1:14:39** · you will run it and you should not see anything so you should just you will not get a message this has been set up not not just by doing this but now G knows who you are and what's your email and the next step is to create what's called a personal access token it's basically a long string of letter and number that will

**1:15:09** · link yes what Alex is saying is that if if you have everything set up local on your machine via SSH via anything that you have you can of course skip this you will then have to use your Loc machine you won't be able to use deposit Cloud but it's totally fine for everybody else just run the create GitHub token this will open again your GitHub page and it will open it

**1:15:42** · um to a page that I'm going to show you on the slide because I will have to set up that as well and the token is something you don't share it will bring you to a page in which you

**1:15:57** · basically need to it's already pre-filled all of the setup are done you will just have to write what is the token about just for you to know where are you using this one and at the end of the page you need to click on generate token now what's him again you need to run the use this

**1:16:19** · create GitHub token to open the web the web page prilled describe what your token will be about it can just be R for Pharma course or whatever and then generate it now what is important is

**1:16:34** · that uh you will see a long string of letter that start with GHP you will see it only once so you need to copy it because you won't be able to retrieve it after you have clicked that you're okay with it you really need to copy it somewhere safe and then we will will move back onto the

**1:16:57** · um uh the you will have to move back on to deposit Cloud I will leave you a few minutes to do that there you go it's done it third times the TR did it didn't like that I share my desktop I wanted to share only this so it means I will not be able to go back and forth so if you run line 22 in the same file of the git cred credential set GitHub path if you just run that empty it should open here a

**1:17:30** · popup where you enter the password you just copy okay and uh don't get freak out if you see um that there is a cash timeout it's fine it should any way work can you increase the size yes better

**1:18:01** · okay um at this point you can also just to to make sure that everything has been set up correctly you can run line 33 and this basically gives you a overview of more or less what you have at the beginning you will see that um personal token has been discovered so I'm set up it's fine hope you all

**1:18:29** · are so to a bit more no you're fine Chris um Irene I think it's fine you think it's fine yeah I think you increased it after that message sorry slow and

**1:19:03** · um I guess you yeah well no I can only share one screen so I canot share any more the PowerPoint but yes when you open the token page just just write a name go the very botton and generate and copy that string and we swear this is the last we do today then it's

**1:19:47** · fine I guess we can go ahead so what we're going to try to do now is we're going to do all of I mean it's going to be a little bit artificial because we want to try to show you several of

**1:20:06** · um if you're using your local R studio and it's set up to get there is absolutely no difference you are in your own GitHub you can clone your project so you can use your local it's just that sometimes there are a lot of restriction if you're using your work computer sir but if you have complete admin and you're using it you you really don't have to use posit Cloud the the only other thing is you need to make sure you have git installed so git is actually a software that you so if you're on a work

**1:20:38** · computer you probably have a software Center or something of a various name that you probably maybe can install get from depending on what your computer your work computers rules are otherwise can't remember where you does it I can't remember where you download it from the internet um yeah I'll put some

**1:20:58** · instructions in the chat box H perfect though thanks otherwise it's on the internet um and you can get it there but if if you're on your personal computer but yeah yeah you need to have git in order to have so part of the the biggest reason we're using posit Cloud right now is because posit Cloud already has get installed so you don't have to install any software and we are sure we can make I think we have the link to to the installation page in the

**1:21:30** · appendix uh May yes yes I think that is the first link we are providing in the so what I was saying is like now it's going to seem a little bit artificial we're going to try to do commit and we're going to do branch and we're going to try to create a conflict like this we can uh go through how um

**1:21:53** · so bit so it might seem a little stupid but just uh consider that the changes we are making is just an example of how you would be able to work so what we're going to ask you is to actually first of all I forgot to say an important part of this G GUI is that you know where you are when you look at here so right now you see we are in main we actually if you check there are

**1:22:19** · there is only one there are no additional Branch there is only Main and you can see that locally we have Main and in the remote there is only main because this is by remote so we only forked main branch so this makes sense

**1:22:35** · and um what we will do after to create a branch and we will switch from one to another to avoid too many conflict because we're going to do a PO request at the end what we're going to ask is to just copy this file the red me that we read me if I can speak just copy and just add your name at the beginning so like this at least we would just create a new file you will have conflict with yourself because we will make it happen but it will just simplify um the work

**1:23:10** · after now uh let's just make some changes and this is a g training in a me we can say and I excuse myself because I make a lot of titles uh I just say that we describe the training and that's it now here I made a

**1:23:30** · change I save and you can see that this has pop up here I made a change before on the G cred when I added my name but we will look at this after so now we have um this file that I actually want to commit because I'm happy with the change we have done and to do so you need to stage it so stage it is a concept that basically so git will track when you decide that you want to track a set of

**1:24:02** · changes um if now I unstage this and I make new changes without committing it from this version that you have here and what I change after G will not be able to tell so you will when you're happy with the changes that you have you need to Stage it meaning at this point if I do a commit I'm happy with this version of the file I want to take a snapshot of this but by not staging this file I'm not going to

**1:24:33** · commit this file yet so I'm just happy with this so you click on Commit here and it will open actually the same page that we looked before for the changes but now we're just looking at this file here is nice because as usual it makes you see what has changed here I just mean because you shared only that screen we can't see the screen okay I need to try to share my desktop let's hope that this time it

**1:25:13** · works let me know yeah it's worked worked okay so now we see the the popup that after you click on making a commit it will come up what is nice here is that I mean everything is in one place so you just write your

**1:25:41** · commit and uh for a question before because I've seen in the chat that there was a question about if I can uh change the message of a commit um just if you click that it will actually change the latest one you can change any commit it's not great but just by doing amend it will join the last two here we are happy we do a commit and um we can close this and you will see that now we are back to only have the G

**1:26:13** · crb because it's the only thing that has changed so basically this file that we have modified and commit now we don't see anymore but it's still only local we haven't pushed it back so my remote hasn't seen that I've added this file to push it you can just put on the push error and uh as we have set up the P token is saying that is is pushing back the change into

**1:26:47** · main now is everybody okay yeah we're all good I'm just don't worry keep going you're good you're doing great because you I see you big in the screen and I see you with a face like ah no I will try to be have a more

**1:27:10** · joyous disposition so now we have um if you go back here we see that we have the G cred that has been modified so now for instance you want to see what has been modified because maybe you have done something by mistake you can click on the diff not on the commit well also on the commit and you see that here I've actually added my name maybe you don't want to do that maybe you want to keep this file just as it was to be the the template you can

**1:27:40** · just do more and revert if you do that will tell you that you're going to lose changes you say yes and actually what we have done is that the G cred has gone back to the original form and uh yes and we're good now let's look in the um

**1:28:07** · history in the G history and now you see that we we have a new commit and that is my name now now let's say that you also want to work on something else you want to start to create a part of the shiny up so you

**1:28:31** · don't want to mess up with this so you're going to create a new Branch like this anything that you change on this Branch will just stay there and until when you don't decid it to merge it will not influence me to create a new Branch you need to use you can use the GUI you need to click on your branch put a name

**1:28:56** · cannot spell brch and as you see here there are already some default uh that are clicked so sync Branch with the remote it means that you are creating your branch but you're also mirroring back to your own remote so after doing

**1:29:13** · that if you go back on giab you will see that there is a second Branch it's not only local it's also on the remote basically you will be able to store what you change in this Branch back if you click create um here you see quite a lot of code just for you to know very often uh what you have here it's code that um it

**1:29:37** · it it's the G command to do what the GOI is doing so when you create a new Branch through the GUI you are automatically in there so as you see here er a branch I've been moved there so it means anything that I change here I'm actually only Chang it in the branch and not in main now to continue our example we can

**1:30:06** · keep changing this file because then we will create a conflict and you can say that in line three we are developing Shin \[Music\] up same as before you need to save commit

**1:30:38** · and commit needs to be a lot more precise than what I'm doing here I mean they need to talk to you you commit and we're going to push back now here you can see that as we were working in the branch here is push back to the branch not in main so you're not affecting anything that is in

**1:31:08** · main right now so we were in Main and a branch has been created and there have been an additional change this is oh branches this this is still linear just because main hasn't

**1:31:30** · changed so now we're going to try to create a conflict and to do that we're going to go back on Main from the top uh right and here you were saying that you switch back to main so in in term that's what the term that was used during the course you check out to me and as you see our code has disappeared so what we have changed on the branch

**1:31:59** · it's not year so if you switch back it's back same file same everything but you're just into parallel branch that for now they're not talking no some's we have a question in the chat about the history could you briefly show this again please see other thing I mean can you make it less wide your your git tab bar because

**1:32:30** · it does collapse a little bit so you lose the word history when it's skinny so you can see when you yes it's here you made it skinny so you click the clock yeah but you want to make sure it says the tab at the top says get as opposed to saying there's a tab that says history it's not that tab I did it three times so yeah that's the history of the code that has been run this is the the history that is the

**1:33:00** · history of the gate commit to look at the network graph and for now the network graph doesn't really look what you might have expected because maybe you were expecting the branch to be off just because it's a branch but for now main hasn't changed so it does seem linear we're going to change Main saying that we are adding

**1:33:31** · picture save usual

**1:33:47** · commit now we're going to commit and push directly and we were in main now so we push back in may now if we look at the history and you will have to click on all branches otherwise you will not see because the default it always go back to either one or the other you see that now we have actually my Branch where we have started to develop the app that now is back so right now

**1:34:20** · those two have diverged and uh as we have changed the same file on purpose they will uh conflict

**1:34:39** · okay so right now there are several way to perform merch and there were questioned before about the different type of merch as I said before we are using the GUI and the giab as much as possible and so the first time we will show you a merge is going to be through GitHub by actually performing a pull request to yourself seems very

**1:35:02** · strange the other option that we show you after is in the terminal that I actually realize I haven't showed you that there is a terminal so in our studio if you go next to the console there is a terminal and this is a a full terminal and if you need to write any git uh command it needs to go here

**1:35:22** · so just the most classical one it's get status to see what it is and for instance it tells you that you are a main you're happy there is nothing different this is a lot of things all so all of the thing that you perform through the GOI they translate into get uh comment you

**1:35:44** · just don't see it but so what I was saying is like for now we're going to go through the method through the GUI and then we will do the terminal way merges are local merges are a bit of a special case because actually doing to the GitHub it's a little bit convoluted but we stick to the to the to the logic of this course and uh the question about the different uh merge so maybe you can um write a little bit more I guess

**1:36:17** · you were asking between a a merge and a rebase I'm not sure what you were asking about the person that ask about the different type of merge so maybe if you can write in the chat we can go uh quickly

**1:36:36** · through okay before going there I'm just going to Super quickly go again over the branching as that is the question so the the branches are handled through the the guy and this part so if you click on

**1:36:58** · the error next to main so what what is written here it's where you are so which branch you have check out meaning where if you make a change it will stays in there now here you can see that two branches exist one is the one that we have created in which we have developed the app and the other one is the main and we have both Branch available in

**1:37:24** · GitHub you see they are in the remote to create a new branch and again you can create as many as you want that was Christina was saying they're cheap uh we show you how to delete them if you don't want them but you can you can create as many as you want and to create it's uh the purple box and you need to

**1:37:46** · write a name and again leave the default as they are because it's nice it's already pushing back to the remote this this branch is going to be mirrored otherwise it's just local is not very useful and um the other thing to think about as you're going between the branches it's just like what we did on the app with question two yeah so that is should I just that is exactly

**1:38:15** · what I was saying is that so head is where you are so what is said in the kind of it says main over on the top corner I'm pointing at my screen which no one can see um because it says main it means that that is where you're located so it will you'll see here when she looks at when she's looking at the history that the origin SL head so the

**1:38:37** · where you are the head is where you're located so in the app we were had the thing that told us where we were was that little black circle around whatever commit dot in this view it's going to have that the wording origin SL head so but that is the head that I was talking about when we talked about it within the app and origin main just tells you so the origin is another name for the

**1:39:11** · remote by nomenclature it's referred to the remote can be anywhere but the specific location for us is the origin so the origin main means that that is what is online like that is the the thing that is on the remote is there I mean you're probably going to go through all of this and it will make more sense um no it's great because if you do

**1:39:40** · a commit here but you don't push that commit you'll see that the origin Main and your main end up in different spots until you push it yes and those are both pushed so that's why you see like that yeah and uh for the question about

**1:40:05** · um so when you merge there are different strategies that get allows you to merge and this is that's going to be theoretical because we're not going to do it so you can merge merge because the common the the gig common is actually merge and what you do is that you create a new commit that is a merge of these two and I'm sorry if I'm doing this Windows here to answer the question uh the rebase is slightly different you will bring this branch that you want to

**1:40:33** · merge and bring it in front so it actually change the history is going to the it's not going to add a new merge commit you're just going to move the one on top of here and uh it

**1:40:49** · actually kind of you you lose the history of the commit but there are cases in which one is better than the other and I guess also personal preference uh generally for merge merge yeah I was say generally for the case of Pharma because we do like auditing things and we do like histories we don't generally recommend rebasing because you lose that history so that's like a very broad you might do something

**1:41:20** · different but for the most part we're going to say merge merge or go through a poll request when you're doing poll requests it can be important to do them which we're going to cover in a second particularly if you're doing like package development you're helping with an open source package you want things to go through po request if they have something called GitHub actions associated with it which is basically just a way to to run a bunch of automated checks and things like that if you have automated automation involved

**1:41:51** · you can't do things locally if there's automation you need to do things in the remote that's what we're going to do now yeah just to show you how you can merge your branch into ma through GitHub so if you go back to your GitHub meaning

**1:42:12** · your um to mine is my own name not the PSI one you will see that now the there is you have this yellow box that is basically telling you then there is a new brch that has new pushes so what do you want to do through the system you can merge it by going through the it's

**1:42:37** · basically an assisted merge you will have to click compare and pull request I know it's a little bit weird because a PO request you usually associate with I send it out my code and decide yes or no to to

**1:42:53** · bring it in here you're basically asking a p request to yourself but still makes sense in term of how you merge things so you're going to click on compare and pro request and I'm going to ask you to just be careful because the default is PSI

**1:43:09** · because usually when you do a put request again is to go back to the original project so you will have to select here what you want now there are all of the different Forks but uh I'll choose mine I mean can you stop sharing and reshare one more time because it seems like there are a couple of people with problems with your screen I think that must be their end because if we can see it then it's obviously sharing okay from Irene so I wouldn't Irene in case it stops fair enough good point I'm

**1:43:42** · sorry I think if some of us can say it then it's obviously not Irene's end this is just maybe just a little bit slow here my connection should be fine but you're good you're good sorry I'm going to get no worries so as you said you need to select your own uh version not the one on PSI otherwise just going to do a put request to Christina uh and

**1:44:07** · then you're going to you basically here you see the error it's basically saying you're going to get the the branch into main is already telling me that I cannot do automatically because we change the same line again get uh tracks line so if we would have changed different places in the file we might have been able to do it automatic not in this case so um yeah here it reports what's your last commit what's nice is like here you can write of course not to yourself but when you do a real request and you do create a full

**1:44:41** · request so it's going to tell me that I cannot automatically merch as you can see here and the conflict needs to be resolved so you need to click on resolve conflict it will open uh a text file that is

**1:45:01** · basically the same that you saw in the exercise before it's the same concept you have the the symbol that describe what it comes from um the branch and what come from Main let just say that here we want to keep both because we're happy with the development of the app and with adding the picture so you will have to take off as we saw before all of the weird uh

**1:45:30** · symbols and once you're done you just say that you have resolved the conflict so you're going to Mark as result and you're going to commit so this to go back is a merge merge so you're creating a commit specific for the merge is not rease you're going to commit and the

**1:45:50** · change but you're not done yet until when you don't do merge for request it actually nothing has been probably merged so we're going to do merge for request we really want to make sure that you are sure confirm merge and you're good to go now here is even proposing you to delay a branch uh from gab you can only delete remote brench not the local one

**1:46:19** · and we will see that after now we leave it but you know that you can do it from here because very often the process is as Christina said you make a change commit go back into main you're done you can delete that Branch now we're going to go back on the posit cloud and what we're going to do at this point back in Main and we're going to pull so we're going to get the changes that we have made in GitHub with the git

**1:46:48** · merch basically and it's going to tell me that he's bringing down stuff and indeed we have the version that we have merged on the system

**1:47:13** · okay why did I take offline um without even realizing it's a it's a bad sign uh um so this is a mer through the go now um what we can do is to actually say we're happy with the changes we've done and we're going to try to do a proper pull request but this time to the original um

**1:47:41** · project and yes so I will go up to the full request I again I cannot do the same anymore just because the branch doesn't exist anymore but we're going to do a pull request to Christina uh original project and you will see that it's basically the same so all the pro requests need to be started from giab you cannot do anything from here so if we go back to um GitHub

**1:48:17** · code now you see that at this point um um I don't have the yellow box anymore that he was saying I have a branch that is ahead of main do you want to merge it back that that would have been what we did before but at the same time there is something here that is relating to the original project so you can see that there is a contribute and there is a SN Fork so this will go over after if a Time syn Fork will be um you made your

**1:48:49** · fork you took time to make your changes now you want to go back to the original project but maybe the original pro project has changed so you can actually not do it directly first you need to integrate the change make sure that everything is fine make sure that the change have not broken your code and when you're really happy with it perform a PO request right now is the simple case the project hasn't changed

**1:49:15** · so we can go directly and do uh P request and the P request can be uh started from contribute here and open pool request and he's telling me that I'm five come here ahead than the original one to go back to um the do you ARA can

**1:49:43** · you make a version uh can you just finish creating that and then show people how to change the their location once they've made one so like once you've made a poll request you can go back if you've sent it to the wrong location which some of you have I've messaged everybody who has who has sent it to the wrong location ah you need to go back and change your destination which should be super easy to do yeah but right yeah but

**1:50:15** · you need to if you finish making it so if you make this I yeah you can do need to delete it actually do you need to fully delete it okay yeah you can change fair enough it's what what I did by mistake yesterday to you so there we go it's easy to do but it's not hard to to make a new one it's just a click of a button I think you cannot we can check merge with original

**1:50:41** · project okay the idea is here if you're actually working on an open source project you want to be very exhaustive in the change you made you can right the changes you made and Etc so this need to need to consider that as a conversation with the developer because it's just going to help to know exactly what you've changed and what are the the news uh it's actually um it's my

**1:51:06** · markdown type of writing in here now I'm not going to do it but just and I'm going to create a request in this case you should be able to merge automatically but it shouldn't allow me because I'm not part of this so right now I cannot do

**1:51:28** · anything anymore unless you close the request and that's also a way how you can yeah what you said if it's on the wrong location and you do close board request you I think you can go all the way up to the top and hit the edit button and change it edit to the right hand side oh and then your base you can change it to a different place I'm blind where uh yeah no where

**1:51:56** · you clicked I think you would just have to put it in I think it would you can choose a branch that is to go to though here is between Main and Analysis yeah I'm merging into I don't

**1:52:12** · enough mind take back what I said but you can side note if you close the request super quickly you're going to get a badge on GitHub saying that you've been reading quick joke so right now actually I think Christina you need to share your screen because I cannot do anything anymore I need to wait that she approves What I've Done yes okay so now if I'm

**1:52:47** · here I see people have been doing mer in poll request which is great I'm going I go to Arena's one and then I can merge this poll request and approve it um oh confirm

**1:53:07** · merge you and now actually yeah you're not going to see it but everyone else will see that they can think the new stuff so if we tried I I'm going to pull in somebody else's at random um they've now added a new file that says um Ana's

**1:53:37** · copy just double check okay I mer this full request for merge great I'm going to stop sharing and AR do you want to go and see about updating your fork because that was a question hopefully you can see my let me know when since we had an issue okay so right now Christina has changed her version so this means that I

**1:54:10** · cannot directly bring down from here what we were working because this environment is linked to my own version of the projects so this means that you need to go

**1:54:30** · um okay code code is in your version and what you will have to do is to sync so I actually accidentally went to my work again that's why it was only one thing so you will have to sync and it's telling me that the branch is out of date it's telling me how many commit and

**1:55:04** · Beyond so we're going to update the branch again as we have different file with different names here was not a conflict I could directly get it all was good

**1:55:22** · otherwise it will it will again open the gooey to merge conflict just to someone's asking a little bit about um the merge about me pulling things in let me run through that a little bit slower I went super fast so I'm going to steal back this screen for one second

**1:55:47** · here so just to explain a little bit more about what's happening from my side so I am the like lead developer what have you so I have the authority to merge things in but aren doesn't because remember she the whole reason she needed to Fork this is because she is not part of the team so because she's not part of the team she had to do things in the Clone or in the forked version so

**1:56:13** · because she's in the fork version here I'm going to pull through and do someone else's Al one docs um so I'm gonna have a view that looks something like this one of the things that I'm going to do because this is the kind of thing you should do when looking at P requests is before just merging this in I'm going to look at the files so I went to files changed um and I saw what vicr did um honestly I was

**1:56:45** · just checking to make sure no one accidentally put their password in but fundamentally that was all I was doing I was just checking what the files had so now that I've seen what those files are and I'm happy with them I can merge this P request I'm the only one with the authority and the the you know decision making power to do this poll request to do this merge um and so basically now

**1:57:10** · I'm going to merge it I've checked the code merging it in when I confirm the merge now if you all sync that you'll also be able to see vr's um version of the code so now if I look at my

**1:57:25** · code my code has three files aren's file because that's the one I did first and then two other people's files because I did two more poll requests um so the reason I did two poll requests is mostly that so that Irene could see

**1:57:44** · one if Irene tried to sync it would say there's nothing to sync because her version was the last version I pulled in so it was really just to allow you to see the syncing so I pulled something else in but now we have three things so we now have three files um fundamentally

**1:58:01** · that's how you're how it's going to the that is how PO requests work when you're doing working on like in the open source is you typically have to ask the main developer hey can you accept my changes and they will look at your code and then they will probably accept their change except your changes or maybe ask you to do some modifications so in the setting of the case study that we had back I think three hours ago almost um Christina you

**1:58:32** · are Camille you are the project owner you have all the authority on your repo and all of the other people who want to merge their pull who want the pull requests be mered in are the adwards like Christina has Authority she reviews all of the changes she approves them or comes back with wishes for

**1:59:01** · change okay so for the protection question I'm gonna go back to sharing and then I mean it's all you um so the only thing about protection is protecting branches is generally a good idea if you're working with a lot of people but as we've seen you guys can't push anything into M unless you have unless I've like approved it because you guys are working on a fork so when you protect a branch

**1:59:32** · you're protecting it from your team that is like has access to read and write what you're going to do is you're going to go into settings and then you're going to go to branches and then add a protection for the most part your not really going to need it but I

**1:59:53** · can there's a lot like of guidance about it I don't want to spend too much time on it because it's a little bit of a side thing but yes you do want to add protections and you just the branch name pattern is probably the hardest bit which is not that hard but basically sometimes you will have a lot of different versions of a branch of like

**2:00:13** · a uh so maybe you'll have multiple versions of Dev or something like that so you might say Dev star which would say apply this Branch to all things that are called Dev we're going to just apply it to main like that um but I'm not going to apply it because I'm the only one who's on this team so I don't need to protect it from myself but anyway arene back to you um okay

**2:00:47** · so let's see if I get granted should be working yeah well waiting for your confirmation but it should be working so at this point as uh well actually now Christina has merged other of stuff I have done the sync this is going to be actually a good opportunity to show you how to perform a local merge uh from um main to your bra brch

**2:01:20** · so from Main i p and I I get the extra file that um from the latest pool um

**2:01:39** · thing that Christina has accepted now if we go back in uh you see I also do that history all the time in history and you select to look at all branches you can see that right now the head is here and there are the results of the pool request that I bought in however I had my Old Branch here actually doesn't have all of this what does it happen if I act sorry

**2:02:10** · we had a question about the head so whilst you're on this tab did just want to explain the difference between the origin Main and the origin head again just briefly uh it I actually found it extremely complicated myself it's just that a head is where you are Al so technically the

**2:02:27** · the origin head is where it is in the origin so remember anything that starts with origin slash is what's going on in remote versus locally so functionally it doesn't really matter too much where the origin head is it's you can kind of ignore that the thing that matters to you is where your head is and that's where you are so because arena is on Maine she her

**2:02:56** · head will be onade you can do some fancy things and have what's called a detached head which means that you're not at the end of the branch which is what we were kind of playing around with in the app where you would move you would check out previous commits and then go there you can do all of that we're not um mostly for

**2:03:19** · Simplicity but it's definitely possible but yeah for the most part the only thing you really care about is where your the little green thing is yeah now I before the head was in main because if we would have changed anything it would have been there right now I switch back to my old branch and you see that the reference to get it here so it's telling you where you are I think that sense

**2:03:54** · now we're going to try to do this local merge and we're going to do it through the terminal just because it's something that might happen if you want to do something only local you just want to in this case you want to bring whatever is in main into your branch as you saw in

**2:04:10** · the exercise to be able to merge into something and this can be a bit convoluted you need to be in where you want to merge into this case means we need to go to the branch and then we are going to merge so we're going to do get merge and we're going to rate M main because that's what we want to merge we are in this

**2:04:40** · branch and we want to merge into Main and just by doing that we are brought back all of the file that were in main into my branch in this case there were no conflict if there would have been a conflict uh posit cloud is set up that it would open a file here a new file that is the commit file where you will have to select as you did before exactly the same taking off the weird uh sign

**2:05:09** · the weird symbol and it's going to be exactly the same what we' have seen in the in GitHub it's just a little simpler for certain thing because you stay local you just want to do local now we wanted to cover another thing that you actually cannot do from GitHub that is actually to delete Branch so right now we have uh for instance a new branch that I've done by mistake and uh you want to delete it locally because again on a remote you

**2:05:40** · can do it through GitHub we're going to move to Main and we to delete a branch you just need to write get Branch because all of the comment related to Branch or Branch minor stick you want to delete it and then the name of the branch of course I don't remember right now New Branch that was

**2:06:06** · it and you have deleted so you will not see it anymore local again it's sometimes good practice to take off if you have many many local branch no unfortunately not every can be done without using the terminal I don't think you can delete L maybe I'm wrong I'm not a very strong user of the GUI I

**2:06:28** · don't think you can delete you have to do this on Terminal you can't do it any other way so if you've made a bunch of branches and even if you've deleted them through poll requests and things like that they'll still be local even if there won't be a remote version um and

**2:06:49** · that's and like here it's the opposite Irene hasn't deleted the the new branch in the remote she's only deleted it locally so you can see it's under the remote origin tab but not under the local section um but I think the opposite is way more common that you end up with the thing not being in your it's not in remotes anymore but you still have a bunch of local branches hanging around kicking around that's how you're going to delete them that that Dash

**2:07:21** · D yes and I would say uh another thing that it's it's actually easier to do through the terminal unless you do it through the release and giab is actually tags those are probably the two things uh that might be you might have to use the terminal and in the slides you will

**2:07:43** · find that there are a lot of reference at the end and there is like a all of the main comment on Terminal that you might ended up using usually if you do all of your merges through Port requests because you're working on open source and you have everything set up through some jobs so you have all of the check done and beside the leading Branch you probably don't have to use the

**2:08:13** · terminal I see that there is a question and then Alex I might leave you the FL because so we have a couple questions we could go back over I guess you can delete it by just uh doing kind of a grap on the name if you have like all of the D you can

**2:08:37** · delete all of the branch together you have to check in Min you definitely can and I just don't remember the code so I look it up every time very possible I always look it up that is something where chat GPT is absolutely yeah yeah rck um just stuff

**2:09:02** · like that highly recommendable this usually works with grax let's say so if you want to add stuff that you want to add it there you can do by asterisk and points I guess it will work also there but I would be surprised that there is not an option somewhere that says oh

**2:09:19** · like yeah one question we had a little while ago was can we copy files from one branch to another or into main without necessarily doing something like merging and I think that's probably a good thing to address so kind of no um but also kind of yes so

**2:09:40** · you're completely allowed to use copy and paste copy and paste still exists um but also what's more likely to happen is like what we've seen here Irene's copy of the read me and the aa's copy of the read me both ended up in this Bran or in

**2:10:01** · her other Branch wait even if you go to your other Branch it will be there um originally they started in other people's branches and then it ended up in the kind of origin one right the the the original C one through that sync function to sync

**2:10:23** · her fork with the original she got the files onto her Main and then once she got the files onto her main she used the merge functionality to do that if you have say a big project with like hundreds of files and you're on a branch with and you only want one of those files and you don't have 50 of the files or something like that first of all just be careful

**2:10:49** · what you're doing but let's just say you only need one file you want a specific file and you specifically don't want any of the other files then I there are times I just use copy and paste like it's just not trying to be potentially and I don't think it's a good practice let's put that out but you can also do it from here because here you can add a file so you can be in M

**2:11:13** · you can be in main on the branch and you can add a file manually will be still tracks through a commit that is done automatically when you add a file this could be a way to do it but yeah but don't you have to download the file and then re-upload the file yeah yeah so sorry copy and paste I'm using as download file from one branch upload file to New Branch so that sort of thing which bad practice it doesn't get tracked that it came from one file to another you don't get that history um

**2:11:46** · but uh so wait other questions the other question I just remembered that we talked about ages ago and I'm going to mention now is the dev the our thoughts on dev branches um I can give my thoughts I'm not sure we've actually had a conversation about this amongst the four of us my general thoughts feelings and Vibes about this as someone who has a horrible memory is I tend to use my main branches where

**2:12:16** · my main development is I don't push I don't pull do poll requests of my other branches into main unless those branches work so Maine should be functional but it tends to be quite deaf for me and then I used T I use Tag releases as like

**2:12:34** · this is an official release um so I use that in order to let people know this is the good bit this is the clean 100% release bit um or a lot of the things I do I put on cray so I'm using cran as that like external marker of standard

**2:12:54** · rather than using Maine to be a I only have released versions on Maine I as someone I've like had things that haven't been released on Maine but they have been on dev and then I've like pushed that to cray and all sorts of chaos because I forget to do that final push to main main but usually my projects are just not complicated enough to Warrant having a Dev and a main basically but that's what I do I don't know Irene what do you

**2:13:29** · do oh she's quiet you've gone away have I scared you off did she just get kicked out she just disappeared I know just disappeared don't know um I can't comment on that CHR but no other people do use Maine as their like the only release versions go on Main which I think is totally fine basically because I work in R primarily and R has the like niess of having craye

**2:13:58** · where everyone goes to get releases people are not really looking at my GitHub to get releases from that the expectation that my main is perfect is relatively low so kind of depends on what you're doing um okay would be great and Irene's coming back sorry I got kicked out no worries no worries are you ready

**2:14:27** · for me to take over or arene what is your thoughts on what is your thoughts on the dev versus because you do the opposite don't you you use Main and Dev and then M and Dev uh for just a reason

**2:14:42** · to have one branch that is always connected to the package manager and is this is really like what shouldn't be it but it's just it's just a nomenclature that we have decided at the beginning but I've seen people that don't use main at all because they don't like the name of Main and they just like they change the name of what's the the main got it's very difficult to explain that but I'm for being simple as well so I totally see why you have a workflow like that depends on the constraint

**2:15:16** · yeah we just have one more question that there's something that seems not to be working but I got kicked out of the chat so can see so what would be the command order of actions if you wanted to or needed to uh handle a poll request locally thinking a more complex case where you Tinker with code so when you're doing a poll request locally that's when you're doing the merch

**2:15:46** · um um so that's when you have the kind of what arene showed about the going onto the branch that you want to merge into and then using the get merge command to merge that

**2:16:05** · in and then as very is struggling to see the files that could be because either in the long wrong location couldn't it like if you've not checked out the branch that you're pulling to or because this often happens I think doesn't it where you you're not getting the changes pulling through um and you need to find out why I think that's a common issue have you performed a sync from the PSI to your

**2:16:39** · remote otherwise you wouldn't be able to see what got added hi can you hear me yeah yeah so so savy um actually so I I guess Christina accepted my change um which got pulled into the main um and then I didn't see a sink anywhere after that but then I just refreshed it and then I saw the three files Vic Irene

**2:17:11** · and mine uh in GitHub but not in so I did yes everything is up to date but I don't see it in POS I only see it in it is it possible because first you need to do this syn Fork I actually not sharing the screen I'm sorry yeah you need to do a poll request so you need to pull down from

**2:17:36** · from the remote where everything is onto M sorry I'm about to be jumped on by a cat um uh Irene you have trouble sharing your screen again at least for me oh my God like but this is a great question AI because this is what happens all the time and then you're like why can't I see things and it's really frustrating so I'm really glad you ra this one yeah please share pull it down um she said

**2:18:01** · that she sees it in in depending on which GitHub because if he sees it on yours that makes sense but he also needs to be on the forked correct so I think that's what it is yeah actually can you share can you share your what you're saying try I can try again but it didn't work for some reason he hates me well uh no I was thinking um

**2:18:27** · yeah I'm very confused why it particularly doesn't like you isn't working I mean oh I'm sorry it worked for a long time so it's not we can yeah I can I can probably share I can share you might uh drop off and see if coming back helps it but no guarantee quick idea I can shot okay um because I

**2:18:54** · think I have the authority to look at everyone's Forks so at the very least I can look at the fork um I think this is one of the most common things of people getting confused when we're just struggling to kind of sync everything back together when you want to

**2:19:24** · sorry I'm trying to to type as fast as I can okay so this is me looking at the everyone's Forks so if I go here yeah so the the problem is I think that you're probably looking at the PSI SL GitHub because when I look at your repo

**2:19:51** · the there's only your file there's none of the other additional files so you need to go back to your repo and sync it and it should and then those files should be able to appear the sync button is going to be like right there but I don't have a fork so I don't have a sync um how do I go to my rep sorry you

**2:20:12** · can go to your repo by honestly going if you you're now probably on the PSI a skit training page and no it's fine she can just go here she can go let me just undo the link sure otherwise she could have used the fork thing because you you only see your own Fork then it takes you

**2:20:43** · there you can also always click on your name if you click on your GitHub name in the top corner here or like I can click on my version and look at my repositories it will be

**2:20:58** · everything I've ever like cloned or forked so for instance I forked the r taes um thing and actually this is a good decent example because I am eight commit or eight both eight commits ahead and 53 commits behind so I'm going to sync that and I'll have to discard a bunch of commits but that's fine um and now I'm

**2:21:22** · all up to date so you should be able to do something similar um to so when you think that Christina it you'd made some changes eight and you discarded them but then it almost brought in the 53 commits that have been made to the repository since you last synced yes exactly and this is specifically because it's a Fork isn't it not a branch from so tree yep

**2:21:53** · perfect you've brought your you've brought the branches in you've synced correctly because now I also see them in your repository thank you no worries okay I think it's now time to hand over to Alex for the last little bit of going through some novel things we can do with GitHub if we want Alex do you want to maybe do 10 minutes of it and then I'll do a summary um yeah sure I'll run through it

**2:22:24** · real quickly um so yeah um no worries you are through the worst of it the hardest part lies behind you so can you see my screen I guess you can um we're

**2:22:41** · officially in the cool down phase so what I'm going to show you is nothing stressful at all you don't have to WRA your head around how to clone a repository get all of the code into your posit workbench and none of that will will play a role at this point I'm going to show you how to work with guub issues um and I've used myself as a as a example here so imagine me and I I

**2:23:09** · personally love deer but I tend to struggle with deers filters um because they tend to drop missing values it just if something is true and if it's anything other than true could be missing um then it drops that I would really love for that to be implemented as one of the filter features like there could be an option where you say Okay include missings true or false so what do I do R is really this great

**2:23:39** · open-source code language so I'm going to take it to GitHub and I'll create issue asking the depler team to implement that so in order to do that let's take it to the Internet so Google is your friend the first thing we are going to do is we're going to locate the GitHub repo for

**2:24:12** · deer so you can see this here is a GitHub link it says okay tidy bir which is the overall structure under which deer is is managed so we're going there and if you're struggling with something like if you if you are not sure if something is an issue or not or if you would like to have it implemented the first thing you do is you check if somebody else has encountered similar issues like is somebody else looking for

**2:24:40** · something so you take it to this issues tab here this is basically the L page this is where all of the plier is managed um these are the issues you can see open poll requests you can see um the insights here for example looking into the network graph that Irene has showed you you can also see that it has 57 TXS so that's kind of cool you see all of

**2:25:08** · the the versions the stable versions have been tched in GitHub so that is that is something cool um to remember and that is that is basically the package code so we would like to see if somebody on the internet has already opened an issue related to

**2:25:27** · filter and the the filter functions Behavior with regards to missingness so I'm seeing all of the open issues here um currently 55 of them are open and 4,838 are closed um we also say see something like

**2:25:48** · the contributing guidelines here like if we were to open an issue um and we're being asked to adhere to the guidelines you can look into that it basically gives you this structure and code of politeness um

**2:26:06** · how to open and cont open and issue and contribute to to Deer so a lot of packages will have that just read through it and make sure to keep all of these things in mind when you open your issues we however are checking if something exists already so the function we're looking at is filter and let's just see if something related to filter and

**2:26:39** · missing filter is open um what did I do wrong okay nothing I probably hit the wrong key so now we are looking for open issues where filter and missing is already mentioned we can browse through them and see okay this one here for example

**2:27:08** · option to optionally retain missing values this sounds promising right so currently filter retains true drops false and an a this matches subset this user well it's Davis Rowen um he would like to request something like retains true and an a drops false and this m

**2:27:31** · matches the brackets H that is basically what I'm looking for so there is no need to open the issue for this um this specific use case um if I am interested in um leaving a

**2:27:47** · note there um I can I can write a comment like if you see we can see that this is an issue that is already being worked on but if you see that a user or a package author is pretty idle and does not reply to your or the person who has issued this um this request does not does not

**2:28:11** · really um reply to this issue um then you might leave a comment like Hey I'm encountering the same thing here same and you might want to leave a couple of lines of code just for the author to be able to see what you do so let's say I would like to open an

**2:28:33** · issue in the PSI aim SK training slides let's quickly walk through this see how it how it works I'm giving something a meaningful title oh it's prepopulated that's it's cool because I worked through this before so I'm choosing a meaningful title in my case um I would like to add

**2:28:55** · the option to choose missing value behavior for deer filter I'm not opening something in the depler GitHub right now I'm just showing it in a safe space which is currently the git training slides imagine this being the the deer repo and I'm writing a couple of lines saying hello team just be polite have a conversation with the authors and describe your

**2:29:23** · problem and then you can see that this piece here where I have these three little high commas and the r and three little closing High commas this is basically markdown language so here I can embed my code I say okay I'm working with deer then my tiple which is the test data that the author is going to use um this is going to look like this and the filter DFX YZ is what I would like to

**2:29:53** · have and you see when I switch from the right to the preview pane I can see this nicely rendered I also did that inline um code chunk or markdown chunk um where I can

**2:30:09** · see here that this is rendered and looks like code now so this is really nice so of course I could add a little bit more text but once I'm happy with how that issue works you would like to hit submit new issue and Christina as the author of the PSI as skit training slides would be informed that there is a pending issue in her repository and she could then reply to me yeah I'm not going to to do this here

**2:30:41** · but in principle whenever you are working with our package is and you encounter something that is not working the way you would expect it to do or it might work but it really took you a very long time to figure out how because you were missing some basic details in in the package documentation please take it to GitHub and use the issue function first of all check if an issue related

**2:31:11** · to something similar to your problem already exists and if it does leave a note for the author like hey same here I'm running this on our version whatever apply uh attach a session info that always helps and if it's related to a couple of lines of code um then provide a reproducible example yeah uh otherwise you open a new issue um kind of kind of going in the

**2:31:41** · same direction make sure to describe your uh your your um issue thoroughly add a couple of lines of example and then submit it newly um if you if you are missing something if you're encountering a bug it does not mean that you can never ever use the the um the package in the future uh the author might just not have considered your specific use case so please feel free to use the issues as

**2:32:09** · much as possible it is a great way to um yeah to to have a conversation with package authors and yeah hopefully get your issues resolved Christina did I overstretch my 10 minutes no you were exactly 10 minutes I'm bad I'll stop sharing them

**2:32:32** · you like to do the rest yeah I'm G just close this out um I guess we actually probably have a little extra time but I want to make sure that people

**2:32:48** · um are not overly done so I'm going to just do a quick summary of today and talk through kind of what we chatted about what we did go back in time to almost three and a half hours ago um

**2:33:06** · so let's just have a quick chat um and then you guys can be free but thank you for everyone for joining the session today and asking great questions and particip that that always makes a doing a workshop so much better but what did we

**2:33:21** · talk about today so you'll recall Back To Yonder year um we talked about the difference between git and GitHub and understand helping that and using that difference to help us understand the difference between what's happening locally on our computer or our posit Cloud session or wherever you happen to be working versus what's happening on remote which is today it was GitHub but

**2:33:44** · it can be whatever um we also talked a bit about committing and the idea of tagging things and that you can tag releases or when you've submitted a project for a final Sack or what have you um we also talked bit about branching and how branching can help us um understand basically branching will

**2:34:06** · help us do updates without having to mess with everything else this can be particularly helpful when you're working in groups of people because then you can do updates on your stuff and even if it doesn't fully run you're not going to break stuff for everybody else um then

**2:34:23** · we also talked a little bit about merging and dealing with merge conflicts finally we talked about remotes um the idea that there's something on in this case GitHub versus on your computer and then we talked about forking at the very end um once we talked about 4K we basically

**2:34:42** · immedi immediately switched over to have you guys practice so you guys made forks and you guys did a great job it looks like most of you were able to do the forks um I get to see the number of forks that were made and it's a reasonably High number so good job everyone give yourself a round of applause I know doing things like this is kind of big and scary and there's a lot of new Ling lingo but you did great um then we created a project in our studio and we connected our our studio to GitHub using a pat token um the one

**2:35:12** · thing we didn't mention about Pat tokens but it's probably worth mentioning or at least I don't remember mentioning it is they can expire um so by default I think the the expiratory is 30 days I want to say and I don't think we changed anything so they may or may not expire um it's fine it's just a way of it's kind of like you probably at work have a company password that expires every two months or

**2:35:38** · whatever your company's policy is and you have to constantly be making new ones it's like that except for you don't have to make a new make up a new one you just go and rerun that code again to open up the thing that makes a pat token copy that again and put it back in so it's pretty easy to do you'll maybe have to do it once a month or a little bit less frequently than that depending on how long it's set up but they can expire and so we've connected that up we' taught

**2:36:04** · you how to connect it which you may do again at some point in your life um then we also did a little bit of committing in our studio we looked at all everything in that little git pane in the top right corner um looking at the history and branching and all sorts pulling and P pulling and pushing um then we also talked a bit about staging um the idea about what's staging the

**2:36:29** · working directory the working directory is where you are it's where your head is right um so you can't see files that are not in your current working directory it's they can't see the files if they're not in the branch that you are on with the head um then finally we had talked a

**2:36:45** · little bit about local repositories versus what's on the remote we did a poll request we did some merge conflicts and we also um talked about kind of authoring issues and all sorts of things like that um and looking at issues which is one of the biggest things that you'll use giab for is looking at the issues for people if you don't end up doing open source development yourself um the other thing we want to leave you with is some additional resources we will send you this sor

**2:37:15** · sorry if you can hear my cat um we will send you these slides they will be updated on the git tra the git test uh training repo they will be put up on the git training repo which you have all forked so you will hit the sync button and then you will the slides will magically appear in your local repository or you can go back to the original PSI one and pull the slides from there um so I can recommend all of

**2:37:44** · these things the happy get by Jenny Bryant is um really quite a nice one for setting up things with r it's very R specific um so if you ever feel like you need a written resource that's not us in the future that is a good place to go