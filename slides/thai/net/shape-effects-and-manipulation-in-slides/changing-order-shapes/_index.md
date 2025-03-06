---
title: การปรับรูปร่างสไลด์การนำเสนอใหม่ด้วย Aspose.Slides สำหรับ .NET
linktitle: การเปลี่ยนลำดับของรูปร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับเปลี่ยนรูปร่างสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ทำตามคำแนะนำทีละขั้นตอนนี้เพื่อจัดลำดับรูปร่างใหม่และปรับปรุงรูปลักษณ์ให้สวยงามยิ่งขึ้น
type: docs
weight: 26
url: /th/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## การแนะนำ
การสร้างสไลด์การนำเสนอที่ดึงดูดสายตาถือเป็นส่วนสำคัญของการสื่อสารที่มีประสิทธิภาพ Aspose.Slides สำหรับ .NET ช่วยให้นักพัฒนาสามารถจัดการสไลด์โดยทางโปรแกรม โดยมีฟังก์ชันการทำงานที่หลากหลาย ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเปลี่ยนลำดับของรูปร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Slides ที่รวมอยู่ในโปรเจ็กต์ .NET ของคุณ ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[หน้าเผยแพร่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาการทำงานด้วย Visual Studio หรือเครื่องมือพัฒนา .NET อื่นๆ
- ความเข้าใจพื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้รวมเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Slides:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการใหม่ใน Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ ตรวจสอบให้แน่ใจว่า Aspose.Slides สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์และรูปร่าง
```csharp
ISlide slide = presentation.Slides[0];
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างใหม่
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## ขั้นตอนที่ 5: แก้ไขข้อความในรูปร่าง
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## ขั้นตอนที่ 6: เพิ่มรูปร่างอื่น
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## ขั้นตอนที่ 7: เปลี่ยนลำดับของรูปร่าง
```csharp
slide.Shapes.Reorder(2, shp3);
```
## ขั้นตอนที่ 8: บันทึกงานนำเสนอที่แก้ไข
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
ซึ่งจะช่วยอธิบายคำแนะนำทีละขั้นตอนสำหรับการเปลี่ยนลำดับรูปร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET อย่างสมบูรณ์
## บทสรุป
Aspose.Slides สำหรับ .NET ช่วยลดความยุ่งยากในการจัดการสไลด์การนำเสนอโดยทางโปรแกรม เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดลำดับรูปร่างใหม่ ซึ่งช่วยให้คุณสามารถปรับปรุงรูปลักษณ์ของงานนำเสนอของคุณได้
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ทั้งในสภาพแวดล้อม Windows และ Linux ได้หรือไม่
ตอบ: ได้ Aspose.Slides สำหรับ .NET เข้ากันได้กับทั้งสภาพแวดล้อม Windows และ Linux
### ถาม: มีข้อควรพิจารณาในการอนุญาตให้ใช้ Aspose.Slides ในโครงการเชิงพาณิชย์หรือไม่
 ตอบ: ได้ คุณสามารถดูรายละเอียดสิทธิ์การใช้งานและตัวเลือกการซื้อได้ที่[หน้าการซื้อ Aspose.Slides](https://purchase.aspose.com/buy).
### ถาม: Aspose.Slides สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถสำรวจคุณสมบัติต่างๆ ได้ด้วย[ทดลองฟรี](https://releases.aspose.com/) มีอยู่ในเว็บไซต์ Aspose.Slides
### ถาม: ฉันจะรับการสนับสนุนหรือถามคำถามที่เกี่ยวข้องกับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อรับการสนับสนุนและมีส่วนร่วมกับชุมชน
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
 ตอบ: คุณจะได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการประเมินผล