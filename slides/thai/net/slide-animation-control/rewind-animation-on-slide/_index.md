---
"description": "เรียนรู้วิธีการย้อนกลับแอนิเมชั่นบนสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้ซึ่งมีตัวอย่างโค้ดต้นฉบับครบถ้วน"
"linktitle": "การย้อนกลับแอนิเมชั่นบนสไลด์"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "เรียนรู้การย้อนกลับแอนิเมชั่นในงานนำเสนอด้วย Aspose.Slides"
"url": "/th/net/slide-animation-control/rewind-animation-on-slide/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เรียนรู้การย้อนกลับแอนิเมชั่นในงานนำเสนอด้วย Aspose.Slides

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา การนำแอนิเมชั่นที่น่าดึงดูดใจมาใช้สามารถช่วยเพิ่มการมีส่วนร่วมได้อย่างมาก Aspose.Slides สำหรับ .NET มอบชุดเครื่องมืออันทรงพลังที่จะช่วยให้การนำเสนอของคุณมีชีวิตชีวาขึ้น คุณลักษณะที่น่าสนใจอย่างหนึ่งคือความสามารถในการย้อนกลับแอนิเมชั่นบนสไลด์ ในคู่มือฉบับสมบูรณ์นี้ เราจะแนะนำคุณทีละขั้นตอน เพื่อให้คุณใช้ประโยชน์จากการย้อนกลับแอนิเมชั่นได้อย่างเต็มที่โดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว หากยังไม่ได้ติดตั้ง ให้ดาวน์โหลดจาก [เอกสาร Aspose.Slides สำหรับ .NET](https://reference-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา .NET: ให้แน่ใจว่าคุณมีการตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ทำงานอยู่
- ความรู้พื้นฐานเกี่ยวกับ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันที่ Aspose.Slides จัดทำไว้สำหรับ .NET นี่คือตัวอย่างเพื่อเป็นแนวทาง:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ใหม่ในสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณหากไม่มีอยู่
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
สร้างตัวอย่าง `Presentation` ชั้นเรียนเพื่อแสดงไฟล์การนำเสนอของคุณ
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // โค้ดของคุณสำหรับขั้นตอนถัดไปอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: ลำดับผลการเข้าถึง
ดึงลำดับเอฟเฟกต์สำหรับสไลด์แรก
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## ขั้นตอนที่ 4: ปรับเปลี่ยนเวลาเอฟเฟกต์
เข้าถึงเอฟเฟกต์แรกของลำดับหลักและแก้ไขเวลาเพื่อให้สามารถย้อนกลับได้
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอที่ปรับเปลี่ยนแล้ว
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## ขั้นตอนที่ 6: ตรวจสอบเอฟเฟกต์การย้อนกลับในการนำเสนอปลายทาง
โหลดงานนำเสนอที่แก้ไขแล้วและตรวจสอบดูว่ามีการใช้เอฟเฟ็กต์ย้อนกลับหรือไม่
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับสไลด์เพิ่มเติม หรือปรับแต่งกระบวนการตามโครงสร้างการนำเสนอของคุณ
## บทสรุป
การปลดล็อกฟีเจอร์การย้อนกลับแอนิเมชั่นใน Aspose.Slides สำหรับ .NET เปิดโอกาสให้สร้างสรรค์งานนำเสนอที่มีชีวิตชีวาและน่าสนใจได้มากมาย ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถผสานการย้อนกลับแอนิเมชั่นเข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น ช่วยเพิ่มความสวยงามให้กับสไลด์ของคุณ
---
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ .NET เข้ากันได้กับ .NET framework เวอร์ชันล่าสุดหรือไม่
Aspose.Slides สำหรับ .NET ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าเข้ากันได้กับเวอร์ชัน .NET framework ล่าสุด ตรวจสอบ [เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับรายละเอียดความเข้ากันได้
### ฉันสามารถใช้แอนิเมชั่นย้อนกลับกับวัตถุที่เจาะจงภายในสไลด์ได้หรือไม่
ใช่ คุณสามารถปรับแต่งโค้ดเพื่อใช้แอนิเมชั่นการย้อนกลับเฉพาะกับวัตถุหรือองค์ประกอบเฉพาะภายในสไลด์ได้
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ .NET หรือไม่
ใช่ คุณสามารถสำรวจคุณสมบัติต่างๆ ได้โดยการขอรับรุ่นทดลองใช้งานฟรีจาก [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อแสวงหาความช่วยเหลือและมีส่วนร่วมกับชุมชน
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase-aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}