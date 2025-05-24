# ประเทศอื่น ๆ

EU Quantum-Safe Europe, U.S. NSTAC

## มาตรฐาน PQC
ถึงแม้ว่าอัลกอริทึม PQC จะถูกเริ่มพัฒนามาตั้งแต่หลายปีก่อนและได้รับการพัฒนาอย่างต่อเนื่อง จนในปัจจุบันมีอัลกอริทึม PQC จำนวนหนึ่งที่ได้รับความสนใจจากผู้เชี่ยวชาญบางกลุ่มและบางองค์กรแต่อัลกอริทึม PQC เหล่านี้ยังคงอยู่ในช่วงการพัฒนาและยังไม่สมบูรณ์เต็มที่ ยังจำเป็นต้องมีการศึกษาเพิ่มเติมและการทดสอบอย่างเข้มงวดจึงจะเชื่อมั่นได้ว่ามีความมั่นคงปลอดภัยและเหมาะกับการใช้งานในสภาพแวดล้อมจริง

หลายองค์กรด้านมาตรฐานและองค์กรด้านความมั่นคงปลอดภัยทั่วโลกได้มีการศึกษา พัฒนาจัดประกวด และออกมาตรฐานและแนวปฏิบัติการใช้อัลกอริทึม PQC เอกสารฉบับนี้ได้รวบรวมสถานะและมุมมองขององค์กรเหล่านี้ต่ออัลกอริทึม PQC ต่าง ๆ ทั้งนี้ สกมช. ไม่ได้สนับสนุนหรือรับรองการใช้งานอัลกอริทึม PQC ใด ๆ ที่กล่าวถึงในเอกสารฉบับนี้มากกว่าอัลกอริทึม PQC อื่น ๆ ที่ไม่ได้กล่าวถึงเพียงแต่ได้นำเสนอเพื่อเป็นข้อมูลตั้งต้นให้ผู้สนใจสามารถไปศึกษาเพิ่มเติมได้ สกมช. มีจุดยืนที่เป็นกลางต่อการเลือกใช้อัลกอริทึม PQC และแนะนำให้ผู้ใช้งานศึกษาคุณลักษณะการใช้งานและข้อจำกัดของแต่ละอัลกอริทึม PQC อย่างถี่ถ้วน เลือกใช้อัลกอริทึมที่สามารถตอบโจทย์ความต้องการได้และเหมาะสมต่อบริบท และควรทดสอบอัลกอริทึมให้รอบด้านก่อนนำไปใช้งานกับระบบในสภาพแวดล้อมจริง

### ประเทศสหรัฐอเมริกา
สถาบันมาตรฐานและเทคโนโลยีแห่งชาติของสหรัฐอเมริกา (The National Institute of Standards and Technology: NIST) กำลังพัฒนามาตรฐานสำหรับอัลกอริทึมประเภท PQC โดยเริ่มดำเนินการพัฒนามาตรฐานตั้งแต่ปี พ.ศ. 2559 โดยในปัจจุบันได้ดำเนินการคัดเลือกอัลกอริทึมมาแล้วทั้งหมด 3 รอบ ซึ่งในแต่ละรอบนั้นทางหน่วยงาน NIST ได้ประเมินคุณสมบัติของแต่ละอัลกอริทึมที่สมัครเข้ารับการคัดเลือก (Candidate Algorithms) เพื่อเปรียบเทียบความปลอดภัยต่อการโจมตีจากทั้งคอมพิวเตอร์แบบดั้งเดิมและแบบควอนตัม รวมถึงการเปรียบเทียบด้านประสิทธิภาพการใช้งาน และปัจจัยอื่น ๆ โดยประกาศผลการคัดเลือกครั้งล่าสุดในวันที่ 5 กรกฎาคม พ.ศ. 2565 และมีแผนในการออกมาตรฐานฉบับสมบูรณ์ในปี พ.ศ. 2567 อัลกอริทึมที่ได้รับการคัดเลือกในรอบที่ 3 ประกอบด้วยอัลกอริทึมสำหรับการแลกเปลี่ยนกุญแจและการเข้ารหัสลับ คือ CRYSTALS-Kyber และอัลกอริทึมสำหรับการลงลายมือชื่อดิจิทัล ได้แก่ CRYSTALS-Dilithium FALCON และ SPHINCS ซึ่งอัลกอริทึมเหล่านี้ถูกนำไปพัฒนาเป็นมาตรฐาน Federal Information Processing Standards (FIPS) สำหรับการใช้งานโดยหน่วยงานรัฐในประเทศ
สหรัฐอเมริกา ได้แก่ 
- FIPS 203 (CRYSTALS-Kyber)
- FIPS 204 (CRYSTAL-Dilithium)
- FIPS 205 (SPHINCS+)

อีกทั้งกำลังดำเนินการคัดเลือกอัลกอริทึมประเภท PQC เป็น [รอบที่ 4](https://csrc.nist.gov/projects/post-quantum-cryptography/round-4-submissions) โดยมีอัลกอริทึม
เพิ่มเติม ได้แก่ 
- BIKE
- Classic McEliece
- HQC
- SIKE

### ประเทศเยอรมนี
BSI ได้แนะนำอัลกอริทึม PQC ที่ส่งสมัครเข้าประกวดในการคัดเลือกของ NIST แต่ให้น้ำหนักการพิจารณาด้านระดับความมั่นคงปลอดภัยมากกว่าด้านประสิทธิภาพในการทำงาน BSI ยังได้แนะนำการใช้ระบบรหัสแบบดั้งเดิมร่วมกับ PQC แต่ลายมือชื่อดิจิทัลที่พัฒนาจากแฮชสามารถใช้งานโดยลำพังได้ถ้ามีการพัฒนาและนำไปใช้ที่มั่นคงปลอดภัย ในรายงาน [TR 02102-1 (2023.1)](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf) BSI ได้แนะนำ FrodoKEM และ Classic McEliece สำหรับการเข้ารหัสลับแบบกุญแจอสมมาตรและการแลกเปลี่ยนกุญแจรหัสลับ
และแนะนำ XMSS และ LMS สำหรับการทำลายมือชื่อดิจิทัล

### ประเทศฝรั่งเศส
สำนักงานความมั่นคงปลอดภัยระบบสารสนเทศแห่งชาติฝรั่งเศส (French National Agency for the Security of Information Systems: ANSSI) แนะนำอัลกอริทึม PQC ที่เข้ารอบสุดท้ายของ NIST โดยใช้พารามิเตอร์ที่ให้ระดับความมั่นคงปลอดภัยสูงที่สุด นอกจากนี้ยังได้แนะนำการใช้ระบบรหัสแบบดั้งเดิมร่วมกับ PQC ในช่วงต้นของการย้ายระบบไปสู่ยุคควอนตัม

### ประเทศจีน
สมาคมวิจัยวิทยาการรหัสลับแห่งชาติจีน (Chinese Association for Cryptologic Research: CACR) สนับสนุนโดย การบริหารระบบรหัสลับแห่งชาติจีน (State Cryptography Administration of China) ได้เปิดรับสมัครการแข่งขันการออกแบบอัลกอริทึมระบบรหัสลับแห่งชาติในปี พ.ศ. 2561 และประกาศผลในปี พ.ศ. 2562 วัตถุประสงค์ในการประกวดครั้งนี้ไม่ได้มุ่งเน้นเพื่อเป็นการพัฒนามาตรฐานระบบรหัสลับ แต่เป็นการซักซ้อมภายในประเทศ มีอัลกอริทึมแบบกุญแจอสมมาตรส่งเข้าประกวด 38 รายการซึ่งถูกออกแบบมาให้ทนทานต่อการโจมตีแบบควอนตัม และมี 11 รายการที่ได้รับรางวัล โดยอัลกอริทึมที่ได้รับรางวัลชนะเลิศ ได้แก่ Aigis สำหรับการเข้ารหัสลับและลายมือชื่อดิจิทัล และ LAC สำหรับการเข้ารหัสลับ

### ประเทศเกาหลีใต้
ศูนย์วิจัยรหัสลับที่ทนทานต่อการโจมตีแบบควอนตัมแห่งประเทศเกาหลี (Korean Quantum Resistant Cryptography Research Center: KpqC Center) ได้จัดการแข่งขันรหัสลับที่ทนทานต่อการโจมตีแบบควอนตัม เพื่อเป็นการยกระดับเทคโนโลยีภายในประเทศด้านรหัสลับที่ทนทานต่อการโจมตีแบบควอนตัมเสริมสร้างศักยภาพการแข่งขัน และสร้างการพัฒนาเทคโนโลยีเชิงรุกโดยการร่วมมือระหว่างภาคอุตสาหกรรมวิชาการ รัฐบาล และสถาบันวิจัย และคัดเลือกอัลกอริทึมรหัสลับสำหรับใช้ภายในประเทศ เริ่มเปิดรับประกวดในช่วงเดือนพฤศจิกายน พ.ศ. 2564 เริ่มพิจารณารอบแรกเดือนธันวาคม พ.ศ. 2565 ซึ่งมีเข้าประกวด 16 รายการ และ [พิจารณารอบที่สองเดือนธันวาคม พ.ศ. 2566](https://www.kpqc.or.kr/competition.html) คัดเลือกเหลือ 4 รายการสำหรับลายเซ็นดิจิทัล และ 4 รายการสำหรับการแลกเปลี่ยนกุญแจรหัสลับ ได้แก่ AIMer, HAETAE, MQ-Sign, NCC-Sign, NTRU+, PALOMA, REDOG, และ SMAUG + TiGER

## มาตรฐานองค์กรระหว่างประเทศ
### ISO
องค์กรระหว่างประเทศว่าด้วยการมาตรฐาน (International Organization for Standardization: ISO) ได้เริ่มดำเนินการพัฒนามาตรฐานด้าน PQC โดยได้จัดตั้งกลุ่มทำงาน ISO/IEC SC 27/WG 2 SD8 ในปี พ.ศ. 2560 มีการดำเนินโครงการ ISO/IEC PWI 19541 และอยู่ระหว่างพัฒนามาตรฐาน ISO/IEC 18033-2:2006/WD Amd 2 โดยมีการพิจารณาเพิ่มอัลกอริทึม PQC ได้แก่ FrodoKEM, NTRU, Classic McEliece และ CRYSTAL-Kyber โดยกฎการโหวตหลักโดยสมาชิก คือ จำนวนอัลกอริทึมควรมีจำนวนน้อยที่สุด โดยให้น้ำหนักกับอัลกอริทึมที่มีลัษณะทางประสิทธิภาพที่แตกต่างกันมากหรือพัฒนาจากหลักการเทคนิคที่แตกต่างกัน และการโหวตเลือกให้ 1 คะแนนต่อ 1 หน่วยงานมาตรฐานของชาติโดยไม่ขึ้นอยู่กับจำนวนผู้แทนเข้าร่วมของแต่ละสมาชิก ให้โหวตเลือกเพื่อประโยชน์ต่อหน่วยงานมาตรฐานของชาติ ปัจจุบันมีสมาชิกเข้าร่วม (Participating Members: P) 58 สมาชิก และสมาชิกสังเกตการณ์ (Observing Members: O) 35 สมาชิก

### IETF
คณะทำงานเฉพาะกิจด้านวิศวกรรมอินเทอร์เน็ต (Internet Engineering Task Force: IETF) ได้มีการจัดตั้งกลุ่มทำงาน [Post-Quantum Use In Protocols (PQUIP) Working Group](https://datatracker.ietf.org/wg/pquip/documents/) เพื่อรองรับวิวัฒนาการของ PQC โดยปรับปรุงโพรโตคอลและเอกสารของ IETF ให้เหมาะสมกับยุคควอนตัม

## Global Landscape of PQC R&D and Regulation 

Active R&D Efforts
- Significant investments in PQC research across Europe, Asia, and Oceania.
- Collaborative projects between governments, academia, and industry driving innovation.

Regulatory Advancements
- Comprehensive regulatory frameworks being established to mandate PQC adoption.
- Alignment with international standards ensuring global interoperability and security.

Key Collaborations
- Participation in international standardization bodies like NIST, ISO, and ETSI.
- Cross-border partnerships enhancing the development and deployment of PQC technologies.

Future Outlook
- Continued investment and collaboration essential for a secure transition to a quantum-safe world.
- Ongoing research and regulatory enhancements to address emerging quantum threats.


## USA 

### PQC R&D Initiatives

National Institute of Standards and Technology (NIST) PQC Standardization
- Leading global efforts in the standardization of PQC algorithms.
- Ongoing evaluation and selection of quantum-resistant algorithms for widespread adoption.

Quantum Economic Development Consortium (QED-C)
- Public-private partnership focusing on advancing quantum technologies, including PQC.
- Collaboration between government agencies, academia, and industry leaders.

Key Research Institutions
- MIT Lincoln Laboratory: Researching advanced PQC algorithms and their implementation.
- Stanford University: Pioneering research in quantum-resistant cryptographic methods.
- DARPA (Defense Advanced Research Projects Agency): Funding innovative PQC projects to enhance national security.

### PQC Regulatory Framework

Executive Orders and Federal Initiatives
- Executive Order on Ensuring Responsible Development of Digital Assets: Includes directives for adopting PQC in federal systems.
- Federal Information Processing Standards (FIPS): Incorporation of PQC algorithms into FIPS for government use.

National Security Agency (NSA) Guidelines
- Quantum-Resistant Cryptography Standards: Recommendations for implementing PQC in defense and intelligence sectors.
- Secure Communication Protocols: Guidelines for transitioning existing cryptographic systems to quantum-safe alternatives.

Federal Risk and Authorization Management Program (FedRAMP)
- Integration of PQC requirements into cloud security standards for federal agencies.
- Certification processes for quantum-resistant encryption solutions used by government contractors.

### Key Projects & Collaborations 
Project Quantum-Safe Cryptography (QSC)
- Collaborative initiative between NIST, NSA, and leading tech companies to develop and implement PQC solutions.
- Focus on securing critical infrastructure and national security systems against quantum threats.

Public-Private Partnerships
- Intel and IBM Collaborations: Joint research on integrating PQC algorithms into hardware and software solutions.
- Microsoft’s PQC Integration Project: Implementing quantum-resistant encryption in Azure cloud services.

International Collaborations
- NIST and ISO/IEC Partnerships: Contributing to global standardization efforts for PQC.
- Academic Consortia: Partnerships with international universities for research exchange and development of PQC technologies.

## EU

### PQC R&D Initiatives
European Commission’s PQC Standardization
Collaboration with NIST for algorithm standardization.
Funding research consortia focused on quantum-resistant algorithms.
Horizon Europe Projects
Significant funding allocated to multiple PQC-focused projects.
Emphasis on interdisciplinary research combining cryptography, quantum computing, and cybersecurity.
Key Institutions Involved
European Cybersecurity Agency (ENISA)
EU-funded research universities and technology institutes.

### PQC Regulatory Framework
EU Cybersecurity Act
- Integration of PQC standards into the EU-wide cybersecurity strategy.
- Establishment of the European Cybersecurity Certification Framework with quantum-safe criteria.

Digital Finance Strategy
- Mandates PQC implementation for financial institutions to ensure data integrity and security.
- GDPR and Data Protection
- Encourages adoption of quantum-resistant encryption to enhance data protection measures.

### Key Projects & Collaborations
PQCRYPTO Project
- Developing and testing quantum-resistant cryptographic protocols.
- Collaboration between academia, industry, and government bodies.

Quantum-Safe Europe Initiative
- Fostering a secure digital single market through PQC adoption.
- Partnerships with international standardization organizations like ISO and ETSI.

## China
### PQC R&D Initiatives

National Quantum Laboratory
- Leading research center dedicated to quantum-safe cryptography.
- Development of proprietary PQC algorithms for national security.

Chinese Academy of Sciences (CAS)
- Extensive research programs on quantum-resistant encryption methods.
- Collaboration with universities and tech companies to advance PQC technologies.

Key Research Institutions
- Tsinghua University’s Quantum Information Science Program.
- Shanghai Institute of Microsystem and Information Technology (SIMIT).

### PQC Regulatory Framework
Cybersecurity Law of the People’s Republic of China
- Mandates adoption of quantum-resistant encryption for critical infrastructure sectors.
- Requirements for data localization and secure data transmission using PQC standards.

National Standards Development
- Establishment of national PQC standards to ensure uniform implementation across industries.
- Collaboration with international bodies to align with global PQC protocols.

Government Initiatives
- State-backed funding for PQC research and development.
- Incentives for private sector adoption of quantum-safe technologies.

### Key Projects & Collaborations
Quantum Computing and PQC Integration Project
- Joint venture between government and leading tech firms like Huawei and Alibaba.
- Focus on integrating PQC into existing communication and financial systems.

International Collaborations
- Partnerships with global research institutions to exchange knowledge and advance PQC standards.
- Participation in international standardization efforts to influence global PQC protocols.

## Japan 
### PQC R&D Initiatives
National Institute of Information and Communications Technology (NICT)
- Leading development of quantum-resistant cryptographic algorithms.
- Conducting extensive testing and validation of PQC solutions.

Quantum Cryptography Projects
- Collaborative projects between academia (e.g., University of Tokyo) and industry leaders.
- Focus on practical implementation of PQC in telecommunications and financial services.

Key Research Areas
- Lattice-based cryptography
- Code-based and hash-based cryptographic schemes

### PQC Regulatory Framework
Basic Act on Cybersecurity
- Guidelines for implementing PQC in public and private sectors.
- Emphasis on protecting critical information infrastructure with quantum-safe methods.

Standards Framework
- Development of national standards aligned with international protocols (e.g., ISO/IEC).
- Regulatory incentives for early adoption of PQC technologies.

Government Policies
- Funding and grants for organizations adopting PQC.
- Public-private partnerships to accelerate PQC integration.

### Key Projects & Collaborations
Quantum-Safe Network Initiative
- Developing a nationwide quantum-safe communication network.
- Collaboration between NICT, major telecom providers, and financial institutions.

International Standardization Efforts
- Active participation in ISO and ITU working groups on PQC.
- Hosting international conferences and workshops to lead global PQC discussions.


## Canada 
### PQC R&D Initiatives
Communications Security Establishment (CSE)
- Leading national research in quantum-resistant cryptography.
- Development of advanced PQC algorithms for government and critical infrastructure.

University Collaborations
- Partnerships with institutions like the University of Waterloo and University of Toronto.
- Joint research projects focused on lattice-based and multivariate cryptographic schemes.

Key Research Centers
- Institute for Quantum Computing (IQC) at the University of Waterloo.
- Vector Institute for Artificial Intelligence’s involvement in PQC research.

### PQC Regulatory Framework
Digital Charter Implementation Act
- Promotes adoption of PQC for enhanced data protection and privacy.
- Establishes guidelines for quantum-safe encryption in digital services.

National Cyber Security Strategy
- Emphasizes transition to quantum-resistant encryption across all sectors.
- Provides funding and support for organizations implementing PQC solutions.

Regulatory Standards
- Development of national standards in collaboration with international bodies.
- Certification programs for PQC compliance in critical industries.

### Key Projects & Collaborations
Quantum-Safe Canada Initiative
- National project aimed at integrating PQC into government and private sector systems.
- Collaboration between Communication Security Establishment (CSE), academia, and industry partners.

International Partnerships
- Engagement with global PQC standardization efforts through organizations like NIST and ISO.
- Joint research projects with international universities and tech companies to advance PQC technologies.

## United Kingdom 
### PQC R&D Initiatives
UK National Quantum Technologies Programme
- Comprehensive program focused on developing and deploying PQC solutions.
- Funding for research in quantum-safe algorithms and their practical applications.

Academic Research
- Leading universities such as Cambridge and Oxford spearheading innovative PQC projects.
- Collaborative research centers dedicated to quantum information science and cryptography.

Key Research Areas
- Quantum key distribution (QKD)
- Lattice-based and code-based cryptographic schemes

### PQC Regulatory Framework
National Cyber Security Centre (NCSC) Guidelines
- Recommendations for PQC adoption in critical systems and infrastructure.
- Guidelines for transitioning existing cryptographic systems to quantum-safe alternatives.

Regulatory Frameworks
- Alignment of national standards with international PQC protocols (e.g., ISO/IEC).
- Certification and compliance requirements for organizations implementing PQC.

Government Policies
- Incentives for businesses to adopt PQC technologies.
- Public funding for PQC research and development initiatives.

### Key Projects & Collaborations
Quantum-Safe Infrastructure Project
- Developing a secure, quantum-resistant national digital infrastructure.
- Collaboration between NCSC, academia, and key industry stakeholders.

International Collaborations
- Active participation in global PQC standardization through ISO and NIST partnerships.
- Hosting international workshops and conferences to drive global PQC adoption.

## Australia 
### PQC R&D Initiatives
Australian Centre for Quantum Computation and Communication Technology (CQC2T)
- Leading research center focused on PQC and quantum-safe technologies.
- Development of advanced cryptographic protocols resistant to quantum attacks.

Industry Partnerships
- Collaborations with major tech firms like Telstra and Atlassian on PQC projects.
- Joint research initiatives with universities such as the University of Sydney and ANU.

Key Research Areas
- Post-quantum algorithms (lattice-based, hash-based, etc.)
- Quantum key distribution (QKD) and secure communication protocols

### PQC Regulatory Framework
Cyber Security Strategy
- Integration of PQC requirements for government agencies and essential services.
- Policies promoting adoption of quantum-safe encryption across all sectors.

Standards Australia
- Development of national standards for PQC implementation aligned with international protocols.
- Certification processes for PQC-compliant products and services.

Government Initiatives
- Funding programs to support organizations transitioning to PQC.
- Public awareness campaigns on the importance of quantum-safe cryptography.

### Key Projects & Collaborations
Quantum-Safe Communications Project
- Developing and deploying PQC in national telecommunications infrastructure.
- Collaboration between CQC2T, industry partners, and government bodies.

International Partnerships
- Engagement with global PQC standardization efforts through ISO and NIST.
- Joint research projects with international universities and tech companies to advance PQC technologies.

## South Korea
### PQC R&D Initiatives
KRISS Quantum Cryptography Research
- Leading national efforts in developing and testing PQC algorithms.
- Focus on creating quantum-resistant solutions for national security applications.

Collaborative Projects
- Joint ventures between government agencies and private sector companies like Samsung and LG.
- Research partnerships with top universities such as KAIST and Seoul National University.

Key Research Areas
- Lattice-based and code-based cryptographic schemes
- Quantum key distribution (QKD) and secure communication protocols

### PQC Regulatory Framework
National Cybersecurity Strategy
- Mandates adoption of PQC to protect digital infrastructure and critical systems.
- Establishes guidelines for transitioning existing cryptographic systems to quantum-safe alternatives.

Standards Development
- Establishment of national PQC standards aligned with global best practices.
- Collaboration with international standardization bodies like ISO and ETSI.

Government Policies
- Funding and incentives for organizations implementing PQC technologies.
- Public-private partnerships to accelerate PQC adoption across industries.

### Key Projects & Collaborations
Quantum-Safe National Network Project
- Developing a secure, quantum-resistant national communication network.
- Collaboration between KRISS, major telecom providers, and government agencies.

International Collaborations
- Active participation in global PQC standardization efforts through ISO and NIST.
- Joint research initiatives with international universities and tech companies to advance PQC technologies.
