---
title: "Emily Yates - Code that Cures: Validating GxP-Compliant R Shiny Apps for Clinical Decisions"
source: "https://www.youtube.com/watch?v=eOXbpiIcYU0"
author:
  - "[[R in Pharma]]"
published: 2024-11-25
created: 2026-04-29
description: "Code that Cures: Validating GxP-Compliant R Shiny Apps for Clinical Decisions - Emily YatesAbstract: GxP-relevant R Shiny application validation ensures compliance and data integrity in regulated in"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=eOXbpiIcYU0)

Code that Cures: Validating GxP-Compliant R Shiny Apps for Clinical Decisions - Emily Yates  
  
Abstract: GxP-relevant R Shiny application validation ensures compliance and data integrity in regulated industries. This complex process relies on three key pillars: people, technology, and processes. A cross-functional team is crucial, comprising an R champion to drive initiatives, technical experts to implement infrastructure, and QA partners to guide regulatory adherence. Essential technologies include validated infrastructure and packages, forming the foundation for reliable application development. Processes should align with GAMP 5 guidelines and incorporate risk-based Software Development Life Cycle (SDLC) principles, such as documented user requirements and robust code testing. This overview serves as a starting point for those interested in building validated R Shiny applications, highlighting the importance of collaboration, risk-based approaches, and continuous learning. By following these guidelines and leveraging available resources, organizations can successfully implement and maintain validated R Shiny applications in GxP environments, ensuring regulatory compliance and operational efficiency.  
  
Resources mentioned in the talk:  
\- GAMP 5: Good Automated Manufacturing Practices https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition  
\- PHUSE Open Source Technology in Clinical Data Analysis - FAQs for using R in Pharma: https://phuse-org.github.io/OSTCDA/  
\- Regulatory Compliance and Validation Issues: A Guidance Document for the Use of R in Regulated Clinical Trial Environments https://www.r-project.org/doc/R-FDA.pdf  
\- R Validation Hub https://www.pharmar.org/  
\- {renv} Project environments in R https://rstudio.github.io/renv/index.html  
\- A Risk-Based Approach for Assessing R Package Accuracy Within a Validated Infrastructure https://www.pharmar.org/white-paper/  
\- Phuse Open Source Technology in Clinical Data Analysis https://phuse-org.github.io/OSTCDA/  
\- R Package Validation Framework https://phuse.s3.eu-central-1.amazonaws.com/Deliverables/Data+Visualisation+%26+Open+Source+Technology/WP059.pdf  
\- R Package Qualification: Automation and Documenttion in a Regulated Environment https://pharmasug.org/proceedings/2023/SI/PharmaSUG-2023-SI-212.pdf  
\- External R Package Qualification Process in Regulated Environment https://pharmasug.org/proceedings/2022/SI/PharmaSUG-2022-SI-057.pdf  
\- Atorus Openval https://www.atorusresearch.com/openval/  
\- Software Development Life Cycle: A Description of R's Development, Testing, Release and Maintenance Process https://www.r-project.org/doc/R-SDLC.pdf  
\- R Package Oriented Software Development Life Cycle in Regulated Clinical Trial Environments https://www.lexjansen.com/phuse-us/2020/tt/TT12.pdf  
\- {testthat} Unit testing for R https://testthat.r-lib.org/  
\- {shinytest2} Testing for Shiny applications https://rstudio.github.io/shinytest2/  
  
Presented at the 2024 R/Pharma Conference

## Transcript

**0:01** · all right hello everybody um my name is Emily Yates I am the associate director of clinical data analytics and programming at formation bio today I'm going to be talking about a strategy for validating GXP compliant

**0:17** · R shiny applications to enable clinical decision- making in clinical research as many of us know a single miscalculation really has the ability to impact patients lives today our shiny applications are increasingly being adopted as a newer technology and we're

**0:34** · beginning to think about okay how can we use these apps to make these critical clinical decisions anything from dose calculations to endpoint analyses one of the biggest draws for the adoption of rshiny is that it's extremely customizable you can create these Dynamic uis for users to be able to interact with the data and of course the open source Community surrounding the tool however all these advantages

**0:59** · that draw people to the tool end up being challenges when we start to think about how we can validate um the methods in our typical validation tool kit things like double programming and output review to me they seem to fall short when tackling something as complicated as an rshiny application so it's clear we need a new validation process but it's not super

**1:21** · clear what that entails in the next 10 minutes I'll give you guys a high level overview of how we can start thinking about validating these applications share some advice and a bunch of resources you can use to get started so let's begin with the why behind validation first and foremost the consideration here is patient safety and clinical impact in this context our shiny applications serve as a decision support tool for these really critical clinical scenarios um some examples of a

**1:53** · GXP shiny application could be an app to monitor data quality throughout the course of a trial or even more critically and app to detect safety signal and identify risks um sooner in a trial uh in this context validation

**2:09** · isn't merely a QA measure uh it's a fundamental requirement for ensuring patient safety and maintaining the Integrity around these really critical clinical decisions the second consideration here is of course Regulatory Compliance specifically I'm thinking about 21 CFR part 11 and IC E9 both which call for

**2:30** · documentation around the reliability of electronic records and statistical analyses Regulators here they don't just want to know that your shiny application is working they want to see the documented evidence of how you're ensuring that it's working um so that means comprehensive testing validated audit trails and robust change control processes during an exp inspection you

**2:54** · have to demonstrate through this documented evidence that the shiny apps are performing as intended and validate can provide the framework necessary to begin to fulfill these regulatory obligations the last Point here really ex uh represents an expanded business opportunity uh when you're doing validation right it can accelerate Innovation rather than hindering it and when your validation process is solid and streamlined you can spend less time firefighting and more time innovating uh your teams can confidently deploy new

**3:24** · features knowing that they have a framework in place to ensure high quality and audit preparedness becomes routine rather than emergency while validation is going to require some initial resource investment it's yielding significant operational efficiencies and is going to in the end allow your organization to drisk innovation in a regulated environment so for for today there's

**3:48** · really three components of validation that I want to cover um and they sort of build on each other uh the first in order to begin even thinking about validating an R shiny application you need a foundation of a validated and verified GXP environment which really at this point seems pretty widely agreed upon in Industry this means that you're validating the installation and any configuration of posit teams um with the

**4:14** · goal of ensuring quality and reproducibility of the environment uh for this piece you're going to need to find a partner in it at your organization to help with this um and they'll also be able to help with establishing some of the operational tooling uh like Define directory structures Access Control Version Control and so on um and now at this point there are a number of vendors on the market who can be contracted to do this work for you the second foundational piece is

**4:42** · some sort of risk-based framework for evaluating the quality of externally developed packages and this is going to be really critical um to unlock the ability to tap into the open source development Community surrounding posit uh because these pack is are open- source and developed outside of your organization the quality of them might be initially unknown um and so it's on

**5:09** · us to think about ways that we can um begin assessing the quality and the risk associated with these external packages ultimately I think this culminates in the creation of an sop at your organization um and there was a number of really great resources available now to help you get started thinking about this um including some papers from the

**5:30** · fuse open source technology in clinical data analytics working group um and some really great pharmer papers over the years the last couple years from the team over at Merc as well um really great resources to help you get started thinking about this some things to consider when assessing a package are how you're going to go about measuring the quality and how you can you quantify quality um as well as what the impact of the use case of the package is um and

**5:56** · you might want to consider having some stricter quality requirements ments for these high impact use cases um ultimately you're generating documentation to assure the quality of each package which is definitely doable but it it ends up being a huge Endeavor to take on internally there's also products available to help uh such as a Taurus as open Val which supplies testing and validation documents for hundreds of popular packages um which is something that uh you can consider when establishing your validation

**6:27** · environments so the last piece that I want to sort of dig into today is an sdlc um which governs how we design build and test shiny applications um and this is going to be a really important document to think about creating internally um I've seen a few published sdlcs I know posit has one published about how they are validating internally developed R packages but we can think about how we can extend that sdlc to also apply to uh validating GXP relevant

**6:59** · shiny applications ANC can help ensure quality of a shiny application which is much more complicated than a typical R script because of that Dynamic and user interaction components a shiny app is going to be fundamentally different than a static R script that you run a single time to create a static output um and an sdlc can contain guidance on um testing requirements uh release management and maintenance to ensure that there's document quality of code over time um

**7:32** · and when considering what sdlc framework is the right fit for your organization I would really encourage you to additionally look into gamp and consider gamp guidelines as a way to um ensure documented quality in a regulated environment so if you're not familiar gamp stands for good automated manufacturing practices and is a guideline developed by the ISP um the value here it's providing a

**7:58** · risk-based approach to to creating uh compliant GXP computerized systems within Industries like Pharmaceuticals biotechnology and Healthcare um gamp is focused on ensuring that these automated systems are properly developed they're tested and they're validated to meet the bar of Industry standards and regulatory requirements so gamp's whole thing is that uh its risk based approach is based on impact and also on complexity the the

**8:27** · impact in our case we can think of it as impact to product quality to patient safety and to clinical data Integrity um a lot of the use cases that we are thinking about are incredibly high impact um and the other input input here is complexity of the system uh shown by the categories on the slide here uh one being the least complex and five being the most complex um the argument I'm making here is that um shiny apps can

**8:53** · fall under category 5 gamp software because of their High complexity anyone on the call Paul who has written code for a shiny app can really attest to the complexity and the amount of customization needed to be able to stand up one of these applications so really the argument I'm making is that by writing our code we're actually developing software and can follow some of the same best practices as software developers in Industry typically an sdlc on its own is

**9:23** · going to be focused on delivering functional software efficiently and goes about outlining the stages of software development on the left here anything from planning and design all the way to implementation testing and maintenance um gamp principles already align really closely with those of um an SCLC but

**9:44** · with an added emphasis on creating uh documentation and artifacts at each of the stages of the sdlc to demonstrate traceability and reproducibility of the system so what I'm saying here is that if you can additionally consider some of these gamp principles when drafting your sdlc you can get closer to a risk-based validated approach that ensures Regulatory Compliance and data Integrity in these GXP regulated

**10:14** · environments so I know that was a ton of information um I included a bunch of links to resources that I found really really helpful when starting my validation Journey there's a number of great resources from posit out there from some of the fuse working groups as well as some like practical R packages out there that can be leveraged to uh directly support these validated workflows I even have a link to gamp uh for those of you who are interested uh and with that I'll take any questions that are in the chat oh risk risk metric is great um so

**10:49** · I'm not using risk metric myself but a lot of the um like for the quantification uh purpose but I've seen it and a lot of the um a lot of the types of Assessments that risk metric is using um we' sort of adopted in our um

**11:08** · sop for uh quantifying sort of like the risk around packages as well but I think if you're if you're just getting started looking at risk metric is a great place to start um the question is who should be the owner of the Sops this is a really great question um the Sops that we um

**11:25** · developed were owned by us like the Analytics group but with really a lot a lot a lot of impact from the dev teams it and then also QA of course um but at this point the sort analytics team was the owner of the

**11:44** · SOP um some challenges and lessons um at least Our IT team it team internally wasn't originally familiar with posit it's sort of a different newer technology and now you know you see these um companies that are springing up like a Taurus that really their whole deal is like deeply understanding posit so one of the initial challenges was having to do a lot of Education with the rest of the it and Tech teams around

**12:09** · what is posit how does it work sort of getting into the nitty-gritty when my background is really just in art programming I didn't even know what was happening under the hood so I think that was the biggest challenge was just figuring out the Deep technical details around how to implement um

**12:27** · posit for automated test yes shiny Test 2 um we're also using test that for some of the uh automated testing um that automated testing is is really the heart and soul of um how we are validating

**12:42** · apps according to sdlc we are doing manual testing on top of it as well as uat with the stakeholders um making sure that what you're building for um whatever team you're working with that the stakeholders are approving and making sure that it's really fit for purpose so we are including uat as a really huge uh manual testing um effort but I think right now we're sort of doing both okay and Phil's closing the chat so thank you everybody