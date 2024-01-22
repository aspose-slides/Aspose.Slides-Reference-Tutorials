---
title: การเพิ่มการยืดชดเชยการเติมรูปภาพในการนำเสนอ PowerPoint
linktitle: การเพิ่มการยืดชดเชยสำหรับการเติมรูปภาพในสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับปรุงงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ .NET ทำตามคำแนะนำทีละขั้นตอนเพื่อเพิ่มออฟเซ็ตการยืดสำหรับการเติมรูปภาพ
type: docs
weight: 18
url: /th/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---
## การแนะนำ
ในโลกแห่งการนำเสนอที่ไม่หยุดนิ่ง ภาพมีบทบาทสำคัญในการดึงดูดความสนใจของผู้ชม Aspose.Slides สำหรับ .NET ช่วยให้นักพัฒนาปรับปรุงการนำเสนอ PowerPoint ของตนโดยมอบชุดฟีเจอร์ที่มีประสิทธิภาพ คุณสมบัติอย่างหนึ่งคือความสามารถในการเพิ่มการยืดเยื้อสำหรับการเติมรูปภาพ ช่วยให้สไลด์มีความคิดสร้างสรรค์และดึงดูดสายตา
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Slides สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้
ตอนนี้ เรามาเริ่มด้วยคำแนะนำทีละขั้นตอนกันดีกว่า
## นำเข้าเนมสเปซ
ขั้นแรก นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Slides ภายในแอปพลิเคชัน .NET ของคุณ
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการ .NET ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ ตรวจสอบให้แน่ใจว่า Aspose.Slides สำหรับ .NET มีการอ้างอิงอย่างถูกต้อง
## ขั้นตอนที่ 2: เริ่มต้นคลาสการนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงไฟล์ PowerPoint
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // รหัสของคุณอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: รับสไลด์แรก
ดึงสไลด์แรกจากงานนำเสนอเพื่อใช้งาน
```csharp
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 4: สร้างอินสแตนซ์คลาส ImageEx
 สร้างอินสแตนซ์ของ`ImageEx` คลาสเพื่อจัดการรูปภาพที่คุณต้องการเพิ่มลงในสไลด์
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## ขั้นตอนที่ 5: เพิ่มกรอบรูป
 ใช้`AddPictureFrame` วิธีการเพิ่มกรอบรูปให้กับสไลด์ ระบุขนาดและตำแหน่งของเฟรม
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขลงในดิสก์
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
แค่นั้นแหละ! คุณได้เพิ่มการยืดชดเชยสำหรับการเติมรูปภาพในสไลด์โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว
## บทสรุป
การปรับปรุงงานนำเสนอ PowerPoint ของคุณง่ายกว่าที่เคยด้วย Aspose.Slides สำหรับ .NET เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีรวมการยืดเยื้อสำหรับการเติมรูปภาพ ซึ่งนำความคิดสร้างสรรค์ระดับใหม่มาสู่สไลด์ของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET บนเว็บแอปพลิเคชันของฉันได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET เหมาะสำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชัน
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุน Aspose.Slides สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อสนับสนุนชุมชน
### ฉันจะหาเอกสารฉบับสมบูรณ์สำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับข้อมูลโดยละเอียด
### ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้หรือไม่
 ใช่คุณสามารถซื้อผลิตภัณฑ์ได้[ที่นี่](https://purchase.aspose.com/buy).