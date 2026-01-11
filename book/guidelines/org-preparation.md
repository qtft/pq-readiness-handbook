# การเตรียมความพร้อมสำหรับยุคควอนตัมในระดับองค์กร

- Migration Plan and Roadmap
- Inventories (Assets and Crypto)
- Task force and centre of excellence
- Regulatory and compliance guidance (NIST Crypto Framework 2.0)

a. Phased rollout strategy
<!-- 
Phased Rollout Strategy
A phased rollout balances minimizing exposure to quantum threats with maintaining system
stability. NIST IR 8547 prescribes a wave-based approach: begin with non-production testbeds
to validate basic functionality, then pilot PQC in low-risk services, before expanding to
mission-critical systems [1]. The CISA factsheet emphasizes vendor engagement
early-confirming PQC support in product roadmaps and firmware updates [2]. Each phase
should include performance benchmarks, error-handling tests, and rollback plans. Documenting
lessons learned in each iteration reduces risk when migrating high-value assets.
- Phase 1-Proof-of-Concept (PoC): Deploy PQC in isolated environments. Validate
key-generation, encryption/decryption, and signature flows.
- Phase 2-Pilot: Integrate PQC into a limited set of production endpoints (e.g., VPN
gateways, partner APIs). Measure handshake latency, CPU/memory overhead, and error
rates.
- Phase 3-Broad Deployment: Extend to customer-facing services (web TLS, mobile
apps). Enforce hybrid mode (classical + PQC) to maintain interoperability.
- Phase 4-Deprecation & Audit: Remove legacy algorithms once PQC coverage is
verified. Conduct third-party audits to confirm compliance.
 -->

b. Interoperability testing and validation frameworks
<!-- 
Interoperability Testing & Validation Frameworks
Interoperability testing verifies that different implementations of PQC schemes can
communicate correctly under real-world conditions. NIST SP 1800-38C provides a
Performance and Interoperability Workstream, which includes test harnesses, sample
configurations, and failure-mode analyses [3]. FIPS 140-3 validation under the CMVP certifies
that cryptographic modules adhere to defined security and physical protection requirements [4].
Together, these frameworks reduce deployment risk by catching integration issues-such as
mismatched parameter sets or message-size overflows-early in the process.
- Test Vector Validation: Use the official NIST PQC Test Vector Packages to ensure each
implementation produces the correct ciphertext, shared secret, or signature for given
inputs.
- Protocol Interoperability: Execute hybrid TLS handshakes combining classical (e.g.,
X25519) and PQC KEMs (e.g., Kyber). Record handshake success rates, round-trip times, and fallback behaviors.
- Module Certification: Submit hardware and software modules incorporating PQC to
FIPS 140-3 testing labs. Validate logical interfaces, state management, and side-channel
resistance.
 -->
c. Training & operational readiness
<!-- 
Training & Operational Readiness
People are the linchpin in a successful PQC migration. NIST SP 800-50 and SP 800-16 offer
guidance on creating role-based training programs, from executive briefings to deep-dive labs
for cryptographic engineers [5][6]. For PQC specifically, curricula should cover algorithm
principles, parameter choices (e.g., security levels), library integrations (e.g., OpenSSL,
BoringSSL PQC forks), and incident response procedures for cryptographic failures.
- Executive Awareness: Workshops that explain the quantum threat, migration timelines,
and business impacts-ensuring leadership buy-in.
- Technical Deep Dives: Hands-on sessions where engineers implement PQC KEM and
signature APIs, troubleshoot integration errors, and benchmark performance.
- Operational Playbooks: Create runbooks detailing PQC key generation, rotation
schedules, backup procedures, and rollback steps.
- Incident Response Drills: Simulate cryptographic failures (e.g., deprecated algorithm
use) and practice recovery workflows.
 -->

(preparation-steps)=
## ขั้นตอนการเตรียมความพร้อม
โดยมีแนวปฏิบัติการเตรียมความพร้อมมีขั้นตอนการดำเนินงานโดยสังเขป ดังนี้

1. จัดทำแผนงาน : กำหนดบุคลากรที่มีความรู้ความสามารถให้ดำเนินการพัฒนาแผนงาน (Roadmap) เพื่อการเตรียมความพร้อมขององค์กรต่อภัยคุกคามจากคอมพิวเตอร์ควอนตัม โดยบุคลากรที่เหมาะสมต่อการพัฒนาแผนงานไม่จำเป็นต้องมีความเชี่ยวชาญด้านเทคโนโลยีควอนตัม ทั้งนี้ การเริ่มต้นจัดทำแผนงานแต่เนิ่น ๆ จะช่วยทำให้กระบวนการเปลี่ยนแปลงเทคโนโลยีมีความราบรื่น อีกทั้งทำให้องค์กรสามารถประเมินค่าใช้จ่ายที่ต้องใช้ในการลงทุน

2. เสริมสร้างความตระหนักรู้ : ดำเนินการศึกษาเทคโนโลยีที่เกี่ยวข้อง รวมถึงเสริมสร้างความตระหนักรู้เกี่ยวกับภัยคุกคามจากคอมพิวเตอร์ควอนตัมให้แก่บุคลากรในแผนกต่าง ๆ ขององค์กร เช่น การให้ความรู้ความเข้าใจแก่แผนกฝ่ายจัดซื้อจัดจ้าง เพื่อให้เจ้าหน้าที่ที่เกี่ยวข้องเลือกใช้ซอฟต์แวร์หรือฮาร์ดแวร์ที่มีข้อกำหนดด้านความปลอดภัยต่อการโจมตีโดยคอมพิวเตอร์ควอนตัม

3. กำหนดหน้าที่ความรับผิดชอบ : มอบหมายความรับผิดชอบให้กับเจ้าหน้าที่ในแต่ละส่วนงานที่เกี่ยวข้องกับการเตรียมความพร้อม ทั้งนี้ ม้ว่าองค์กรจะไม่ได้พัฒนาระบบซอฟต์แวร์ของตนเอง บุคลากรขององค์กรควรมีความรู้ความเข้าใจเกี่ยวกับเทคโนโลยีระบบรหัสลับที่องค์กรของตนเลือกใช้

4. จัดทำรายการสินทรัพย์ทางสารสนเทศ : จัดทำรายการสินทรัพย์ทางสารสนเทศ (IT asset inventory) มีความเกี่ยวข้องกับระบบรหัสลับ โดยตรวจสอบและจัดทำรายการสำหรับสินทรัพย์ที่เป็นทั้งซอฟต์แวร์และฮาร์ดแวร์ พื่อทำความเข้าใจว่าองค์กรมีการใช้เทคโนโลยีระบบรหัสลับอย่างไร เช่น ศึกษาว่ากุญแจเข้ารหัสลับถูกสร้าง จัดเก็บ และ ใช้งานอย่างไรบ้างในปัจจุบัน

5. ประเมินความเหมาะสมของเทคโนโลยีตัวเลือก : ประเมินความเหมาะสม ประสิทธิภาพรวมถึงข้อดีและข้อเสียในการประยุกต์ใช้เทคโนโลยีประเภท PQC หรือ QKD กับระบบสารสนเทศภายในองค์กร ตามความเหมาะสมกับองค์ประกอบของระบบที่แตกต่างกัน ทั้งนี้ องค์กรอาจเตรียมประยุกต์ใช้ระบบความปลอดภัยแบบผสม (Hybrid Security Approach) ซึ่งอาจผสมผสานทั้งระบบรหัสลับแบบดั้งเดิมและ PQC

6. ทำการทดลองและทดสอบ : แม้ว่า ในปัจจุบันมาตรฐานเกี่ยวกับ PQC และ QKD ยังอยู่ในระหว่างการพัฒนา องค์กรสามารถเริ่มต้นดำเนินการทดลองและทดสอบระบบและเทคโนโลยีที่เกี่ยวข้อง ได้เลย เพื่อเตรียมความพร้อมสำหรับการเปลี่ยนแปลงระบบสารสนเทศในอนาคต ทั้งนี้ การดำเนินการทดลอง และทดสอบดังกล่าว จะช่วยเสริมสร้างความรู้ความเข้าใจให้องค์กรเกี่ยวกับเทคโนโลยีที่ควรนำมาประยุกต์ใช้ และปัญหาที่อาจเกิดขึ้นจากการปรับเปลี่ยนระบบรหัสลับในระบบสารสนเทศขององค์กร

7. ติดตามความก้าวหน้าอย่างต่อเนื่อง : ติดตามความก้าวหน้าขององค์กรในการเตรียมความพร้อมอย่างต่อเนื่อง พร้อมทั้งดำเนินการประเมินความเสี่ยงและระยะเวลาก่อนเกิดภัยคุกคามใหม่เป็นระยะ

## แนวทางการสื่อสารเพื่อสร้างความตระหนักรู้ภายในองค์กร
การเตรียมองค์กรให้มีความพร้อมต่อภัยคุกคามจากคอมพิวเตอร์ควอนตัมต้องอาศัยความร่วมมือจากเจ้าหน้าที่ในทุกระดับภายในองค์กร ตั้งแต่ ผู้บริหารระดับสูง ผู้จัดการ จนไปถึงเจ้าหน้าที่ระดับปฏิบัติการ เนื่องจากว่าการเปลี่ยนแปลงระบบรหัสลับภายในองค์กรอาจส่งผลกระทบต่อการทำงานของระบบสารสนเทศ ทั้งหมดภายในองค์กร ดังนั้น เจ้าหน้าที่ที่ได้รับมอบหมายให้ผู้นำเตรียมความพร้อมและเปลี่ยนแปลงระบบขององค์กร ควรดำเนินการสื่อสารและสร้างความตระหนักรู้เกี่ยวกับภัยคุกคามจากคอมพิวเตอร์ควอนตัมให้กับเจ้าหน้าที่ในองค์กรทุกภาคส่วน

การสื่อสารและสร้างความตระหนักรู้มีแนวทางโดยสังเขป สามารถสรุปใน {numref}`org-preparation` {cite:p}`qrwg2021canadian` ดังนี้

- ผู้บริหารระดับสูง : ควรจัดเตรียมข้อมูลที่เกี่ยวข้องกับการกำหนดนโยบายขององค์กร เพื่อให้ผู้บริหารระดับสูงมีความรู้ความเข้าใจถึงภัยคุกคามจากคอมพิวเตอร์ควอนตัมที่อาจเกิดขึ้นในอนาคต และสามารถตัดสินใจเพื่อวางนโยบายเกี่ยวกับการพัฒนาและปรับเปลี่ยนระบบสารสนเทศสนเทศขององค์กร ทั้งในด้านการจัดสรรทรัพยากรบุคคลงบประมาณการลงทุนการจัดซื้อจัดจ้างซอฟต์แวร์และฮาร์ดแวร์ขององค์กร เป็นต้น

- เจ้าหน้าที่ระดับผู้จัดการ : ควรจัดเตรียมข้อมูลเชิงกลยุทธ์รวมถึงกำหนดข้อเสนอแนะการเตรียมความพร้อมให้แก่เจ้าหน้าที่ระดับผู้จัดการ ให้มีความรู้ความเข้าใจถึงภัยคุกคามจากคอมพิวเตอร์ควอนตัม ทำให้สามารถจัดระดับความสำคัญในการเตรียมความพร้อม บริหารจัดการระบบงาน รวมถึงนำนโยบายของผู้บริหารระดับสูงมาปฏิบัติใช้ได้อย่างมีประสิทธิภาพ

- เจ้าหน้าที่ระดับปฏิบัติการ : ควรจัดเตรียมแนวปฏิบัติเชิงเทคนิคให้แก่เจ้าหน้าที่ระดับปฏิบัติการที่เกี่ยวข้องกับเทคโนโลยีสารสนเทศและความมั่นคงปลอดภัยทางไซเบอร์เพื่อให้สามารถดำเนินการเปลี่ยนแปลงซอฟต์แวร์และฮาร์ดแวร์ขององค์กรให้ทันสมัยมีความปลอดภัยต่อการโจมตีจากทั้งคอมพิวเตอร์ในปัจจุบันและคอมพิวเตอร์ควอนตัมในอนาคต

```{figure} ../figures/org-preparation.png
---
name: org-preparation
---
เตรียมความพร้อมสำหรับยุคควอนตัมในระดับองค์กร
```

## การจัดทำแผนและ Roadmap 

## การจัดเตรียมบุคลากร
- PQ Champion
- Task force

## Compliance Guidance
Ref. NIST Crypto Framework 2.0

<!-- 
Continuous Monitoring, Evaluation & Governance
Cryptographic risk is dynamic: new attacks, algorithm deprecations, or implementation flaws
can emerge at any time. Embedding continuous monitoring and governance processes ensures
the cryptographic estate remains robust. NIST CSF 2.0’s “Detect” and “Respond” functions
mandate automated alerts for deprecated algorithm usage, performance anomalies, and
validation failures [9]. FIPS 140-3 revalidation cycles and ISO/IEC 27002’s control A.12.6.1 on
technical review of applications reinforce the necessity of recurring audits.
- Automated Alerts: Integrate cryptographic module logs into SIEM systems and set
alerts for deprecated algorithm calls or failed certificate validations.
- Performance Baselines: Maintain metrics on encryption/decryption latencies, error
rates, and resource consumption. Investigate significant deviations.
- Vulnerability Assessments: Schedule annual third-party penetration tests focused on
cryptographic implementations, including side-channel and fault injections.
- Governance Board Reviews: Convene a Cryptography Governance Board quarterly to
review audit findings, algorithm roadmaps, incident reports, and update migration plans.
 -->