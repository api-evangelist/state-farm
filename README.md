# State Farm (state-farm)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

State Farm is the largest property and casualty insurance provider in the United States, headquartered in Bloomington, Illinois. Founded in 1922, the company offers a comprehensive range of insurance products including auto, home, renters, life, health, business, and farm/ranch insurance, as well as banking and financial services. State Farm operates through a network of approximately 19,000 agents across the US and Canada. The company has invested heavily in its digital transformation, operating a Partner Gateway developer portal at developer.statefarm.com that exposes APIs enabling partners, agents, and third-party platforms to integrate with State Farm's insurance products and services. State Farm is a mutual company owned by its policyholders, consistently ranked among the Fortune 50.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/state-farm/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/state-farm/refs/heads/main/apis.yml)

## Timestamps

- **Modified:** 2026-05-19

## APIs

### Renters Insurance API

The State Farm Renters Insurance API enables partner platforms, real estate applications, and property management systems to offer embedded renters insurance quotes and policies to tenants. Partners can request quotes, initiate policy applications, and retrieve policy status using this API. State Farm is the industry leader in renters insurance, providing coverage for personal belongings, liability protection, and additional living expenses. Available in all US states except California, Massachusetts, and Rhode Island.

- **Human URL:** [https://developer.statefarm.com/api/renters](https://developer.statefarm.com/api/renters)
- **Base URL:** `https://api.statefarm.com/v1`

#### Tags

- Insurance
- Renters Insurance
- Property
- Embedded Insurance
- Partner

#### Properties

- [Documentation](https://developer.statefarm.com/api/renters)
- [OpenAPI](openapi/state-farm-renters-insurance-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/state-farm-renters-insurance.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/state-farm-renters-insurance.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Auto Insurance API

The State Farm Auto Insurance API supports partner integrations for automobile insurance quoting, policy management, and claims inquiry. This API enables auto dealers, telematics platforms, and financial institutions to embed State Farm auto insurance products within their own applications. State Farm is the largest auto insurer in the US. The API supports retrieving quotes, checking policy status, and accessing coverage information.

- **Human URL:** [https://developer.statefarm.com/](https://developer.statefarm.com/)
- **Base URL:** `https://api.statefarm.com/v1`

#### Tags

- Insurance
- Auto Insurance
- Vehicles
- Partner
- Embedded Insurance

#### Properties

- [Documentation](https://developer.statefarm.com/)
- [Postman Collection](collections/state-farm-renters-insurance.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/state-farm-renters-insurance.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### B2B Insurance Inquiry API

The State Farm B2B Insurance Inquiry API is designed for lenders, mortgage servicers, and financial institutions that need to verify homeowner and auto insurance policy status for collateral protection purposes. This API supports home and auto lenders in verifying that borrowers maintain the required insurance coverage on financed assets. Accessible through the State Farm B2B portal.

- **Human URL:** [https://b2b.statefarm.com/b2b-content/home-auto-lenders/ins-inquiry](https://b2b.statefarm.com/b2b-content/home-auto-lenders/ins-inquiry)
- **Base URL:** `https://b2b.statefarm.com/api/v1`

#### Tags

- Insurance
- B2B
- Lenders
- Mortgage
- Verification

#### Properties

- [Documentation](https://b2b.statefarm.com/b2b-content/home-auto-lenders/ins-inquiry)
- [Postman Collection](collections/state-farm-renters-insurance.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/state-farm-renters-insurance.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.statefarm.com)
- [Developer  Portal](https://developer.statefarm.com)
- [Git Hub](https://github.com/StateFarmIns)
- [Engineering  Blog](https://engineering.statefarm.com/blog)
- [B2 B  Portal](https://b2b.statefarm.com)
- [LinkedIn](https://www.linkedin.com/company/state-farm)
- [Twitter](https://twitter.com/StateFarm)
- [Privacy Policy](https://www.statefarm.com/customer-care/privacy-security/privacy/privacy-policy)
- [Terms of Service](https://www.statefarm.com/customer-care/legal-disclaimer)
- [F A Q](https://developer.statefarm.com/faq)
- [OpenAPI](openapi/state-farm-renters-insurance-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](json-schema/state-farm-renters-policy-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/state-farm-renters-policy-structure.json)
- [JSON-LD](json-ld/state-farm-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](vocabulary/state-farm-vocabulary.yml)
- [Spectral Rules](rules/state-farm-rules.yml)
