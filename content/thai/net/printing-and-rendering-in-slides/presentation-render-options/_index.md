---
title: ตัวเลือกการแสดงผล Aspose.Slides - ยกระดับการนำเสนอของคุณ
linktitle: สำรวจตัวเลือกการเรนเดอร์สำหรับสไลด์การนำเสนอใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: สำรวจ Aspose.Slides สำหรับตัวเลือกการเรนเดอร์ .NET ปรับแต่งแบบอักษร เลย์เอาต์ และอื่นๆ เพื่อการนำเสนอที่น่าหลงใหล ปรับปรุงสไลด์ของคุณได้อย่างง่ายดาย
type: docs
weight: 15
url: /th/net/printing-and-rendering-in-slides/presentation-render-options/
---
การสร้างงานนำเสนอที่น่าทึ่งมักเกี่ยวข้องกับการปรับแต่งตัวเลือกการเรนเดอร์อย่างละเอียดเพื่อให้ได้ผลลัพธ์ทางภาพที่ต้องการ ในบทช่วยสอนนี้ เราจะเจาะลึกเข้าไปในโลกของตัวเลือกการเรนเดอร์สำหรับสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามเพื่อค้นหาวิธีเพิ่มประสิทธิภาพการนำเสนอของคุณด้วยขั้นตอนและตัวอย่างโดยละเอียด
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มการผจญภัยในการเรนเดอร์นี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides พบกับห้องสมุดได้ที่[ลิงค์นี้](https://releases.aspose.com/slides/net/).
- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณและจดจำเส้นทาง คุณจะต้องใช้มันสำหรับตัวอย่างโค้ด
## นำเข้าเนมสเปซ
ในแอปพลิเคชัน .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## ขั้นตอนที่ 1: โหลดการนำเสนอและกำหนดตัวเลือกการเรนเดอร์
เริ่มต้นด้วยการโหลดงานนำเสนอของคุณและกำหนดตัวเลือกการเรนเดอร์ ในตัวอย่างที่กำหนด เราใช้ไฟล์ PowerPoint ชื่อ "RenderingOptions.pptx"
```csharp
string dataDir = "Your Document Directory";
string presPath = Path.Combine(dataDir, "RenderingOptions.pptx");
using (Presentation pres = new Presentation(presPath))
{
    IRenderingOptions renderingOpts = new RenderingOptions();
    // สามารถตั้งค่าตัวเลือกการเรนเดอร์เพิ่มเติมได้ที่นี่
}
```
## ขั้นตอนที่ 2: ปรับแต่งเค้าโครงบันทึกย่อ
ปรับเค้าโครงบันทึกย่อในสไลด์ของคุณ ในตัวอย่างนี้ เราตั้งค่าตำแหน่งบันทึกย่อเป็น "BottomTruncated"
```csharp
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderingOpts.SlidesLayoutOptions = notesOptions;
```
## ขั้นตอนที่ 3: สร้างภาพขนาดย่อด้วยแบบอักษรที่แตกต่างกัน
สำรวจผลกระทบของแบบอักษรต่างๆ ในงานนำเสนอของคุณ สร้างภาพขนาดย่อด้วยการตั้งค่าแบบอักษรเฉพาะ
## ขั้นตอนที่ 3.1: แบบอักษรดั้งเดิม
```csharp
pres.Slides[0].GetThumbnail(renderingOpts, 4 / 3f, 4 / 3f).Save(Path.Combine(RunExamples.OutPath, "RenderingOptions-Slide1-Original.png"), ImageFormat.Png);
```
## ขั้นตอนที่ 3.2: แบบอักษรเริ่มต้นของ Arial Black
```csharp
renderingOpts.SlidesLayoutOptions = null;
renderingOpts.DefaultRegularFont = "Arial Black";
pres.Slides[0].GetThumbnail(renderingOpts, 4 / 3f, 4 / 3f).Save(Path.Combine(RunExamples.OutPath, "RenderingOptions-Slide1-ArialBlackDefault.png"), ImageFormat.Png);
```
## ขั้นตอนที่ 3.3: แบบอักษรเริ่มต้น Arial Narrow
```csharp
renderingOpts.DefaultRegularFont = "Arial Narrow";
pres.Slides[0].GetThumbnail(renderingOpts, 4 / 3f, 4 / 3f).Save(Path.Combine(RunExamples.OutPath, "RenderingOptions-Slide1-ArialNarrowDefault.png"), ImageFormat.Png);
```
ทดลองใช้แบบอักษรต่างๆ เพื่อค้นหาแบบอักษรที่เข้ากับสไตล์การนำเสนอของคุณ
## บทสรุป
การเพิ่มประสิทธิภาพตัวเลือกการเรนเดอร์ใน Aspose.Slides สำหรับ .NET มอบวิธีที่มีประสิทธิภาพในการปรับปรุงรูปลักษณ์ที่สวยงามของงานนำเสนอของคุณ ทดลองใช้การตั้งค่าต่างๆ เพื่อให้ได้ผลลัพธ์ที่ต้องการและดึงดูดผู้ชมของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งตำแหน่งของบันทึกย่อในทุกสไลด์ได้หรือไม่
 ตอบ: ได้ โดยการปรับ`NotesPosition` ทรัพย์สินใน`NotesCommentsLayoutingOptions`.
### ถาม: ฉันจะเปลี่ยนแบบอักษรเริ่มต้นสำหรับงานนำเสนอทั้งหมดได้อย่างไร
 ตอบ: ตั้งค่า`DefaultRegularFont` คุณสมบัติในตัวเลือกการเรนเดอร์เป็นแบบอักษรที่คุณต้องการ
### ถาม: มีตัวเลือกเค้าโครงเพิ่มเติมสำหรับสไลด์หรือไม่
ตอบ: ได้ โปรดดูเอกสารประกอบของ Aspose.Slides เพื่อดูรายการตัวเลือกเค้าโครงที่ครอบคลุม
### ถาม: ฉันสามารถใช้แบบอักษรแบบกำหนดเองที่ไม่ได้ติดตั้งบนระบบของฉันได้หรือไม่
 ตอบ: ใช่ ระบุเส้นทางไฟล์ฟอนต์โดยใช้ไฟล์`AddFonts` วิธีการใน`FontsLoader` ระดับ.
### ถาม: ฉันจะขอความช่วยเหลือหรือติดต่อกับชุมชนได้ที่ไหน
ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อการสนับสนุนและการมีส่วนร่วมของชุมชน