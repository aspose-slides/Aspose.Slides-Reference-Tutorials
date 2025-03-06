---
title: แปลงการนำเสนอเป็นรูปแบบ HTML5
linktitle: แปลงการนำเสนอเป็นรูปแบบ HTML5
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ HTML5 โดยใช้ Aspose.Slides สำหรับ .NET การแปลงที่ง่ายและมีประสิทธิภาพสำหรับการแชร์เว็บ
weight: 22
url: /th/net/presentation-conversion/convert-presentation-to-html5-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงการนำเสนอเป็นรูปแบบ HTML5

## แปลงการนำเสนอเป็นรูปแบบ HTML5 โดยใช้ Aspose.Slides สำหรับ .NET

ในคู่มือนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงงานนำเสนอ PowerPoint (PPT/PPTX) เป็นรูปแบบ HTML5 โดยใช้ไลบรารี Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีอันทรงพลังที่ให้คุณจัดการและแปลงงานนำเสนอ PowerPoint ในรูปแบบต่างๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Visual Studio: คุณต้องติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ .NET จาก[ที่นี่](https://downloads.aspose.com/slides/net).

## ขั้นตอนการแปลง

ทำตามขั้นตอนเหล่านี้เพื่อแปลงงานนำเสนอเป็นรูปแบบ HTML5:

### สร้างโครงการใหม่

เปิด Visual Studio และสร้างโครงการใหม่

### เพิ่มการอ้างอิงถึง Aspose.Slides

ในโครงการของคุณ คลิกขวาที่ "การอ้างอิง" ใน Solution Explorer และเลือก "เพิ่มการอ้างอิง" เรียกดูและเพิ่ม Aspose.Slides DLL ที่คุณดาวน์โหลด

### เขียนโค้ดการแปลง

ในตัวแก้ไขโค้ด ให้เขียนโค้ดต่อไปนี้เพื่อแปลงงานนำเสนอเป็นรูปแบบ HTML5:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

namespace PresentationToHTML5Converter
{
    class Program
    {
        static void Main(string[] args)
        {
            // โหลดงานนำเสนอ
            using (Presentation presentation = new Presentation("input.pptx"))
            {
                // กำหนดตัวเลือก HTML5
                Html5Options options = new Html5Options();

                // บันทึกการนำเสนอเป็น HTML5
                presentation.Save("output.html", SaveFormat.Html, options);
            }
        }
    }
}
```

 แทนที่`"input.pptx"` พร้อมเส้นทางสู่การนำเสนอข้อมูลของคุณและ`"output.html"` ด้วยเส้นทางไฟล์ HTML เอาต์พุตที่ต้องการ

## เรียกใช้แอปพลิเคชัน

สร้างและรันแอปพลิเคชันของคุณ มันจะแปลงงานนำเสนอเป็นรูปแบบ HTML5 และบันทึกเป็นไฟล์ HTML

## บทสรุป

ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ HTML5 ได้อย่างง่ายดายโดยใช้ไลบรารี Aspose.Slides สำหรับ .NET ซึ่งช่วยให้คุณสามารถแบ่งปันงานนำเสนอของคุณบนเว็บโดยไม่ต้องใช้ซอฟต์แวร์ PowerPoint

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของเอาต์พุต HTML5 ได้อย่างไร

 คุณสามารถปรับแต่งลักษณะที่ปรากฏของเอาต์พุต HTML5 ได้โดยตั้งค่าตัวเลือกต่างๆ ใน`Html5Options`ระดับ. อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/net/aspose.slides.export/html5options) สำหรับตัวเลือกการปรับแต่งที่มีอยู่

### ฉันสามารถแปลงงานนำเสนอที่มีภาพเคลื่อนไหวและการเปลี่ยนภาพได้หรือไม่

ใช่ Aspose.Slides สำหรับ .NET รองรับการแปลงงานนำเสนอด้วยภาพเคลื่อนไหวและการเปลี่ยนเป็นรูปแบบ HTML5

### มี Aspose.Slides เวอร์ชันทดลองใช้งานหรือไม่

 ใช่ คุณสามารถรับ Aspose.Slides สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/net).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
