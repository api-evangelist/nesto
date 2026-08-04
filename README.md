# Nesto (nesto)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Nesto Inc. is a Montreal-headquartered Canadian digital mortgage lender and mortgage technology provider, founded in 2018 and licensed across Canadian jurisdictions. It sits on the financing side of the residential real estate value chain rather than the listings side — originating, underwriting, and servicing mortgages direct-to-consumer at nesto.ca, and, following its 2024 acquisition of CMLS Group, administering roughly CA$73 billion in residential and commercial mortgage assets. Its Nesto Cloud business (nestocloud.ca) sells the same origination, underwriting, and servicing platform to banks, credit unions, and commercial lenders as SaaS or fully outsourced BPO, and advertises "seamless API integrations with your existing systems and third-party providers" alongside a Maestro AI underwriting engine. That API surface is not publicly documented: there is no developer portal, no published reference, no OpenAPI or other machine-readable contract, and no self-serve signup. Access is a commercial engagement negotiated with the Nesto Cloud team. As a mortgage lender Nesto sits outside the listings syndication layer entirely — no RESO Web API or Data Dictionary certification, no RESO UPI usage, and no CREA Data Distribution Facility participation is published or discoverable. The company's only machine-readable public artifact is a security.txt whose disclosure scope explicitly names "Web applications, APIs, and customer-facing services", confirming APIs exist while none are documented for outside developers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/nesto/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/nesto/refs/heads/main/apis.yml)

## Tags

- Real Estate
- Canada
- Mortgage
- Lending
- PropTech
- Mortgage Technology
- Financial Services
- Underwriting
- Loan Servicing

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## APIs

No publicly documented APIs. Nesto Cloud markets API integration as a platform capability but publishes no developer portal, no API reference, and no machine-readable contract. See [review.yml](review.yml) for every URL probed and its HTTP status.

## RESO Posture

**Certified:** No. **Posture:** no RESO reference found; mortgage lender outside the listings layer.

No RESO Web API certification, no RESO Data Dictionary certification, no version claim, no RESO certification directory listing, and no Universal Property Identifier (UPI) usage was discoverable across nesto.ca, nestocloud.ca, nestogroup.ca, or the open web. An OData `$metadata` probe against `api.nesto.ca` returned 404. Nesto is a mortgage lender and lending-platform vendor, not an MLS, board, listings portal, or IDX/VOW consumer; in Canada listings flow through CREA's single national Data Distribution Facility, and Nesto publishes no participation in it. RESO's absence here is structural, not a publication gap.

## Access Gate

**Gate:** `partner-only`.

There is no path for an unaffiliated developer. Nesto Cloud is sold as an enterprise SaaS or fully outsourced BPO engagement to financial institutions, credit unions, and commercial lenders. Reaching any API requires negotiating a commercial contract — the published entry points are a "book a demo" form, `info@nestocloud.ca`, and 1.866.297.7407. No developer agreement, sandbox terms, rate card, or self-serve signup exists. `app.nesto.ca` is the consumer borrower login, not a developer console.

## Open Data

None. Nesto publishes no open dataset; rate tables are web pages, not a data product.

## Auth Model

Not published. `https://nesto.ca/.well-known/openid-configuration` returned 404. Nesto Cloud markets SOC 2 Type II compliance and a security-first architecture for Canadian regulatory requirements but documents no authentication scheme for any API.

## Webhooks, Events, SDKs, Postman

None published — the absence is itself the finding for a vendor selling an API-integrated lending platform.

## Security and Compliance

Published and third-party audited, in sharp contrast to the API surface. `https://www.nesto.ca/security/` names **SOC 1 Type II**, **SOC 2 Type II**, and **ISO 27001:2022**, with TLS 1.2+ in transit, AES-256 at rest, static analysis, manual code review, and yearly penetration testing on Google Cloud infrastructure. A Vanta trust center is live at `app.vanta.com/nesto.ca/trust/edzpx9i0szdy5sgukfq0w`. Vulnerability reports go to `security@nesto.ca`; there is no bug bounty — "we do not offer compensation for vulnerability disclosures." The `security.txt` is real and hand-written but carries no RFC 9116 `Expires:` field. DNSSEC is signed and DMARC is `p=reject` on nesto.ca; no CAA records exist on any domain.

## Open Source

Nesto's GitHub organization, [`nestoca`](https://github.com/nestoca), has 19 actively maintained public repositories — all internal developer-platform tooling under MIT, none of it an API client. The flagship is [`joy`](https://github.com/nestoca/joy), a GitOps CLI for Kubernetes deployments and promotions (v0.97.0, installable via `brew install nestoca/public/joy`), alongside `joy-operator`, `joy-generator`, `jen-cli` (microservice scaffolding), `jac`, `canonyze`, and `public-actions`. Every repo was searched for OpenAPI, AsyncAPI, `.proto`, GraphQL, `AGENTS.md`, and `llms.txt` — zero hits. Catalogued in [packages/](packages/nesto-packages.yml) and [cli/](cli/nesto-cli.yml); deliberately **not** wired as `SDKs` or `CLI`, because neither can call a Nesto service.

## Artifacts

- [well-known/](well-known/nesto-well-known.yml) — discovery index across five hosts; raw [security.txt](well-known/nesto-security.txt) and [PGP key](well-known/nesto-pgp-key.txt)
- [security/](security/) — [domain security](security/nesto-domain-security.yml), [trust center](security/nesto-trust-center.yml), [vulnerability disclosure](security/nesto-vulnerability-disclosure.yml)
- [conformance/](conformance/nesto-conformance.yml) — standards conformance, including the API-shaped standards asserted false on probed evidence
- [lifecycle/](lifecycle/nesto-lifecycle.yml) — evidence of absence: no versioning, deprecation, SLA, status page, or changelog
- [packages/](packages/nesto-packages.yml) and [cli/](cli/nesto-cli.yml) — first-party open source
- [llms/](llms/nesto-llms.txt) — generated llms.txt

No `openapi/`, `asyncapi/`, `graphql/`, `mcp/`, `skills/`, `scopes/`, `authentication/`, `errors/`, `conventions/`, `sandbox/`, or `arazzo/` directory exists. Each would require inventing an interface Nesto does not publish.

## Common Properties

- [Website](https://www.nesto.ca/)
- [Website — Nesto Cloud](https://nestocloud.ca/)
- [Website — Nesto Group](https://nestogroup.ca/)
- [About](https://www.nesto.ca/about-us/)
- [Blog](https://www.nesto.ca/advice/)
- [Blog RSS](https://www.nesto.ca/feed/)
- [Blog RSS — Nesto Cloud](https://nestocloud.ca/feed/)
- [Security](https://www.nesto.ca/security/)
- [security.txt](well-known/nesto-security.txt)
- [Trust Center (Vanta)](https://app.vanta.com/nesto.ca/trust/edzpx9i0szdy5sgukfq0w)
- [Compliance — SOC 1/SOC 2/ISO 27001](https://www.nesto.ca/security/)
- [GitHub Organization](https://github.com/nestoca)
- [Terms of Services](https://www.nesto.ca/terms-of-services/)
- [Privacy Policy](https://www.nesto.ca/privacy-policy/)
- [Privacy Policy — Nesto Cloud](https://nestocloud.ca/privacy-policy/)
- [Support](https://www.nesto.ca/contact/)
- [Support — Nesto Cloud](https://nestocloud.ca/contact/)
- [FAQ](https://www.nesto.ca/faq/)
- [Careers](https://www.nesto.ca/careers/)
- [Login](https://app.nesto.ca/)
- [Affiliate program](https://www.nesto.ca/affiliate-program/)
- [Trusted partners](https://www.nesto.ca/financial-advisor/trusted-partners/)

## Maintainers

- Kin Lane — kin@apievangelist.com
