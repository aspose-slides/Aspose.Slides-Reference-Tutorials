---
title: เพิ่มความคิดเห็นลงในสไลด์
linktitle: เพิ่มความคิดเห็นลงในสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เพิ่มความลึกและการโต้ตอบให้กับงานนำเสนอของคุณด้วย Aspose.Slides API เรียนรู้วิธีรวมความคิดเห็นลงในสไลด์ของคุณอย่างง่ายดายโดยใช้ .NET เพิ่มการมีส่วนร่วมและดึงดูดผู้ชมของคุณ
type: docs
weight: 13
url: /th/net/slide-comments-manipulation/add-slide-comments/
---

ในโลกของการจัดการงานนำเสนอ ความสามารถในการเพิ่มความคิดเห็นลงในสไลด์อาจเป็นตัวเปลี่ยนเกมได้ ความคิดเห็นไม่เพียงแต่ช่วยเพิ่มการทำงานร่วมกันเท่านั้น แต่ยังช่วยในการทำความเข้าใจและแก้ไขเนื้อหาสไลด์อีกด้วย ด้วย Aspose.Slides สำหรับ .NET ซึ่งเป็นไลบรารี่ที่ทรงพลังและหลากหลาย คุณสามารถรวมความคิดเห็นไว้ในสไลด์การนำเสนอของคุณได้อย่างง่ายดาย ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการเพิ่มความคิดเห็นลงในสไลด์โดยใช้ Aspose.Slides สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ในโลกแห่งการพัฒนา .NET บทช่วยสอนนี้จะให้ข้อมูลเชิงลึกทั้งหมดที่คุณต้องการ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกคำแนะนำทีละขั้นตอน เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่จำเป็นในการเริ่มต้น:

1.  Aspose.Slides สำหรับ .NET: คุณต้องมี Aspose.Slides สำหรับ .NET ติดตั้งอยู่ หากคุณยังไม่มี คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเว็บไซต์ .NET](https://releases.aspose.com/slides/net/).

2. สภาพแวดล้อมการพัฒนา: คุณควรตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนระบบของคุณ

3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# นั้นมีประโยชน์ เนื่องจากเราจะใช้ C# เพื่อสาธิตการใช้งาน

เมื่อมีคุณสมบัติเบื้องต้นเหล่านี้แล้ว เรามาเจาะลึกกระบวนการเพิ่มความคิดเห็นลงในสไลด์ในงานนำเสนอของคุณกันดีกว่า

## นำเข้าเนมสเปซ

ขั้นแรก มาตั้งค่าสภาพแวดล้อมการพัฒนาของเราโดยการนำเข้าเนมสเปซที่จำเป็น

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

ตอนนี้เมื่อเราจัดเรียงข้อกำหนดเบื้องต้นและเนมสเปซแล้ว เราก็ไปยังคำแนะนำทีละขั้นตอนได้

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

เราจะเริ่มต้นด้วยการสร้างงานนำเสนอใหม่ที่เราสามารถเพิ่มความคิดเห็นลงในสไลด์ได้ โดยทำตามโค้ดด้านล่าง:

```csharp
string FilePath = @"..\..\..\..\Sample Files\";
string FileName = FilePath + "Add a comment to a slide.pptx";

using (Presentation pres = new Presentation())
{
    // การเพิ่มสไลด์เปล่า
    pres.Slides.AddEmptySlide(pres.LayoutSlides[0]);

    // กำลังเพิ่มผู้แต่ง
    ICommentAuthor author = pres.CommentAuthors.AddAuthor("Zeeshan", "MZ");

    // ตำแหน่งของความคิดเห็น
    PointF point = new PointF();
    point.X = 1;
    point.Y = 1;

    // การเพิ่มความคิดเห็นของสไลด์สำหรับผู้แต่งบนสไลด์
    author.Comments.AddComment("Hello Zeeshan, this is a slide comment", pres.Slides[0], point, DateTime.Now);
    
    // บันทึกการนำเสนอ
    pres.Save(FileName, SaveFormat.Pptx);
}
```

เรามาดูรายละเอียดสิ่งที่เกิดขึ้นในโค้ดนี้กันดีกว่า:

-  เราเริ่มต้นด้วยการสร้างงานนำเสนอใหม่โดยใช้`Presentation()`.
- ต่อไป เราจะเพิ่มสไลด์เปล่าลงในงานนำเสนอ
-  เราเพิ่มผู้เขียนสำหรับความคิดเห็นโดยใช้`ICommentAuthor`.
-  เรากำหนดตำแหน่งสำหรับความคิดเห็นบนสไลด์โดยใช้`PointF`.
- เราเพิ่มความคิดเห็นลงในสไลด์เพื่อให้ผู้เขียนใช้`author.Comments.AddComment()`.
- สุดท้าย เราจะบันทึกงานนำเสนอพร้อมเพิ่มความคิดเห็น

รหัสนี้สร้างงานนำเสนอ PowerPoint พร้อมความคิดเห็นในสไลด์แรก คุณสามารถปรับแต่งชื่อผู้เขียน ข้อความแสดงความคิดเห็น และพารามิเตอร์อื่นๆ ได้ตามความต้องการของคุณ

ด้วยขั้นตอนเหล่านี้ คุณได้เพิ่มความคิดเห็นลงในสไลด์โดยใช้ Aspose.Slides สำหรับ .NET ได้สำเร็จ ตอนนี้คุณสามารถยกระดับการจัดการการนำเสนอของคุณไปอีกระดับโดยปรับปรุงการทำงานร่วมกันและการสื่อสารกับทีมหรือผู้ชมของคุณ

## บทสรุป

การเพิ่มความคิดเห็นลงในสไลด์เป็นคุณสมบัติที่มีคุณค่าสำหรับผู้ที่ทำงานกับการนำเสนอ ไม่ว่าจะเป็นสำหรับโครงการความร่วมมือหรือวัตถุประสงค์ทางการศึกษา Aspose.Slides สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณสร้าง แก้ไข และจัดการความคิดเห็นได้อย่างง่ายดาย ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณจะสามารถควบคุมประสิทธิภาพของ Aspose.Slides สำหรับ .NET เพื่อปรับปรุงการนำเสนอของคุณได้

 หากคุณพบปัญหาหรือมีคำถาม อย่าลังเลที่จะขอความช่วยเหลือได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/).

---

## คำถามที่พบบ่อย

### 1. ฉันจะปรับแต่งลักษณะที่ปรากฏของความคิดเห็นใน Aspose.Slides สำหรับ .NET ได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของความคิดเห็นได้โดยการแก้ไขคุณสมบัติต่างๆ เช่น สี ขนาด และแบบอักษร โดยใช้ไลบรารี Aspose.Slides ตรวจสอบเอกสารสำหรับคำแนะนำโดยละเอียด

### 2. ฉันสามารถเพิ่มความคิดเห็นให้กับองค์ประกอบเฉพาะภายในสไลด์ เช่น รูปร่างหรือรูปภาพ ได้หรือไม่

ใช่ Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถเพิ่มความคิดเห็นได้ไม่เพียงแต่กับทั้งสไลด์เท่านั้น แต่ยังรวมไปถึงองค์ประกอบแต่ละรายการภายในสไลด์ด้วย เช่น รูปร่างหรือรูปภาพ

### 3. Aspose.Slides สำหรับ .NET เข้ากันได้กับไฟล์ PowerPoint เวอร์ชันต่างๆ หรือไม่

ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบไฟล์ PowerPoint หลากหลาย รวมถึง PPTX, PPT และอื่นๆ

### 4. ฉันจะรวม Aspose.Slides สำหรับ .NET เข้ากับแอปพลิเคชัน .NET ของฉันได้อย่างไร

หากต้องการรวม Aspose.Slides สำหรับ .NET เข้ากับแอปพลิเคชัน .NET ของคุณ โปรดดูเอกสารประกอบที่ให้ข้อมูลโดยละเอียดเกี่ยวกับการติดตั้งและการใช้งาน

### 5. ฉันสามารถลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อได้หรือไม่

ได้ คุณสามารถสำรวจ Aspose.Slides สำหรับ .NET ได้โดยใช้รุ่นทดลองใช้ฟรี เยี่ยมชม[หน้าทดลองใช้ฟรี Aspose.Slides](https://releases.aspose.com/) ที่จะเริ่มต้น.