---
"description": "เรียนรู้วิธีการควบคุมเอฟเฟกต์ภาพเคลื่อนไหวต่อเนื่องในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยองค์ประกอบภาพแบบไดนามิก"
"linktitle": "ควบคุมหลังจากพิมพ์แอนิเมชันในสไลด์"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "เรียนรู้การสร้างเอฟเฟกต์ After-Animation ใน PowerPoint ด้วย Aspose.Slides"
"url": "/th/net/slide-animation-control/control-after-animation-type/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เรียนรู้การสร้างเอฟเฟกต์ After-Animation ใน PowerPoint ด้วย Aspose.Slides

## การแนะนำ
การปรับปรุงงานนำเสนอของคุณด้วยแอนิเมชั่นแบบไดนามิกถือเป็นส่วนสำคัญในการดึงดูดผู้ฟัง Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการควบคุมเอฟเฟกต์แอนิเมชั่นหลังการนำเสนอในสไลด์ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการใช้ Aspose.Slides สำหรับ .NET เพื่อจัดการประเภทแอนิเมชั่นหลังการนำเสนอในสไลด์ หากปฏิบัติตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถสร้างงานนำเสนอที่โต้ตอบได้และดึงดูดสายตาได้มากขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มเรียนรู้บทช่วยสอน ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และ .NET
- ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น Visual Studio
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides เพิ่มบรรทัดต่อไปนี้ลงในโค้ดของคุณ:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
ตอนนี้เรามาแบ่งโค้ดที่ให้มาเป็นหลายขั้นตอนเพื่อความเข้าใจที่ดีขึ้น:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ตรวจสอบให้แน่ใจว่าไดเร็กทอรีที่ระบุมีอยู่ หรือสร้างขึ้นใหม่หากไม่มี
## ขั้นตอนที่ 2: กำหนดเส้นทางไฟล์เอาท์พุต
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
ระบุเส้นทางไฟล์เอาต์พุตสำหรับการนำเสนอที่แก้ไข
## ขั้นตอนที่ 3: โหลดงานนำเสนอ
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
สร้างอินสแตนซ์คลาสการนำเสนอและโหลดการนำเสนอที่มีอยู่
## ขั้นตอนที่ 4: แก้ไขเอฟเฟกต์ After Animation บนสไลด์ที่ 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
โคลนสไลด์แรก เข้าถึงลำดับไทม์ไลน์ และตั้งค่าเอฟเฟ็กต์หลังการเคลื่อนไหวเป็น "ซ่อนเมื่อคลิกเมาส์ครั้งถัดไป"
## ขั้นตอนที่ 5: แก้ไขเอฟเฟกต์ After Animation บนสไลด์ที่ 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
โคลนสไลด์แรกอีกครั้ง คราวนี้เปลี่ยนเอฟเฟกต์หลังการเคลื่อนไหวเป็น "สี" ด้วยสีเขียว
## ขั้นตอนที่ 6: แก้ไขเอฟเฟกต์ After Animation บนสไลด์ที่ 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
โคลนสไลด์แรกอีกครั้ง โดยตั้งค่าเอฟเฟ็กต์หลังการเคลื่อนไหวเป็น "ซ่อนหลังการเคลื่อนไหว"
## ขั้นตอนที่ 7: บันทึกการนำเสนอที่แก้ไขแล้ว
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
บันทึกการนำเสนอที่แก้ไขแล้วโดยใช้เส้นทางไฟล์เอาท์พุตที่ระบุ
## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการควบคุมเอฟเฟกต์ภาพเคลื่อนไหวหลังการนำเสนอบนสไลด์โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว ทดลองใช้เอฟเฟกต์ภาพเคลื่อนไหวหลังการนำเสนอประเภทต่างๆ เพื่อสร้างการนำเสนอที่ไดนามิกและน่าสนใจยิ่งขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถใช้เอฟเฟ็กต์หลังการเคลื่อนไหวที่แตกต่างกันกับองค์ประกอบแต่ละองค์ประกอบภายในสไลด์ได้หรือไม่
ใช่ คุณสามารถทำได้ ทำซ้ำผ่านองค์ประกอบต่างๆ และปรับเอฟเฟกต์หลังการเคลื่อนไหวให้เหมาะสม
### Aspose.Slides เข้ากันได้กับ .NET เวอร์ชันล่าสุดหรือไม่
ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อให้มั่นใจถึงความเข้ากันได้กับเวอร์ชัน .NET framework ล่าสุด
### ฉันจะเพิ่มแอนิเมชั่นแบบกำหนดเองลงในสไลด์โดยใช้ Aspose.Slides ได้อย่างไร
อ้างอิงเอกสารประกอบ [ที่นี่](https://reference.aspose.com/slides/net/) สำหรับข้อมูลโดยละเอียดเกี่ยวกับการเพิ่มแอนิเมชั่นแบบกำหนดเอง
### Aspose.Slides รองรับรูปแบบไฟล์ใดบ้างสำหรับการบันทึกงานนำเสนอ?
Aspose.Slides รองรับรูปแบบต่างๆ เช่น PPTX, PPT, PDF และอื่นๆ อีกมากมาย โปรดดูเอกสารประกอบเพื่อดูรายการทั้งหมด
### ฉันจะได้รับการสนับสนุนหรือถามคำถามที่เกี่ยวข้องกับ Aspose.Slides ได้จากที่ไหน
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการโต้ตอบกับชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}