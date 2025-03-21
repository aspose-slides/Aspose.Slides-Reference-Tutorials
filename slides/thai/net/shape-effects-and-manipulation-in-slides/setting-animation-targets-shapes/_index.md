---
title: การเรียนรู้เป้าหมายแอนิเมชั่นด้วย Aspose.Slides สำหรับ .NET
linktitle: การตั้งค่าเป้าหมายภาพเคลื่อนไหวสำหรับรูปร่างสไลด์การนำเสนอโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีทำให้งานนำเสนอของคุณมีชีวิตชีวาด้วย Aspose.Slides สำหรับ .NET! กำหนดเป้าหมายภาพเคลื่อนไหวได้อย่างง่ายดายและดึงดูดผู้ชมของคุณ
weight: 22
url: /th/net/shape-effects-and-manipulation-in-slides/setting-animation-targets-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้เป้าหมายแอนิเมชั่นด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก การเพิ่มภาพเคลื่อนไหวลงในสไลด์ของคุณอาจเป็นตัวเปลี่ยนเกมได้ Aspose.Slides สำหรับ .NET ช่วยให้นักพัฒนาสามารถสร้างงานนำเสนอที่น่าดึงดูดและดึงดูดสายตาโดยให้การควบคุมเป้าหมายแอนิเมชั่นสำหรับรูปร่างสไลด์ได้อย่างแม่นยำ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่าเป้าหมายภาพเคลื่อนไหวโดยใช้ Aspose.Slides สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนนี้จะช่วยให้คุณควบคุมพลังของแอนิเมชั่นในการนำเสนอของคุณได้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้บนเครื่องของคุณ
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Slides เพิ่มข้อมูลโค้ดต่อไปนี้ในโครงการของคุณ:
```csharp
using System;
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Animation;
using Aspose.Slides.DOM.Ole;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์การนำเสนอ
เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาสการนำเสนอซึ่งเป็นตัวแทนของไฟล์ PPTX ตรวจสอบให้แน่ใจว่าได้กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
string presentationFileName = Path.Combine(dataDir, "AnimationShapesExample.pptx");
using (Presentation pres = new Presentation(presentationFileName))
{
    // รหัสของคุณสำหรับการดำเนินการเพิ่มเติมอยู่ที่นี่
}
```
## ขั้นตอนที่ 2: วนซ้ำผ่านสไลด์และเอฟเฟกต์แอนิเมชั่น
ตอนนี้ วนซ้ำแต่ละสไลด์ในงานนำเสนอและตรวจสอบเอฟเฟกต์ภาพเคลื่อนไหวที่เกี่ยวข้องกับแต่ละรูปร่าง ข้อมูลโค้ดนี้สาธิตวิธีการบรรลุเป้าหมายนี้:
```csharp
foreach (ISlide slide in pres.Slides)
{
    foreach (IEffect effect in slide.Timeline.MainSequence)
    {
        Console.WriteLine(effect.Type + " animation effect is set to shape#" +
                          effect.TargetShape.UniqueId +
                          " on slide#" + slide.SlideNumber);
    }
}
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีกำหนดเป้าหมายภาพเคลื่อนไหวสำหรับรูปร่างสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว ตอนนี้ ปรับปรุงการนำเสนอของคุณด้วยแอนิเมชั่นที่น่าดึงดูด
## คำถามที่พบบ่อย
### ฉันสามารถใช้ภาพเคลื่อนไหวที่แตกต่างกันกับรูปร่างหลาย ๆ รูปบนสไลด์เดียวกันได้หรือไม่
ใช่ คุณสามารถตั้งค่าเอฟเฟ็กต์ภาพเคลื่อนไหวที่ไม่ซ้ำกันสำหรับแต่ละรูปร่างได้
### Aspose.Slides รองรับภาพเคลื่อนไหวประเภทอื่นนอกเหนือจากที่กล่าวถึงในตัวอย่างหรือไม่
อย่างแน่นอน! Aspose.Slides มีเอฟเฟกต์แอนิเมชั่นมากมายเพื่อตอบสนองความต้องการเชิงสร้างสรรค์ของคุณ
### มีการจำกัดจำนวนรูปร่างที่ฉันสามารถเคลื่อนไหวในงานนำเสนอเดียวได้หรือไม่
ไม่ Aspose.Slides ช่วยให้คุณสามารถสร้างภาพเคลื่อนไหวในงานนำเสนอได้ไม่จำกัดจำนวน
### ฉันสามารถควบคุมระยะเวลาและเวลาของเอฟเฟ็กต์ภาพเคลื่อนไหวแต่ละรายการได้หรือไม่
ใช่ Aspose.Slides มีตัวเลือกในการปรับแต่งระยะเวลาและเวลาของภาพเคลื่อนไหวแต่ละรายการ
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 สำรวจ[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/) สำหรับข้อมูลโดยละเอียดและตัวอย่าง
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
