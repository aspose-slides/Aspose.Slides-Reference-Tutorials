---
"description": "สำรวจวิธีการแสดงความเห็นในสไลด์ใน Aspose.Slides สำหรับ .NET ด้วยบทช่วยสอนแบบทีละขั้นตอนของเรา ปรับแต่งรูปลักษณ์ของความเห็นและยกระดับการทำงานอัตโนมัติของ PowerPoint ของคุณ"
"linktitle": "การแสดงความคิดเห็นสไลด์ใน Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การแสดงความคิดเห็นสไลด์ใน Aspose.Slides"
"url": "/th/net/printing-and-rendering-in-slides/rendering-slide-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การแสดงความคิดเห็นสไลด์ใน Aspose.Slides

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการเรนเดอร์คำอธิบายประกอบสไลด์โดยใช้ Aspose.Slides สำหรับ .NET! Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนาสามารถทำงานกับงานนำเสนอ PowerPoint ในแอปพลิเคชัน .NET ได้อย่างราบรื่น ในคู่มือนี้ เราจะเน้นที่งานเฉพาะอย่างหนึ่ง นั่นคือการเรนเดอร์คำอธิบายประกอบสไลด์ และจะพาคุณผ่านขั้นตอนต่างๆ ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มเรียนรู้บทช่วยสอน ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ไลบรารี Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET ไว้ในสภาพแวดล้อมการพัฒนาของคุณแล้ว หากยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้และมีความเข้าใจพื้นฐานเกี่ยวกับ C#
ตอนนี้เรามาเริ่มบทช่วยสอนกันเลย!
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟีเจอร์ Aspose.Slides เพิ่มบรรทัดต่อไปนี้ที่จุดเริ่มต้นของไฟล์ของคุณ:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ
เริ่มต้นด้วยการระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีการนำเสนอ PowerPoint อยู่:
```csharp
string dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: ระบุเส้นทางเอาต์พุต
กำหนดเส้นทางที่คุณต้องการบันทึกภาพที่เรนเดอร์พร้อมคำอธิบาย:
```csharp
string resultPath = Path.Combine(dataDir, "OutPresBitmap_Comments.png");
```
## ขั้นตอนที่ 3: โหลดงานนำเสนอ
โหลดการนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides:
```csharp
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## ขั้นตอนที่ 4: สร้างบิตแมปสำหรับการเรนเดอร์
สร้างวัตถุบิตแมปที่มีมิติตามต้องการ:
```csharp
Bitmap bmp = new Bitmap(740, 960);
```
## ขั้นตอนที่ 5: กำหนดค่าตัวเลือกการแสดงผล
กำหนดค่าตัวเลือกการแสดงผล รวมถึงตัวเลือกเค้าโครงสำหรับบันทึกและความคิดเห็น:
```csharp
IRenderingOptions renderOptions = new RenderingOptions();
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.CommentsAreaColor = Color.Red;
notesOptions.CommentsAreaWidth = 200;
notesOptions.CommentsPosition = CommentsPositions.Right;
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderOptions.SlidesLayoutOptions = notesOptions;
```
## ขั้นตอนที่ 6: เรนเดอร์เป็นกราฟิก
เรนเดอร์สไลด์แรกพร้อมคำอธิบายถึงวัตถุภาพกราฟิกที่ระบุ:
```csharp
using (Graphics graphics = Graphics.FromImage(bmp))
{
    pres.Slides[0].RenderToGraphics(renderOptions, graphics);
}
```
## ขั้นตอนที่ 7: บันทึกผลลัพธ์
บันทึกภาพที่เรนเดอร์พร้อมคำอธิบายลงในเส้นทางที่ระบุ:
```csharp
bmp.Save(resultPath, ImageFormat.Png);
```
## ขั้นตอนที่ 8: แสดงผลลัพธ์
เปิดภาพที่แสดงผลโดยใช้โปรแกรมดูรูปภาพเริ่มต้น:
```csharp
System.Diagnostics.Process.Start(resultPath);
```
ขอแสดงความยินดี! คุณได้แสดงความเห็นในสไลด์โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราจะมาสำรวจกระบวนการแสดงความเห็นในสไลด์โดยใช้ Aspose.Slides สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอน คุณจะสามารถปรับปรุงความสามารถในการทำงานอัตโนมัติของ PowerPoint ได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: Aspose.Slides เข้ากันได้กับเวอร์ชัน .NET framework ล่าสุดหรือไม่
ตอบ: ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อรองรับเวอร์ชัน .NET framework ล่าสุด
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของความคิดเห็นที่แสดงได้หรือไม่
A: แน่นอน! บทช่วยสอนนี้มีตัวเลือกในการปรับแต่งสี ความกว้าง และตำแหน่งของพื้นที่แสดงความคิดเห็น
### ถาม: ฉันสามารถหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้จากที่ใด
ก. สำรวจเอกสาร [ที่นี่](https://reference-aspose.com/slides/net/).
### ถาม: ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
A: คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ถาม: ฉันสามารถขอความช่วยเหลือและการสนับสนุนสำหรับ Aspose.Slides ได้จากที่ใด
ก. เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อการสนับสนุนชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}