# CRUD คืออะไร?

การพัฒนา CRUD API ใน Node.js คือ การสร้างชุดของฟังก์ชันบนฝั่งเซิร์ฟเวอร์ (Backend) ด้วย Node.js ที่อนุญาตให้แอปพลิเคชันอื่น ๆ (เช่น แอปพลิเคชันฝั่ง Frontend หรือ Mobile App) สามารถดำเนินการพื้นฐานกับข้อมูลได้ โดยใช้หลักการของ CRUD.

CRUD ย่อมาจาก:

- Create (สร้าง): การเพิ่มข้อมูลใหม่เข้าไปในฐานข้อมูล
- Read (อ่าน): การดึงข้อมูลที่มีอยู่จากฐานข้อมูล
- Update (อัปเดต): การแก้ไขข้อมูลที่มีอยู่แล้วในฐานข้อมูล
- Delete (ลบ): การลบข้อมูลออกจากฐานข้อมูล

## API คืออะไร?

API (Application Programming Interface) คือชุดของกฎเกณฑ์และกลไกที่กำหนดวิธีการที่ซอฟต์แวร์สองตัวจะสื่อสารกันได้ ในบริบทนี้ API คือกลุ่มของ Endpoint (URL ที่เฉพาะเจาะจง) ที่เมื่อถูกเรียกใช้งานด้วย HTTP Methods (เช่น GET, POST, PUT, DELETE) จะทำการกระทำบางอย่างกับข้อมูลและส่งผลลัพธ์กลับมา

## การพัฒนา CRUD API ใน Node.js

เมื่อพูดถึงการพัฒนา CRUD API ใน Node.js หมายถึงการเขียนโค้ด JavaScript ฝั่งเซิร์ฟเวอร์ (โดยใช้ Node.js) เพื่อ:

**1. ตั้งค่าเซิร์ฟเวอร์**

มักจะใช้เฟรมเวิร์กยอดนิยมอย่าง Express.js เพื่อสร้างเซิร์ฟเวอร์ HTTP และกำหนดเส้นทาง (Routes) สำหรับ API Endpoint ต่างๆ

**2. เชื่อมต่อกับฐานข้อมูล**

เชื่อมต่อ Node.js กับฐานข้อมูลที่ต้องการใช้งาน เช่น MongoDB (NoSQL) หรือ PostgreSQL/MySQL (SQL) โดยใช้ Driver หรือ ORM/ODM (Object-Relational Mapper / Object-Document Mapper) ที่เหมาะสม (เช่น Mongoose สำหรับ MongoDB, Sequelize สำหรับ SQL)

**3. สร้าง Endpoint สำหรับแต่ละการกระทำ**

- **Create (POST)**: สร้าง Endpoint สำหรับรับข้อมูลใหม่ (มักจะส่งมาในรูปแบบ JSON) และบันทึกลงในฐานข้อมูล เช่น `POST /api/products` เพื่อสร้างสินค้าใหม่
- **Read (GET)**: สร้าง Endpoint สำหรับดึงข้อมูล อาจจะดึงข้อมูลทั้งหมด หรือดึงข้อมูลเฉพาะบางรายการโดยใช้ ID เช่น `GET /api/products` (ดึงสินค้าทั้งหมด) หรือ `GET /api/products/:id` (ดึงสินค้าตาม ID)
- **Update (PUT/PATCH)**: สร้าง Endpoint สำหรับแก้ไขข้อมูลที่มีอยู่ มักจะรับ ID ของข้อมูลที่ต้องการแก้ไขและข้อมูลใหม่ที่จะอัปเดต เช่น `PUT /api/products/:id` เพื่ออัปเดตสินค้าตาม ID
- **Delete (DELETE)**: สร้าง Endpoint สำหรับลบข้อมูลออกจากฐานข้อมูล โดยระบุ ID ของข้อมูลที่ต้องการลบ เช่น `DELETE /api/products/:id` เพื่อลบสินค้าตาม ID


**4. จัดการคำขอและตอบกลับ**

โค้ดในแต่ละ Endpoint จะรับคำขอจาก Client (Request), ประมวลผลข้อมูล (เช่น ตรวจสอบความถูกต้อง, บันทึกลงฐานข้อมูล), และส่งผลลัพธ์กลับไปยัง Client (Response) ในรูปแบบที่เข้าใจได้ (มักจะเป็น JSON)

## ตัวอย่างง่ายๆ ของ Use Case:

สมมติว่าเรากำลังสร้างแอปพลิเคชันสำหรับจัดการสินค้าในร้านค้า:

`POST /products:` เพิ่มสินค้าใหม่

`GET /products:` ดูรายการสินค้าทั้งหมด

`GET /products/:id:` ดูรายละเอียดสินค้าชิ้นเดียว

`PUT /products/:id:` แก้ไขข้อมูลสินค้า

`DELETE /products/:id:` ลบสินค้า

::: tip
การพัฒนา CRUD API ใน Node.js จึงเป็นพื้นฐานสำคัญในการสร้างแอปพลิเคชันเว็บและโมบายสมัยใหม่ที่ต้องการจัดการข้อมูลบนเซิร์ฟเวอร์
:::

## เรียนรู้การพัฒนา NodeJS Application

<iframe width="560" height="315" src="https://www.youtube.com/embed/rrtQ3GaSC9s?si=_SavdBC8SUce4Ony" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>