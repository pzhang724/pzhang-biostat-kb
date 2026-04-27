---
title: "SDTM programming in R using {sdtm.oak} package"
source: "https://www.youtube.com/watch?v=t62MICj_5Ng"
author:
  - "[[R in Pharma]]"
published: 2026-02-08
created: 2026-04-27
description: "SDTM programming in R using {sdtm.oak} package - Rammprasad GanapathyAbstract: The {sdtm.oak} package is an EDC (Electronic Data Capture) and data standard-agnostic solution designed to empower the"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=t62MICj_5Ng)

======SDTM programming in R using {sdtm.oak} package====== - Rammprasad Ganapathy  
  
Abstract: The {sdtm.oak} package is an EDC (Electronic Data Capture) and data standard-agnostic solution designed to empower the pharmaceutical programming community to develop CDISC SDTM datasets using R. By leveraging reusable algorithms, {sdtm. oak} offers a modular programming framework that can potentially automate the creation of SDTM datasets based on standard SDTM specifications. In this workshop, we will cover the fundamentals of the V0.1 {sdtm.oak} package and provide detailed guidance for programmers to begin utilizing it effectively. Users will be given access to an R environment for the session. Users do not need to install R or other tools/packages prior to the session.  
  
Resources mentioned in the workshop:  
  
\* Workshop slides: https://pharmaverse.github.io/rinpharma-SDTM-workshop  
\* Workshop GitHub repository: https://github.com/pharmaverse/rinpharma-SDTM-workshop  
\* ==sdtm.oak documentation: https://pharmaverse.github.io/sdtm.oak/==

## ==Transcript==

**0:00** · Hello everyone. Uh it's already time and uh we have around 30 participants joined this section and welcome to this section. Um my name is Shaolini and I'm statician uh from TA. I'm working in Japan.

**0:19** · So uh today uh in this session we will have Ram to talk about the SDTM OK. So um before the before the section I will uh have a brief introduction for uh Ram uh he's a principal data scientist at Ro genetic and with over 15 years our experience in EDC and the statistical programs and he

**0:50** · has he's passionate about developing our package and creating innovative solutions and automation.

**0:57** · uh he I lead the O team and the rock product uh inside of ROS and which is already utilized in the uh automated SDM in more than 50 studies in ROS or regulatory reporting and he is also the owner and one of the developer for the SDM or EK and so uh well uh I will hand over to you.

**1:25** · All right. Yeah, thank you. Thank you Jolene. Hello everybody. Um good afternoon and good morning for uh people from uh Asia joining this call. So yeah my name is Ram. I'll be leading this workshop today and uh let me share my screen and get started. Um I hope you all can see my screen. Um yes we can see it.

**1:47** · Right.

**1:47** · Thank you. All right. So um today we will um we'll um this is the stmm.org oak workshop as part of our inform. I'm excited to pres present the version 0.2 of the package. Last year um I did ran a similar workshop where we did version 0.1 of the package. So we have developed um a lot of new features uh since then.

**2:12** · All right. So yeah, I think um yeah um Zylin already gave gave an introduction about me. Um yeah, I am Ram. I am I am based in San Francisco. Um I am I am the developer for the ro version of the work package and and then following the footsteps of Admiral um we took the parts of the package that can be open sourced and we developed an open source version of the package called stmm.org book and internally in RO

**2:42** · the RO version of the package is being used uh in more than like 50 studies for regulatory reporting use and we have already done one filing um from the ro version of the work package all right so we had one more presenter but she's not joining us today she's on holidays I'll I'll skip okay so by the end of this workshop we'll uh we'll have updated the code for con vital al science, demographics and adverse event domains. So I choose one domain from each class.

**3:12** · Um so so you know like we can cover multiple examples and then you should have gained an understanding of how to use the estm.org package and uh and I have also a lot of resources available. So I'll I will walk them through while I am presenting. You'll also get a chance to see the package documentation form examples and and everything.

**3:37** · Okay. So uh we we think that you should have a basic understanding of the CISK standards but even if you uh if you do not have a basic understanding of CISK STM standards that's totally fine. I think you will still learn a lot from the session today and uh we also assume that you know R and how to use R packages and familiar with the R studio IDE um and also how to use the the the chaining for like chain parameter and and and write the code accordingly.

**4:11** · Okay.

**4:13** · All right. So we have a packed agenda today. So first 10 minutes we'll uh we'll set up the workspace and then followed by that we'll have a 20 minutes presentation of uh the stmm.org to give a background of work about the stmm.org network R package and then we'll spend 30 minutes um programming the CM domain

**4:34** · followed by a 10-minut break and then another 30 minutes for vital signs domain and then we'll spend 10 minutes for demographics domain and 10 minutes for adverse event domain and if the if time permits we'll have an optional exercise okay all right so let's do the let's do the SJ the works space setup. Okay. So, um probably we'll we'll help you in chat. Okay. So, I'm going to bring something to uh to the screen here.

**5:07** · So, I'm going to copy this and paste it in the chat. So, everybody in the chat, so if you click on this link, it'll take you to the posit workspace and then you know like then it'll say like join workspaces. Yes. And then you will see R inform STM workshop. then you need to click start and then the project will deploy in our inform or and the environment will be ready for you to use. Okay.

**5:33** · So once you click this link it's going to take you to uh to this and uh and you will see you know like R inform HTTM workshop and then you have to follow the click start and then you deploy and then you will see your own own session created like this. Okay. So I'm just going to use this this version that I have created. Uh but you guys can follow the steps and uh and and finish it. And if you run into any issues uh please post your question in the chat.

**6:02** · Uh I'll be happy to uh help you um for the next 5 minutes or so. So we have until uh we have like five more minutes to finish this task and then we can continue with the presentation.

**6:17** · All right. Yeah, it's well past the time. So let me um let me start the slides and then uh and then while while I'm presenting the sli while I am presenting the slides people can still uh continue with u uh with registering and and creating the workspaces. Okay.

**6:38** · All right. Yeah. So so once you set up your workspace you will already see uh um everything available there. Okay. So when you after you set up your workspace, I'm going to go in here and then know like you will see this um yeah you will see the folder here project and then you have the specification scripts and uh and and everything here. All the packages are are pre-installed and pre-loaded.

**7:06** · So you can directly go into the scripts you can access these uh these these files and start executing the program. So there is no setup required.

**7:19** · So or if you want to um if you want to uh do it outside of this workshop. So I'll paste this link to uh in the chat you can you can also use your you can directly clone from the gitlab and u and you can use in your your desktop or or you have if you have positron at in your desktop you can use that to uh to uh to run the exercises as well.

**7:47** · All right, on the next slide. All right, so let's starts with the slides. So introduction to httm.org. So about the package, this package was originally started with the collaboration from uh the CISKOA. Circus Kosa stands for Cisco open source alliance and and a lot of former companies uh were involved in creation of this package like ro fiser GSK vortex

**8:16** · research patent institute transition technologies and lot of companies so this is a part of like pharmas group of packages and um and this is like this this package is used to create STM and we have admiral to create Adam and we have like a lot of packages in farmovers to create the tables listings and graphs and this is like um based on the ro version of the R work package.

**8:36** · So we originally we first had Adams and TLG packages and e submission packages in form and stmm.org is the last one to uh to join the party and it addresses the critical gap. Um and now with the form packages you'll be able to do end to end clinical reporting development in R.

**9:00** · All right. So um why why was the stmm.org was the last one to join the party in formovers because you know like we have different sets of challenges in STM. So although STM is simpler and it has less complex derivations compared to ADOM but it has like different sets of challenges like unlike STM unlike Adam that has STM as the standard source

**9:25** · which has a well- definfined structure STM relies on raw data sets as an input and raw data sets can be widely vary from from study to study and also from vendor to vendor. Okay. So different EDC systems produce different structures with different variable names and data set names.

**9:45** · If you take the standard ECRF from the ECRF portal and design the same ECRF in different ADC systems when you extract the data, it is going to look different for each and every ADC system.

**10:01** · And also you know like there is no um standard data collection uh standards available across the industry although we have Cdash. So Cash is not mandated by FDA. So so so every company you know like has their own way to collect the data and also if if the data is collected in different ways when you extract it from the EDC it is going to look different.

**10:22** · So developing an package that can support the different EDC systems and also different data collection standards seemed impossible but stmm.org package exactly solves that challenge in the industry.

**10:40** · So version 0.2 is available on cran and uh it is EDC agnostics. So the package is designed in a way that it can work with different EDC systems and different vendors. So a lot of collaborators have tested this with different EDC systems like mediator, viva, wault and uh and and inform and they all confirmed that it is working and and also we tested with like different vendor data sets like ECG, lab and it seemed to work. Okay.

**11:10** · And also we tested with like different data standards. So the package is like data standard agnostic. So for example, ro does not follow Ca standards. So we tested the htm.work package in with the ro data standards and it seemed to work and we have like few uh few volunteers who test tested this with the cach standards. So it works and that means like it works for the cdisk defined cdash or any sponsor defined data standards.

**11:41** · So it provides a framework for modular programming making it a valuable addition to uh to form ecosystem. So when we start looking at the code you will see that the code is very readable and anyone who reads the code can easily understand what we are doing very very much similar to the admiral packages.

**12:00** · So um so algorithms is a key concept in in the stmm.org package. So it'll be good to understand uh a little bit more about algorithms before we d before we start the workshop.

**12:13** · So the SCTM mapping that transforms the collected source to the target source model are grouped into different logic and each of the logic is named as algorithm. Okay. So these the the algorithms forms the uh backbone of the package STM.org or package. So the algorithms can be reused across multiple studies um multiple domains and even multiple variables within the same STM domain.

**12:44** · So the algorithms are programming language agnostic. So if someone wants to take this algorithm and create a Python library, they should be able to do it or create a SAS mag SAS macro library, they should be able to do it. So we just chose R to implement these algorithms so that you know like we have an end toend uh connection in the form group of R packages.

**13:06** · So the STM.org has multiple R functions to represent each of these algorithm. Let's start with the first one. So um the the first one is the simplest of all algorithms.

**13:20** · Um assign no CT. So what that means is like onetoone mapping between the raw source to the target HTTM variable and has no control terminology associated to it. It's a s just a simple assign statement. For example, you know like when in the medical history um MH domain.

**13:39** · So we usually map the value that is collected on the CRF to MH term and the same thing on the on the adverse event domain. we collect we directly map the value on the AECF to the AE term without making any changes or applying any control terminology.

**13:57** · So and and you know like as you see the function name matches with the algorithm name so it and um and it has no control terminology associated to it. The name is like kind of self-explanatory. So it can be used across multiple domains. any any mapping that does not involve control terminology and and is collected on a CRF can be used for with assign no CT algorithm.

**14:21** · So on contrary assign CT algorithm is to map the values collected on ECRFs but has a control terminology associated to it. So examples are you know like vital signs position laterality and uh and and and you know like when you when you collect the values in the position.

**14:38** · So you can there can be like uh like maybe like 10 different values for positional laterality and then you just use this algorithm and the algorithm takes care of converting the collected value to the CD submission value and uh and and you know like if if your collected value doesn't align with the CD submission value it gives a note in your console that you can see that uh you have some non-standard values and this can be used across multiple domains as well.

**15:10** · An assign date time is an algorithm that that is uh that is used to map the the date and date and time or or or you know like date or time separately or date and time together on the CRF to to ISO 8601 format across any domain. This algorithm also handles unknown dates as defined in the CISK implementation guide.

**15:38** · All right. The next set of algorithms is like hot code CT and hot code no CT algorithm. So in some cases you know like you we don't collect the values on the ECRFs right like for example you know like for uh for for systolic blood pressure you may not collect yum yum hg as a as a as like a user entered value on the CRF on it will be printed on the CRF so that the site can enter the values in millimeter um he mercury so

**16:09** · when this when when when this is not collected in STM you have to hardcode the unit to mhg. So in any cases where you have to hardcode a value and uh that is not corrected on the CRF and you need to apply a control terminology you can use hardcode CT algorithm and hardcode CT hardcode noct algorithm is on contrary where you want to hardcode a value but that has that does not have any control terminology associated with it. In such cases you use the hardcode noct algorithm.

**16:40** · Couple of examples are you know like vital signs BS category you hardcode that to vital signs and in some cases you may have to hardcode the value of CMTRT whatever it is right so any hard-coded value that does not have control terminology associated to it so condition add is an algorithm where you want to check a condition and then perform the mapping like for example in this um in this example BS.BS BS method when BS test code equals temperature.

**17:12** · So we need to map the method only when BS test code is equals to temperature or you know like another example is MD prior equals 1 then cm. CM str equals before. So in these like in such examples you need to perform this mapping only when empty prior has a value of one. Right? So the condition add algorithm can check the value check the condition and if the condition satisfied it can call one of the uh associated mapping algorithms.

**17:44** · So this condition add can work with assign city assign no city hardcore city hardcore no CT and assign data. So that makes it very versatile. So you can check a condition and perform a mapping in one function call and voke calc reference dates algorithm is used to derive reference states in the DM domain like reference start date or reference end date those types of things.

**18:12** · All right so these are the core set of algorithms that we want to remember. Okay. So, so this is an example that shows you know like how assign no CT algorithm can be used across multiple domains across multiple variables. So if you see MH term and vital science original result and we already saw um a

**18:31** · term and you know like for for in lab domain it can be used to assign lab original result right and there is an example for a non-standard STM variable like cmtht in subcm is a non-standard stmm variable that means like this variable is not defined in the cdisk model still you can use the algorithm to perform the mapping so these are the five key algorithms and the same way All these algorithms can be used across multiple domains and multiple variables.

**19:04** · All right. So, so you may have a question like why why not deep player, right? Why should we even use this algorithm? So, hard code is just a mutate statement. Why can't I just use mutate? Why should I use hardcode CT or hardcode noct algorithm? So, that's that's the first question that comes to any programmer's mind who uh who is familiar with deployer.

**19:24** · So the stmm.org algorithms enhances D player functions. Okay. So allowing it allows users to perform multiple actions in one function call.

**19:35** · So like for example applying if conditions or control terminology in a function call directly instead of using case one statements. Just imagine like you your CRF may have like laterality and location collected on your CRF that can be like 10 to 20 different locations based on the CRF. So if you want to write a case one statement, your case one statement is going to be very lengthy. So instead you can just use assign CT algorithm and define the control terminology as part of your control terminology file.

**20:02** · And then your code is going to look more elegant and more shorter and easier to read and and also it it gives you some other advantages like it maps the HTTM variable only if the source contains data. particularly helpful when in case of hard coding. If the source value is empty, it does not perform the mapping and it hands the unknown dates very well.

**20:30** · So it covers both scenario when date and time are collected separately or together on the on the same raw variable and and it also helps with like the chaining of your code. So you can create the topic variable and one add one qualifier at a time using another concept called works that we will explain in the upcoming slide.

**20:55** · So while all these can be achieved using D player your STM.work package just provides a more elegant and efficient approach to uh to coding.

**21:06** · All right. So how do we program? So it's very close to the htm concept. So we provide a straightforward way step by step to do STM programming in R. So that is first map the topic variable and then add one qualifier at a time. So the programming steps are always the same for different classes like events, interventions and findings. So you don't have to do different style of programming based on the domain class.

**21:34** · So this picture kind of illustrates how you how we will program. So you know like it doesn't matter what domain it is we we first start with the topic variable that defines a record in the htm domain and once you do once you once you map the topic variable then you add the qualifiers like position test original result category and then you

**21:57** · add the identifier variables like study domain new subject ID sequence number and then the timing variables like start date, end date, study day, time point and all those So always you start here and then you add qualifiers, identifiers and timing variables. So we'll see this example when we when we do the programming. So what are the programming steps? So first you read the raw data sets and create the ID wars in the raw data set.

**22:24** · And how do I create the ID wars? We are going to talk about that in the upcoming slide. And read in the control terminology and then map the topic variable map rest of the variables. So repeat the map topic and map rest for every topic variable on your CRF. For example, your adversive CRF will have only one topic variable that's a term and then your vital sign CRF will have multiple topic variables like height, weight, systolic blood pressure, diastolic blood pressure. Right?

**22:54** · So you just repeat the steps again and again for each topic variables and then create the derived variables and then add labels and attributes. So that will be the last step. Adding labels and attributes will be the last step. Okay. So what are works right? So you may have seen like your our raw data sets can be in a in a long format where each piece of collected data is represented as a column.

**23:25** · So when we do STM mappings we often we have to we may have to transpose multiple records to uh that the in your STM domain will be a single record in your raw data set. For example, height and weight will be a column in uh in your raw data set but it has to be a row in your STM domain. Right? Alternatively in other other raw data sets like um your one record in htm domain will be created from one record in your raw data set like a term and adversive and raw data set is a great example.

**23:57** · So usually one record in a raw data set will will translate to one record in your AE domain and you know like in both cases we need to map the qualifiers accordingly right to the topic variables. So how do we know when we need to transpose and when we do not have to transpose? Right? So to to to solve this problem or to solve this puzzle, we created something called as OKD variables.

**24:22** · And OKD variables is extensible and uh you can add anything but the basic three required parameters is patient number, row number and the raw data set and the raw data set name.

**24:35** · So these are the three basic things that you need to have. But if you want to add more things on top of it, you can you can easily add it. But from from what we have done from what we have tested these three uh is more than enough for us to create an ID variable in a raw data set and then it works really nicely with with multiple different types of raw data sets. Okay. And these ID variables provide the key link between the HTTM data sets and the raw data sets during the programming. Okay. All right.

**25:05** · So we are right on time. We can uh start looking at the CM domain. Okay. So how we will code today? So I'll walk you through the coding of CM, DM and all these four domains and we will go get into the details of each function call and its arguments. Okay.

**25:27** · So after the first couple of exercises I have um a quiz for us to uh for us to keep engaged and then yeah move along very quickly. If you run into any problems, please your uh please post your questions in chat. So um even though I am looking at I have two screens. I have the chat open in one screen. So if if there are any questions, if you are stuck anywhere, if you post it, uh I can reply to your uh I'm constantly monitoring the chat messages, I can reply back to you.

**25:57** · Okay? And yeah, full scripts are available in the scripts folders. If you want to um um follow along, you can follow along. Okay. All right. So let's review the ACR of and then jump into the programming.

**26:14** · All right. So yeah, we have like 78 participants now. So that's uh that's amazing. Um yeah. Um so we have this is the ACRF and for for CM domain I have used the the CISK standard ECRF from this from this um from the CISK ECF portal that follows the C-ash standards.

**26:37** · Okay. So your topic variable is mapped from uh from this this field it cmtr and then you have indication and then you have cm dose. So the if if numeric then you map it to cm dose if character you map it to cm dose text and then you have cm dose u dose unit mapped and then you

**27:00** · have the the cmd dose formulation mapped to cm dose frm and then frequency mapp mapped to cmd dose freak and and route mapped to cm route and then your start date is mapped to cm stdtc And then you have an ongoing flag yes or no. If yes then cme tpt equals ongoing.

**27:26** · If yes then cme and tpt equals data last assessment and then end date to cmetc. Right? So yeah it's it's a pretty good CRF um simple and straightforward and it it covers like all the examples we have seen like six algorithms. I can explain all the six algorithms using this one CR. Okay. All right, let's get started.

**27:51** · All right, so if you go to the SIS scripts folder, you will see a file called cm c-tr. And uh yeah, this is the file that we are going to walk through. Okay, so you have um you have the reference documents. Okay, the reference documents are present in the specs folder um specs cm d- folder and then we distribute the CRF and then we can start looking at it.

**28:18** · Okay.

**28:20** · All right. So I'm going to run the one line at a time. So I'm just going to initiate the two packages. So before that I'll clear this so that like it's it's clear. So I'm going to select these two lines and click the run button. It is done and then I am going to read in the study control terminology. Okay.

**28:45** · Okay. So study control terminology is in the data sets folder. Okay. So it's a it's a pre-prepared file. So what I have done is like um you know like all of us have the htm specifications. So you can you can um you can directly read your uh your control terminology file from your HTTM specifications.

**29:08** · But for this for the purpose of this exercise I have stored that as a CSV file and I am importing that to a data set. Okay.

**29:18** · If you look at the data set is a standard data set. you have like code list code term code term value collected value and then pre and then the submission value and then any synonyms that we are using. So this control terminology file it covers all the domains. Okay. So I'm reading it and then I'm going to read the raw data set.

**29:39** · Okay.

**29:41** · And then you know like there there could be some blank values in the CSV file. So I'm converting that to uh to NA values.

**29:48** · Okay.

**29:50** · So if I open the raw data it's like a simple and straightforward. So you have uh TRT collected indication and uh dose dose unit formulation frequency route and then if you see for um for the date you have like unknown values here right?

**30:17** · So this is to show how unknown values can be handled and you have like full values and then also values with with with unknown.

**30:29** · All right. If you see we don't have an ID variables created here, right? So now our next step if you remember so we finished probably I'll go back to the programming steps here. Yeah. So we read the we read the raw data sets. Now I think now the next step is to we read the control terminology and then what is remaining is we need to create the um we need to create the ID variables in the raw data set. So that will be our next step to create the ID variables in the raw data set.

**30:58** · So to do that you have a function called uh generate OKD and it gets two parameters the patient variable patient variable is platinum and raw source is CM raw. So if you look at your CM raw data set, your patient number is platinum and then the name of the raw data set is CM raw.

**31:21** · Okay, so I'm just going to call this function and create the ID bars. Okay, the ID bars are now being created. If I open the files, you see the three additional columns are being created, right? So work ID is just the row number. So there are like 14 records in this raw data set and you see a sequential number. It doesn't care about patients. It just go goes top to bottom from 1 to 14. And the raw source is the name of the raw data set and patient number is the patent.

**31:54** · Okay.

**31:56** · So now we have created the ID variables.

**31:58** · So now I'm going to read um the DM domain. Okay. So I'm going to read a DM domain from formula STM. So power stmm is a standard um um uh package where you have like test STM domains. Okay. So I'm going to read it from there and then I'm going to um uh going to convert blanks to NA. Okay. So so you can also select this line and click run button or you know like you can click command enter to to run it.

**32:30** · Okay. So I have the DM domain read from the former HTTM package and all the blanks are converted to NA values. Okay. So then what is my next step? So my next step is to map the topic variable. Okay. So if I come back to my ACRF, my topic variable is mapped from the CMTRT and the raw variable the raw um raw variable ID is it. CMTRT right so

**33:03** · there is no control terminology associated I'm just going to map whatever the value collected in this field to this domain this particular variable so I may have I have to use the assign no CT algorithm okay so I'll use the assign noct algorithm and the assign no algorithm has like different parameters okay let streamm.org assign no city. Okay, let me let's check what are all the different parameters.

**33:46** · These all the different parameters for target that target variable raw data raw variable and ID bars. So when I first create the topic variable, I need to specify my raw data set name as cm raw that is available in the global environment and what is the raw variable where the value is present. I can find it from the annotated CRF is it cmtr right and what is the target variable I am creating is cmtr yeah so we have everything that we need.

**34:18** · So I'm going just going to run this line of code and if you see uh a CM domain is created with four variables right what are the other three variables you can look at it so you will always retain the OKD bars because this provides the key linkage between your target domain and the raw data set so see I have like 14 records and I have 14 records in my raw data set and I have created 14 records with cmtr already mapped.

**34:50** · Yeah, my first step is done. So then what is the second step? Okay, let's we have to map all the rest of the variables. So what are all the rest of the variables? We have to map the qualifiers, identifiers, and all the timing variables. Okay, let's map one variable at a time. Okay. So then my next mapping is CM indication. Okay. Send CM indication here. Again, CM indication is a free text field in CM domain.

**35:22** · Indication is not controlled by control terminology. So, I'm just going to map whatever value is collected in this indication is mapped to CMDC. So, I again I am going to use the assign no CT algorithm. Okay. So, I'm going to select from here to here and I'm going to hit the run button here. Now you see cm domain is created with five variables. Okay.

**35:48** · And if you see this time I am giving one additional parameter here ID wars. I have to give based on this id wars the cm indication is being created and it is merged with the data set that's being passed from the previous step with that has the topic variable.

**36:08** · If you look at it you see you'll be able to find it. Like for example in my raw data set for patient number 375 your indication is blank and patient number 375 when your treatment is cartisporin you have the indication is nausea right. So let's go and check here. So when it is baby aspirin indication is blank. When it is cartisporin indication is nausea.

**36:34** · How does it know? It is able to map these two things based on this ok variables. Okay, that's why you know like you have to specify what are your ID bars. All right, so I have created two variables at a time. Now let's look at the third what is the third mapping that we need to do. Okay, so my third mapping is so there is only one field here.

**36:56** · Okay, one data point. Whatever the value is collected in this field, if the value collected value is numeric, I need to map that to cmd dose. If the collected value is character, I need to map that to cm dose text. So now you know like you have an if condition involved and then you have you're mapping that to CM dose and cm dose does not have any units or control terminology associated to it. Right?

**37:26** · So then it is a combination of condition and assign no CT. So I have to check the condition and then if it is satisfied then I need to use the algorithms assign no CT. So let's go and find out how to do that.

**37:44** · Okay.

**37:46** · All right. So this is how you need to do it. So if I just type cm raw here. Okay.

**37:56** · Put head.

**38:03** · Yeah. You see you see the first six uh first six records and then you have you print all these things. Right. So now I am going to check the condition. Okay, this is this is the condition that I generated to check if the collected value is is a is a numeric value. Okay, if it is a numeric value, then I need to map that to cmdos. Let's see what happens. Okay, so I'm just going to copy this code and I'm going to run it here.

**38:31** · Okay, you see you it gives um the true or false flag. Okay, what is a true or false flag? If the collected value is numerical, the flag is true. The collected value is blank or character, the flag is false. Okay. So when you add this condition, this mapping will work only for the records where you have this condition as true. Okay. So let's let's just run run up until here.

**39:01** · So this is a combination of two function calls, right?

**39:07** · So I'm going to run until here. Then I have cm domain mapped with two variables. You see you have only the numeric values that are mapped here. All the character and blank values are ignored. Right? So then we are not not done with the mapping right.

**39:25** · So we have one more part of it. So that means that you need to map the qualifier to cm do txt when the collected value is a character. And this is the uh um logical expression to check if the value is a character value. And I am using the condition add function. And in cm raw if this value is a character if this condition is satisfied then I am going to map that value to cm dot txt.

**39:57** · Let's run this one this one alone and see what happens in the console.

**40:02** · Okay. You see all these you have the false flag here and then you have only for the record number six you have true and you see your dose txt is one and then for again you have dot txt is two you have true and for rest everything you have false it's working as expected so I can select from all the way from here to here and run it

**40:30** · okay you see yeah so So you have all the dose values and and you know like whenever it's not um it's not numeric you have you are mapping it to do txt. All right so now we have seen two algorithms how to use two algorithms. We have seen how to use assign OCT and also we have seen how to use condition. Let's move on to the next one. Okay the next one here is the dose unit.

**41:00** · Okay. So do those unit always units are always associated with control terminology. Okay. And uh and let's go back here. Yep. And like and this is my control terminology. And if I look into my study CT here, I have all these control terminology values defined here. So it's already predefined.

**41:23** · So if any of the collected values is not here then I'll get a message that okay one of the values that you have in your raw data set is not here. Okay let's run it and see and then if you see um the the parameters are a little bit different here right so when you are assign CT you need to tell what code list term to look at okay and what is your control terminology for data set name.

**41:52** · So you have study CT and you have your your your study CT in your global environment. You have to mention the object name and also you need to mention the the code list code that you need to look at. Right? So I'm going to select all the way from here to here and click the run button. Okay. There are no warnings here. That means like everything all the collected value is there in my data set.

**42:19** · Then if I open my data set, you see your standardized values are being uh mapped here milligram gram let's see so gram. So if you see for the second record you have gram that's converted to g here. So it has applied uh your control terminology and it is it's just applying like SAS formats it's converted to G. Okay. So my what is my next one in my example?

**42:46** · My next one in my example is the dose formulation and again I think dose formulation has control terminology associated to it. We need to use the assign uh CT algorithm correct? Yeah, assign CT algorithm. And then let and then the next one is dose frequency.

**43:09** · Again I need to use as CT algorithm and then route again I that has control triage associated with it. I need to use the assign city algorithm. So let me run all these three mappings because it's the same thing, right?

**43:24** · So I'm going to run all the way until route.

**43:36** · Okay.

**43:38** · So there is some uh some some message here, right? So there are these terms could not be mapped to control terminology and there is a space. So there is like um there is like there are some values that are not in your standard control terminology and you are getting this warning message and I see that there's a question okay

**43:58** · there is a collected value column in CT how to get that because it is not in standard CT I don't understand the question actually so the collected value is the value that is appearing in your raw data sets Okay. So if you see here gram in your city, you need to specify gram here.

**44:38** · Yeah. So collect collected value can be in your collect. So it's so ideally you know like collected value can be in your preferred term or collected value column or synonyms column. So we have just given this as an example. So it can be part of either either either of the three columns. So we look for a match in all these three. If you find a match then it'll be then it will be like term values the is the submission value. It will be changed to the submission value.

**45:10** · All right. What values if collected in other it is a non-standard right? So I don't have an example for that's a great question. I don't have an example for other but whatever value you enter in the text box other if it is a non-standard value it will just you know like for all non-standard values will just map but you will get a message in your console like this. Okay. So you will get a message in your console that these terms could not be mapped as per the standard control technology.

**45:37** · So let me run until here. Okay, I think I should have more examples. Yeah, I think in frequency only I have like some um some some unknown values. So it is not mapping the the spaces. So if you have a a valid value like this, you'll get something a message like this when you when you run your console.

**46:18** · All right. So now we have mapped until uh CM route. Okay. And then the next thing is our CM start date. Okay. So let's look at the CM start date. So cm started is going to be a little bit um more details are needed. So let me go to the package documentation. Okay. Um httm.org right so you have an article on how to convert dates and time to ISO8601 format.

**46:54** · So we have it's it's a it's a it's a very lengthy article so I'm not going to go through go through it in detail but in the essence uh in the essence what it does is whatever whatever the format of your date day month and year and time you specify the format of the collected value and these functions that we have built will be able to interpret the collected value in this particular format and convert that into ISO 8601. Right?

**47:25** · So when you specify 2001, you specify year, space, month, space, date and we know that okay. So this is like fourdigit year, twodigit month and twodigit day and then we should be able to process that as you know like um in ISO6 format. Same thing for time.

**47:46** · This way you specify hm yes and then we should be able to format it this way and then y for we have like standard set of define tools y for year M for month d for day and hours minutes and seconds and then if your date is like this year hyphen month day space hours colon minutes cols then you specify the format as y - m d space hmms MS then the function can convert that into the ISO format ISO860 format.

**48:22** · So this goes on and on and we we do a lot of different uh different examples. Okay. And different format variations. It can be like this y / m/d and then it can be month day year and then it can be like in in multiple formats. Okay. So I think there is like uh uh some examples for unknowns as well. Yeah. Parsing date and time components. Let me look where we have unknowns.

**48:57** · Yeah. I think unknown is not covered here. Okay. I think we have the we have it in the example.

**49:02** · So let me go back to the examples back here. I think there's again more questions on control terminology. Can you explain please explain the process of creating your control terminology file? There is no specific process. Um the standard process every STM specification will have a control terminology tab. You just take that tab and map your values code list code and term code and try to create this file.

**49:27** · So we need all these six columns and it is like self-explanatory. So your collected value and submission value goes into different things and and we have documentation in our package documentation site as well. All right. So let's map the cmsdc from from this particular variable cm std. Okay. So let me look at the raw data set in cm std you know like I have dd

**49:58** · date hyphen month hyphen year okay and I have unknown values as collected as unk okay so I need to be able to specify all these things when I do the function column all right I am using the um um

**50:17** · function assign day time and my raw data set name is CM raw and my variable is like I like whatever the value from the CRF right and then my target variable is CM stdtc and my format is d-m y right so date month year so I am just using d-m y and then I am also telling that my raw data sets can have unknown values in the form of U or U and K and you can add anything like this.

**50:50** · You can also add like something like U here. If you if you're expecting U as well, you can also add like this U as an additional value. It doesn't matter.

**51:01** · So when you do this what happens is my assign date time function looks in this column uh and then d-m y and then you know like and then you can looks for this unknown values and converts converts into the ISO861 format. So let me select until here. Sorry, let me select until here and run it. Okay. And now I should have my CM stdtc with all unknown values handled. Okay.

**51:41** · Yep. See, so for uh you see for you have only 2019 here. So un 19 is mapped to 2019 and in wherever you have the full dates you have it in ISO861 format.

**51:58** · All right. What if the raw data set I have a question here. I'm going to read that question. What if the raw data set doesn't have unk or u or and just dash for example two dash. I think it might work. So you can just uh mention this as d- dash u in terms of uh um month. I think it'll still work. You can try it and if it doesn't work you can create an issue in our uh in our GitHub repository we'll uh we can fix it.

**52:33** · All right. So yeah so we have tested it and you know like and and anything the unknown values are getting converted. So we are good from that perspective and we can move on to the next one. Right? All right. So we have seen all different algorithms. Now we have seen assign CT, assign no CT, we have seen condition where we have to use if else logic and then we have also seen assign day time. So now there are two more algorithms left for us to look at. Um it's like hardcode CT and hardcode noct. Yeah.

**53:06** · And before we move there you know like that is like uh another question here from Dineshumar.

**53:14** · What if one year or month and month and year we should be able to handle all these scenarios right? So if you go into this examples right we have given different examples on how to deal with it here. So you see here you know like when you have like month and day you still be able to define that. Okay. And you have to just when you specify the format you have to just specify if it is month hyphen day. So it can be m day h and m. So it's like it's like mix and match. So it's like very versatile.

**53:47** · You should be able to handle all different types of scenarios with this. So I recommend you to read this article and and if this does not cover your specific scenario then reach out to us in uh in GitLab or in Slack. We'll be able to help you. All right, going back to the coding. So, yeah, hot code, right? So, let's look at the the next mapping that we need to do.

**54:21** · Okay, so this is a very interesting mapping. Okay, so if yes is selected um so once once at the end of this workshop there there's a question. Yeah, I think yeah, someone already shared the article.

**54:37** · Thank you. All right. Anyway, at the end of this workshop, I'll share the link to the slides and all these materials and you'll you will find everything uh all the sources in in the slides where where you have links to the formula, examples, our package documentation and everything. All right. So, going to the next mapping, right? This is a very interesting mapping.

**55:04** · So if yes, I need to hardcode the value to CMEN or TPT as ongoing. Right? I am not collecting ongoing on the CRF. I am collecting either yes or no. If the site answers yes, my CMEN or TPT should be ongoing. So this is a hardcode algorithm. Okay.

**55:24** · So when am I going to use the hardcode algorithm? Only if the value is yes, I need to use the hot code algorithm. I think it has control terminology associated to it with it. So if the value is yes then I need to use hardcode CT algorithm right. So let's look how we how to do that. All right. So yeah so if on if uh if cm ongo is yes then cmept equals ongoing.

**55:53** · Yeah, I need to use the hardcode CT algorithm and in my raw data set I am checking for the condition in my raw data set. If this particular column equals equals yes, then I am using this control terminology specification this code list code and my target value. I'm going to hardcode the target value as ongoing. Okay, let's say let's see if any of the um records have meets this condition. Okay.

**56:26** · Yeah. So, a lot of records meet this condition. You see true here for a lot of records. Okay. So, so let's run it and see what happens. Right. So now now we see that there are some values that could not could not be mapped for control terminology. your ongoing is not in your control terminology specification. So that's why you are not able to map it. Let's go and search for it.

**56:57** · Do I have ongoing here?

**57:05** · I have it as up case ongoing. Right? But you have on you have hardcoded as mixed case ongoing. So it it gives you a message that it's uh it's not working. So now if I change here to up case ongoing this message will disappear. Of course this is not correct. This is just to demonstrate how this function works.

**57:35** · So that message disappeared. So, so what the advantage of using this uh the hardcode algorithm is you are always keeping your control terminology file up to date. So, you don't run into pinnacle 21 issues later in the time. So, pinnacle 21 you know like it always complains if you don't have control terminology in your in your specification and then you have in your data set it always complains.

**58:01** · So, you can actually keep your specification up to date uh while you are programming. Let's look at the output data set here. You see ongoing is mapped for set in records and for set in records it's blank.

**58:17** · Yep. And then we have an example for assign no CT here. Okay. So what is that value here? Right. So if yes then CN rpt should be date of last assessment. So I have to hardcode the value date of last assessment.

**58:31** · So that's very nice um easy to use right. So I am using hardcode noct algorithm because it doesn't have any control terminology associated in cme tpt and again I'm checking the condition yes. If this condition is satisfied, I am going to hardcode this value.

**58:57** · Right?

**59:01** · Yep. See wherever you see ongoing you have date of last assessment as well. Right. All right. What is left here? I think I have only one one one mapping left that is CMN date. All right. So then um then I am next one is cm amended. So let me run run it all the way up until here.

**59:27** · All right. So I finished the cm amended derivation as well. Okay. So then I can do all these derived variables. Right.

**59:35** · So I'm just using mutate statement to assign my study name, domain name, cm category as general con medication and I am deriving new subject ID and then and then I am doing all the derived variables. If I go back to my slides, I finished all the rest of the variables and if you look this CRF has only one topic variable here, right? CMTRT. So I don't have to do this step.

**1:00:01** · I don't have to repeat map topic and map rest for every topic variable because the CRF has only one topic variable. And then my next step is to do htm derived variables. Right? So all my derived variables function calls are here. So I have derived sequence number and I'm creating target sequence number and I'm creating what are the record wares and this is extensible. You can specify any number of variables you want here.

**1:00:30** · And then I am deriving study day based on my DM domain. RFX stdtc for cmetc I'm creating cmd ndy for cm stdtc I'm creating cm stdy and I am just

**1:00:47** · going to select all the target stmm variables that I have created right and then remove anything that I drop the okay variables and everything right so yeah so then I do and yeah I have a nice uh cm domain here with all the variables mapped nicely in order with sequence number here and then for every

**1:01:15** · every CMSDC it should have a CMSD I don't know why it's not getting mapped maybe um maybe I think the subject numbers does not match between this file and and the DM domain yeah it doesn't match that's why we don't see any CM study day mappings I I'll I'll show that in the next domain in the vital science domain. Okay.

**1:01:39** · All right. Yeah, that concludes our CM domain uh programming. Okay. Um let's go back to our slides.

**1:01:51** · Yeah, there are like many questions are being posted here. Are there articles this? Yeah, from are these derive XS?

**1:01:58** · No, the derive XX functions are not from the Admiral package. uh admiral doesn't have studied derivation. So we do study the derivation in stmm. So these are new functions in stmm.walk package. Yeah. So we have uh we are developing a function where we are splitting the characters to uh to 200 characters and maybe it's already there or it's it's under development. I can um let's find out. Yeah, it's it's it's under development.

**1:02:35** · I don't see a function here. Okay. So, we'll we are developing a function to split the cmd code to 200 characters like cmd code 1 2 and 3. Um, so once it is developed, you will find that function name here in this uh in this in this articles in the reference page. Yep. So you are right Rohit. The best use is to have the CT in place to avoid future connect 21 issues.

**1:03:07** · All right. I think I have addressed all all the questions. Okay. Let's go back to recap here. Okay. So we did uh the function calls assign daytime.

**1:03:18** · Everything worked right. So now we have a quiz. So you can type your response in the chat. Okay. So what function should be used for CM route? A assign CT sorry A assign no CT B assign CT. It seems like people are able to understand right. So CM route has a control terminology associated with it. Code list is associated with it. So we have to use assign function. Great job guys.

**1:03:49** · All right. Yeah. We'll uh we'll start now. It's like um I hope everybody can hear me. Um it's like 10:45 p.m. All right. So we have questions coming in. So can conditional argument in hardcore city can be used to create DM multiple by checking.

**1:04:10** · Um I think we can do it right. So you check uh you have to check if not null and not null and not null like different columns and then you can hardcode the value as multiple. We should be able to do that. All right. So next let's jump into the next section like vital signs. Okay. All right. So we'll do into vital signs domain. So let's review the vital signs ACRF here.

**1:04:42** · All right. So my vital signs ACRF, it starts with the date that is mapped to VSDTC. And if you see it's a mix of C dash and non C dash column names. So BLTD is a non C dash column name. And you know like height is a C dash column name. So you have it. It height VSRS. Then we are mapping that to VSRS when VS test code equals height. VSRs U equals inches.

**1:05:14** · And then we are collecting weight. VSRS when VS test code equals weight. And then my unit is pounds. And MSRS when VS test code equals temperature. And my unit is Fahrenheit.

**1:05:27** · And this location is applicable only for the temperature. It's not applicable to height and weight. And then you have a log portion in here. And then uh you have like a time point uh collected after laying down 1 minute and 3 minutes. And then you collect systolic blood pressure, diastolic blood pressure that has mapped to VSRS when VS test code equals SISBP.

**1:05:51** · And you have the unit mapped and then you have the pulse that's beats per minute and then position is applicable only to systolic blood pressure, diastolic blood pressure and pulse. Right?

**1:06:08** · So this is a little bit complicated CRF where you have a non-log portion that is measured only once and then you have a log portion that is measured three times. So after lying down, after standing and after standing for 3 minutes.

**1:06:23** · Um so so let's see how to deal with this. Okay. Um in the meantime we have a question in the chat. A data frame have special characters. When I am exporting a CSV then special characters are are displayed as spaces. How to overcome that? Yeah. So I think we saw that. No. So in your examples you have a function in admiral package convert blanks to NA.

**1:06:51** · So you can just use that to uh to to to replace your uh blanks as NA values or spaces as NA values or if you still have it you have to just you know like find and replace using using your code any any code generator will be able to help you with that. All right so let me clear the session and close all these files and let's start working in vital signs. Okay.

**1:07:23** · So I'm going to scripts folder and I'm going to create the vital surface.

**1:07:29** · Right. So this is this is how my code looks like. Okay. So if you if you go if you go back to the slides, right? So we saw that um we go back to my programming steps here, right? So you read in your raw data set, create ID bars, read in your study control terminology, map topic, map rest and then you repeat your map topic and map rest for every topic variable and then create STM derived variables. Right? So here we have an example.

**1:08:01** · Here we have an example where you have multiple topic variables height, weight, temperature, systolic blood pressure, diastolic blood pressure and pulse. So we have like six topic variables in this CRF. Okay. So that means like you have to repeat the steps six times. So if I look at my code, you have repeated six times. You read the specification.

**1:08:23** · You read dotted raw data set KDRs map temperature and its qualifiers, systolic blood pressure and its qualifiers, diastolic and its qualifiers, pulse, height, weight, right? and then combine all topic variables to a single data frame and map qualifiers that are topic all that are common to all topic variables including the grade variables. Right? So these are the different programming steps that we need to do. So I'll just expand everything and uh and then we can uh do it.

**1:08:54** · So it's option shift command. Okay, good. So I am reading my uh study control. Let me just load my packages first.

**1:09:07** · Load packages. Read my control terminology. It's the same file. And then you know like if you see here I am reading the raw data sets from a package called formover raw. Okay. So for raw is a package that we have created. So the way that we did that we reverse engineered farmover STM package and we created the form raw package. So you can have a continuous connection.

**1:09:29** · So using form raw and httm.work and you can create the domains that will be equivalent to form stmm and then you can use the admineral packages and you can create the atom data sets that will be equent to form over right. So we have created this link uh all the way from raw to the tlgs.

**1:09:52** · So let me read the raw data set. It's going to be a big one. So we have like 12,978 records here. Right? So yeah, it's a big data set here and uh and then we generate the OKD bars. Okay. And I'm since we have already seen it, I'm not going to repeat it again. And then I'm going to read the DM domain from farmersm package. Right.

**1:10:18** · So my DM domain is here very nice and tidy and my raw data sets are here. My work variables are created. If I go all the way to the end, it will be like 12,978 that matches with the row number and you have patient number as platinum and raw source as vitals.

**1:10:41** · Okay, so I just kept the raw source name as vital. You can keep it as VS raw or vitals. It doesn't matter. I just keep that as vitals. Okay, so let's start from temperature here. Okay, so if I go back to my um CRF here. Okay. So in I'm not going in an order to this uh in this um in this file.

**1:11:00** · So let me start from temperature and then I can I can explain temperature location and uh and then that will be um that will be it and then probably I'll I'll just run the code for the rest of the sections. Okay. So when you look at temperature right so you are collecting only one value on the CRF that is the the value of the temperature enter but how many things that we need to map whatever the value entered in this text box should be mapped to RS and

**1:11:32** · then I need to hardcode the value of VS tempus temperature so whenever I see VS test code there is a VS test associated to it that's temperature and then I am collecting a unit here and I'm hard coding that value in BS original unit and then we there is a standard unit I need to convert the original unit to standard unit as well right and then

**1:11:59** · only when you are uh only when this uh for this temperature I am also collecting an associated position and I need to map that to temperature so there is like like probably like five to six variables I need to map one original result two test code VS test code three

**1:12:18** · BS test four original unit five standard unit and six position like six H STM variables I need to create so let's look at our code right so yeah so as we say you know like we have to start with the topic variable mapping right so here my topic variable mapping is I am hard coding the value as temperature so temp Right? That's the value that I need to hardcode.

**1:12:44** · So for uh VS temperature, my target variable is VS code because first thing we need to do is topic variable mapping and the value that I need to hardcode is temp. And I have the control terminology file and I have the code list code created here. So I'm just getting here and I have four observations and you see a lot of values are NAS here. Why?

**1:13:15** · Why there are like so many NAS right? So let's look at what's happening in OKD variable one. So in my OKD variable one my temperature value is blank and temperature location is also blank. Right? So if for all these blank values so I'm not I'm not the the hardcode function has not hardcoded the value as temperature.

**1:13:42** · So we have a pinnacle 21 rule that you know like if you're um if your topic so topic variable is blank then you don't have to keep that record in your htm domain. So let me drop it as a next step right. So I'll drop all these variables where you have VS test code as CNA. And now we my VS temp is clean. So I have only the work bar where value is present and I am hard coding the value as VS temp.

**1:14:12** · Okay. So then my next thing that I need to hardcode is VS test. I finished creating that uh test code. That's a topic variable. The next thing let me do is the test. And the test is again the value that I need to hardcode that is temperature. It is not collected on the CRF. So I'm going to run from here to here.

**1:14:32** · Right? So now my value has temperature here. Okay? So then what's the next thing? Right? So next thing I am going to assign the collected value original result. Whatever value is collected on the CRF on the CRF in this text box I am I am I am mapping that to VS original result. All right. So here yeah so it's uh it's it's like whatever the value collected is mapped here.

**1:15:13** · Right. So then then once the original result is mapped I'm going to map hardcode the value of original result unit and then I am going to u I'm going to map the vss location only when your raw variable is blank. So this this this condition is already satisfied because you know like so we have this na here. So this condition is already satisfied but just to demonstrate I have it here.

**1:15:40** · So let me run it all the way here because all we have looked into all these algorithms in our previous example, right? So I run it all the way here and then my VS temperature has you know like nicely mapped temp temperature original result and location is mapped. So next thing I need to do is like standard result derivation.

**1:16:04** · So I'm just using um you know like a simple R code to convert my original result to standard result. That's it. That's in Celsius and uh and that I am hard coding it here in the next step. And uh this is a standard formula to convert uh my my Fahrenheit to Celsius.

**1:16:28** · So if I run all the way from here to here, right? So my temperature this is my this is the data frame a completed data frame with all records where temperature is mapped. Um yeah so we have finished the first topic variable and its qualifiers. I believe there's a question here or maybe not. There are no questions. Good. So I have finished my uh temperature and all the all the qualifiers are mapped.

**1:17:03** · Let's go back to go back and look at the CRF right. So I have uh original results test code test original unit standard unit standard result and VS position.

**1:17:22** · Yep. All the values are all all these things are here. So let's let's do a small experiment here. Okay. What happens if I comment this line?

**1:17:31** · Right? So let me run from here to here by commenting this one line. That means I'm going to create all the empty values.

**1:17:44** · Okay.

**1:17:47** · Okay. So now my VS temperature has 12,9 12,978 records and it has 10 variables.

**1:17:56** · You see it's just you know like everywhere there is NA. So only when your VS test code is present all these qualifiers are mapped in all other places it is NA. So it's it's like even if you don't remove it it's you will just have a lot of records where your topic variable is uh was blank. If your topic variable is blank anyway pinnacle 28 is going to comply right. So it's better to remove it. So that's why we added the line here. Right.

**1:18:27** · So, let me uncomment this line and run it again. Right. So, and run it again here. All right. So, I finished my um I finished the mapping of my temperature.

**1:18:45** · Okay. Let's look at the next example of systolic blood pressure. So, what do I have to do with systolic blood pressure?

**1:18:52** · So systolic blood pressure is actually in the log portion in the repeating portion right. So for systolic blood pressure I need to map original result um test code unit standard unit and standard result and then and then you know like if you have to do numeric and character I can still do numerical character right and then I need to map vst and uh and yeah and then I think I need to map the position as well.

**1:19:22** · So I need two this many number of mappings. Yeah, I see a question here. How do you derive stress N and stress U consistently across mixed units? Uh F2C inches to centimeter, LB to kg. Is there a built-in converter in STM.org or should be standardized with custom functions? So currently we don't have u a built-in function to do f2c inches to cm and uh and lap to um pounds to kilogram.

**1:19:54** · So it's pretty much standard right. So I don't know if I want to create a function to to do on top of things. So it's it's a very simp line code. Um probably we can create a function. I don't know. So for now we have not done it. So you can uh can you can simply convert it using this or we can put this oneline R code in a function and then you'll call that function here. So anyway it's going to be one line. So um we can think about it. Okay. Mhm.

**1:20:25** · That's what I would say. Um yeah. So let's look at the uh systolic blood pressure. Before that there's one more question. um a function could be beneficial for lab domain. Yeah. So that's a great question. So we have not looked into lab domain conversion yet.

**1:20:49** · The reason being I think we need more volunteers to share with us how they perform the standard unit conversion in their company or in the way that they are doing it because um from what we have seen every company maintains the metadata in a different format for original result and standard result and the conversion is being maintained in different ways.

**1:21:13** · So I don't know if um I can we can create a solution in stmm.org work but I don't know if that will be applicable to every company because every company does it differently. So um so probably you know like we need more collaborators to develop the unit conversion for lab domains. All right, that is one more question.

**1:21:35** · Um, another basic question for VS position and location when there are applicable to certain test do you recommend condition per qualifier or post filter approach? Which is the best one? Right. So let's uh that's a great question. Okay, let's look at what we have here in this example. My temperature location is applicable only to this temperature, right? So I can condition is the best way to do it. I I don't think we need to do any post-processing. Okay.

**1:22:04** · So we want to avoid any pre-processing or post-processing. So that's that's why we created the condition algorithm. So the best way to do it is condition. And uh and if you have look if you look here in our examples yeah we have the condition add being put here. So when you do it it works nicely.

**1:22:32** · All right. So let's um let's look at the uh systolic blood pressure uh here. So you have um yeah systolic blood pressure. You always start with the topic variable. So we have started my second topic variable here. So my um I'm just going to do a code walk through and then run the entire code at once instead of running one step at a time. Right?

**1:22:50** · So my VS test code has I am using hardcode CT algorithm and my target value is sis BP and my code list object and my code list code and I filter out all the records where SIS BP is blank cuz we don't need it and then I map the BS test value as systolic blood pressure and I give the code list code and my control terminology object

**1:23:20** · and CIS BP is the raw variable where we are collecting the original result. So I am using the assign CT algorithm and then I am mapping the original result and then for this original result we need to map the original unit that is mummg that's hardcoded on the CRM. So I'm using hardcode CT algorithm and I am specifying the code list code and my control terminology object.

**1:23:49** · And then if you look here for VS position I don't have to use condition add right because it is within this context of this data frame. So I am directly mapping the VS position that's applicable um sorry so if I go back to my CRF here this position is applicable only to systolic blood pressure diastolic blood pressure and pulse it is not applicable to height and weight. Right?

**1:24:16** · So I can achieve that by doing this mapping within the context of CISB. Right? So when I do this, it nicely works. So I'm going to select from from line number here to here.

**1:24:36** · And that creates my CISB data set. So with 8,000 records and my temperature data sets has 2,00 uh like 2,700 records. So you could you have like 8,200 records for cis BP. Obviously we have collected more systolic blood pressures and then you see the OKDs you know like you see four five four and five are missing. Why is four and five are missing? Let me look at my raw data set.

**1:25:01** · So for OK4 my systolic and diastolic blood pressure is blank and my position is also blank. Right? So when these three things are blank I don't need to create it. So I don't see a OKD record number four in my systolic blood pressure. So for every patient for every record where I have uh a value collected result collected for systolic blood pressure I have mapped everything. Okay. So yeah so that's it. So that will be it.

**1:25:39** · So um so this is my systolic blood pressure. So simply the same way I run my diastolic blood pressure code and you know like I create the diastolic blood pressure and then I run the code for pulse and I run the code for height and I run the code for weight. Right? So now I have covered all the topic variables. Okay.

**1:26:12** · So I have diastolic blood pressure, height, pulse, systolic blood pressure, temperature and weight. So now I just need to do uh I need to combine all these raw data set using bind rows. So that will create my entire vital science domain. I'm just going to create one combined VS.

**1:26:33** · So it has like 29,635 records, right? So your raw data set has 12,978 But your VS domain has 29,635 because you know like you have your transposing and you are doing in doing it like that. All right. So let's look at this one and see and yeah it's nicely arranged here.

**1:26:56** · So diastolic it's not it's not arranged by subject because you know you haven't sorted or create the sequence number and stuff but when you just filter for a subject you can see Right?

**1:27:12** · You see diastolic blood pressure height collected only once and pulse collected many times and then systolic blood pressure temperature weight. Okay. All right. So this is my combined data set. Now you know like now if I go back to my slides here.

**1:27:38** · So I have I have repeated you know like uh map topic uh repeat map topic and map rest for everything. And now I need to create the derived variables and any topic variables that are common to all the topics. Right? So that's that that's my next step. Let me go back to the slides here. Okay. Looks there are a couple of uh couple of uh questions.

**1:28:02** · Okay.

**1:28:04** · Looks like you don't list specify work rewards before a function called dep player in each program. Is there any particular reason? That's a great question. Okay, so this rewards um so let me let me do this one here.

**1:28:28** · Okay, so is is is hardcoded here. So even if I don't specify it, it uh it does it if I um if I if I go to my package documentation. So key variables used to join between the raw data set and the target STM data set. So it's always the three values that you are creating here.

**1:28:56** · Scroll all the way to the top. Right? So when you create your generate okay divs in your VS raw data set. So this this is the three variables that are created it will always be this. Okay. So if you extend it it'll it'll be whatever the extra values that you use to uh asd so you don't have to specify these variables again and again since it is like standard across all domains. We are we are just you know like um reducing the number of key key strokes.

**1:29:25** · Okay, that's that's that's that's the one making it simpler. That's it. And there is next question that you know does all these apply to PP domain too.

**1:29:36** · Um PP domain. Yeah. Right. So PP domain you will create it from a PPP file. So yeah, if you hard code hard don't hard code and whatever from your raw data set you can still that still applies to preppp but it'll be mostly you know like um uh assign and hot code you may not have condition and all those examples

**1:30:07** · all right so I have created my vss combined right so let me go back okay so there is one more question. Okay. So, is there any starter to get all topic variables mapped cons consistently like in SAS macro can be created and repeated tasks? Okay. Yeah. So, you can create a wrapper function on on on top of this and then you can make this repeated function calls. So, we have not created this part of the package but that's definitely possible to do.

**1:30:33** · So, our next in our next uh releases what we are planning to do is to is to create an agent for httm.work work package. So, um to answer that specific question, I might have to uh uh deviate from what I am presenting now and probably I think that's okay to deviate at this point.

**1:30:57** · So, if I go to my uh specifications, right? So, if I go to Cdash, uh I have um a specification here, right? So, I'll import this data set.

**1:31:16** · All right. So um I have this I will import this data set. We just saw this example for CM doain. So you have raw variable and then you have your annotation text and then you all you all you have your mapping algorithm name and then you have the hardcoded value and everything. So we are trying something like this. Okay. So if you are able to add all these details to your specification then you can use an agent to generate code for for your htm.org. So you don't have to hand type all these things.

**1:31:48** · So that's the next thing that we are trying to achieve. So hopefully in version 0.3 uh we'll we'll we'll come up with an MCP on uh on top of this package where you have to just create your Excel specification that has your raw data set name, variable name, target domain name, target variable name, your algorithm and any parameters that you use for the function call. And then once you give that file as an input to your agent, that agent will be able to create your R code for you.

**1:32:22** · So um yeah, keep um uh keep watching uh our space. So we'll hope once we develop it, we'll definitely share it with the community. All right. So let's go back to VS Combined.

**1:32:41** · So you know like this four 500 600 lines of R code is a mundane task, right? The the the what is the complicated task?

**1:32:48** · The complicated task is to figure out what algorithm to use and how to map STM. So once you figure out how to map your raw to STM and uh and once you decide what algorithm to use, your programming will be a low-level task that can be done by an agent in the future. That's very near future. We are not even so far behind.

**1:33:09** · All right. So now let's look at um the the common variables that are that are you know like that are mapped to that we need to assign to this right so if I go back to my to my raw CRF what are the common qualifiers my date is is

**1:33:26** · applicable to all topic variables and uh and I believe yeah that's the only thing and maybe I think I'm mapping also the time point to all the variables I don't know let's look at look at it yeah I mapping the time point as mapping the time point as well to all the variables that may be correct or incorrect I don't know whatever it is I think that's correct because I we wanted to match that with the the atom advs so

**1:33:52** · so the time point is applicable to all the topic variables okay so so I am doing assign date time and why am I doing two formats here right let's look at the raw data set here if I look at my raw data said in many cases you have uh as day, month, year and in some cases you also have the the format in ddmm y or dmmy. Right?

**1:34:17** · So I I just covering both cases and then I am doing the time point and then time point number and I am mapping the the value from instance to visit and visit number. All these things are qualifiers that are common to uh all the topic variables.

**1:34:39** · And then I am doing study id domain and then I am creating you know like stress c stress n stress u and elapsed time time point reference and you know like we have not programmed vs start so it's like n character but yeah we need to add it that's the only thing that's pending.

**1:34:58** · So these are all the qualifiers that are common to all topic variables. Then I am arranging everything, subject ID, test code, visit number and then I am creating sequence number, study day and then I am deriving a baseline flag.

**1:35:15** · Right? Yeah. So that's the end of it. So I'm going to select all this and I'm command enter that will run all these steps and then I'm going to create a baseline flag and select only the values that are needed.

**1:35:32** · Okay.

**1:35:34** · All right. So that's the vital signs domain. So nice and beautiful vital signs domain here. So we have uh visit number visit BSDTC time point time point number elapse time point time point reference everything populated as we expected.

**1:35:55** · Yeah. So yeah what we have seen right?

**1:35:57** · So this is a comp. Okay. Vital signs is a simple one but you know like it's the the CRF design has made it a little bit complicated right you have like a non-log portion and a log portion but still we were able to map it without even deciding when to transpose and when not to transpose. So theor technically you know like all you need is to create this work variables and once these are created you are just you know you can forget about when to transpose and when not to transpose. this work variables will take care of that.

**1:36:30** · All right. So let's go back to the slides here. All right. So yeah, so review a record. Okay. Code walk through is completed. We are going here. Okay. So yeah. So there was a comment or question.

**1:36:48** · Yep. The question is like they like someone like um posted that they like the exercise and uh and this presentation. Will this be available uh for later reference? Okay. So, couple of things. Okay. So, all our informer sessions are being recorded and it'll be available in YouTube and when it is published in YouTube uh we'll also share the link where your GitHub where the GitHub repository is. I shared it previously in the chat room. I'll just share it again here. So, this is the this is a GitHub link.

**1:37:17** · You can clone it and you can test it anytime that you want. Okay. So, I'm just sharing it in the in the chat. All right. So let's uh um let's look at this one. Okay. So I'm going to look at this one. Patient number 70110 1 1034 Okay 213 instance week 2 and vital signs date. Time point is after lying down for 5 minutes. Systolic blood pressure is 183 and diastolic blood pressure is 81.

**1:37:46** · Okay let's look at this subject 701- 1034. Right. And my work ID is 234 I believe. Yeah. 213, right? So and my week two, right? So and then 15th July and then after laying down for 5 minutes 181 81 86, right? So let's look at this one subject in vital instrument. So this is just a QC of our work. 701- 1034 and then my week two.

**1:38:44** · Okay. So, we two, right? That's Yeah. week two and then you have 15th July and then after lying down for 5 minutes you have 183 and 81 right so let's look at after lying down for 5 minutes I just filtered it okay and then Yeah. So now now we have we have filter it exactly to that. So your systolic blood pressure is 183 and diastolic blood pressure is 81 and pulse rate is 86.

**1:39:37** · So this is just a QC to to showcase you know like uh our code and our functions and everything works perfectly fine. All right. So um I think we are uh we have 10 minutes left right so we are actually we are running behind so I'll probably cover quickly cover the DM and a examples and uh and then we can uh we can wrap up the session

**1:40:05** · all right yeah we have one more quiz okay um so let's let's let's ask this question so when to use hardcode mapping algorithm to assign a collected value on the CR of A B to hardcode HTTM variable that has not been directly corrected on the CRF. Yeah, you can type your answers in the chat. Yep, the correct answer is B. To hardcode a value, use the hardcode algorithms. To assign a corrected value, you use assign algorithms.

**1:40:37** · All right, let's jump into DM domain.

**1:40:39** · Okay, so our DM domain is a beast. Okay, so it has like three ACRFs. So let me close this that we don't want here, right? So my demographics domain I'm collecting birth date and uh and all these things here. Okay. But the only thing that I need to showcase here is um my e my exposure as collected CRF and my subject disposition CRF. Okay, it's like pretty much standard uh standard CRFs. Okay, the only thing that I want to showcase in the DM domain is the reference states.

**1:41:10** · Okay, reference state is um is the most complicated thing in the DM domain. So how are we doing it? The DM doain has like reference state RF stdtc and DTC, ICDTC and like and RFP and DTC. So the programming logic usually includes deriving this as a maximum or minimum date from raw data across multiple CRFs.

**1:41:34** · So we have created a function called oak calc reference state that can help the users to derive this reference state based on the metadata provided in a configuration file. So it can be a configuration file or you can just create it directly in your program and we have named that as reference state configuration data frame. Users have to prepare this in addition to the metadata file for for refer for deriving reference states. So now two key takeaways here. Okay. So v calc reference state is the function that is used to create the reference state derivations in DM domain.

**1:42:10** · To do that you need to prepare another file called as reference state configuration file that will tell stmm.work on how to derive the reference states. Okay. So now we'll look at this example.

**1:42:24** · So what is the reference state configuration? It's an intuitive way to let h stmm.no know won't know where to look for reference states. Multiple CRFs are raw data sets and variables can be specified to derive a specific reference state and the column names are very simple. You give the raw data set name, date variable name, time variable name, date format and time format and tell what um what reference date is being used for. Okay, let me quickly uh run the code.

**1:42:53** · Let me clear the environment here and close all these things that are needed or not needed. Okay. So I'm directly going to uh the the section where we are defining reference dates. I'm going to run all the code before that. Okay. All right. So this is the this is how I define my reference configuration file.

**1:43:28** · Okay. So my raw data set name, date variable, time variable, date format, time format and what htm variable name it is being used for. Right. So this this is all we need to tell. Okay. So my um I'm going to derive RX STDC from my ex raw data set from EC start date and then RFX E and DTC is derived from my exposure data set EC end date.

**1:44:02** · Okay. So my reference start date is derived from DS raw disposition start date and reference end date from so so you just define it like this okay so for example let's say that your study has more than one study administration forms you can just copy this file line and tell that okay so I have one more stuff here exot 2 okay and and then you can tell that okay my ex raw also should have this.

**1:44:32** · Then what happens is RS RFX STDC is the minimum date, right?

**1:44:40** · Start date should always be minimum. So then it stacks these two raw data sets and it finds the minimum value in ECTd across the two raw data sets.

**1:44:51** · So you can you can specify any number of data sets that you want uh to do this for to to make it simple. We have just one for each. Okay. And then for death date right I'm just looking at okay in my disposition raw data set look at this column and then map that to death date. So it's very simple.

**1:45:11** · Oh this is the metadata file. You can create that as a CSV or you or you can just create that as a dribble in your uh in your raw data sets and then you create a data frame like this and then httm.work uses this data frame to derive all these htm variables. Okay. Um there is a question here is there a validation process for what we do here in STM. So your validation process is controlled by your company. Okay.

**1:45:39** · So whatever your company SOP states you have to uh validate it um both the software and also the domains based on it. Okay. So we are not uh involved in any of these validation processes. All right. So once my DM domain is created right so I'll um I'll directly go to the place where we are doing reference dates. Okay. So reference the reference state derivation is here.

**1:46:09** · So wal reference date. Okay. So my input data set dot means whatever comes from the previous step is being used. My derivation is R of SDC. Min or max is min. my start date will always be min and this is the the data set from my global environment I'm using and these are the raw data sets that I need to create my uh created that are

**1:46:36** · being referred in this file right so I am passing all these raw data sets so then creating this we'll create by passing all these using work this function call and then again I am doing the same function call for rxs this entc and this time I'm using max because entc I need to use the max parameter right so then yeah you repeat the same steps use the file and pass the parameters and do it okay so I'm just going to source the entire data set here

**1:47:10** · then uh you have the final DM data set created you see all the reference states are beautifully created okay and there's one subject that has died and you know like both death date and death flag is being created Yeah, it's very simple, very easy and elegant way to uh to create your DM domain. All right, so I think there's another question here. So it means that there will be no double programming for HTTM.

**1:47:36** · It's it's up to your choice uh whoever the person asked that question. If you want to do double programming, you can do double programming. It is the QC process is controlled by your company, not by the package.

**1:47:52** · All right. So yeah, so DM doain is complete. I'll skip this in the interest of time. And for a domain, I'm going to showcase the form examples. Okay. So if you go to the form example site, so we have um we have like DM, PS and AE. We already saw DM and VS. Now I'm looking at AE. And again we have clearly explained all these uh all these steps here. Okay.

**1:48:20** · If you want to understand how to create an a data set you can just you know like copy these files to clipboard and then you can run it. It works seamlessly.

**1:48:33** · Yeah.

**1:48:36** · So it works seamlessly. So you can just copy paste each and every line and then we also we have given the snippet of the data and then you can you can just copy the file and then you can and just keep keep practicing map topic and rest. And then you do all the u um uh you do all the what is it the the coding variables. Okay. And then you nicely arrange everything together.

**1:49:13** · Yeah.

**1:49:16** · Yeah. Let me and then yeah so really summary so at this point you know like we you can create majority of the HTTM domains. So only the trial design domains, subject visits, subject elements, R track cannot be done anyways you know like these cannot be these cannot be very these are like very company specific right so you cannot uh

**1:49:42** · uh we will not be able to do I I don't think we'll be able to do it at the package level and maybe we'll be able to do associated person domains um because uh that that's different but other things have to be dealt at the at the company level okay and yeah so we had some exercises we'll skip in the interest of time. Yeah, if you want to get involved, uh we have given you some links.

**1:50:01** · You can ask question in the Slack channel or you can directly ask the question in the GitHub or GitHub repository link and then you have the package documentation form examples, the httm.work YouTube video from last year and a farmer blog and then the poster that we presented. uh that that's like very nice that will actually give you um very good end to end uh of how to use the package in just in one page.

**1:50:36** · All right. Yeah. So that is it. Yeah. Thank you guys. Thank you everybody. Like we uh we had like 70 we are still at 70 participants. That's amazing um that everybody stayed all the way through the end like a ramp. Uh I think there is a question so it's already time but I hope you can answer it.

**1:50:58** · Yeah sure I'll answer the question.

**1:51:01** · So there's a question any difference between version 0.1 and 0.2? Yeah 0.2 has a lot of new features that were not available in 0.1. So if you are starting now I recommend you to start with version 0.2. Okay. And Ramnath is there an MCP agent for stmm.org?

**1:51:20** · How can I contribute to the issues? Can you share the repo link contributor guidelines? I would say that everything is available. Okay, you can search for httm.work GitHub it will pop up and then within the GitHub repository you have all the information that you are looking for. So it's very simple. We don't need a link. You can just Google it. And for the MCP agent that that's part of the version 0.3 release. So whenever we are we we have developed it we'll definitely share it with the community.

**1:51:52** · Okay, thank you Ram. So, uh I think we it's a very wonderful workshop.

**1:51:57** · Yeah, one more question. The Slack channel seems to be restricted. How do I get invite to it? Oh, that seems strange. So, I'll um I'll I'll check with the moderator and uh and make sure it's a self-subscribed Slack channel.

**1:52:13** · So, if you are not able to post it there, you can actually post it in the form channel. So, we also monitor the form channel. So if you have any questions, we'll be able to get back to you in the farm hours.

**1:52:24** · All right. Yeah.

**1:52:26** · Okay, Ram, I think that's all the questions.

**1:52:29** · Thank you. Thank you so much. It's 11:35 in San Francisco, so I'm I'm very wide awake now. I don't think I'll be able to sleep now. Oh, good night.

**1:52:40** · All right. Thank you everybody.

**1:52:41** · Okay, I will close this section. Thank you so much. Bye-bye.

**1:52:45** · Bye.