---
title: "Is Claude HIPAA-Compliant? BAA, Coverage, and Gaps"
source: "https://www.aptible.com/hipaa/claude-baa"
author:
published:
created: 2026-04-29
description: "Claude for Enterprise offers a HIPAA BAA, but it's sales-only, Claude Code coverage depends on ZDR configuration, and beta features aren't covered at all. Here's what that means."
tags:
  - "clippings"
---
Platform

Solutions

Resources

[Guides](https://www.aptible.com/guides)

\>

Is Claude HIPAA compliant? What the BAA covers and what it doesn't

## Is Claude HIPAA compliant? What the BAA covers and what it doesn't

**By Mat Steinlin, Head of Information Security @ Aptible**

*Last updated April 2026*

If you're building a healthcare product and want to use Claude, the question you need to answer before sending any patient data is straightforward: does Anthropic offer a BAA?

A [BAA](https://www.aptible.com/hipaa/baa) (Business Associate Agreement) is a legal contract required under HIPAA before you share protected health information with a vendor. It establishes what the vendor can do with your data, what safeguards they must maintain, and their liability if a breach occurs. Without one, sending PHI to any third-party service (including an LLM provider) is a HIPAA violation.

Yes, Anthropic offers a BAA. But which product you're using determines how you get it, what it covers, and what you still need to build.

## The Anthropic product lineup: which version has BAA coverage

Anthropic offers several products with different compliance postures. This matters because a developer who uses Claude.ai for a quick test is in a completely different situation from a team running Claude's API in production with a signed BAA.

| Product | BAA available | Notes |
| --- | --- | --- |
| Claude.ai (Free, Pro) | No | Consumer product. Do not use with PHI. ([Source](https://privacy.claude.com/en/articles/8114513-business-associate-agreements-baa-for-commercial-customers)) |
| Claude.ai Team | No | Not designed for regulated data. ([Source](https://privacy.claude.com/en/articles/8114513-business-associate-agreements-baa-for-commercial-customers)) |
| Claude for Enterprise (HIPAA-ready plan) | Yes | The Enterprise plan can be purchased self-serve or sales-assisted, but BAA coverage requires the sales-assisted path. ([Source](https://support.claude.com/en/articles/9797531-what-is-the-enterprise-plan)) |
| Claude API (pre-Dec 2025 BAA) | Legacy | API BAAs signed before December 2, 2025 cover API usage only, not Enterprise plan access. ([Source](https://privacy.claude.com/en/articles/8114513-business-associate-agreements-baa-for-commercial-customers)) |
| Claude Code (CLI) | Eligible with ZDR | BAA coverage requires Zero Data Retention (ZDR) to be enabled. ZDR is available for qualified accounts only. Contact Anthropic sales to arrange. ([Source](https://privacy.claude.com/en/articles/8114513-business-associate-agreements-baa-for-commercial-customers)) |
| Claude Code beta features | No | Web, Desktop, Review, Security, and Computer Use are not covered under the BAA and are incompatible with ZDR. ([Source](https://privacy.claude.com/en/articles/8114513-business-associate-agreements-baa-for-commercial-customers)) |

The most important distinction: **Claude.ai is a consumer product. Claude for Enterprise is a separate, sales-negotiated offering with HIPAA-ready configuration**. A clinician who pastes patient data into Claude.ai because "Anthropic is HIPAA compliant" has sent PHI to a consumer product with no BAA coverage. [This is already happening at scale](https://www.medpagetoday.com/opinion/second-opinions/119842): surveys show 17% of healthcare workers admit using unapproved AI tools at work, most commonly for documentation.

A secondary one that trips up developers: Claude Code's BAA coverage is conditional and limited to the CLI, and only when Zero Data Retention is explicitly configured on your account. Beta features have no coverage path. See the FAQ below for the full breakdown.

## What Anthropic's BAA covers

When you execute a BAA with Anthropic, you're establishing a legal agreement that:

- Defines Anthropic as a business associate under HIPAA
- Requires Anthropic to implement appropriate safeguards for PHI on their end
- Establishes no model training on your data
- Sets data retention terms (API data is retained briefly for trust and safety purposes, then deleted; consult your actual BAA for specifics)
- Creates shared liability for how your data is handled on Anthropic's infrastructure

## What Anthropic's BAA does not cover

When you execute a BAA with Anthropic, it governs how Anthropic handles PHI within their infrastructure. It does not cover what happens before the request is sent or after the response is returned.

In practice, most HIPAA failures with LLM usage happen in this layer, not at the provider.

The BAA does not cover:

- **Your audit logging.** Anthropic does not log prompts and responses in a way that satisfies HIPAA audit requirements. If you cannot show who accessed what data and when, you have a gap.
- **Storage of those logs:** the logs you generate contain PHI. If they are stored without encryption or proper access controls, you have created a new compliance risk.
- **Key management:** API keys must be scoped, rotated, and controlled across environments. The BAA does not address how your organization manages credentials
- **Access controls:** you are responsible for enforcing which users and systems can send PHI to Claude and under what conditions.
- **PHI handling before the model:** de-identification, validation, and filtering of inputs are your responsibility.
- **Retention requirements:** HIPAA requires six years of log retention. Anthropic does not retain your application level audit logs.
- **Other vendors in your stack:** your database, logging pipeline, analytics tools, and any downstream systems that touch PHI all require their own controls and, where applicable, BAAs.

A signed BAA ensures Anthropic is operating as a compliant business associate. It does not make your system compliant.

### A common failure pattern

A typical implementation looks compliant on the surface:

- The team signs a BAA with Anthropic
- PHI is sent only through approved API paths
- Every prompt and response is logged for auditability

At this point, many teams believe they are covered.

The failure happens in the next step.

Those logs are often shipped into an existing observability or analytics stack such as a log aggregator, search index, or data warehouse. That system was designed for operational telemetry, not regulated data. As a result:

- Logs may be stored in plaintext or with weak encryption
- Access is broader than intended, often including engineering or support teams that do not require PHI access
- Retention policies are short lived or inconsistent with HIPAA requirements
- Data may be copied into downstream systems for debugging, dashboards, or machine learning workflows

At that moment, the compliance boundary has shifted.

The interaction with the model is compliant under the BAA. The system storing and exposing that same data is not.

## Getting the BAA: what to expect

Anthropic's Enterprise plan can be purchased self-serve or through a sales-assisted process. The self-serve path gets you the plan, but it does not get you a BAA. BAA coverage and ZDR configuration are only available through the sales-assisted path.

**The process**

Contact Anthropic's sales team, review the BAA and implementation guide, execute the agreement, and configure the plan with your account team. Plan for this to take weeks, not days. If you're building toward a go-live with a health system customer and need a signed BAA before their security team will approve you, start this conversation early.

**If you have an existing API BAA**

BAAs signed with Anthropic before December 2, 2025 cover API usage only. They do not extend to the HIPAA-ready Enterprise plan. If you need Enterprise features, you'll need a new agreement.

**Claude Code requires ZDR**

The CLI can be covered under a BAA, but only if Zero Data Retention (ZDR) is enabled, and ZDR is available for qualified accounts only, not automatically on any plan. You need to contact Anthropic sales to arrange it. If you have an Enterprise agreement and haven't explicitly configured ZDR, your Claude Code usage is not covered. Claude Code's beta features (Web, Desktop, Review, Security, Computer Use) are not covered under the BAA and are incompatible with ZDR entirely; there is no path to coverage for those.

**Claude Code**

CLI coverage requires Zero Data Retention to be configured; available for qualified accounts only, not automatic on any plan. Beta features (Web, Desktop, Review, Security, Computer Use) cannot be covered regardless of plan or configuration. Contact Anthropic sales to discuss eligibility.

**What affects timeline**

Anthropic is a fast-growing company and their enterprise compliance process reflects that. Teams have encountered delays getting BAAs executed, particularly compared to cloud providers like AWS where a BAA is part of the standard enterprise agreement. Don't assume you can close a healthcare deal and then get the BAA in place before your customer's onboarding date.

**The multi-model problem**

If your application uses Claude for some tasks and OpenAI or AWS Bedrock for others, you need separate BAAs with each provider. This creates contract management overhead and increases the risk of accidentally routing PHI through an uncovered path when models are swapped for testing or performance reasons. An [AI gateway](https://www.aptible.com/platform/ai-gateway) that covers all your LLM traffic under a single BAA eliminates this problem.

## What you still need to build

Executing a BAA with Anthropic is step one. The infrastructure underneath it is still your responsibility.

HIPAA's technical safeguards ([45 CFR 164.312](https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-C/section-164.312)) require controls on any system that handles PHI. When your system calls Claude with patient data, those controls apply to the call:

[**Audit logging**](https://www.aptible.com/hipaa-ai-security/audit-logging)

Every prompt and response that involves PHI needs to be logged with timestamps, user attribution, and model identity. The Anthropic API does not generate these logs for you. You need infrastructure that captures them before they're needed, not during an audit.

**Encrypted log storage**

Your logs contain PHI. They must be encrypted at rest and access-controlled. We regularly see teams diligently log every LLM interaction and then store those logs in an unencrypted S3 bucket or plaintext Elasticsearch index. The logging is correct. The storage is a compliance gap.

**Log retention**

Audit logs must be retained for six years under HIPAA. Your operational log pipeline probably isn't designed for this. You need a log drain to long-term storage with appropriate retention enforcement.

[**PHI de-identification**](https://www.aptible.com/hipaa-ai-security/phi-deidentification)

The safest PHI is PHI that never reaches the model in identifiable form. De-identifying before the prompt and re-identifying after the response adds a meaningful layer of protection. It's not required if your BAA is in place, but it reduces risk exposure if controls elsewhere fail.

[**Key management**](https://www.aptible.com/hipaa-ai-security/key-management)

Anthropic gives you API keys. For a small team, that's manageable. For a growing organization, you need scoping by application, team, and environment (and the ability to rotate or revoke keys without affecting unrelated systems).

**Access controls**

Which users and systems in your organization can send PHI to Claude? How is that enforced? For HIPAA, you need to be able to demonstrate who accessed what and when.

For a full breakdown of these requirements in the context of LLM usage, see [HIPAA-Compliant AI: What Developers Need to Know](https://www.aptible.com/hipaa/hipaa-compliant-ai).

## The developer workflow risk

Production AI features are not the only surface to worry about.

Engineers use Claude in debugging workflows, internal tooling, and data exploration. When a developer runs Claude Code in a codebase that contains PHI (in test fixtures, database dumps, or log files) those interactions are in scope. If your team's development environment isn't covered by your BAA and doesn't have the same controls as production, you have a gap.

The same applies to any automated tooling that calls Claude as part of its operation. A tool that uses Claude to analyze your AWS compliance posture, for example, may not have PHI flowing through it directly, but if it operates in an environment where PHI is present, the configuration matters.

The practical question is not just "did we sign a BAA?" but "do we have visibility into everywhere Claude is being used, and are all of those paths covered?"

For a framework for discovering and governing unauthorized AI tool usage in your organization, see [Shadow AI in healthcare](https://www.aptible.com/hipaa-ai-security/shadow-ai).

## How Aptible AI Gateway covers what Anthropic's BAA doesn't

[Aptible AI Gateway](https://www.aptible.com/platform/ai-gateway) is a managed compliance layer that sits between your application and LLM providers. When you route Claude traffic through AI Gateway:

- **One BAA covers everything.** Your Aptible BAA covers all AI Gateway usage, across all supported models. You don't need separate BAAs with Anthropic, OpenAI, or AWS Bedrock.
- **Audit logging is automatic.** Every prompt and response is logged with full metadata, encrypted at rest, and available for compliance review. You don't build the logging pipeline.
- **PHI de-identification is built in.** Sensitive data is scrubbed before it reaches the model and restored after the response returns.
- **Key management is handled.** Scopes for applications, teams, and environments give you attribution and control without managing it in application code.
- **Switching models doesn't restart compliance.** You can move between Claude, OpenAI, and Bedrock models without re-implementing controls or negotiating new BAAs.

For teams building in digital health who want to use Claude without building the compliance infrastructure themselves, AI Gateway removes the implementation burden.

[Learn more](https://www.aptible.com/platform/ai-gateway) or [**request AI Gateway beta access →**](http://aptible.com/ai-gateway-beta)

## FAQs

**Is Claude HIPAA compliant?**

Not by default. Claude for Enterprise with a signed BAA can be used in a HIPAA-compliant implementation; if you've also built the required infrastructure around it (audit logging, encryption, access controls). Claude.ai in all its consumer tiers (Free, Pro, Team) does not offer a BAA and should not be used with PHI. Compliance depends on implementation, not the product itself.

**Is Claude.ai HIPAA compliant?**

No. Claude.ai Free, Pro, and Team do not offer BAAs. Do not use them with real patient data, including in testing or debugging. Claude for Enterprise is a separate, sales-negotiated product.

**How do I get a BAA with Anthropic?**

Through Anthropic's sales team. The Enterprise plan itself can be purchased self-serve, but BAA coverage requires the sales-assisted path; you need to contact sales, review the BAA, execute it, and configure the plan with your account team. Plan for weeks, not days. If you have a legacy API BAA from before December 2, 2025, it covers API usage only and does not extend to the Enterprise plan.

**Can I use Claude Code with PHI?**

It depends on which Claude Code surface and whether your account has Zero Data Retention (ZDR) enabled.

The CLI can be covered under an Anthropic BAA, but only if ZDR is enabled on your account. ZDR is not automatic; it's available for qualified accounts only and requires working with Anthropic sales to configure. If you have an Enterprise agreement but haven't set up ZDR, your Claude Code CLI usage is not covered.

Claude Code's beta features (Web, Desktop, Review, Security, Computer Use) are a different situation: they are not covered under the BAA and are incompatible with ZDR. There is no path to BAA coverage for those surfaces under the current Anthropic offering.

The practical default: if your developers use Claude Code in environments where PHI may be present, assume that usage is outside your BAA unless you've explicitly verified ZDR is configured on your account.

**Does Anthropic train on my data?**

For API customers, Anthropic's policy is that API data is not used for model training. Data is retained briefly for trust and safety purposes, then deleted. What matters legally is what your BAA says, not what a policy page says; policies can change, contracts are enforceable.

**What's the difference between HIPAA eligible and HIPAA compliant for Claude?**

"HIPAA eligible" means Anthropic will sign a BAA. "HIPAA compliant" means your full implementation meets HIPAA requirements. Getting a BAA is necessary. Your audit logging, encryption, access controls, and the rest of the compliance infrastructure are still your responsibility to implement correctly.

*For the full technical requirements for HIPAA-compliant LLM usage, see* [*HIPAA-Compliant AI: What Developers Need to Know*](https://www.aptible.com/hipaa/hipaa-compliant-ai)*. For BAA requirements more broadly, see* [*What is a HIPAA BAA*](https://www.aptible.com/hipaa/baa)*.*