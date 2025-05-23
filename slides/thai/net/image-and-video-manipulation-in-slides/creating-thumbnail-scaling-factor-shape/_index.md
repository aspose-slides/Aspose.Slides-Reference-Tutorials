---
"description": "เรียนรู้การสร้างภาพย่อของ PowerPoint ที่มีขอบเขตเฉพาะโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการผสานรวมที่ราบรื่น"
"linktitle": "การสร้างภาพขนาดย่อด้วยปัจจัยการปรับขนาดสำหรับรูปร่างใน Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การสร้างภาพขนาดย่อด้วยปัจจัยการปรับขนาดสำหรับรูปร่างใน Aspose.Slides"
"url": "/th/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างภาพขนาดย่อด้วยปัจจัยการปรับขนาดสำหรับรูปร่างใน Aspose.Slides

## การแนะนำ
ยินดีต้อนรับสู่คู่มือที่ครอบคลุมของเราเกี่ยวกับการสร้างภาพขนาดย่อพร้อมขอบเขตสำหรับรูปร่างใน Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนาสามารถทำงานกับงานนำเสนอ PowerPoint ในแอปพลิเคชัน .NET ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกถึงกระบวนการสร้างภาพขนาดย่อพร้อมขอบเขตเฉพาะสำหรับรูปร่างภายในงานนำเสนอโดยใช้ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาที่เหมาะสมสำหรับ .NET เช่น Visual Studio ตั้งค่าบนเครื่องของคุณ
## นำเข้าเนมสเปซ
ในแอปพลิเคชัน .NET ของคุณ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าการนำเสนอ
เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาสการนำเสนอที่แสดงไฟล์การนำเสนอ PowerPoint ที่คุณต้องการใช้งาน:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // โค้ดของคุณสำหรับการสร้างภาพขนาดย่ออยู่ที่นี่
}
```
## ขั้นตอนที่ 2: สร้างภาพขนาดเต็ม
ภายในบล็อกการนำเสนอ ให้สร้างภาพขนาดเต็มของรูปร่างที่คุณต้องการสร้างภาพขนาดย่อ:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // โค้ดสำหรับบันทึกภาพของคุณอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: บันทึกภาพลงในดิสก์
บันทึกภาพที่สร้างขึ้นลงในดิสก์ โดยระบุรูปแบบ (ในกรณีนี้คือ PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีสร้างภาพขนาดย่อพร้อมขอบเขตสำหรับรูปร่างโดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว คุณลักษณะนี้อาจมีประโยชน์อย่างยิ่งเมื่อคุณต้องสร้างภาพขนาดเฉพาะของรูปร่างภายในงานนำเสนอ PowerPoint ของคุณโดยใช้โปรแกรม
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Slides ร่วมกับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ใช่ Aspose.Slides เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ ซึ่งให้ความยืดหยุ่นในการบูรณาการเข้ากับแอปพลิเคชันประเภทต่างๆ
### คำถามที่ 2: มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides หรือไม่
ใช่ คุณสามารถสำรวจฟังก์ชันการทำงานของ Aspose.Slides ได้โดยดาวน์โหลดเวอร์ชันทดลองใช้ [ที่นี่](https://releases-aspose.com/).
### คำถามที่ 3: ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
คุณสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้โดยเข้าไปที่ [ลิงค์นี้](https://purchase-aspose.com/temporary-license/).
### คำถามที่ 4: ฉันสามารถค้นหาการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
หากมีคำถามหรือต้องการความช่วยเหลือ โปรดไปที่ฟอรัมสนับสนุน Aspose.Slides [ที่นี่](https://forum-aspose.com/c/slides/11).
### คำถามที่ 5: ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้หรือไม่
แน่นอน! หากต้องการซื้อ Aspose.Slides สำหรับ .NET โปรดไปที่หน้าการซื้อ [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}