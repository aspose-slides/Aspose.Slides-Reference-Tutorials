---
"description": "เรียนรู้วิธีปรับปรุงการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อเพิ่มการชดเชยการยืดด้านซ้ายสำหรับกรอบรูป"
"linktitle": "การเพิ่มการยืดออฟเซ็ตไปทางซ้ายสำหรับกรอบรูปใน Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การเพิ่มออฟเซ็ตยืดไปทางซ้ายใน PowerPoint ด้วย Aspose.Slide"
"url": "/th/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่มออฟเซ็ตยืดไปทางซ้ายใน PowerPoint ด้วย Aspose.Slide

## การแนะนำ
Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถจัดการงานนำเสนอ PowerPoint ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะสำรวจกระบวนการเพิ่มค่าออฟเซ็ตยืดด้านซ้ายสำหรับกรอบรูปโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อพัฒนาทักษะของคุณในการทำงานกับรูปภาพและรูปทรงในงานนำเสนอ PowerPoint
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว หากยังไม่ได้ติดตั้ง ให้ดาวน์โหลดจาก [เอกสาร Aspose.Slides สำหรับ .NET](https://reference-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาที่ทำงานด้วยความสามารถของ .NET
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโครงการ .NET ของคุณ:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการใหม่หรือเปิดโครงการที่มีอยู่ ตรวจสอบว่าคุณมีไลบรารี Aspose.Slides อ้างอิงในโครงการของคุณแล้ว
## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ
สร้างตัวอย่าง `Presentation` คลาสที่แสดงไฟล์ PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // โค้ดของคุณสำหรับขั้นตอนต่อไปจะอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: รับสไลด์แรก
ดึงข้อมูลสไลด์แรกจากการนำเสนอ:
```csharp
ISlide slide = pres.Slides[0];
```
## ขั้นตอนที่ 4: สร้างภาพตัวอย่าง
โหลดภาพที่คุณต้องการใช้:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## ขั้นตอนที่ 5: เพิ่มรูปสี่เหลี่ยมผืนผ้าอัตโนมัติ
สร้าง AutoShape ของชนิดสี่เหลี่ยมผืนผ้า:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## ขั้นตอนที่ 6: ตั้งค่าประเภทการเติมและโหมดการเติมรูปภาพ
กำหนดค่าประเภทการเติมรูปร่างและโหมดการเติมรูปภาพ:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## ขั้นตอนที่ 7: ตั้งค่ารูปภาพให้เติมรูปร่าง
ระบุรูปภาพที่จะเติมรูปร่าง:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## ขั้นตอนที่ 8: ระบุค่าออฟเซ็ตการยืด
กำหนดค่าออฟเซ็ตของภาพจากขอบที่สอดคล้องกันของกล่องขอบเขตของรูปร่าง:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## ขั้นตอนที่ 9: บันทึกการนำเสนอ
เขียนไฟล์ PPTX ลงดิสก์:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
ขอแสดงความยินดี! คุณได้เพิ่มค่าออฟเซ็ตยืดด้านซ้ายให้กับกรอบรูปสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET
## บทสรุป
ในบทช่วยสอนนี้ เราจะมาสำรวจขั้นตอนการจัดการกรอบรูปในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET เมื่อปฏิบัติตามคำแนะนำทีละขั้นตอนแล้ว คุณจะได้รับข้อมูลเชิงลึกเกี่ยวกับการทำงานกับรูปภาพ รูปร่าง และออฟเซ็ต
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้การยืดออฟเซ็ตกับรูปร่างอื่นนอกจากสี่เหลี่ยมผืนผ้าได้หรือไม่
A: แม้ว่าบทช่วยสอนนี้จะเน้นที่รูปสี่เหลี่ยมผืนผ้า แต่การยืดออฟเซ็ตสามารถนำไปใช้กับรูปร่างต่างๆ ที่รองรับโดย Aspose.Slides ได้
### ถาม: ฉันจะปรับการยืดออฟเซ็ตเพื่อให้ได้เอฟเฟกต์ต่างๆ ได้อย่างไร
A: ทดลองใช้ค่าออฟเซ็ตที่แตกต่างกันเพื่อให้ได้ผลลัพธ์ตามที่ต้องการ ปรับแต่งค่าต่างๆ ให้เหมาะกับความต้องการเฉพาะของคุณ
### ถาม: Aspose.Slides เข้ากันได้กับ .NET framework ล่าสุดหรือไม่
ตอบ: Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อให้มั่นใจถึงความเข้ากันได้กับเวอร์ชัน .NET framework ล่าสุด
### ถาม: ฉันสามารถหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
ก. สำรวจ [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/net/) สำหรับตัวอย่างและคำแนะนำที่ครอบคลุม
### ถาม: ฉันสามารถใช้การยืดแบบหลายค่ากับรูปร่างเดียวได้หรือไม่
A: ใช่ คุณสามารถรวมการยืดออฟเซ็ตหลาย ๆ แบบเพื่อสร้างเอฟเฟกต์ภาพที่ซับซ้อนและกำหนดเองได้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}