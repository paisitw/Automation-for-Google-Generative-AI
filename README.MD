ตัวอย่าง Automation ที่ใช้ทำงานร่วมกับ Google Generative AI 
 
หลักการคร่าวๆ คือ 
 
1. ภาพที่จะส่งไปให้ Google AI ต้องอยู่ใน Directory ที่มี permission เหมาะสม โดยดูการกำหนด permission ใน configuration.yaml ดังนี้
 
homeassistant:
  allowlist_external_dirs:
    - /config/www/snapshot
 
  whitelist_external_dirs:
    - /config/www/snapshot
 
2. ตัวอย่างด้านล่างเป็นการใช้ motion sensor มา trigger ให้กล้อง camera.indoor6 ทำการ snapshot แล้วเก็บที่ไฟล์ jpeg 
   หลังจากนั้น delay สัก 3 วินาทีเพื่อให้กล้อง snapshot และเขียนไฟล์ลงบนจุดนัดพบให้เรียบร้อย 
3. ทำการส่งภาพไปที่ Google AI โดย Call Service แล้ว Goolge จะส่งผลกลับมาที่ตัวแปร generated_content
4. เราสามารถส่งผลลัพธื (คำอธิบาย)​ที่ได้ไปที่ HA Noti หรือ Line, Telegram ได้หมด แม้กระทั่งป่าวประกาศผ่าน TTS ไปยัง Smart Speaker 
   ตัวอย่างด้านล่างคือส่ง Noti ไปที่มือถือที่ติดตั้ง HA Companion App ชื่อ paisit 
 
--------------------------------------------------------
