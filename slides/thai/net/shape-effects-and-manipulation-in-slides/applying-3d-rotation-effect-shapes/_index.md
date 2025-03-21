---
title: เชี่ยวชาญการหมุน 3 มิติในการนำเสนอด้วย Aspose.Slides สำหรับ .NET
linktitle: การใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างในสไลด์การนำเสนอ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงการนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET! เรียนรู้วิธีใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างในบทช่วยสอนนี้ สร้างงานนำเสนอแบบไดนามิกและสวยงามตระการตา
weight: 23
url: /th/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เชี่ยวชาญการหมุน 3 มิติในการนำเสนอด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
การสร้างสไลด์การนำเสนอที่น่าดึงดูดและมีชีวิตชีวาเป็นส่วนสำคัญของการสื่อสารที่มีประสิทธิภาพ Aspose.Slides สำหรับ .NET มีชุดเครื่องมืออันทรงพลังเพื่อปรับปรุงการนำเสนอของคุณ รวมถึงความสามารถในการใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่าง ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio เพื่อเขียนและเรียกใช้โค้ดของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Slides รวมเนมสเปซต่อไปนี้ไว้ที่จุดเริ่มต้นของโค้ดของคุณ:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการใหม่ในสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิง Aspose.Slides ในโครงการของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
สร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อเริ่มทำงานกับสไลด์:
```csharp
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างอัตโนมัติ
เพิ่มรูปร่างอัตโนมัติให้กับสไลด์ โดยระบุประเภท ตำแหน่ง และขนาด:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## ขั้นตอนที่ 4: ตั้งค่าเอฟเฟกต์การหมุน 3 มิติ
กำหนดค่าเอฟเฟกต์การหมุน 3 มิติสำหรับรูปร่างอัตโนมัติ:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วโดยใช้เอฟเฟกต์การหมุน 3 มิติ:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 6: ทำซ้ำสำหรับรูปร่างอื่น ๆ
หากคุณมีรูปร่างเพิ่มเติม ให้ทำซ้ำขั้นตอนที่ 3 ถึง 5 สำหรับแต่ละรูปร่าง
## บทสรุป
การเพิ่มเอฟเฟ็กต์การหมุน 3 มิติให้กับรูปร่างในสไลด์การนำเสนอของคุณสามารถเพิ่มความน่าดึงดูดทางสายตาได้อย่างมาก ด้วย Aspose.Slides สำหรับ .NET กระบวนการนี้จะตรงไปตรงมา ช่วยให้คุณสร้างงานนำเสนอที่น่าดึงดูดได้
## คำถามที่พบบ่อย
### ฉันสามารถใช้การหมุน 3 มิติกับกล่องข้อความใน Aspose.Slides สำหรับ .NET ได้หรือไม่
ได้ คุณสามารถใช้เอฟเฟ็กต์การหมุน 3 มิติกับรูปร่างต่างๆ รวมถึงกล่องข้อความได้ โดยใช้ Aspose.Slides
### มี Aspose.Slides สำหรับ .NET เวอร์ชันทดลองใช้งานหรือไม่
 ใช่ คุณสามารถเข้าถึงเวอร์ชันทดลองได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุน Aspose.Slides สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
