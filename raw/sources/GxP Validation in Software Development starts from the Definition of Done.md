---
title: "GxP Validation in Software Development starts from the Definition of Done"
source: "https://www.appsilon.com/post/gxp-software-validation-starts-with-definition-of-done?utm_source=social&utm_medium=linkedin&utm_campaign=blog&utm_term=appsilon-account&utm_content=gxp"
author:
  - "[[By:Paweł Przytuła]]"
published:
created: 2026-04-30
description: "Discover how the Definition of Done can be a good starting point for GxP validation in software development for the pharmaceutical industry."
tags:
  - "clippings"
---
Reading time:

6

min

GxP validation can be a complex and often misunderstood process, with each company implementing their own unique approach. During a recent roundtable I attended at the [R/Pharma Summit in Seattle](https://posit.co/blog/register-for-r-pharma-at-posit-conf-2024/), there was a recurring theme that stood out to me – every company seems to have their own definition of validation and different validation processes, and it was difficult to point out concrete validation tools.

> We reduced the time needed to generate reports from 5 weeks to 5 minutes for a premier biopharmaceutical company's GxP compliance process. [Explore how we did it in this case study.](https://www.appsilon.com/case-studies/gxp-reporting-automation-from-5-weeks-to-5-minutes)

This blog aims to shed some light on that from our perspective at Appsilon, as we’ve supported Fortune 500 Pharmaceutical companies [with their GxP processes](https://www.appsilon.com/case-studies/boosting-the-generation-of-gxp-documents-posit-and-shiny-solutions). We’ll explore what GxP means from a software development point of view, our approach towards validation for pharmaceutical clients, our definition of done, and how it can be a good foundation for GxP validation.

## What is GxP?

[GxP](https://en.wikipedia.org/wiki/GxP) is an abbreviation for “good practice.” It is an umbrella term that includes a variety of regulatory guidelines and standards that ensure the safety, quality, and efficacy of pharmaceutical products. The "x" in GxP represents different focus areas, including:

- **Good Manufacturing Practice (GMP):** Ensures products are consistently produced and controlled according to quality standards.
- **Good Laboratory Practice (GLP):** Governs the proper management of laboratory work to ensure consistency and reliability.
- **Good Documentation Practice (GDocP):** Ensures that all documentation is accurate, legible, and traceable.
- [**Good Software Engineering Practices (GSEP)**](https://www.tricentis.com/learn/gxp-compliance-checklist-what-you-need-to-know): Makes sure software development and testing is structured and compliant.

Other variations include:

- Good Pharmacovigilance Practice (GVP)
- Good Distribution Practice (GDP)
- Good Data Management Practice (GDMP)
- Good Automated Manufacturing Practice (GAMP)
- Good Storage Practices (GSPs)
- Good Clinical Practices (GCPs)

**Note:** Sometimes, a “c” or “C” can be placed in front of this initialism to mean “current”, such as cGMP meaning “current good manufacturing practice.”

## So, what is GxP Validation in Software Development?

Finding a succinct definition of [GxP for software development](https://www.aiti.at/en/glossar/software-validation/) wasn’t easy, but in a nutshell, **GxP validation in software development ensures that software in regulated industries meets required standards and consistently delivers reliable results through careful planning, testing, documentation, and verification to guarantee compliance, safety, and quality.**

Software companies support GxP validation by **providing** [**documentation**](https://www.appsilon.com/post/gxp-compliance-in-pharma-made-easier-good-documentation-practices-with-r-markdown-and-officedown) and **technical assistance** for [IQ](https://www.thefdagroup.com/blog/a-basic-guide-to-iq-oq-pq-in-fda-regulated-industries#:~:text=Installation%20Qualification%20\(IQ\)%20verifies%20that,manufacturer's%20specifications%20or%20installation%20checklist.) (installation qualification - verifying the correct installation of the system to the manufacturer’s specification), OQ (operation qualification - identifying and inspecting equipment features that could impact final product quality), and PQ (performance qualification - user requirements are verified by the qualification and validation team). \[[IQ, OQ, and PQ](https://www.thefdagroup.com/blog/a-basic-guide-to-iq-oq-pq-in-fda-regulated-industries#:~:text=Installation%20Qualification%20\(IQ\)%20verifies%20that,manufacturer's%20specifications%20or%20installation%20checklist.) are methods for demonstrating that installed equipment meets quality requirements.\]

In terms of GxP documentation, there are three main areas of compliance:

- Traceability - entire product lifecycle (design, development, testing, release, and end of life), complete with all logs and changes.
- Accountability - identification of all contributors alongside timestamps for each change.
- Data Integrity - the reliability of data generated by the system.

Each report has to clearly demonstrate not only the outcomes and conclusions but also all the data, data sources, and tools used to produce them.

> Learn more about good documentation practices using R Markdown and {officedown}. [Our blog post covers everything you need to know.](https://www.appsilon.com/post/gxp-compliance-in-pharma-made-easier-good-documentation-practices-with-r-markdown-and-officedown)

In summary, the primary goal of GxP validation is to guarantee that software is fit for its intended use and complies with stringent regulatory standards. While there [isn’t a central governing body](https://www.tricentis.com/learn/gxp-compliance-checklist-what-you-need-to-know) for GxP validation, it is closely monitored by regulatory bodies such as the [U.S. Food and Drug Administration](https://www.fda.gov/) (FDA) and the [European Medicines Agency](https://www.ema.europa.eu/en/homepage) (EMA). Non-compliance can lead to significant penalties, including product recalls or delays in getting new therapies to market.

## Why Every Company’s Validation Process is Different

Another observation at the roundtable was that each company has a different definition, approach, and process for GxP validation. This is normal, and it’s something we’ve observed in our years of experience developing R/Python software solutions for hundreds of customers at Appsilon; it’s dependent on:

- The company’s technology stack
- Type of software that needs to be validated – these could be packages, dashboards, scripts, or reports
- The purpose or end-use of the software – Is it a prototype, or is it a solution that will be part of a regulatory submission?

Given these variations, general advice (as was discussed at the roundtable) like "use a Git workflow," "implement Rhino for GxP development," or "automate your tests" can be helpful starting points. However, these tips need to fit each company’s specific needs.

So, what do these tips really mean in practice? How do you put them into action when each company’s context is so different? And what else do you need to consider to create a well-rounded validation strategy? These are the kinds of questions that companies need to address to develop a GxP validation process that works for them.

To navigate these complexities, we recommend using the **Definition of Done (DoD)**, a key concept from the [Scrum methodology](https://www.scrum.org/resources/what-definition-done), as **a starting point**.

## Appsilon’s Approach to Definition of Done (DoD)

DoD represents a **shared understanding between the Product Owner and the Development Team** of what requirements need to be fulfilled before a piece of software can be considered complete. By clearly defining these criteria upfront, we ensure that everyone involved in the project has a **clear understanding of what constitutes a "done" piece of software.**

![](https://cdn.prod.website-files.com/654fd3ad88635290d9845b9e/66cc52aa233c2c3cf53a3464_AD_4nXfja_0kcPTZfXJD4WmrMYm0hSvd1q3k9smRhWG6YcU6uh1tIT2cwqF_vlXdnBc7QCKGPVwF7ZLsy4jYhfZyNSfuoiu0pNbomzrEGOFPoCX0NlOlZcqrmaSFEcrpZUGKrPhESCtnej60OGbnyFHmtOa0T14.png)

### So, when do we consider something “done”?

The Definition of Done defines our common quality standard and gives us a shared understanding of completeness. **It’s more than just a checklist—it's our Code of Honor**. It helps us deliver a product (increment) that meets the client's needs and is ready for them to use.

**Here’s how it works:** At the start of each project, we sit down with the Product Owner/client and define what “done” looks like. Next, we create a DoD by selecting points from our Definition of Done template (listed below) and customize it to include project-specific criteria. Those checkpoints can include specific GxP verifications. Thus, developers can quickly react if any particular solution does not meet a specific GxP check. That boosters the alignment of the whole team with GxP compliance and contributes to smooth transition between the entire software lifecycle stages.

**Here are the key aspects of our DoD:**

- **Verified by the Author of the Change:**
	- The change corresponds to a well-defined and described task.
		- The author regularly updates the task status to reflect its current state.
		- A pull request is opened, and a reviewer is assigned.
- **Verified by the Reviewer:**
	- The change has been tested (manually or with automated tests), and everything works as expected without breaking existing functionality.
		- No new errors or warning messages are introduced.
		- All user interactions and messages are clear, actionable, and user-friendly.
		- Documentation, including README and code comments, is updated with all relevant information.
		- All code is reviewed and merged into the development branch.
		- Continuous integration checks pass, including linter, unit tests, and integration tests.
		- Unit tests are added for all new or changed logic.
		- End-to-end and integration tests are added.
		- The solution is tested under all required browsers.
		- All changes are reviewed by the Business Analyst and approved.
		- All assumptions about data are explicitly written in the code.
		- All task requirements are satisfied and verified by the reviewer.
		- The change follows our style guide.
		- Results are reproducible, and data sources are documented.
		- Models are validated appropriately.
- **Good Practices:**
	- Self-review your code.
		- Update credentials in the password manager if related to the change.

In summary, our Definition of Done ensures that each software change meets a comprehensive set of quality standards, from initial development through rigorous testing and final documentation, before it can be considered complete and ready for the client.

## Next Steps: Open-Sourcing Our Definition of Done

Navigating GxP validation in software development is no small task, but by using simple tools like the Definition of Done, companies can create a solid foundation for compliance.

We plan to release a full list of our Definition of Done criteria as an open-source resource on [GitHub](https://github.com/Appsilon). At Appsilon, we believe that the broader community could greatly benefit from collaborating on this project to put together all possible requirements for the DoD in GxP development.

Plus, keep an eye out for more content about Appsilon’s Quality Test process, which will offer deeper insights into how we ensure the highest standards of software quality and compliance, as DoD is just one step in our entire process.

> **Make GxP compliance for software development easier with a clear Definition of Done.** [**Download the checklist and set your team up for success.**](https://www.appsilon.com/resources/definition-of-done-checklist-for-pharma-teams)

## Resources

To learn more about GxP, you can take a look at these resources:

- [Software Development for the Pharmaceutical Industry](https://biosistemika.com/blog/software-development-for-pharmaceutical-industry/)
- [GxP Compliance in Pharma Made Easier: Good Documentation Practices with R Markdown and {officedown}](https://www.appsilon.com/post/gxp-compliance-in-pharma-made-easier-good-documentation-practices-with-r-markdown-and-officedown)
- [Boosting the generation of GxP documents, Posit and Shiny solutions for automated GxP compliant reports.](https://www.appsilon.com/case-studies/boosting-the-generation-of-gxp-documents-posit-and-shiny-solutions)
- [Software validation](https://www.aiti.at/en/glossar/software-validation/)
- [GxP Compliance: Leveraging Test Automation for Validation and Security](https://www.opkey.com/blog/gxp-compliance-leveraging-test-automation-for-validation-and-security)
- [GxP compliance checklist: What you need to know](https://www.tricentis.com/learn/gxp-compliance-checklist-what-you-need-to-know)
- [GxP Systems Compliance](https://www.arbourgroup.com/services/validation-compliance/gxp-systems-compliance/)

#### Is Your Software GxP Compliant?

Download a checklist designed for clinical managers in data departments to make sure that software meets requirements for FDA and EMA submissions.

[Get the Checklist](https://www.appsilon.com/resources/definition-of-done-checklist-for-pharma-teams)

#### Ensure Your R and Python Code Meets FDA and EMA Standards

A comprehensive diagnosis of your R and Python software and computing environment compliance with actionable recommendations and areas for improvement.

[Book the Audit](https://www.appsilon.com/services/gxp-audit)