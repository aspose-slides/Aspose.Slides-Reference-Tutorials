---
title: การสร้างรูปขนาดย่อพร้อมปัจจัยมาตราส่วนสำหรับรูปร่างใน Aspose.Slides
linktitle: การสร้างรูปขนาดย่อพร้อมปัจจัยมาตราส่วนสำหรับรูปร่างใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีการสร้างภาพขนาดย่อของ PowerPoint ที่มีขอบเขตเฉพาะโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 12
url: /th/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมของเราเกี่ยวกับการสร้างภาพขนาดย่อที่มีขอบเขตสำหรับรูปร่างใน Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานร่วมกับงานนำเสนอ PowerPoint ในแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการสร้างภาพขนาดย่อที่มีขอบเขตเฉพาะสำหรับรูปร่างภายในงานนำเสนอโดยใช้ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาที่เหมาะสมสำหรับ .NET เช่น Visual Studio ที่ติดตั้งบนเครื่องของคุณ
## นำเข้าเนมสเปซ
ในแอปพลิเคชัน .NET ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าการนำเสนอ
เริ่มต้นด้วยการสร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์งานนำเสนอ PowerPoint ที่คุณต้องการใช้งาน:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // รหัสของคุณสำหรับการสร้างภาพขนาดย่ออยู่ที่นี่
}
```
## ขั้นตอนที่ 2: สร้างภาพขนาดเต็ม
ภายในบล็อกการนำเสนอ ให้สร้างรูปภาพขนาดเต็มของรูปร่างที่คุณต้องการสร้างภาพขนาดย่อ:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // รหัสของคุณสำหรับการบันทึกภาพอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: บันทึกรูปภาพลงดิสก์
บันทึกอิมเมจที่สร้างขึ้นลงดิสก์ โดยระบุรูปแบบ (ในกรณีนี้คือ PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีสร้างภาพขนาดย่อที่มีขอบเขตสำหรับรูปร่างโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว คุณลักษณะนี้มีประโยชน์อย่างเหลือเชื่อเมื่อคุณต้องการสร้างรูปภาพขนาดเฉพาะของรูปร่างภายในงานนำเสนอ PowerPoint ของคุณโดยทางโปรแกรม
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Slides กับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ใช่ Aspose.Slides เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ ซึ่งให้ความยืดหยุ่นในการรวมเข้ากับแอปพลิเคชันประเภทต่างๆ
### คำถามที่ 2: Aspose.Slides มีเวอร์ชันทดลองใช้งานหรือไม่
 ใช่ คุณสามารถสำรวจฟังก์ชันการทำงานของ Aspose.Slides ได้ด้วยการดาวน์โหลดเวอร์ชันทดลองใช้งาน[ที่นี่](https://releases.aspose.com/).
### คำถามที่ 3: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้โดยไปที่[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).
### คำถามที่ 4: ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือ โปรดไปที่ฟอรัมสนับสนุน Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
### คำถามที่ 5: ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้หรือไม่
 แน่นอน! หากต้องการซื้อ Aspose.Slides สำหรับ .NET โปรดไปที่หน้าการซื้อ[ที่นี่](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
