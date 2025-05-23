---
"description": "ปรับปรุงการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ควบคุมแอนิเมชันได้อย่างง่ายดาย ดึงดูดใจผู้ชม และสร้างความประทับใจไม่รู้ลืม"
"linktitle": "ทำซ้ำแอนิเมชั่นบนสไลด์"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "เรียนรู้การสร้างภาพเคลื่อนไหว PowerPoint ด้วย Aspose.Slides .NET"
"url": "/th/net/slide-animation-control/repeat-animation-on-slide/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เรียนรู้การสร้างภาพเคลื่อนไหว PowerPoint ด้วย Aspose.Slides .NET

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา ความสามารถในการควบคุมแอนิเมชั่นมีบทบาทสำคัญในการดึงดูดและดึงดูดความสนใจของผู้ชม Aspose.Slides สำหรับ .NET ช่วยให้ผู้พัฒนาสามารถควบคุมประเภทแอนิเมชั่นในสไลด์ได้ ทำให้การนำเสนอมีปฏิสัมพันธ์และน่าสนใจยิ่งขึ้น ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการควบคุมประเภทแอนิเมชั่นบนสไลด์โดยใช้ Aspose.Slides สำหรับ .NET ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มลงลึกในบทช่วยสอน ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Aspose.Slides สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [ที่นี่](https://releases-aspose.com/slides/net/).
2. สภาพแวดล้อมการพัฒนา .NET: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ
## นำเข้าเนมสเปซ
ในโครงการ .NET ของคุณ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานที่ Aspose.Slides จัดให้:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
สร้างไดเร็กทอรีใหม่สำหรับโปรเจ็กต์ของคุณและสร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อแสดงไฟล์การนำเสนอ
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
## ขั้นตอนที่ 2: ลำดับผลการเข้าถึง
ดึงข้อมูลลำดับเอฟเฟกต์สำหรับสไลด์แรกโดยใช้คุณสมบัติ MainSequence
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## ขั้นตอนที่ 3: เข้าถึงเอฟเฟกต์แรก
รับผลแรกของลำดับหลักเพื่อควบคุมคุณสมบัติของมัน
```csharp
IEffect effect = effectsSequence[0];
```
## ขั้นตอนที่ 4: แก้ไขการตั้งค่าการทำซ้ำ
เปลี่ยนคุณสมบัติการจับเวลา/การทำซ้ำของเอฟเฟกต์เป็น "จนกว่าจะสิ้นสุดสไลด์"
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขเพื่อแสดงการเปลี่ยนแปลง
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
ทำซ้ำขั้นตอนเหล่านี้เพื่อรับเอฟเฟกต์เพิ่มเติมหรือปรับแต่งตามความต้องการในการนำเสนอของคุณ
## บทสรุป
การรวมแอนิเมชั่นแบบไดนามิกในงานนำเสนอ PowerPoint ของคุณไม่เคยง่ายอย่างนี้มาก่อนด้วย Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณมีความรู้ในการควบคุมประเภทแอนิเมชั่น รับรองว่าสไลด์ของคุณจะสร้างความประทับใจให้กับผู้ชมได้ไม่รู้ลืม
## คำถามที่พบบ่อย
### ฉันสามารถใช้แอนิเมชั่นเหล่านี้กับวัตถุที่เจาะจงภายในสไลด์ได้หรือไม่
ใช่ คุณสามารถกำหนดเป้าหมายวัตถุเฉพาะได้โดยการเข้าถึงเอฟเฟกต์แต่ละรายการภายในลำดับ
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดได้หรือไม่
Aspose.Slides รองรับ PowerPoint เวอร์ชันต่างๆ มากมาย เพื่อให้เข้ากันได้กับทั้งเวอร์ชันเก่าและใหม่
### ฉันสามารถหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมได้ที่ไหน
สำรวจ [เอกสารประกอบ](https://reference.aspose.com/slides/net/) เพื่อตัวอย่างที่ครอบคลุมและคำอธิบายโดยละเอียด
### ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
เยี่ยม [ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อสอบถามข้อมูลในการขอใบอนุญาตชั่วคราว
### ต้องการความช่วยเหลือหรือมีคำถามเพิ่มเติมหรือไม่?
มีส่วนร่วมกับชุมชน Aspose.Slides บน [ฟอรั่มสนับสนุน](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}