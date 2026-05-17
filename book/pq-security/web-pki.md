# โครงสร้างพื้นฐานกุญแจสาธารณะสำหรับเว็บ

โครงสร้างพื้นฐานกุญแจสาธารณะสำหรับเว็บ (Web Public Key Infrastructure: Web PKI) คือระบบที่ใช้ในการพิสูจน์ตัวตนและสร้างความเชื่อถือบนอินเทอร์เน็ต โดยอาศัยใบรับรองดิจิทัล (Digital Certificate) เชื่อมโยงกุญแจสาธารณะ (Public Key) เข้ากับตัวตนของเจ้าของ เช่น เว็บไซต์หรือองค์กร Web PKI เป็นรากฐานของโปรโตคอล HTTPS ที่ผู้ใช้งานอินเทอร์เน็ตทุกคนพึ่งพาในการสื่อสารที่ปลอดภัย

การเปลี่ยนผ่านสู่ยุคหลังควอนตัมสำหรับ TLS แบ่งออกเป็นสองส่วน ได้แก่
1. **การสร้างกุญแจรหัสลับร่วมกัน (Key Establishment)** ซึ่งมีความเร่งด่วนสูง เพราะมีความเสี่ยงจาก HNDL
2. **ลายมือชื่อดิจิทัล (Digital Signatures)** ในใบรับรองของ Web PKI เพื่อยืนยันตัวตนของเซิร์ฟเวอร์และรับรองห่วงโซ่ใบรับรอง (Certificate Chain)

การเปลี่ยนแปลงอัลกอริทึมลของ Digital Signatures แม้จะไม่เร่งด่วนเท่า Key Establishment ทว่ามีความท้าทายเชิงเทคนิคมากกว่า เนื่องจากลายมือชื่อแบบ PQC มีขนาดใหญ่กว่าแบบดั้งเดิมอย่างมีนัยสำคัญ ทำให้อาจส่งผลกระทบต่อประสิทธิภาพของ TLS

## ความท้าทายของ Web PKI ในยุคควอนตัม

เมื่อเบราว์เซอร์ (Client) เยี่ยมชมเว็บไซต์หนึ่ง ๆ ผ่าน HTTPS เบราว์เซอร์จะสร้างการเชื่อมต่อกับเซิร์ฟเวอร์ (Server) ของเว็บไซต์นั้นด้วยโพรโทคอล TLS Handshake โดยเซิร์ฟเวอร์จะลงลายมือชื่อในข้อมูลที่ทำการแลกเปลี่ยน (เรียกว่า Transcript) จากนั้นส่ง Certificate Chain ให้กับ Client ประกอบไปด่้วย[ลายมือชื่อดิจิทัลทั้งหมด 5 ลายมือชื่อ และ กุญแจสาธารณะ 2 กุญแจ](https://blog.cloudflare.com/bootstrap-mtc/) {cite:p}`cloudflare2024bootstrapmtc`

```{figure} ../figures/webpki-certificates.png
---
name: webpki-certificates
---
ห่วงโซ่ใบรับรอง (Certificate Chain) ของ Web PKI (ที่มา : [A look at the latest post-quantum signature standardization candidates](https://blog.cloudflare.com/another-look-at-pq-signatures/#how-many-added-bytes-are-too-many-for-tls), Cloudflare, 2024)
```

การเปลี่ยนผ่าน Web PKI ไปสู่ PQC เผชิญกับความท้าทายสำคัญที่เกิดจากขนาดของลายมือชื่อดิจิทัลและกุญแจสาธารณะที่ใหญ่กว่าอัลกอริทึมแบบดั้งเดิมอย่างมีนัยสำคัญ ดังแสดงในตารางต่อไปนี้ {cite:p}`nist2024fips203` {cite:p}`nist2024fips204` {cite:p}`nist2024fips205`

```{table} ขนาดกุญแจสาธารณะและขนาดลายมือชื่อของอัลกอริทึมลายมือชื่อแบบดั้งเดิม (Classical) และ PQC
---
name: signature-algorithms-size
---
| อัลกอริทึมลายมือชื่อ    | ประเภทอัลกอริทึม | ขนาดกุญแจสาธารณะ (bytes) | ขนาดลายมือชื่อ (bytes) |
|-------------------|-------------- |-------------------------|---------------------|
| RSA 2048          | Classical     | 256                     | 256                 |
| RSA 4096          | Classical     | 512                     | 512                 |
| Ed25519           | Classical     | 32                      | 64                  |
| ECDSA P-256       | Classical     | 64                      | 64                  |
| ML-DSA-44         | PQC           | 1,312                   | 2,420               |
| ML-DSA-65         | PQC           | 1,952                   | 3,309               | 
| ML-DSA-87         | PQC           | 2,592                   | 4,627               | 
| SLH-DSA-SHA2-128s | PQC           | 32                      | 7,856               |
| SLH-DSA-SHA2-128f | PQC           | 32                      | 17,088              |
```

ปัญหาหลักคือขนาดของกุญแจสาธารณและลายมือชื่อของอัลกอริทึมใหม่เหล่านี้ที่ใหญ่กว่าแบบดั้งเดิมอย่างมาก ยกตัวอย่างเช่น ML-DSA-44 ซึ่งเป็นหนึ่งในอัลกอริทึม PQC ที่มีประสิทธิภาพสูงที่สุดที่ เปรียบเทียบกับ ECDSA P-256 ซึ่งลายมือชื่อแบบดั้งเดิมที่ใช้งานอยู่ในปัจจุบัน พบว่ามีขนาดลายมือชื่อและกุญแจสาธารณะเพิ่มขึ้นถึง 38 และ 20 เท่า ตามลำดับ ยิ่งไปกว่านั้น การทำ TLS Handshake หนึ่งครั้งต้องรวมกุญแจสาธารณะและลายมือชื่อหลายรายการ ทำให้มี overhead รวมกันหลายสิบกิโลไบต์ต่อ Handshake ซึ่งจะส่งผลกระทบอย่่างมีนัยสำคัญต่อประสิทธิภาพของ TLS

## Merkle Tree Certificates

Merkle Tree Certificates (MTC) คือรูปแบบใบรับรองใหม่สำหรับ Web PKI ที่ออกแบบมาเพื่อรองรับลายมือชื่อ PQC ที่มีขนาดใหญ่ แนวคิดหลักคือแทนที่จะลงนามใบรับรองแต่ละใบแยกกัน CA จะรวบรวมใบรับรองเป็น Batch แล้วลงนามเพียงครั้งเดียวที่ Root Hash ของ Merkle Tree เซิร์ฟเวอร์ส่งเพียง Merkle Inclusion Proof ขนาดเล็กแทนลายมือชื่อ PQC เต็มหลายรายการ ทำให้ข้อมูลต่อ TLS Handshake ลดลงอย่างมีนัยสำคัญ

MTC กำลังถูกพัฒนาร่าง [draft-ietf-plants-merkle-tree-certs](https://datatracker.ietf.org/doc/draft-ietf-plants-merkle-tree-certs/) ภายใต้ Working Group [PKI, Logs, And Tree Signatures (PLANTS)](https://datatracker.ietf.org/wg/plants/about/) ของ Internet Engineering Task Force (IETF)

```{seealso}
- [Cultivating a robust and efficient quantum-safe HTTPS](https://blog.google/security/cultivating-a-robust-and-efficient-quantum-safe-https/) — Google Security Blog
- [Merkle Tree Certificates](https://tweedegolf.nl/en/blog/150/merkle-tree-certificates) — Tweede golf
- [Bootstrapping Merkle Tree Certificates](https://blog.cloudflare.com/bootstrap-mtc/) — Cloudflare Blog
```