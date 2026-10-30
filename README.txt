MESOOK REGISTRATION SYSTEM — ชุดไฟล์พร้อมใช้งาน
=====================================================

ไฟล์ในชุด
1) index.html   — หน้าเว็บลงทะเบียนสำหรับ Vercel
2) Code.gs      — Backend สำหรับ Google Apps Script / Google Sheets
3) vercel.json  — การตั้งค่า Vercel สำหรับเว็บ Static HTML
4) README.txt   — คู่มือนี้

ปลายทาง Google Apps Script ที่ตั้งไว้ใน index.html
https://script.google.com/macros/s/AKfycbyxDkYTUqhfoQZBWtZI1XUjRg-bQ6a-IyA7eWgIdqfr1VFLYlk52iQx6n9zLLDDaTiE/exec

A) ติดตั้ง Code.gs
-------------------
1. เปิด Google Sheet ที่ต้องการเก็บข้อมูล
2. Extensions > Apps Script
3. เปิด Code.gs แล้วลบโค้ดเดิม
4. วางเนื้อหาจาก Code.gs ในชุดนี้
5. กด Save

B) Deploy Apps Script
---------------------
1. Deploy > Manage deployments
2. ถ้ามี Web app เดิม กด Edit (รูปดินสอ)
   หรือ Deploy > New deployment > Web app
3. Execute as: Me
4. Who has access: Anyone
5. Version: New version
6. Deploy
7. อนุญาตสิทธิ์ Google Sheets หากระบบถาม
8. Web app URL ต้องลงท้าย /exec

หมายเหตุ:
ถ้า Apps Script สร้าง URL /exec ใหม่ ต้องนำ URL ใหม่นั้นไปแทนค่า
APPS_SCRIPT_URL ภายใน index.html

C) อัปโหลดหน้าเว็บขึ้น GitHub/Vercel
-----------------------------------
วางไฟล์เหล่านี้ไว้ที่ root ของ Repository:
  index.html
  vercel.json

สำคัญ: ชื่อต้องเป็น index.html ตัวพิมพ์เล็ก

Vercel:
- Framework Preset: Other
- Root Directory: ./
- Build Command: ว่าง
- Output Directory: ว่าง
- Install Command: ว่าง

Commit changes แล้วรอ Vercel Deploy อัตโนมัติ

D) ทดสอบ
---------
1. เปิด URL Vercel
2. กรอกชื่อทดลอง
3. กด "ยืนยันลงทะเบียนเข้างาน"
4. เมื่อสำเร็จจะได้เลข MS-xxxxx
5. เปิด Google Sheet
6. จะมีชีตชื่อ Registrations และข้อมูลแถวใหม่

คอลัมน์:
เวลา | เลขทะเบียน | ชื่อ-นามสกุล | เบอร์โทร | หน่วยงาน | ผู้ติดตาม | หมายเหตุ

E) ถ้าข้อมูลไม่เข้า Google Sheets
--------------------------------
- ตรวจ Who has access = Anyone
- Deploy เป็น New version หลังแก้ Code.gs
- ตรวจว่า index.html ใช้ URL /exec ล่าสุด
- ทดสอบ URL /exec ใน Private/Incognito
- ตรวจ Executions ใน Apps Script เพื่อดู error

MESOOK CATERING AND ORGANIZE CO., LTD.
มีสุข รับจัดงานบุญ ครบวงจร
