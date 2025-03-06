---
title: สร้างการไล่ระดับสีที่น่าทึ่งใน PowerPoint ด้วย Aspose.Slides
linktitle: การเติมรูปร่างด้วยการไล่ระดับสีในสไลด์การนำเสนอโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงการนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET! เรียนรู้กระบวนการทีละขั้นตอนในการเติมรูปร่างด้วยการไล่ระดับสี ดาวน์โหลดทดลองใช้ฟรีตอนนี้!
weight: 21
url: /th/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
การสร้างสไลด์การนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญในการดึงดูดและรักษาความสนใจของผู้ชม ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการปรับปรุงสไลด์ของคุณโดยการเติมรูปร่างวงรีด้วยการไล่ระดับสีโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  Aspose.Slides สำหรับไลบรารี .NET ดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- ไดเร็กทอรีโครงการเพื่อจัดระเบียบไฟล์ของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้รวมเนมสเปซที่จำเป็นสำหรับ Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: สร้างงานนำเสนอ
เริ่มต้นด้วยการสร้างงานนำเสนอใหม่โดยใช้ไลบรารี Aspose.Slides:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // รหัสของคุณอยู่ที่นี่...
}
```
## ขั้นตอนที่ 2: เพิ่มรูปร่างวงรี
แทรกรูปร่างวงรีลงในสไลด์แรกของงานนำเสนอของคุณ:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## ขั้นตอนที่ 3: ใช้การจัดรูปแบบไล่ระดับสี
ระบุว่าควรเติมรูปร่างด้วยการไล่ระดับสีและกำหนดลักษณะการไล่ระดับสี:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## ขั้นตอนที่ 4: เพิ่มการหยุดการไล่ระดับสี
กำหนดสีและตำแหน่งของจุดไล่ระดับสี:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอของคุณด้วยรูปร่างที่เต็มไปด้วยการไล่ระดับสีที่เพิ่มเข้ามาใหม่:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
ทำซ้ำขั้นตอนเหล่านี้ในโค้ด C# ของคุณ เพื่อให้แน่ใจว่าค่าลำดับและพารามิเตอร์ถูกต้อง ซึ่งจะส่งผลให้ไฟล์งานนำเสนอมีรูปร่างวงรีที่ดึงดูดสายตาซึ่งเต็มไปด้วยการไล่ระดับสี
## บทสรุป
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้การไล่ระดับสีกับรูปร่างอื่นที่ไม่ใช่วงรีได้หรือไม่
ตอบ: แน่นอน! Aspose.Slides สำหรับ .NET รองรับการเติมไล่ระดับสีสำหรับรูปร่างต่างๆ เช่น สี่เหลี่ยม รูปหลายเหลี่ยม และอื่นๆ
### ถาม: ฉันจะหาตัวอย่างเพิ่มเติมและเอกสารโดยละเอียดได้ที่ไหน
 ตอบ: สำรวจ[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม
### ถาม: Aspose.Slides สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
 ตอบ: ขอความช่วยเหลือและมีส่วนร่วมกับชุมชนในเรื่อง[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
 ตอบ: แน่นอน คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
