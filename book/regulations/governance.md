# Regulatory, Compliance & Governance

<!-- 
As organizations advance toward quantum-safe operations, they must navigate a complex
landscape of directives, mandates, and governance frameworks. Regulatory pressure now
extends beyond traditional information-technology (IT) security into quantum readiness,
requiring enterprises to embed cryptographic agility into their risk-management and compliance
programs. This chapter examines (a) global directives that set high-level expectations; (b)
industry-specific mandates shaping sectoral compliance; (c) cross-cutting governance
frameworks for policy, oversight, and auditing; and (d) the vendor ecosystem, including
certification bodies. By understanding these elements and the specific terminology they employ,
executives can align their Post-Quantum Cryptography (PQC) strategies with current and
emerging obligations.


## Global Directives
Global directives are high-level policy instruments-often non-binding recommendations-issued
by governmental or multinational organizations to harmonize practices across borders:

- EU Commission Recommendation on Post-Quantum Cryptography urges Member
States to develop coordinated plans for migrating to quantum-resistant algorithms by
2026 (general infrastructure) and 2030 (critical services) [1].
- U.S. NSTAC (National Security Telecommunications Advisory Committee) Study
on National Preparedness for Post-Quantum Cryptography (Aug 2024) analyzes
gaps in critical-infrastructure security; NSTAC reports inform presidential policy but do
not carry legislative force [2].
- NIST IR 8547 (“Initial Public Draft”) formalizes a phased migration roadmap, defining key
concepts such as confidentiality horizon (the duration data must remain secure) and
hybrid deployment (running classical and PQC algorithms in parallel) to standardize
U.S. federal guidance [3].
- ETSI TS 104 015 V1.1.1 is a Technical Specification that prescribes hybrid
key-exchange profiles-layering classical algorithms (e.g., X25519) with post-quantum
Key-Encapsulation Mechanisms (KEMs, e.g., Kyber) under attribute-based access
policies for fine-grained decryption control [4].
- ITU-T Recommendation Y.3800 establishes the architectural framework for Quantum
Key Distribution (QKD) networks, defining terms such as QKD link, trusted node, and
key-management layer to ensure global interoperability [5].
- BIS (Bank for International Settlements) Paper No 158,
“Quantum-readiness for the
financial system: a roadmap,
” provides a structured framework for central banks and
financial institutions, emphasizing awareness, comprehensive cryptographic inventory,
crypto-agility, defence-in-depth, and phased migration planning [13].


## Industry Mandates
Industry mandates are regulatory requirements or standards embedded within sector-specific
compliance regimes:

### Finance:
- EBA (European Banking Authority) Guidelines on ICT (Information and
Communications Technology) and Security Risk Management
(EBA/GL/2019/04) require robust cryptographic risk assessments and
key-rotation policies. These guidelines feed into the EU’s DORA (Digital
Operational Resilience Act), which mandates that financial entities maintain
crypto-agility capabilities-that is, the ability to switch algorithms quickly-in
support of continuous operations [6][7].
- MAS (Monetary Authority of Singapore) Advisory MAS/TCRS/2024/01
outlines the cybersecurity risks posed by quantum computing and recommends
measures such as algorithm inventory, hybrid-scheme adoption, and governance
updates for financial institutions [14].

### Healthcare:
- FDA (U.S. Food and Drug Administration) “Cybersecurity in Medical
Devices” Guidance (Jun 2025) requires device manufacturers to demonstrate
reasonable assurance that encryption controls remain effective over the product
lifecycle, and to plan for post-market algorithm updates [8].

### Critical Infrastructure:
- CISA (Cybersecurity and Infrastructure Security Agency) Critical
Infrastructure Cybersecurity Framework incorporates findings from RAND’s
Quantum Vulnerabilities Assessment, urging operators to develop sector-specific
PQC roadmaps and treat quantum-hardening as a core resilience activity [9].

## Frameworks for Policy & Oversight
To govern PQC adoption, organizations should leverage established governance and
compliance models:

The NIST Cybersecurity Framework 2.0 (Draft, Mar 2024) introduces a new top-level
function, Govern, explicitly recognizing the need for organizational oversight and policy
management of the cybersecurity program-including cryptographic governance. Under
Govern, roles and responsibilities are defined for approving algorithm choices,
establishing key-management policies, and mandating periodic reviews. The existing five
functions are then applied to cryptography as follows:

- Identify: Maintain a complete algorithm inventory, tagged with business impact and confidentiality horizon [3].
- Protect: Apply and configure cryptographic controls-selecting, implementing, and updating algorithms per policy.
- Detect: Monitor for usage of deprecated or weakened algorithms, integration failures, and module validation errors.
- Respond: Execute pre-approved incident playbooks for cryptographic failures-rotating keys, reissuing certificates, and invoking fallback mechanisms.
- Recover: Restore cryptographic services and validate integrity post-incident, ensuring updated algorithms are in place. 
    
Together, Govern plus the five core functions establish a continuous, metrics-driven lifecycle for cryptographic assets-covering inventory, validation, deprecation, and oversight [10].

ISO/IEC 27001:2013 defines an Information Security Management System (ISMS)
with Annex A.10 mandating documented cryptographic policies, key-management
procedures, and periodic key reviews [11].

ISO/IEC 27002:2013 offers a code of practice detailing controls-such as Control 8.24
(Use of cryptography), mandating that cryptographic mechanisms be designed and operated
to protect the confidentiality, integrity, and authenticity of information, and that key
management processes support their secure lifecycle..

COBIT 2019 provides a governance framework introducing objectives like EDM05
(Ensure Risk Optimization)and DSS05 (Manage Security Services), which can be
mapped to cryptographic governance processes and crypto-agility requirements [12].

## Ecosystem & Vendor Landscape
The PQC ecosystem comprises several vendor and service categories, each contributing to a
secure, resilient infrastructure. Key roles, typical activities, and illustrative examples are outlined
below:

### Crypto-Inventory Providers
- Role: Automated discovery and classification of all cryptographic assets
(algorithms, key lengths, protocol contexts) across networks, applications, and
endpoints.
- Activities:
    - Initial baseline scan; asset annotation with metadata (e.g., confidentiality
horizon per NIST IR 8547).
    - Continuous integration with configuration-management databases or
GRC (Governance, Risk, and Compliance) platforms.
- Examples: Venafi Crypto-Inventory Service; Thales CipherTrust Discovery.

### Threat-Register Services
- Role: Real-time intelligence on cryptanalytic advances, new vulnerabilities, and
PQC standard updates.
- Activities:
    - Publishing subscription feeds of side-channel exploits, algorithm
deprecations, and draft standards.
    - Correlating advisories with inventory to flag at-risk assets and trigger
governance workflows.
- Examples: CISA Quantum-Readiness Alerts; Recorded Future PQC Intelligence.

### PQC Software Vendors
- Role: Implementations of NIST-approved PQC algorithms in two forms: reference
code for proof-of-concept and production SDKs for enterprise deployment.
- Activities:
    - Compatibility validation using libraries such as liboqs (Open Quantum
Safe).
    - Performance benchmarking and integration into pilot environments.
- Examples: PQShield SDK; ISARA Radiate; QuSecure Universe.

### Digital-Communication Hardware Vendors
- Role: Embedded PQC support in devices securing data-in-transit (e.g., firewalls,
VPN gateways, HSMs).
- Activities:
    - Firmware updates enabling hybrid key-exchange (e.g., X25519+Kyber) in
TLS (Transport Layer Security) or IPsec (Internet Protocol Security)
handshakes.
    - Configuration interfaces for PQC parameter selection and monitoring
handshake metrics.
- Examples:
    - Firewalls & VPNs: Cisco Secure Appliance PQC Module; Palo Alto
Networks TLS+Kyber Preview.
    - HSMs: Thales nShield PQC Firmware; Utimaco CryptoServer PQC
Edition.

### Open-Source vs. Commercial Suites
- Open-Source Projects: Community-driven, transparent codebases (e.g., liboqs)
under permissive licenses but without formal SLAs or certification.
- Commercial Solutions: Offer SLAs, integration services, certified modules,
graphical management, and policy-engine capabilities.
- Activities: Early proofs-of-concept with open-source, followed by production
deployment on commercial platforms.
- Examples: liboqs; Thales CipherTrust Manager with PQC plug-in; Venafi
KeyProtect PQC.

### Certification & Conformance Labs
- Role: Validation and certification of cryptographic modules against security and
interoperability standards.
- Activities:
    - FIPS 140-3 testing under NIST CMVP, yielding Validation Certificates for
U.S. federal compliance [3].
    - Common Criteria (ISO/IEC 19790/24759) evaluations assigning EALs
(Evaluation Assurance Levels).
    - Interoperability events (e.g., ETSI Plugtests) to verify conformance to
PQC profiles and hybrid-TLS specifications.
Examples: NCC Group, TÜV Rheinland, A-LIGN (CMVP labs); BSI (Germany),
ANSSI (France) (Common Criteria test bodies).
 -->