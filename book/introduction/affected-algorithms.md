# อัลกอริทึมระบบรหัสลับที่ได้รับผลกระทบจากคอมพิวเตอร์ควอนตัม

มาตรฐานระบบรหัสลับสำหรับยุคควอนตัม (Post-Quantum Cryptography: PQC) ซึ่งจะถูกนำมาใช้แทนที่ระบบรหัสลับแบบกุญแจอสมมาตร (Asymmetric Key Cryptography) ที่มีการใช้งานอย่างแพร่หลายในปัจจุบัน รวมถึง การลงลายมือชื่อดิจิทัล (Digital Signature) และ การสร้างกุญแจรหัสลับร่วมกัน (Key Establishment) {cite:p}`nist2024ir8547`

## อัลกอริทึมการลงลายมือชื่อดิจิทัล
การลงลายมือชื่อดิจิทัลเป็นอัลกอริทึมระบบรหัสลับที่มีการใช้งานหลากหลายรูปแบบ รวมถึงการยืนยันตัวตน (Identity Authentication) การยืนยันความถูกต้องและความสมบูรณ์ของข้อมูล (Integrity Authentication) การยืนยันแหล่งที่มาของข้อมูล (Source Authentication) อีกทั้งมีคุณสมบัติห้ามการปฏิเสธความรับผิด (Non-repudiation) และสามารถใช้ลายมือชื่อดิจิทัล แทนการลงลายมือชื่อที่กฎหมายรองรับ ตามมาตรา 26 แห่ง พรบ. ว่าด้วยธุรกรรมทางอิเล็กทรอนิกส์ พ.ศ. 2544 และที่แก้ไขเพิ่มเติม

ทั้งนี้ อัลกอริทึมการลงลายมือชื่อดิจิทัลที่มีการใช้อย่างแพร่หลายในปัจจุบันล้วนมีความเสี่ยงถูกโจมตีการคอมพิวเตอร์ควอนตัมประเภท Shor’s Algorithm รวมถึง อัลกอริทึมระบบรหัสดังต่อไปนี้
- RSA ตามมาตรฐาน [RFC 8017](https://datatracker.ietf.org/doc/html/rfc8017) , [PKCS 1 เวอร์ชัน 1.5](https://datatracker.ietf.org/doc/html/rfc3447)
- เส้นโค้งเชิงวงรี (Elliptic Curve Digital Signature Algorithm: ECDSA) ตามมาตรฐาน [ISO/IEC 14888-3](https://www.iso.org/standard/76382.html) และ [SEC2](https://www.secg.org/sec2-v2.pdf)  เป็นต้น 
- Edwards-Curve Digital Signature Algorithm (EdDSA) ตามมาตรฐาน [RFC 8032](https://datatracker.ietf.org/doc/html/rfc8032)

โดยมาตรฐาน [FIPS 204](https://csrc.nist.gov/pubs/fips/204/final) และ [FIPS 205](https://csrc.nist.gov/pubs/fips/205/final) ระบุอัลกอริทึมการลงลายมือชื่อดิจิทัลที่ทนทานต่อการโจมตีจากคอมพิวเตอร์ควอนตัม โดย FIPS 204 ระบุ Module-Lattice-Based Digital Signature Algorithm (ML-DSA) ซึ่งพัฒนามาจากการอัลกอริทึม [CRYSTALS-Dilithium](https://pq-crystals.org/dilithium/index.shtml)  ในขณะที่ FIPS 205 ระบุ Stateless Hash-Based Digital Signature Algorithm (SLH-DSA) ซึ่งพัฒนามาจากการเสนอ [SPHINCS+](https://sphincs.org/)

## อัลกอริทึมการสร้างกุญแจรหัสลับร่วมกัน
การสร้างกุญแจรหัสลับร่วมกัน (Key Establishment) คือกระบวนการที่ใช้ในการสร้างและส่งมอบกุญแจรหัสลับให้แก่หน่วยงานที่ได้รับอนุญาตให้ใช้งานกุญแจดังกล่าว โดยในปัจจุบันมาตรฐานอัลกอริทึมการสร้างกุญแจรหัสลับร่วมกัน มีความปลอดภัยตั้งอยู่บนปัญหาทางคณิตศาสตร์ประเภท Discrete Logarithm Problem เช่น ระบบรหัสลับแบบเส้นโค้งวงรี (Elliptic Curve Cryptography) และ การแยกตัวประกอบจำนวนเต็ม (Integer Factorization) เช่น  ระบบรหัสลับประเภท RSA

FIPS 203 ระบุระบบรหัสลับที่เรียกว่า Module-Lattice-Based Key-Encapsulation Mechanism (ML-KEM) ซึ่งพัฒนามาจากการอัลกอริทึม CRYSTALS-KYBER สำหรับ Key-Encapsulation Mechanism (KEM)

โดย NIST กำลังดำเนินกระบวนการกำหนดมาตรฐานระบบรหัสลับสำหรับยุคควอนตัม (NIST PQC Standardization Process) เพื่อเป็นตัวเลือกเพิ่มเติมเพื่อเป็นทางเลือกเสริมให้กับ ML-KEM ในอนาคต

## อัลกอริทึมระบบรหัสลับแบบกุญแจสมมาตร 
อัลกอริทึมระบบรหัสลับแบบกุญแจสมมาตร (Symmetric-Key Algorithms) ใช้กุญแจรหัสลับเดียวกันในการเข้ารหัสลับและถอดรหัสลับ โดยมีมาตรฐานในการใช้งานที่หลากหลาย เช่น 
- การเข้ารหัสลับแบบบล็อกไซเฟอร์ (Block Cipher) เช่น Advanced Encryption Standard (AES)
- ฟังก์ชันแฮช (Hash functions)
- รหัสการยืนยันความถูกต้องของข้อมูล (Data Authentication) ด้วยบล็อกไซเฟอร์
- รหัสการยืนยันความถูกต้องของข้อความ (Message Authentication Code - HMAC)
- การสร้างกุญแจใหม่ (Key Derivation) จากกุญแจข้อมูลความลับ
- การเข้ารหัสกุญแจ (Key wrapping)
- การสร้างเลขสุ่ม (Random Bit Generation)

ทั้งนี้ มาตรฐานอัลกอริทึมระบบรหัสลับแบบกุญแจสมมาตร_มีความเสี่ยงต่อการถูกโจมตีโดยคอมพิวเตอร์ควอนตัมน้อย_ จึงยังไม่มีความจำเป็นต้องเปลี่ยยนแปลงมาตรฐานเหล่านี้ในกระบวนการเตรียมความพร้อมสำหรับยุคควอนตัม
