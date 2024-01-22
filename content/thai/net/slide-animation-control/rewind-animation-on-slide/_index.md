---
title: การเรียนรู้ภาพเคลื่อนไหวย้อนกลับในการนำเสนอด้วย Aspose.Slides
linktitle: กรอกลับภาพเคลื่อนไหวบนสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีกรอกลับภาพเคลื่อนไหวบนสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมตัวอย่างซอร์สโค้ดที่สมบูรณ์
type: docs
weight: 13
url: /th/net/slide-animation-control/rewind-animation-on-slide/
---
## การแนะนำ
ในโลกการนำเสนอที่ไม่หยุดนิ่ง การผสมผสานแอนิเมชั่นที่น่าดึงดูดจะช่วยเพิ่มการมีส่วนร่วมได้อย่างมาก Aspose.Slides สำหรับ .NET มอบชุดเครื่องมืออันทรงพลังที่จะทำให้การนำเสนอของคุณมีชีวิตชีวา คุณสมบัติที่น่าสนใจประการหนึ่งคือความสามารถในการกรอกลับภาพเคลื่อนไหวบนสไลด์ ในคู่มือที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน ซึ่งช่วยให้คุณสามารถควบคุมศักยภาพเต็มรูปแบบของการกรอกลับแอนิเมชันโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว ถ้าไม่เช่นนั้น ให้ดาวน์โหลดจาก[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา .NET: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้
- ความรู้พื้นฐาน C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานที่ Aspose.Slides สำหรับ .NET มอบให้ นี่เป็นตัวอย่างเพื่อแนะนำคุณ:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการใหม่ในสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณหากไม่มีอยู่
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงไฟล์การนำเสนอของคุณ
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // รหัสของคุณสำหรับขั้นตอนต่อไปอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: ลำดับเอฟเฟกต์การเข้าถึง
ดึงลำดับเอฟเฟกต์สำหรับสไลด์แรก
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## ขั้นตอนที่ 4: แก้ไขการกำหนดเวลาเอฟเฟกต์
เข้าถึงเอฟเฟกต์แรกของซีเควนซ์หลักและแก้ไขจังหวะเวลาเพื่อเปิดใช้งานการกรอกลับ
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไข
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## ขั้นตอนที่ 6: ตรวจสอบเอฟเฟกต์การกรอกลับในการนำเสนอปลายทาง
โหลดงานนำเสนอที่แก้ไขแล้วและตรวจสอบว่ามีการใช้เอฟเฟกต์การกรอกลับหรือไม่
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับสไลด์เพิ่มเติมหรือปรับแต่งกระบวนการตามโครงสร้างของงานนำเสนอของคุณ
## บทสรุป
Unlocking the rewind animation feature in Aspose.Slides for .NET opens up exciting possibilities for creating dynamic and engaging presentations. By following this step-by-step guide, you can seamlessly integrate animation rewind into your projects, enhancing the visual appeal of your slides.
---
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ .NET เข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ล่าสุดหรือไม่
 Aspose.Slides สำหรับ .NET ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าสามารถเข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ล่าสุด ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับรายละเอียดความเข้ากันได้
### ฉันสามารถใช้ภาพเคลื่อนไหวแบบย้อนกลับกับวัตถุเฉพาะภายในสไลด์ได้หรือไม่
ได้ คุณสามารถปรับแต่งโค้ดเพื่อใช้ภาพเคลื่อนไหวแบบกรอกลับกับวัตถุหรือองค์ประกอบเฉพาะภายในสไลด์ได้
### มีรุ่นทดลองใช้สำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติต่างๆ ได้โดยการทดลองใช้ฟรีจาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุน Aspose.Slides สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือและมีส่วนร่วมกับชุมชน
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).