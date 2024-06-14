---
title: การแสดงความคิดเห็นสไลด์ใน Aspose.Slides
linktitle: การแสดงความคิดเห็นสไลด์ใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: สำรวจวิธีแสดงความคิดเห็นเกี่ยวกับสไลด์ใน Aspose.Slides สำหรับ .NET ด้วยบทช่วยสอนทีละขั้นตอนของเรา ปรับแต่งลักษณะที่ปรากฏของความคิดเห็นและยกระดับการทำงานอัตโนมัติของ PowerPoint ของคุณ
type: docs
weight: 12
url: /th/net/printing-and-rendering-in-slides/rendering-slide-comments/
---
## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมของเราเกี่ยวกับการแสดงความคิดเห็นเกี่ยวกับสไลด์โดยใช้ Aspose.Slides สำหรับ .NET! Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานร่วมกับงานนำเสนอ PowerPoint ในแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ในคู่มือนี้ เราจะเน้นที่งานเฉพาะ นั่นคือ การแสดงข้อคิดเห็นของสไลด์ และแนะนำคุณตลอดกระบวนการทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
-  Aspose.Slides สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้ และมีความเข้าใจพื้นฐานเกี่ยวกับ C#
เอาล่ะ เรามาเริ่มด้วยบทช่วยสอนกันดีกว่า!
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้คุณสมบัติ Aspose.Slides เพิ่มบรรทัดต่อไปนี้ที่จุดเริ่มต้นของไฟล์:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ
เริ่มต้นด้วยการระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีการนำเสนอ PowerPoint:
```csharp
string dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: ระบุเส้นทางเอาต์พุต
กำหนดเส้นทางที่คุณต้องการบันทึกรูปภาพที่แสดงผลพร้อมความคิดเห็น:
```csharp
string resultPath = Path.Combine(dataDir, "OutPresBitmap_Comments.png");
```
## ขั้นตอนที่ 3: โหลดการนำเสนอ
โหลดงานนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides:
```csharp
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## ขั้นตอนที่ 4: สร้างบิตแมปสำหรับการเรนเดอร์
สร้างวัตถุบิตแมปด้วยขนาดที่ต้องการ:
```csharp
Bitmap bmp = new Bitmap(740, 960);
```
## ขั้นตอนที่ 5: กำหนดค่าตัวเลือกการแสดงผล
กำหนดค่าตัวเลือกการแสดงผล รวมถึงตัวเลือกเค้าโครงสำหรับบันทึกย่อและความคิดเห็น:
```csharp
IRenderingOptions renderOptions = new RenderingOptions();
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.CommentsAreaColor = Color.Red;
notesOptions.CommentsAreaWidth = 200;
notesOptions.CommentsPosition = CommentsPositions.Right;
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderOptions.SlidesLayoutOptions = notesOptions;
```
## ขั้นตอนที่ 6: แสดงผลเป็นกราฟิก
แสดงสไลด์แรกพร้อมความคิดเห็นไปยังวัตถุกราฟิกที่ระบุ:
```csharp
using (Graphics graphics = Graphics.FromImage(bmp))
{
    pres.Slides[0].RenderToGraphics(renderOptions, graphics);
}
```
## ขั้นตอนที่ 7: บันทึกผลลัพธ์
บันทึกภาพที่แสดงผลพร้อมความคิดเห็นไปยังเส้นทางที่ระบุ:
```csharp
bmp.Save(resultPath, ImageFormat.Png);
```
## ขั้นตอนที่ 8: แสดงผล
เปิดภาพที่แสดงผลโดยใช้โปรแกรมดูรูปภาพเริ่มต้น:
```csharp
System.Diagnostics.Process.Start(resultPath);
```
ยินดีด้วย! คุณแสดงความเห็นเกี่ยวกับสไลด์ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการแสดงความเห็นเกี่ยวกับสไลด์โดยใช้ Aspose.Slides สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณจะสามารถเพิ่มความสามารถอัตโนมัติของ PowerPoint ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: Aspose.Slides เข้ากันได้กับเฟรมเวิร์ก .NET เวอร์ชันล่าสุดหรือไม่
ตอบ: ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อรองรับเวอร์ชันเฟรมเวิร์ก .NET ล่าสุด
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของความคิดเห็นที่แสดงผลได้หรือไม่
ตอบ: แน่นอน! บทช่วยสอนนี้มีตัวเลือกในการปรับแต่งสี ความกว้าง และตำแหน่งของพื้นที่แสดงความคิดเห็น
### ถาม: ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 ตอบ: สำรวจเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/net/).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะขอความช่วยเหลือและสนับสนุน Aspose.Slides ได้ที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อสนับสนุนชุมชน