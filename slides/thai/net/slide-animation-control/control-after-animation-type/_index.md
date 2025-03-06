---
title: การเรียนรู้เอฟเฟกต์หลังแอนิเมชั่นใน PowerPoint ด้วย Aspose.Slides
linktitle: ควบคุมหลังจากประเภทภาพเคลื่อนไหวในสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีควบคุมเอฟเฟกต์หลังภาพเคลื่อนไหวในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอของคุณด้วยองค์ประกอบภาพแบบไดนามิก
weight: 11
url: /th/net/slide-animation-control/control-after-animation-type/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
การปรับปรุงการนำเสนอของคุณด้วยภาพเคลื่อนไหวแบบไดนามิกเป็นส่วนสำคัญในการดึงดูดผู้ชมของคุณ Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการควบคุมเอฟเฟกต์หลังแอนิเมชั่นในสไลด์ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการใช้ Aspose.Slides สำหรับ .NET เพื่อจัดการประเภทอาฟเตอร์แอนิเมชันบนสไลด์ เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถสร้างงานนำเสนอที่มีการโต้ตอบและดึงดูดสายตามากขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และ .NET
-  ติดตั้ง Aspose.Slides สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Slides เพิ่มบรรทัดต่อไปนี้ลงในโค้ดของคุณ:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
ตอนนี้ เรามาแบ่งโค้ดที่ให้มาออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ดีขึ้น:
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ตรวจสอบให้แน่ใจว่าไดเร็กทอรีที่ระบุมีอยู่ หรือสร้างไดเร็กทอรีดังกล่าวหากไม่มี
## ขั้นตอนที่ 2: กำหนดเส้นทางไฟล์เอาท์พุต
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
ระบุเส้นทางไฟล์เอาต์พุตสำหรับการนำเสนอที่แก้ไข
## ขั้นตอนที่ 3: โหลดการนำเสนอ
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
สร้างอินสแตนซ์ของคลาสการนำเสนอและโหลดการนำเสนอที่มีอยู่
## ขั้นตอนที่ 4: แก้ไขหลังจากเอฟเฟกต์ภาพเคลื่อนไหวบนสไลด์ 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
โคลนสไลด์แรก เข้าถึงลำดับไทม์ไลน์ และตั้งค่าเอฟเฟกต์หลังแอนิเมชั่นเป็น "ซ่อนเมื่อคลิกเมาส์ครั้งถัดไป"
## ขั้นตอนที่ 5: แก้ไขหลังจากเอฟเฟกต์ภาพเคลื่อนไหวบนสไลด์ 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
โคลนสไลด์แรกอีกครั้ง คราวนี้เปลี่ยนเอฟเฟกต์อาฟเตอร์แอนิเมชันเป็น "สี" ด้วยสีเขียว
## ขั้นตอนที่ 6: แก้ไขหลังจากเอฟเฟกต์ภาพเคลื่อนไหวบนสไลด์ 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
โคลนสไลด์แรกอีกครั้ง โดยตั้งค่าเอฟเฟกต์อาฟเตอร์แอนิเมชันเป็น "ซ่อนหลังจากแอนิเมชัน"
## ขั้นตอนที่ 7: บันทึกงานนำเสนอที่แก้ไข
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขด้วยเส้นทางไฟล์เอาต์พุตที่ระบุ
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีควบคุมเอฟเฟกต์อาฟเตอร์แอนิเมชั่นบนสไลด์สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET ทดลองกับอาฟเตอร์แอนิเมชั่นประเภทต่างๆ เพื่อสร้างงานนำเสนอที่มีชีวิตชีวาและน่าดึงดูดยิ่งขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถใช้เอฟเฟ็กต์อาฟเตอร์แอนิเมชั่นที่แตกต่างกันกับแต่ละองค์ประกอบภายในสไลด์ได้หรือไม่
ใช่คุณสามารถ. วนซ้ำองค์ประกอบต่างๆ และปรับเอฟเฟ็กต์อาฟเตอร์แอนิเมชั่นตามนั้น
### Aspose.Slides เข้ากันได้กับ .NET เวอร์ชันล่าสุดหรือไม่
ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าเข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ล่าสุด
### ฉันจะเพิ่มภาพเคลื่อนไหวที่กำหนดเองลงในสไลด์โดยใช้ Aspose.Slides ได้อย่างไร
 โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/net/) สำหรับข้อมูลโดยละเอียดเกี่ยวกับการเพิ่มภาพเคลื่อนไหวที่กำหนดเอง
### Aspose.Slides รองรับการบันทึกงานนำเสนอในรูปแบบไฟล์ใดบ้าง
Aspose.Slides รองรับรูปแบบต่างๆ รวมถึง PPTX, PPT, PDF และอื่นๆ ตรวจสอบเอกสารเพื่อดูรายการทั้งหมด
### ฉันจะรับการสนับสนุนหรือถามคำถามที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อการสนับสนุนและการมีปฏิสัมพันธ์กับชุมชน
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
