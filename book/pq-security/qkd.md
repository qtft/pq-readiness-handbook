# การกระจายกุญแจเชิงควอนตัม (Quantum Key Distribution)

การกระจายกุญแจเชิงควอนตัมเป็นกระบวนการที่อาศัยปรากฏการณ์เชิงควอนตัมเพื่อการ
แลกเปลี่ยนกุญแจรหัสลับ โดยทั่วไป QKD จะใช้ฮาร์ดแวร์เฉพาะทางเพื่อการส่งคิวบิตเชิงแสง (Photonic Qubits)
ผ่านทางใยแก้วนำแสงหรือทางอากาศ หากมีผู้ไม่ประสงค์ดีพยายามที่จะดักฟัง (Eavesdrop) ข้อมูล
ที่สื่อสารกัน การดักฟังนั้นจะส่งผลกระทบต่อคิวบิตเชิงแสงดังกล่าว ทำให้ผู้รับข้อมูลปลายทางสามารถใช้
คุณสมบัติเชิงควอนตัมเพื่อตรวจสอบได้ว่ามีการดักฟังเกิดขึ้นหรือไม่ ดังนั้นผู้ที่สื่อสารสามารถมั่นใจได้ว่าข้อมูล
ที่สื่อสารไม่รั่วไหลไปยังผู้อื่น QKD เป็นกระบวนการที่เพิ่มความปลอดภัยในการแลกเปลี่ยนกุญแจรหัสลับสำหรับ
การใช้ในโพรโทคอลการสื่อสารอื่น ๆ ต่อไป

การแลกเปลี่ยนกุญแจด้วยกระบวนการประเภท QKD มีความปลอดภัยในทางทฤษฎี (Theoretically Secure) จากทั้งคอมพิวเตอร์แบบดั้งเดิมและคอมพิวเตอร์ควอนตัม ทั้งนี้ QKD นั้นมีข้อจำกัดในแง่ของการใช้งาน ทำให้ใช้ได้กับบางกรณีการใช้งานที่เฉพาะเจาะจงเท่านั้น ข้อจำกัดของเทคโนโลยี QKD ในปัจจุบันมีดังนี้

- QKD มีความเหมาะสมกับการใช้งานที่มีระยะทางสั้นไม่เกิน 125 กิโลเมตรเท่านั้น {cite:p}`qedc2022guide` โดยการส่งคิวบิตเชิงแสงผ่านใยแก้วนำแสงแบบจุดต่อจุด (Point-to-point) ทั้งนี้ เทคโนโลยี Quantum repeaters หรือการจัดส่งคิวบิตเชิงแสงผ่านทางดาวเทียม อาจถูกนำมาใช้เพื่อขยายระยะทางของ QKD ได้ในอนาคต
- QKD มีอัตราในการแลกเปลี่ยนกุญแจรหัสลับ (Key exchange rate) ที่ต่ำ เมื่อเทียบกับโพรโทคอลการแลกเปลี่ยนกุญแจแบบดั้งเดิม ทั้งนี้ ในปัจจุบัน QKD มีอัตราการแลกเปลี่ยนกุญแจที่มากกว่า 1 Mbps ซึ่งเพียงพอต่อการใช้งานสำหรับบางแอปพลิเคชันเท่านั้น
- QKD มีความจำเป็นต้องใช้ฮาร์ดแวร์เฉพาะทาง ซึ่งอาจมีต้นทุนสูง
- QKD สามารถนำไปใช้เพื่อการแลกเปลี่ยนกุญแจ แต่ไม่สามารถนำไปใช้ในการยืนยันตัวตน (Authentication) ได้ ทำให้ติดตั้งเครือข่าย QKD ต้องอาศัยการยืนยันตัวตนโดยบุคคล (Manual Authentication) หรือ อาศัยโพรโทคอลการยืนยันตัวตนแบบอื่นร่วมด้วย
- QKD มีความเสี่ยงต่อการโจมตีที่ช่องโหว่ด้านความปลอดภัยของอุปกรณ์ฮาร์ดแวร์ (Hardware Vulnerabilities) และการโจมตีประเภท Side-Channel ซึ่งอาศัยการวิเคราะห์ข้อมูลความร้อนหรือคลื่นแม่เหล็กไฟฟ้าจากอุปกรณ์ฮาร์ดแวร์ในการโจมตี เป็นต้น 

นอกจากนี้หน่วยงานที่มีบทบาทสำคัญและเกี่ยวข้องในต่างประเทศมีมุมมองต่อ QKD ดังต่อไปนี้ {cite:p}`qedc2022guide` {cite:p}`ncsc2020preparing` 
- ANSSI ได้ทำการศึกษาและวิเคราะห์ข้อดีข้อเสียของ PQC และ QKD และได้ข้อสรุปว่า PQC เป็นทางเลือกที่ง่ายและต้นทุนต่ำกว่าในการนำไปใช้งานจริงและไม่ติดข้อจำกัดต่าง ๆ ของ QKD ดังนั้น จึงควรที่จะมุ่งเน้นการพัฒนา PQC เพื่อเตรียมตัวเข้าสู่ยุคควอนตัม
- สำนักงานความมั่นคงแห่งชาติเห็นข้อจำกัดของ QKD และยังไม่สนับสนุนการใช้ QKD ในระบบความมั่นคงของชาติจนกว่าข้อจำกัดดังกล่าวจะได้รับการแก้ไข
- ศูนย์ความมั่นคงปลอดภัยไซเบอร์แห่งชาติ (National Cyber Security Centre: NCSC) สหราชอาณาจักรยังไม่สนับสนุนการใช้ QKD ในแอปพลิเคชันของรัฐและทหาร ข้อจำกัดทางด้านเทคโนโลยีในปัจจุบันดังกล่าว ทำให้ QKD อาจยังไม่เหมาะสมต่อการใช้งานทั่วไป อาจเหมาะสมเพียงแอปพลิเคชันบางประเภทเท่านั้น