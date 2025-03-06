---
title: การเรียนรู้เอฟเฟกต์เอียงใน Aspose.Slides - บทช่วยสอนทีละขั้นตอน
linktitle: การใช้เอฟเฟกต์เอียงกับรูปร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงสไลด์การนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET! เรียนรู้การใช้เอฟเฟกต์มุมเอียงที่น่าหลงใหลในคำแนะนำทีละขั้นตอนนี้
weight: 24
url: /th/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้เอฟเฟกต์เอียงใน Aspose.Slides - บทช่วยสอนทีละขั้นตอน

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก การเพิ่มความดึงดูดสายตาให้กับสไลด์ของคุณสามารถเพิ่มผลกระทบของข้อความของคุณได้อย่างมาก Aspose.Slides สำหรับ .NET มีชุดเครื่องมือที่มีประสิทธิภาพในการจัดการและตกแต่งสไลด์การนำเสนอของคุณโดยทางโปรแกรม คุณสมบัติที่น่าสนใจประการหนึ่งคือความสามารถในการใช้เอฟเฟกต์เอียงกับรูปร่าง เพิ่มความลึกและมิติให้กับภาพของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ของคุณ และมีความเข้าใจพื้นฐานเกี่ยวกับ C#
- ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีสำหรับเอกสารของคุณซึ่งไฟล์การนำเสนอที่สร้างขึ้นจะถูกบันทึก
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ให้รวมเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Slides
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ตรวจสอบให้แน่ใจว่าไดเร็กทอรีเอกสารมีอยู่ สร้างใหม่หากไม่มีอยู่
## ขั้นตอนที่ 2: สร้างอินสแตนซ์การนำเสนอ
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
เริ่มต้นอินสแตนซ์การนำเสนอและเพิ่มสไลด์ที่จะใช้งาน
## ขั้นตอนที่ 3: เพิ่มรูปร่างให้กับสไลด์
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
สร้างรูปร่างอัตโนมัติ (วงรีในตัวอย่างนี้) และปรับแต่งคุณสมบัติการเติมและเส้น
## ขั้นตอนที่ 4: ตั้งค่าคุณสมบัติ ThreeDFormat
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
ระบุคุณสมบัติสามมิติ รวมถึงประเภทมุมเอียง ความสูง ความกว้าง ประเภทกล้อง ประเภทแสง และทิศทาง
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอโดยใช้เอฟเฟกต์มุมเอียงที่นำไปใช้กับไฟล์ PPTX
## บทสรุป
ยินดีด้วย! คุณใช้เอฟเฟกต์มุมเอียงกับรูปร่างในงานนำเสนอของคุณได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET ทดลองใช้พารามิเตอร์ต่างๆ เพื่อปลดปล่อยศักยภาพสูงสุดในการปรับปรุงภาพในสไลด์ของคุณ
## คำถามที่พบบ่อย
### 1. ฉันสามารถใช้เอฟเฟกต์เอียงกับรูปร่างอื่นได้หรือไม่
ได้ คุณสามารถใช้เอฟเฟกต์เอียงกับรูปร่างต่างๆ ได้โดยการปรับประเภทรูปร่างและคุณสมบัติให้เหมาะสม
### 2. ฉันจะเปลี่ยนสีของมุมเอียงได้อย่างไร?
 ปรับเปลี่ยน`SolidFillColor.Color` ทรัพย์สินภายใน`BevelTop` คุณสมบัติในการเปลี่ยนสีของมุมเอียง
### 3. Aspose.Slides เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่
ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าเข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุด
### 4. ฉันสามารถใช้เอฟเฟกต์เอียงหลายแบบกับรูปร่างเดียวได้หรือไม่?
แม้ว่าจะไม่ธรรมดา แต่คุณก็สามารถทดลองวางรูปร่างหลาย ๆ แบบซ้อนกันหรือปรับแต่งคุณสมบัติมุมเอียงเพื่อให้ได้ผลลัพธ์ที่คล้ายคลึงกัน
### 5. มีเอฟเฟกต์ 3D อื่นๆ ใน Aspose.Slides หรือไม่
อย่างแน่นอน! Aspose.Slides นำเสนอเอฟเฟกต์ 3D ที่หลากหลายเพื่อเพิ่มความลึกและความสมจริงให้กับองค์ประกอบการนำเสนอของคุณ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
