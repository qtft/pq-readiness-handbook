# ทะเบียนความเสี่ยง (Risk Register)

<!-- 
An accurate, up-to-date inventory is the foundation of any cryptographic transition. NIST’s IR
8547 instructs organizations to catalog every instance where encryption, digital signatures, or
key exchange is used-across servers, applications, network devices, and cryptographic libraries
[1]. For each asset, record the algorithm name (e.g., RSA-2048), key length, mode of operation
(e.g., RSA-OAEP for key wrap), and context of use (TLS, S/MIME, code-signing, database
encryption). Assess dependencies such as hardware security modules (HSMs), cloud-managed
KMS, and third-party SDKs to uncover hidden uses. Classify assets by confidentiality
horizon-the period during which data must remain secure (e.g., 1 year for ephemeral logs, 10
years for financial records)-to prioritize high-impact migrations [1]. Finally, map each asset to its
business owner and risk profile to streamline governance.
- Discovery Tools: Leverage automated scanners and code analysis tools to detect
cryptographic API calls and certificate stores.
- Metadata Tagging: Annotate each asset with custom attributes: data classification,
compliance requirements (e.g., GDPR data), and recovery procedures.
- Risk Scoring: Apply a scoring model that weights factors such as data sensitivity, attack
surface, and confidentiality horizon.
 -->