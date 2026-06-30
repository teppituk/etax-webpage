# eTax Platform — Portal (หน้า Index)

หน้า index สำหรับบอกข้อมูลภาพรวมและการใช้งานระบบ **eTax (e-Tax Invoice & e-Receipt)** ของ GEC
ออกแบบให้เข้ากับธีมเดิมของ `ui-service` (สี Material Indigo `#1A237E / #283593`, โลโก้ GEC)

## โครงสร้าง
```
etax-webpage/
├── index.html        # หน้า webpage (self-contained, ไม่ต้อง build)
├── assets/
│   ├── logo-gec-etax.png   # โลโก้ GEC eTax
│   ├── favicon.png         # favicon (โลโก้มีขอบ)
│   └── customers/          # โลโก้ลูกค้า
└── README.md
```

## รันทดสอบที่ Local
ใช้เว็บเซิร์ฟเวอร์ตัวใดก็ได้ เช่น:

```bash
cd etax-webpage
python3 -m http.server 8088
# เปิดเบราว์เซอร์ที่ http://localhost:8088
```

หรือเปิดไฟล์ `index.html` ตรง ๆ ในเบราว์เซอร์ก็ได้ (รูปโลโก้จะแสดงเมื่อเสิร์ฟผ่าน http server)

## เนื้อหาในหน้า (มุมมอง business สำหรับลูกค้า)
- **ภาพรวม** e-Tax Invoice & e-Receipt + ตัวเลขคุณค่า
- **การรับรอง** — กรมสรรพากร (RD), ISO/IEC 27001:2022, ETDA
- **ระบบคืออะไร / ความสามารถ** ของระบบ
- **เอกสารที่รองรับ** (ใบกำกับภาษีเต็มรูป/ย่อ, ใบเพิ่มหนี้, ใบลดหนี้, ใบรับ ฯลฯ)
- **ขั้นตอนการใช้งาน** (สร้าง → ลงลายมือชื่อ → ส่ง → นำส่งสรรพากร → จัดเก็บ)
- **โซลูชัน 3 แบบ** — E-Tax Basic / ERP Plug-and-Go / Frontline Auto Invoicing
- **ราคา** — ค่าติดตั้งครั้งเดียว, ค่าบริการรายปี, ตารางค่าบริการรายเดือนตามปริมาณ (per Doc.No)
- **เปรียบเทียบต้นทุน** กระดาษ vs e-Tax (ลด 87%) และ GEC vs ผู้ให้บริการทั่วไป
- **ติดต่อ** — ข้อมูลบริษัทและฝ่ายบริการลูกค้าจริง

## ภาษา (TH / EN)
- ปุ่มสลับ `TH | EN` บน nav · จำค่าด้วย localStorage
- เปิดตรงภาษาได้: `http://localhost:8088/?lang=en`

> ข้อมูลราคา/โซลูชัน/การเปรียบเทียบ อ้างอิงจากสไลด์ `GEC eTax_v7_Price.pdf`
> ข้อมูลพอร์ต/บริการ (เชิงเทคนิค) อ้างอิงจาก `application.yml` และ `etax-cicd/.../docker-compose.yaml`
