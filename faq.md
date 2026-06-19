## 1. Vulnerability databases exist already. How is the EUVD different?

Contrary to other vulnerability databases, the EUVD comes with a holistic approach and aims for ensuring a high level of interconnection of information sources. It does so by leveraging the open-source software [Vulnerability-Lookup](https://github.com/cve-search/vulnerability-lookup) which enables a quick correlation of vulnerabilities from multiple known sources.

The EUVD team embraces a multi-stakeholder approach by collecting publicly available vulnerability information from multiple sources, including advisories provided by vendors and CSIRTs (such as the members of the [EU CSIRTs network](https://csirtsnetwork.eu/)), as well as other relevant stakeholders.

Providing aggregated, reliable, and actionable information related to vulnerabilities (e.g. mitigation measures and exploitation status) contributes to making the EUVD a trusted source for enhanced situational awareness. Utilising the Common Security Advisory Framework ([CSAF](https://www.csaf.io/)), a standardised format for vulnerability advisories, the EUVD supports automation in the processing, consumption, and distribution of security advisories.

## 2. What is the main objective and target audience of the EUVD?

Timely and detailed information on vulnerabilities allow users to take appropriate mitigating measures and apply patches as early as possible. As such the EUVD was designed as a publicly accessible database displaying details about disclosed vulnerabilities impacting IT products and services. With a focus on suppliers of network and information systems and entities using their services, information documented in the EUVD is of particular interest to competent authorities such as CSIRTs, as well as private companies and researchers, with the objective to limit exposure to threat, ultimately contributing to a collective cybersecurity approach, by contributing to an enhanced EU vulnerability disclosure and vulnerability information sharing landscape.

## 3. Why does the EUVD homepage display three different dashboards?

The homepage initially displays three dashboards, each providing a specific view on the latest processed vulnerability data. More specifically, the "Critical Vulnerabilities" dashboard provides information filtered by criticality according to the Common Vulnerability Scoring System ([CVSS](https://www.first.org/cvss/user-guide)) (i.e. CVSS score of 9 or above), the "Exploited Vulnerability" dashboard highlights vulnerabilities reported being actively exploitated, and the "EU Coordinated Vulnerabilities" dashboard listing vulnerabilities coordinated by European CSIRTs such as the members of the [EU CSIRTs network](https://csirtsnetwork.eu/).

## 4. Which data and services are used to feed the EUVD?

Information displayed in the EUVD is collected from different sources and made available through different views. In addition to advisories and bulletins published by vendors and CSIRTs the primary source of data is the CVE program database. The EUVD service retrieves its data by querying the Vulnerability-Lookup collection, enriches the data, and assigns a unique EUVD identifier (on top of existing identifiers such as CVE) to each vulnerability record.

The database builds upon the OASIS Common Security Advisory Framework ([CSAF](https://www.csaf.io/)) to support automation in the processing, production and distribution of security advisories.

## 5. Why is an EUVD identifier assigned?

Vulnerability identifiers serve the purpose of a reference point. Nevertheless, different sources of vulnerability data may utilize individual identifiers for the vulnerability data in scope of their activity. The EUVD service builds upon the CVE system and vulnerabilities in the scope of the CVE numbering service receive a CVE. In addition, the EUVD data aggregates and enriches the vulnerability information and lists an EUVD ID on top of the CVE when new vulnerability entries are created. To allow further cross referencing, the CVE identifier and additional vulnerability identifiers are listed when available.

## 6. How does the EUVD enrich the existing vulnerability information?

The EUVD collects and references vulnerability information collected from existing databases (such as MITRE's [CVE DB](https://www.cve.org/), GitHub's [Advisory Database](https://github.com/github/advisory-database), [JVN iPedia](https://jvndb.jvn.jp/en/), [GSD-Database](https://github.com/cloudsecurityalliance/gsd-database/)), adds additional information via references to advisories and alerts issued by national CSIRTs, mitigation and patching guidelines published by vendors, and enriches it with exploited vulnerability markings (such as [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog)) and FIRST's Exploit Prediction scores ([EPSS](https://www.first.org/epss/)). By default, and when available, EUVD data records include

- information describing the vulnerability,
- the affected ICT products or ICT services, affected versions, and the severity of the vulnerability in terms of the circumstances under which it may be exploited,
- the availability of related patches and, in the absence of available patches,
- guidance provided by the competent authorities including CSIRTs addressed to users of vulnerable ICT products and ICT services as to how the risks resulting from disclosed vulnerabilities can be mitigated.

## 7. Why does the EUVD rely on non-EU services?

ICT services are very commonly provided across national jurisdictions. Similarly, vulnerability coordination requires international cooperation and alignment. Building on EU sources for vulnerability information, the ENISA EUVD service aims at capitalizing on already existing sources and standards. As such, ENISA initiated a structured cooperation with MITRE's federated CVE Program and the EUVD service is integrating its data as well as vulnerability data provided by ICT vendors maturely disclosing vulnerability information via advisories and relevant information such as CISA's Known Exploited Vulnerability Catalogue. By 2026, manufacturers will be obliged to notify actively exploited vulnerabilities that impact IT products with digital elements via a reporting mechanism referred to as the [Cyber Resilience Act](https://data.consilium.europa.eu/doc/document/PE-100-2023-INIT/en/pdf)'s Single Reporting Platform. After a security update or another form of corrective or mitigating measure is available the reported data will, in agreement with the product manufacturer, also be asynchronized and published via the EUVD.

## 8. How is the EUVD related to the Single Reporting Platform (SRP) mandated in the CRA?

The Single Reporting Platform (SRP) established under the [Cyber Resilience Act](https://data.consilium.europa.eu/doc/document/PE-100-2023-INIT/en/pdf) (CRA) is different from the NIS2 Directive-established EUVD.

Each platform serves a different purpose. While the objective of the EUVD is to make information on publicly known vulnerabilities accessible, the SRP focuses on the mandatory reporting of actively exploited vulnerabilities contained in products with digital elements, not yet publicly documented. The latter can be sensitive and will be handled as such.

However, in agreement with the manufacturer or once disclosed, vulnerabilities notified through the SRP will also be published via the EUVD to make the information accessible (as mandated by Article 17 of the Cyber Resilience Act, in agreement with the manufacturer or once disclosed vulnerabilities notified through the SRP will also be published via the EUVD to make the information accessible.).

## 9. How does ENISA support vulnerability disclosure? Does ENISA act as a coordinator itself?

Onboarded as a CVE Numbering Authority (CNA) since January 2024, ENISA initiated a vulnerability registry service covering the vulnerabilities in information technology (IT) products discovered by CSIRTs or reported to EU CSIRTs for [coordinated disclosure](https://csirtsnetwork.eu/homepage?tab=cvd). For the time being, ENISA may register vulnerabilities and support vulnerability disclosure in relation to

- vulnerabilities in IT products discovered by EU CSIRTs themselves and
- vulnerabilities reported to EU CSIRTs for coordinated disclosure as long they are not in another CNA's scope.

## 10. Questions by subject

**General feedback**

Q1: Where can I share feedback about the EUVD platform?
You can submit your feedback directly on the platform.

Q2: What happens after I submit feedback?
Your input is reviewed internally and considered as part of our ongoing improvements.

Q3: Will I hear back about my feedback?
We don't provide individual responses, but key updates will appear on our Q&A page.

**Bugs and technical issues**

Q1: I found a technical issue on the EUVD platform. What should I do?
Please report it directly through the platform. We are monitoring all validated issues and track them via our Q&A page: [https://euvd.enisa.europa.eu/faq](https://euvd.enisa.europa.eu/faq)

Q2: Will I be notified when my bug report is resolved?
Resolutions and updates are posted on the Q&A page regularly. We do not send individual follow-ups.

Q3: How quickly are bugs fixed?
Response times vary depending on issue severity. Critical bugs are prioritized.

**Feature requests**

Q1: How can I suggest a new feature for EUVD?
Submit your suggestion through the platform's feedback option.

Q2: What happens after I suggest a feature?
Your idea is recorded and reviewed. Feasibility and impact are key criteria for implementation.

Q3: Will my feature request be added right away?
Not necessarily. All suggestions are considered, but implementation depends on strategic priorities.
