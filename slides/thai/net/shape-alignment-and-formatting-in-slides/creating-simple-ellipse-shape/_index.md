---
title: สร้างรูปร่างวงรีได้อย่างง่ายดายด้วย Aspose.Slides .NET
linktitle: การสร้างรูปร่างวงรีอย่างง่ายในสไลด์การนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างรูปทรงวงรีที่น่าทึ่งในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ขั้นตอนง่ายๆ สำหรับการออกแบบไดนามิก!
weight: 11
url: /th/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในโลกแบบไดนามิกของการออกแบบการนำเสนอ การผสมผสานรูปทรงต่างๆ เช่น วงรีสามารถเพิ่มความคิดสร้างสรรค์และความเป็นมืออาชีพได้ Aspose.Slides สำหรับ .NET นำเสนอโซลูชันอันทรงพลังสำหรับการจัดการไฟล์การนำเสนอโดยทางโปรแกรม บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างรูปร่างวงรีอย่างง่ายในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[หน้าเผยแพร่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
เนมสเปซเหล่านี้มีคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับสไลด์และรูปร่างการนำเสนอ
## ขั้นตอนที่ 1: ตั้งค่าการนำเสนอ
เริ่มต้นด้วยการสร้างงานนำเสนอใหม่และเข้าถึงสไลด์แรก เพิ่มรหัสต่อไปนี้เพื่อให้บรรลุสิ่งนี้:
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// ชั้นเรียนการนำเสนออินสแตนซ์
using (Presentation pres = new Presentation())
{
    // รับสไลด์แรก
    ISlide sld = pres.Slides[0];
```
โค้ดนี้เริ่มต้นการนำเสนอใหม่และเลือกสไลด์แรกเพื่อการจัดการเพิ่มเติม
## ขั้นตอนที่ 2: เพิ่มรูปร่างวงรี
 ตอนนี้ เรามาเพิ่มรูปร่างวงรีให้กับสไลด์โดยใช้`AddAutoShape` วิธี:
```csharp
// เพิ่มรูปร่างอัตโนมัติของประเภทวงรี
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
บรรทัดโค้ดนี้สร้างรูปร่างวงรีที่พิกัด (50, 150) โดยมีความกว้าง 150 หน่วยและสูง 50 หน่วย
## ขั้นตอนที่ 3: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขลงในดิสก์ด้วยชื่อไฟล์ที่ระบุโดยใช้รหัสต่อไปนี้:
```csharp
// เขียนไฟล์ PPTX ลงดิสก์
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
ขั้นตอนนี้ช่วยให้แน่ใจว่าการเปลี่ยนแปลงของคุณยังคงอยู่ และคุณสามารถดูงานนำเสนอผลลัพธ์ด้วยรูปร่างวงรีที่เพิ่มใหม่ได้
## บทสรุป
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งรูปร่างวงรีเพิ่มเติมได้หรือไม่
ได้ คุณสามารถปรับเปลี่ยนคุณสมบัติต่างๆ ของรูปร่างวงรีได้ เช่น สี ขนาด และตำแหน่ง เพื่อให้ตรงตามข้อกำหนดการออกแบบเฉพาะของคุณ
### Aspose.Slides เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่
ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าเข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุด
### ฉันจะหาบทช่วยสอนและตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 ปฏิบัติตาม[ลิงค์ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อขอใบอนุญาตชั่วคราวเพื่อการทดสอบ
### ต้องการความช่วยเหลือหรือมีคำถามเฉพาะเจาะจง?
 เยี่ยมชม[ฟอรั่มการสนับสนุน Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อรับความช่วยเหลือจากชุมชนและผู้เชี่ยวชาญ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
