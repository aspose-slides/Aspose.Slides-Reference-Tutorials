---
title: ซ่อนรูปร่างใน PowerPoint ด้วย Aspose.Slides .NET Tutorial
linktitle: การซ่อนรูปร่างในสไลด์การนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีซ่อนรูปร่างในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับแต่งการนำเสนอด้วยโปรแกรมด้วยคำแนะนำทีละขั้นตอนนี้
weight: 21
url: /th/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ซ่อนรูปร่างใน PowerPoint ด้วย Aspose.Slides .NET Tutorial

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก การปรับแต่งเป็นสิ่งสำคัญ Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม ข้อกำหนดทั่วไปประการหนึ่งคือความสามารถในการซ่อนรูปร่างเฉพาะภายในสไลด์ บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการซ่อนรูปร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการสำหรับ .NET
- ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับ C# เนื่องจากตัวอย่างโค้ดที่ให้มาเป็นภาษานี้
## นำเข้าเนมสเปซ
หากต้องการเริ่มทำงานกับ Aspose.Slides ให้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ C# ของคุณ สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงคลาสและวิธีการที่จำเป็นได้
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
ตอนนี้ เรามาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ชัดเจนและกระชับ
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ C# ใหม่ และอย่าลืมรวมไลบรารี Aspose.Slides ไว้ด้วย
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสซึ่งเป็นตัวแทนของไฟล์ PowerPoint เพิ่มสไลด์และรับข้อมูลอ้างอิง
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างลงในสไลด์
เพิ่มรูปร่างอัตโนมัติลงในสไลด์ เช่น สี่เหลี่ยมและดวงจันทร์ โดยมีขนาดเฉพาะ
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## ขั้นตอนที่ 4: ซ่อนรูปร่างตามข้อความแสดงแทน
ระบุข้อความแสดงแทนและซ่อนรูปร่างที่ตรงกับข้อความนี้
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขลงในดิสก์ในรูปแบบ PPTX
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## บทสรุป
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Slides รองรับ .NET Core ซึ่งให้ความยืดหยุ่นในสภาพแวดล้อมการพัฒนาของคุณ
### ฉันสามารถซ่อนรูปร่างตามเงื่อนไขอื่นที่ไม่ใช่ข้อความแสดงแทนได้หรือไม่
อย่างแน่นอน! คุณสามารถปรับแต่งตรรกะการซ่อนตามคุณลักษณะต่างๆ เช่น ประเภทรูปร่าง สี หรือตำแหน่ง
### ฉันจะหาเอกสารประกอบ Aspose.Slides เพิ่มเติมได้จากที่ไหน
 สำรวจเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/net/)สำหรับข้อมูลเชิงลึกและตัวอย่าง
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.Slides หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/)เพื่อวัตถุประสงค์ในการทดสอบ
### ฉันจะรับการสนับสนุนจากชุมชนสำหรับ Aspose.Slides ได้อย่างไร
 เข้าร่วมชุมชน Aspose.Slides บน[ฟอรั่ม](https://forum.aspose.com/c/slides/11) เพื่อหารือและช่วยเหลือ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
