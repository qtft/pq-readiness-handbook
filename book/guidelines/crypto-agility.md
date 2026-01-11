# Cryptographic Agility

องค์กรควรพิจารณาปรับปรุงระบบสารสนเทศขององค์กรให้มีความยืดหยุ่นรองรับการปรับเปลี่ยนอัลกอริทึมระบบรหัสลับ โดยมีความสอดคล้องตามหลักการความคล่องตัวระบบรหัสลับ (Crypto Agility) ซึ่งหมายถึง การที่ระบบรักษาความปลอดภัยสามารถปรับเปลี่ยนอัลกอริทึมระบบรหัสลับให้มีความทันสมัยได้อย่างรวดเร็ว หลักการนี้มีความสำคัญอย่างยิ่งในการเตรียมตัวเข้าสู่ยุคควอนตัมในอนาคตการจะปฏิบัติตามหลักการนี้ไม่ใช่เพียงการออกแบบและพัฒนาให้ระบบและโพรโทคอลมีความคล่องตัว แต่จะต้องมีมาตรฐานอัลกอริทึม PQC ที่พัฒนาจากปัญหาที่ยากแบบต่าง ๆ เพื่อเป็นตัวเลือกที่หลากหลายตัวเลือกของอัลกอริทึมที่หลากหลายเหล่านี้ยังเป็นประโยชน์ต่อการใช้งานที่มีความต้องการด้านประสิทธิภาพและความมั่นคงปลอดภัยที่แตกต่างกัน ทั้งนี้ อัลกอริทึม PQC ยังไม่ได้อยู่ในสภาวะที่สมบูรณ์เต็มที่และยังจำเป็นที่จะต้องได้รับการพัฒนาต่อยอด ทดสอบ และผ่านบทพิสูจน์อีกมากมาย บางอัลกอริทึม PQC ในปัจจุบันอาจถูกค้นพบจุดอ่อนหรือช่องโหว่ที่ทำให้ไม่มีความมั่นคงปลอดภัยจากการศึกษาเพิ่มเติมในอนาคต เช่น SIKE ที่ได้รับการประเมินหลายปีโดย NIST จนกระทั่งเดือนสิงหาคม พ.ศ. 2565 จึงค้นพบว่ามีปัญหาด้านความมั่นคงปลอดภัย ดังนั้นอัลกอริทึมที่ใช้ในระบบควรที่จะสามารถถูกสับเปลี่ยนทดแทนได้อย่างคล่องตัวและรวดเร็ว

<!-- 
Crypto-agility is the organization’s ability to switch cryptographic algorithms and parameters
quickly in response to new vulnerabilities or standards updates. NIST SP 800-57 Part 3 and IR
8417 outline architecture patterns-such as abstraction layers, policy engines, and key
envelopes-that decouple application logic from specific algorithms [7][8]. The emerging NIST
Cybersecurity Framework 2.0 embeds cryptography within its “Protect", “Detect” and “Respond”
functions, emphasizing continuous algorithm review and replacement mechanisms [9].
International standards-ISO/IEC 27001 (control A.10.1.2) and ENISA’s Crypto-Agility
Guidelines-similarly mandate planning for algorithm migration and modular cryptographic
implementations.

- Abstraction Layers: Implement cryptographic service providers (CSPs) or
crypto-service APIs that expose generic interfaces (encrypt, decrypt, sign, verify), hiding
algorithm-specific details.
- Policy Engines: Store algorithm preferences and parameter roll-out schedules in
external policy files or configuration databases to avoid code changes for algorithm
swaps.
- Key Envelopes: Wrap data-encryption keys (DEKs) with key-encryption keys (KEKs)
bound to specific algorithms-simplifying bulk re-encryption when KEK algorithms change.
- Vendor Requirements: Include crypto-agility capabilities in procurement contracts and
require timely firmware or library updates to support new algorithms.
 -->