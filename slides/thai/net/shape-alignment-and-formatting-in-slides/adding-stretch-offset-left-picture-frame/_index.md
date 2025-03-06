---
title: การเพิ่มการยืดออฟเซ็ตไปทางซ้ายใน PowerPoint ด้วย Aspose.Slide
linktitle: การเพิ่มการยืดออฟเซ็ตไปทางซ้ายสำหรับกรอบรูปใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีการปรับปรุงงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ทำตามคำแนะนำทีละขั้นตอนของเราเพื่อเพิ่มการยืดเยื้อไปทางซ้ายสำหรับกรอบรูป
weight: 14
url: /th/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่มการยืดออฟเซ็ตไปทางซ้ายใน PowerPoint ด้วย Aspose.Slide

## การแนะนำ
Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาจัดการงานนำเสนอ PowerPoint ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะสำรวจกระบวนการเพิ่มการยืดเยื้อไปทางซ้ายสำหรับกรอบรูปโดยใช้ Aspose.Slides สำหรับ .NET ทำตามคำแนะนำทีละขั้นตอนนี้เพื่อพัฒนาทักษะของคุณในการทำงานกับรูปภาพและรูปร่างภายในงานนำเสนอ PowerPoint
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว ถ้าไม่เช่นนั้น ให้ดาวน์โหลดจาก[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาการทำงานที่มีความสามารถ. NET
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโครงการ .NET ของคุณ:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการใหม่หรือเปิดโครงการที่มีอยู่ ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Slides ที่อ้างอิงในโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสซึ่งเป็นตัวแทนของไฟล์ PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // รหัสของคุณสำหรับขั้นตอนต่อไปจะอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: รับสไลด์แรก
ดึงสไลด์แรกจากการนำเสนอ:
```csharp
ISlide slide = pres.Slides[0];
```
## ขั้นตอนที่ 4: สร้างอินสแตนซ์ของรูปภาพ
โหลดภาพที่คุณต้องการใช้:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## ขั้นตอนที่ 5: เพิ่มรูปร่างอัตโนมัติแบบสี่เหลี่ยมผืนผ้า
สร้างรูปร่างอัตโนมัติประเภทสี่เหลี่ยมผืนผ้า:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## ขั้นตอนที่ 6: ตั้งค่าประเภทการเติมและโหมดการเติมรูปภาพ
กำหนดค่าประเภทการเติมของรูปร่างและโหมดการเติมรูปภาพ:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## ขั้นตอนที่ 7: ตั้งค่ารูปภาพเพื่อเติมรูปร่าง
ระบุรูปภาพเพื่อเติมรูปร่าง:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## ขั้นตอนที่ 8: ระบุค่าชดเชยการยืด
กำหนดออฟเซ็ตรูปภาพจากขอบที่สอดคล้องกันของกรอบขอบของรูปร่าง:
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
ยินดีด้วย! คุณได้เพิ่มการยืดชดเชยทางด้านซ้ายสำหรับกรอบรูปโดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการจัดการกรอบรูปในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET โดยการปฏิบัติตามคำแนะนำทีละขั้นตอน คุณจะได้รับข้อมูลเชิงลึกในการทำงานกับรูปภาพ รูปร่าง และออฟเซ็ต
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้การยืดเยื้อกับรูปร่างอื่นนอกเหนือจากสี่เหลี่ยมได้หรือไม่
ตอบ: แม้ว่าบทช่วยสอนนี้จะเน้นไปที่สี่เหลี่ยม แต่การยืดออฟเซ็ตสามารถนำไปใช้กับรูปร่างต่างๆ ที่ Aspose.Slides รองรับได้
### ถาม: ฉันจะปรับค่าชดเชยการยืดเพื่อให้ได้เอฟเฟกต์ต่างๆ ได้อย่างไร
ตอบ: ทดลองใช้ค่าออฟเซ็ตต่างๆ เพื่อให้ได้ภาพที่สวยงามตามที่ต้องการ ปรับแต่งค่าอย่างละเอียดเพื่อให้เหมาะกับความต้องการเฉพาะของคุณ
### ถาม: Aspose.Slides เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่
ตอบ: Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าสามารถใช้งานร่วมกับ .NET Framework เวอร์ชันล่าสุดได้
### ถาม: ฉันจะหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 ตอบ: สำรวจ[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/net/) สำหรับตัวอย่างและคำแนะนำที่ครอบคลุม
### ถาม: ฉันสามารถใช้การยืดเยื้อหลายแบบกับรูปร่างเดียวได้หรือไม่
ตอบ: ได้ คุณสามารถรวมการยืดขยายหลายแบบเข้าด้วยกันเพื่อให้ได้เอฟเฟ็กต์ภาพที่ซับซ้อนและปรับแต่งเองได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
