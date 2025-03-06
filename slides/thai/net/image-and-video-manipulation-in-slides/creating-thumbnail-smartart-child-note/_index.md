---
title: การสร้างภาพขนาดย่อสำหรับบันทึกย่อเด็ก SmartArt ใน Aspose.Slides
linktitle: การสร้างภาพขนาดย่อสำหรับบันทึกย่อเด็ก SmartArt ใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างภาพขนาดย่อ SmartArt Child Note ที่น่าดึงดูดใจโดยใช้ Aspose.Slides สำหรับ .NET ยกระดับการนำเสนอของคุณด้วยภาพแบบไดนามิก!
weight: 15
url: /th/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างภาพขนาดย่อสำหรับบันทึกย่อเด็ก SmartArt ใน Aspose.Slides

## การแนะนำ
ในขอบเขตของการนำเสนอแบบไดนามิก Aspose.Slides สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมืออันทรงพลัง ช่วยให้นักพัฒนาสามารถจัดการและปรับปรุงงานนำเสนอ PowerPoint โดยทางโปรแกรมได้ คุณสมบัติที่น่าสนใจประการหนึ่งคือความสามารถในการสร้างภาพขนาดย่อสำหรับ SmartArt Child Notes ซึ่งเพิ่มความน่าดึงดูดทางสายตาให้กับงานนำเสนอของคุณ คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการสร้างภาพขนาดย่อสำหรับ SmartArt Child Notes โดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Slides ที่รวมอยู่ในโปรเจ็กต์ .NET ของคุณ ถ้าไม่เช่นนั้น ให้ดาวน์โหลดจาก[หน้าเผยแพร่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้ และมีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
- การนำเสนอตัวอย่าง: สร้างหรือรับงานนำเสนอ PowerPoint ที่มี SmartArt พร้อม Child Notes สำหรับการทดสอบ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ เนมสเปซเหล่านี้ให้การเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับ Aspose.Slides
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ
 เริ่มต้นด้วยการยกตัวอย่าง`Presentation` คลาสซึ่งเป็นตัวแทนของไฟล์ PPTX ที่คุณจะใช้งาน
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่ม SmartArt
 ตอนนี้ เพิ่ม SmartArt ลงในสไลด์ภายในงานนำเสนอ ในตัวอย่างนี้ เรากำลังใช้`BasicCycle` เค้าโครง
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## ขั้นตอนที่ 3: รับการอ้างอิงโหนด
หากต้องการทำงานกับโหนดเฉพาะใน SmartArt ให้รับข้อมูลอ้างอิงโดยใช้ดัชนี
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## ขั้นตอนที่ 4: รับภาพขนาดย่อ
ดึงภาพขนาดย่อของ Child Note ภายในโหนด SmartArt
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## ขั้นตอนที่ 5: บันทึกภาพขนาดย่อ
บันทึกภาพขนาดย่อที่สร้างขึ้นไปยังไดเร็กทอรีที่ระบุ
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับโหนด SmartArt แต่ละโหนดในงานนำเสนอของคุณ โดยปรับแต่งเค้าโครงและสไตล์ตามต้องการ
## บทสรุป
โดยสรุป Aspose.Slides สำหรับ .NET ช่วยให้นักพัฒนาสามารถสร้างงานนำเสนอที่น่าสนใจได้อย่างง่ายดาย ความสามารถในการสร้างภาพขนาดย่อสำหรับ SmartArt Child Notes ช่วยเพิ่มความดึงดูดสายตาให้กับงานนำเสนอของคุณ โดยมอบประสบการณ์ผู้ใช้แบบโต้ตอบและไดนามิก
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถกำหนดขนาดและรูปแบบของภาพขนาดย่อที่สร้างขึ้นได้หรือไม่
ตอบ: ได้ คุณสามารถปรับขนาดและรูปแบบของภาพขนาดย่อได้โดยการแก้ไขพารามิเตอร์ที่เกี่ยวข้องในโค้ด
### ถาม: Aspose.Slides รองรับเค้าโครง SmartArt อื่นๆ หรือไม่
ตอบ: แน่นอน! Aspose.Slides มีเค้าโครง SmartArt ที่หลากหลาย ช่วยให้คุณสามารถเลือกเค้าโครงที่เหมาะกับความต้องการในการนำเสนอของคุณได้ดีที่สุด
### ถาม: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล
### ถาม: ฉันจะขอความช่วยเหลือหรือติดต่อกับชุมชน Aspose.Slides ได้ที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อมีส่วนร่วมกับชุมชน ถามคำถาม และค้นหาแนวทางแก้ไข
### ถาม: ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้หรือไม่
 ตอบ: แน่นอน! สำรวจตัวเลือกการซื้อ[ที่นี่](https://purchase.aspose.com/buy) เพื่อปลดล็อกศักยภาพสูงสุดของ Aspose.Slides ในโครงการของคุณ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
