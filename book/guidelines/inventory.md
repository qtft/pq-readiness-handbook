# แนวทางการจัดทำรายการสินทรัพย์ทางสารสนเทศ

การจัดทำรายการสินทรัพย์ทางสารสนเทศ (IT Asset Inventory) ซึ่งเป็นขั้นตอนที่ 4 ใน {ref}`preparation-steps` อาจถือได้ว่าเป็นขั้นตอนที่ซับซ้อนและสำคัญที่สุดในการเตรียมความพร้อมขององค์กร เนื่องจากองค์กรไม่สามารถวางแผนเปลี่ยนผ่านระบบที่ตนเองไม่ทราบว่ามีอยู่ได้ ด้วยเหตุนี้ หน่วยงานของรัฐบาลกลางสหรัฐอเมริกาจึงถูกกำหนดให้จัดทำและส่งรายการระบบที่ใช้ระบบรหัสลับที่มีความเปราะบางต่อคอมพิวเตอร์ควอนตัมเป็นประจำทุกปีตามบันทึก M-23-02 ของสำนักงานบริหารและงบประมาณ (Office of Management and Budget: OMB) {cite:p}`omb2022m2302`

การจัดทำรายการสินทรัพย์ทางสารสนเทศเพื่อเตรียมความพร้อมต่อการโจมตีจากคอมพิวเตอร์ควอนตัมยังให้ผลพลอยได้ คือ ช่วยให้ระบบสารสนเทศขององค์กรมีความมั่นคงปลอดภัยไซเบอร์มากยิ่งขึ้นต่อการโจมตีจากคอมพิวเตอร์ในปัจจุบัน เนื่องจากช่วยให้องค์กรระบุจุดอ่อนหรือช่องโหว่ในระบบรักษาความปลอดภัยที่มีอยู่ เช่น การใช้อัลกอริทึมหรือขนาดกุญแจที่ล้าสมัย และสามารถปรับปรุงระบบได้อย่างมีประสิทธิภาพ

การจัดทำรายการสินทรัพย์ทางสารสนเทศช่วยให้องค์กรจัดลำดับความสำคัญของการเตรียมความพร้อม โดยมีองค์ประกอบสำคัญ 2 ส่วน ได้แก่ รายการสินทรัพย์ข้อมูล (Data Asset Inventory) และรายการสินทรัพย์ระบบรหัสลับ (Cryptographic Asset Inventory) {cite:p}`ncsa2023guidelines`

## การจัดทำรายการสินทรัพย์ข้อมูล (Data Asset Inventory)

องค์กรควรจัดทำรายการข้อมูลที่ใช้งานภายในองค์กร เพื่อให้ทราบประเภท ระดับความสำคัญ และระยะเวลาที่ต้องรักษาความลับของข้อมูลแต่ละประเภท ซึ่งเป็นตัวแปรสำคัญในการประเมินความเสี่ยงจากการโจมตีแบบเก็บเกี่ยวข้อมูลเพื่อถอดรหัสลับในภายหลัง (Harvest Now, Decrypt Later: HNDL) ตามโมเดลของ Mosca (ดู [โมเดลของ Mosca](../situations/mosca.md)) โดยมีปัจจัยที่ต้องระบุและพิจารณา ดังนี้

- ระบุว่าข้อมูลประเภทใดในองค์กรที่มีความสำคัญและต้องรักษาเป็นความลับ
- ระบุข้อมูลที่ต้องรักษาเป็นความลับเป็นระยะเวลานาน เช่น มากกว่า 10 ปี
- ระบุสถานที่ ระบบ หรืออุปกรณ์ที่ใช้จัดเก็บข้อมูลขององค์กร
- ระบุกระบวนการหรือระบบที่ใช้ในการรับส่งและโอนย้ายข้อมูล
- ระบุวิธีการบริหารจัดการการเข้าถึงข้อมูล และวิธีป้องกันการเข้าถึงโดยบุคคลที่ไม่ได้รับอนุญาต

ตัวอย่างรายการสินทรัพย์ข้อมูลแสดงใน {numref}`data-asset-inventory`

```{table} ตัวอย่างรายการสินทรัพย์ข้อมูล (Data Asset Inventory)
---
name: data-asset-inventory
---
| ลำดับ | ชื่อสินทรัพย์ข้อมูล | คำอธิบาย | เจ้าของข้อมูล | ที่จัดเก็บ | ประเภทข้อมูล | ระดับความอ่อนไหว | อายุการรักษาความลับ (Confidentiality Lifetime) | กฎหมายที่เกี่ยวข้อง |
|--|--|--|--|--|--|--|--|--|
| 1 | ข้อมูลลูกค้า (KYC) | ข้อมูลระบุตัวตนลูกค้า | Head of Compliance | Core Banking DB | PII | สูง | 10–15 ปี | PDPA / กฎหมายป้องกันและปราบปรามการฟอกเงิน |
| 2 | สัญญาทางธุรกิจ | สัญญากับคู่ค้า | Legal Department | DMS / Cloud | Confidential | สูง | 10 ปี | ประมวลกฎหมายแพ่งและพาณิชย์ |
| 3 | ข้อมูลบุคลากร | เงินเดือนและประวัติพนักงาน | HR Director | HR System | PII | สูง | 5–10 ปี | PDPA / กฎหมายคุ้มครองแรงงาน |
| 4 | บันทึกธุรกรรม (Transaction Log) | บันทึกธุรกรรมของระบบ | IT Operations | SIEM | Operational | กลาง | 3–5 ปี | ข้อกำหนดของหน่วยงานกำกับดูแล |
| 5 | เอกสารวิจัยและพัฒนา | งานวิจัยและแบบผลิตภัณฑ์ | CTO | Secure File Server | IP | สูงมาก | มากกว่า 15 ปี | กฎหมายทรัพย์สินทางปัญญา |
```

## การจัดทำรายการสินทรัพย์ระบบรหัสลับ (Cryptographic Asset Inventory)

องค์กรควรจัดทำรายการสินทรัพย์ระบบรหัสลับ ซึ่งหมายถึงรายการอัลกอริทึม โพรโทคอล ใบรับรองดิจิทัล กุญแจรหัสลับ และไลบรารีระบบรหัสลับทั้งหมดที่ใช้งานภายในองค์กร เพื่อให้ทราบว่าระบบใดบ้างที่มีความเสี่ยงจากการถูกโจมตีด้วยคอมพิวเตอร์ควอนตัม เช่น โพรโทคอลแลกเปลี่ยนกุญแจที่องค์กรใช้ในปัจจุบัน ซึ่งมีความเสี่ยงต่อการโจมตีแบบ HNDL โดยมีปัจจัยที่ต้องระบุและพิจารณา ดังนี้

- ระบุกระบวนการเข้ารหัสลับและวิธีการรักษาความปลอดภัยของกุญแจรหัสลับ
- ระบุประเภทของอัลกอริทึมระบบรหัสลับและขนาดของกุญแจที่ใช้ในใบรับรองดิจิทัล (Digital Certificate) แอปพลิเคชัน โพรโทคอลการสื่อสาร และระบบเครือข่าย
- ระบุซอฟต์แวร์ขององค์กรที่มีอัลกอริทึมระบบรหัสลับเป็นองค์ประกอบสำคัญ รวมถึงข้อจำกัดของซอฟต์แวร์ในการเปลี่ยนไปใช้อัลกอริทึมอื่น
- ระบุกระบวนการและขั้นตอนที่จำเป็นในการเปลี่ยนซอฟต์แวร์ขององค์กรไปใช้อัลกอริทึมระบบรหัสลับใหม่

เนื่องจากระบบรหัสลับมักฝังอยู่ในหลายชั้นของระบบ ตั้งแต่ซอร์สโค้ด ไลบรารี ระบบปฏิบัติการ อุปกรณ์เครือข่าย ไปจนถึงบริการคลาวด์ การสำรวจด้วยตนเองเพียงอย่างเดียวจึงมักไม่ครบถ้วน องค์กรควรใช้เครื่องมือค้นหาและจัดทำรายการระบบรหัสลับแบบอัตโนมัติ (Automated Cryptography Discovery and Inventory: ACDI) ซึ่งแบ่งได้เป็น 3 กลุ่มหลัก ได้แก่ เครื่องมือวิเคราะห์ซอร์สโค้ดและไบนารีในกระบวนการพัฒนาซอฟต์แวร์ (CI/CD Pipeline) เครื่องมือสแกนระบบและแอปพลิเคชันที่ใช้งานอยู่ และเครื่องมือตรวจสอบบริการและทราฟฟิกบนเครือข่าย {cite:p}`cisa2024acdi,nist2023sp180038b` ตัวอย่างเครื่องมือดังกล่าวจะกล่าวถึงในหัวข้อ [เครื่องมือสำหรับเทคโนโลยี PQC ในปัจจุบัน](../tech-considerations/tools-and-vendors.md)

ตัวอย่างรายการสินทรัพย์ระบบรหัสลับแสดงใน {numref}`crypto-asset-inventory`

```{table} ตัวอย่างรายการสินทรัพย์ระบบรหัสลับ (Cryptographic Asset Inventory)
---
name: crypto-asset-inventory
---
| ลำดับ | ระบบ/แอปพลิเคชัน | Business Function | Crypto Function | Algorithm | Algorithm Family | Key Length | Protocol/Standard | Library/Module | Deployment Location | Data Protected | Exposure | Owner | Key Storage | Key Rotation | Cert Expiry | PQC Vulnerable? | Migration Priority | Notes |
|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|
| 1 | Internet Banking | Online Transaction | Key Exchange | ECDHE | ECC | P-256 | TLS 1.3 | OpenSSL | Cloud | Customer Data | External | IT Sec | HSM | Yearly | 2027 | Yes | High | Public-facing, HNDL risk |
| 2 | VPN Gateway | Secure Tunnel | Encryption | AES-256 | Symmetric | 256 | IPsec (ESP) | StrongSwan | On-Prem | Internal Traffic | Internal | NetOps | HSM | 2 Years | N/A | No | Low | Symmetric safe; IKEv2 key exchange (DH/ECDH) must be listed as a separate, quantum-vulnerable entry |
| 3 | Email Signing | Integrity | Signature | RSA-2048 | RSA | 2048 | S/MIME | MS PKI | Corp IT | Email | External | IT | Software Keystore | 3 Years | 2026 | Yes | High | Long-term trust |
| 4 | Code Signing | Integrity | Signature | RSA-3072 | RSA | 3072 | PKI | SignTool | DevOps | Software | External | DevOps | HSM | 5 Years | 2028 | Yes | Medium | Legacy clients |
```

จากตัวอย่างใน {numref}`crypto-asset-inventory` จะเห็นว่าระบบหนึ่งระบบอาจมีหน้าที่ด้านระบบรหัสลับหลายประเภท เช่น VPN ที่ใช้ AES-256 สำหรับการเข้ารหัสลับข้อมูลซึ่งยังคงปลอดภัย แต่ใช้การแลกเปลี่ยนกุญแจแบบ Diffie-Hellman หรือ ECDH ในโพรโทคอล IKEv2 ซึ่งมีความเปราะบางต่อคอมพิวเตอร์ควอนตัม องค์กรจึงควรบันทึกแต่ละหน้าที่แยกกัน (Key Exchange, Encryption, Signature) เพื่อไม่ให้ประเมินความเสี่ยงต่ำเกินจริง

(cbom)=
## บัญชีรายการวัสดุด้านระบบรหัสลับ (Cryptography Bill of Materials: CBOM)

ผลลัพธ์ของการสำรวจสินทรัพย์ระบบรหัสลับควรจัดเก็บในรูปแบบมาตรฐานที่เครื่องมือต่าง ๆ สามารถแลกเปลี่ยนกันได้ บัญชีรายการวัสดุด้านระบบรหัสลับ (Cryptography Bill of Materials: CBOM) เป็นรูปแบบข้อมูลมาตรฐานสำหรับบันทึกสินทรัพย์ระบบรหัสลับที่อยู่ในซอฟต์แวร์ ระบบ หรือบริการ โดยขยายแนวคิดของบัญชีรายการวัสดุซอฟต์แวร์ (Software Bill of Materials: SBOM) ซึ่งบันทึกเพียงส่วนประกอบและไลบรารีของซอฟต์แวร์ ให้ครอบคลุมถึงอัลกอริทึม ชุดพารามิเตอร์ โพรโทคอล ใบรับรองดิจิทัล และกุญแจรหัสลับที่ส่วนประกอบเหล่านั้นใช้งาน CBOM ถูกบรรจุเป็นส่วนหนึ่งของข้อกำหนด CycloneDX ตั้งแต่รุ่น 1.6 ซึ่งเผยแพร่ในปี ค.ศ. 2024 {cite:p}`cyclonedxcbom`

รายการตรวจสอบแบบตารางเหมาะสำหรับการสื่อสารกับผู้บริหาร แต่มีข้อจำกัดเมื่อองค์กรมีระบบจำนวนมาก CBOM ช่วยแก้ข้อจำกัดดังกล่าว เนื่องจากเครื่องมือค้นหาระบบรหัสลับแบบอัตโนมัติสามารถสร้าง CBOM ได้โดยตรง และองค์กรสามารถรวบรวม CBOM จากหลายระบบ รวมถึง CBOM ที่ได้รับจากผู้ให้บริการ เพื่อนำมาวิเคราะห์ในภาพรวมได้ {cite:p}`cisa2024acdi` นอกจากนี้ องค์กรยังสามารถกำหนดให้ผู้ให้บริการส่งมอบ CBOM พร้อมผลิตภัณฑ์เป็นส่วนหนึ่งของข้อกำหนดการจัดซื้อจัดจ้าง เพื่อลดความเสี่ยงจากห่วงโซ่อุปทาน

ใน CycloneDX สินทรัพย์ระบบรหัสลับแต่ละรายการถูกบันทึกเป็นส่วนประกอบประเภท `cryptographic-asset` และระบุชนิดของสินทรัพย์ผ่านฟิลด์ `assetType` ซึ่งมี 4 ประเภท ดังนี้ {cite:p}`cyclonedxcbom`

- __"อัลกอริทึม (`algorithm`)"__: อัลกอริทึมระบบรหัสลับ พร้อมรายละเอียด เช่น ประเภทพื้นฐาน (`primitive`) ชุดพารามิเตอร์หรือเส้นโค้งวงรี สภาพแวดล้อมการทำงาน ระดับการรับรอง และระดับความมั่นคงปลอดภัยแบบดั้งเดิม (`classicalSecurityLevel`) และหมวดหมู่ความปลอดภัยของ NIST ในยุคควอนตัม (`nistQuantumSecurityLevel`) โดยค่า 0 หมายถึงอัลกอริทึมที่มีความเปราะบางต่อคอมพิวเตอร์ควอนตัม
- __"ใบรับรองดิจิทัล (`certificate`)"__: ใบรับรองดิจิทัล พร้อมชื่อเจ้าของ ผู้ออกใบรับรอง ช่วงเวลาที่ใช้งานได้ และอัลกอริทึมที่ใช้ลงลายมือชื่อดิจิทัล
- __"โพรโทคอล (`protocol`)"__: โพรโทคอล เช่น TLS, SSH และ IPsec พร้อมรุ่นของโพรโทคอลและชุดอัลกอริทึม (Cipher Suite) ที่ใช้งาน
- __"วัสดุด้านระบบรหัสลับที่เกี่ยวข้อง (`related-crypto-material`)"__: กุญแจรหัสลับ ความลับร่วม หรือวัสดุอื่น พร้อมสถานะของกุญแจและกลไกที่ใช้ปกป้อง เช่น HSM

{numref}`cbom-example` แสดงตัวอย่าง CBOM ในรูปแบบ JSON สำหรับระบบ Internet Banking ในลำดับที่ 1 ของ {numref}`crypto-asset-inventory` ซึ่งใช้ TLS 1.3 ร่วมกับการแลกเปลี่ยนกุญแจแบบ ECDH บนเส้นโค้ง P-256 (secp256r1) และใบรับรองดิจิทัลที่ลงลายมือชื่อด้วย RSA-2048 โดยกุญแจส่วนตัวจัดเก็บใน HSM

```{code-block} json
:caption: ตัวอย่าง CBOM ตามข้อกำหนด CycloneDX 1.6 สำหรับระบบ Internet Banking
:name: cbom-example

{
  "bomFormat": "CycloneDX",
  "specVersion": "1.6",
  "serialNumber": "urn:uuid:3e671687-395b-41f5-a30f-a58921a69b79",
  "version": 1,
  "metadata": {
    "timestamp": "2026-09-18T09:00:00Z",
    "component": {
      "type": "application",
      "bom-ref": "app/internet-banking",
      "name": "Internet Banking",
      "version": "4.2.0"
    }
  },
  "components": [
    {
      "type": "cryptographic-asset",
      "bom-ref": "crypto/protocol/tls13",
      "name": "TLS",
      "cryptoProperties": {
        "assetType": "protocol",
        "protocolProperties": {
          "type": "tls",
          "version": "1.3",
          "cipherSuites": [
            {
              "name": "TLS_AES_256_GCM_SHA384",
              "algorithms": ["crypto/algorithm/aes-256-gcm", "crypto/algorithm/sha-384"],
              "identifiers": ["0x13", "0x02"]
            }
          ],
          "cryptoRefArray": ["crypto/algorithm/ecdh-p256", "crypto/certificate/ib-server"]
        }
      }
    },
    {
      "type": "cryptographic-asset",
      "bom-ref": "crypto/algorithm/ecdh-p256",
      "name": "ECDH",
      "cryptoProperties": {
        "assetType": "algorithm",
        "algorithmProperties": {
          "primitive": "key-agree",
          "curve": "secp256r1",
          "executionEnvironment": "software-plain-ram",
          "implementationPlatform": "x86_64",
          "cryptoFunctions": ["keygen", "keyderive"],
          "classicalSecurityLevel": 128,
          "nistQuantumSecurityLevel": 0
        }
      }
    },
    {
      "type": "cryptographic-asset",
      "bom-ref": "crypto/algorithm/aes-256-gcm",
      "name": "AES-256-GCM",
      "cryptoProperties": {
        "assetType": "algorithm",
        "algorithmProperties": {
          "primitive": "ae",
          "parameterSetIdentifier": "256",
          "mode": "gcm",
          "executionEnvironment": "software-plain-ram",
          "cryptoFunctions": ["encrypt", "decrypt"],
          "classicalSecurityLevel": 256,
          "nistQuantumSecurityLevel": 5
        }
      }
    },
    {
      "type": "cryptographic-asset",
      "bom-ref": "crypto/algorithm/sha-384",
      "name": "SHA-384",
      "cryptoProperties": {
        "assetType": "algorithm",
        "algorithmProperties": {
          "primitive": "hash",
          "cryptoFunctions": ["digest"],
          "classicalSecurityLevel": 192,
          "nistQuantumSecurityLevel": 4
        }
      }
    },
    {
      "type": "cryptographic-asset",
      "bom-ref": "crypto/algorithm/rsa-2048",
      "name": "RSA-2048",
      "cryptoProperties": {
        "assetType": "algorithm",
        "algorithmProperties": {
          "primitive": "signature",
          "parameterSetIdentifier": "2048",
          "executionEnvironment": "hardware",
          "certificationLevel": ["fips140-3-l3"],
          "cryptoFunctions": ["sign", "verify"],
          "classicalSecurityLevel": 112,
          "nistQuantumSecurityLevel": 0
        }
      }
    },
    {
      "type": "cryptographic-asset",
      "bom-ref": "crypto/certificate/ib-server",
      "name": "ib.example.co.th",
      "cryptoProperties": {
        "assetType": "certificate",
        "certificateProperties": {
          "subjectName": "CN=ib.example.co.th",
          "issuerName": "CN=Example Issuing CA",
          "notValidBefore": "2026-01-15T00:00:00Z",
          "notValidAfter": "2027-01-15T00:00:00Z",
          "signatureAlgorithmRef": "crypto/algorithm/rsa-2048",
          "certificateFormat": "X.509"
        }
      }
    },
    {
      "type": "cryptographic-asset",
      "bom-ref": "crypto/key/ib-server-private",
      "name": "Internet Banking server private key",
      "cryptoProperties": {
        "assetType": "related-crypto-material",
        "relatedCryptoMaterialProperties": {
          "type": "private-key",
          "state": "active",
          "algorithmRef": "crypto/algorithm/rsa-2048",
          "size": 2048,
          "securedBy": {
            "mechanism": "HSM"
          }
        }
      }
    }
  ],
  "dependencies": [
    {
      "ref": "app/internet-banking",
      "dependsOn": ["crypto/protocol/tls13"]
    }
  ]
}
```

จากตัวอย่างใน {numref}`cbom-example` เครื่องมือวิเคราะห์สามารถค้นหาสินทรัพย์ที่มีค่า `nistQuantumSecurityLevel` เท่ากับ 0 ได้โดยอัตโนมัติ ซึ่งในกรณีนี้คือ ECDH P-256 ที่ใช้สร้างกุญแจรหัสลับร่วมกัน และ RSA-2048 ที่ใช้ลงลายมือชื่อดิจิทัลในใบรับรอง ทั้งสองรายการจึงต้องได้รับการวางแผนเปลี่ยนผ่าน เช่น เปลี่ยนการสร้างกุญแจรหัสลับร่วมกันเป็นแบบผสม X25519MLKEM768 {cite:p}`rfc10024` และเปลี่ยนใบรับรองเป็น ML-DSA เมื่อผู้ออกใบรับรองรองรับ ขณะที่ AES-256-GCM และ SHA-384 ยังคงใช้งานต่อได้ นอกจากนี้ ฟิลด์ `bom-ref` ยังช่วยเชื่อมโยงความสัมพันธ์ระหว่างสินทรัพย์ เช่น ใบรับรองที่อ้างอิงอัลกอริทึมลงลายมือชื่อดิจิทัล และกุญแจส่วนตัวที่อ้างอิงอัลกอริทึมเดียวกัน ทำให้องค์กรประเมินผลกระทบได้ครบถ้วนเมื่อต้องเปลี่ยนอัลกอริทึมใดอัลกอริทึมหนึ่ง