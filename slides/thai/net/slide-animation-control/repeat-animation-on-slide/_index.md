---
title: การเรียนรู้ภาพเคลื่อนไหว PowerPoint ด้วย Aspose.Slides .NET
linktitle: ทำซ้ำภาพเคลื่อนไหวบนสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ควบคุมแอนิเมชั่นได้อย่างง่ายดาย ดึงดูดผู้ชม และสร้างความประทับใจไม่รู้ลืม
weight: 12
url: /th/net/slide-animation-control/repeat-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้ภาพเคลื่อนไหว PowerPoint ด้วย Aspose.Slides .NET

## การแนะนำ
ในโลกแห่งการนำเสนอแบบไดนามิก ความสามารถในการควบคุมแอนิเมชั่นมีบทบาทสำคัญในการมีส่วนร่วมและดึงดูดความสนใจของผู้ชม Aspose.Slides สำหรับ .NET ช่วยให้นักพัฒนาสามารถดูแลประเภทแอนิเมชั่นภายในสไลด์ได้ ช่วยให้นำเสนอแบบโต้ตอบและดึงดูดสายตามากขึ้น ในบทช่วยสอนนี้ เราจะสำรวจวิธีการควบคุมประเภทภาพเคลื่อนไหวบนสไลด์โดยใช้ Aspose.Slides สำหรับ .NET ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Slides สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[ที่นี่](https://releases.aspose.com/slides/net/).
2. สภาพแวดล้อมการพัฒนา .NET: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานที่ Aspose.Slides มอบให้:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
สร้างไดเร็กทอรีใหม่สำหรับโครงการของคุณและสร้างอินสแตนซ์คลาสการนำเสนอเพื่อแสดงไฟล์การนำเสนอ
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // รหัสของคุณอยู่ที่นี่
}
```
## ขั้นตอนที่ 2: ลำดับเอฟเฟกต์การเข้าถึง
ดึงลำดับเอฟเฟกต์สำหรับสไลด์แรกโดยใช้คุณสมบัติ MainSequence
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## ขั้นตอนที่ 3: เข้าถึงเอฟเฟกต์แรก
รับเอฟเฟกต์แรกของลำดับหลักเพื่อจัดการคุณสมบัติของมัน
```csharp
IEffect effect = effectsSequence[0];
```
## ขั้นตอนที่ 4: แก้ไขการตั้งค่าการทำซ้ำ
เปลี่ยนคุณสมบัติ Timing/Repeat ของเอฟเฟกต์เป็น "จนกระทั่งสิ้นสุดสไลด์"
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขเพื่อให้เห็นภาพการเปลี่ยนแปลง
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
ทำซ้ำขั้นตอนเหล่านี้เพื่อดูเอฟเฟ็กต์เพิ่มเติมหรือปรับแต่งตามความต้องการในการนำเสนอของคุณ
## บทสรุป
การรวมภาพเคลื่อนไหวแบบไดนามิกในงานนำเสนอ PowerPoint ของคุณง่ายกว่าที่เคยด้วย Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนนี้จะทำให้คุณมีความรู้ในการควบคุมประเภทแอนิเมชั่น เพื่อให้มั่นใจว่าสไลด์ของคุณจะสร้างความประทับใจไม่รู้ลืมให้กับผู้ชมของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ภาพเคลื่อนไหวเหล่านี้กับวัตถุเฉพาะภายในสไลด์ได้หรือไม่
ใช่ คุณสามารถกำหนดเป้าหมายวัตถุเฉพาะได้โดยการเข้าถึงเอฟเฟกต์แต่ละรายการภายในลำดับ
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดหรือไม่
Aspose.Slides ให้การสนับสนุน PowerPoint เวอร์ชันต่างๆ มากมาย ทำให้มั่นใจได้ถึงความเข้ากันได้กับเวอร์ชันเก่าและเวอร์ชันใหม่
### ฉันจะหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน
 สำรวจ[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับตัวอย่างที่ครอบคลุมและคำอธิบายโดยละเอียด
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 เยี่ยม[ที่นี่](https://purchase.aspose.com/temporary-license/) สำหรับข้อมูลเกี่ยวกับการขอรับใบอนุญาตชั่วคราว
### ต้องการความช่วยเหลือหรือมีคำถามเพิ่มเติม?
 มีส่วนร่วมกับชุมชน Aspose.Slides บน[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
