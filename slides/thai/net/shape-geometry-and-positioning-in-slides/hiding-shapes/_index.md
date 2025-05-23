---
"description": "เรียนรู้วิธีซ่อนรูปร่างในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับแต่งการนำเสนอด้วยโปรแกรมด้วยคู่มือทีละขั้นตอนนี้"
"linktitle": "การซ่อนรูปร่างในสไลด์การนำเสนอด้วย Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "ซ่อนรูปร่างใน PowerPoint ด้วย Aspose.Slides บทช่วยสอน .NET"
"url": "/th/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ซ่อนรูปร่างใน PowerPoint ด้วย Aspose.Slides บทช่วยสอน .NET

## การแนะนำ
ในโลกของงานนำเสนอที่เปลี่ยนแปลงตลอดเวลา การปรับแต่งถือเป็นปัจจัยสำคัญ Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการจัดการงานนำเสนอ PowerPoint ด้วยโปรแกรม ข้อกำหนดทั่วไปประการหนึ่งคือความสามารถในการซ่อนรูปร่างเฉพาะภายในสไลด์ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับกระบวนการซ่อนรูปร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการสำหรับ .NET
- ความรู้พื้นฐานเกี่ยวกับ C#: ทำความคุ้นเคยกับ C# เนื่องจากตัวอย่างโค้ดที่ให้มาอยู่ในภาษา C#
## นำเข้าเนมสเปซ
หากต้องการเริ่มทำงานกับ Aspose.Slides ให้ทำการอิมพอร์ตเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ ซึ่งจะช่วยให้คุณสามารถเข้าถึงคลาสและเมธอดที่จำเป็นได้
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
ตอนนี้มาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ชัดเจนและกระชับ
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการ C# ใหม่และตรวจสอบให้แน่ใจว่าได้รวมไลบรารี Aspose.Slides ไว้ด้วย
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
สร้างตัวอย่าง `Presentation` คลาสที่แสดงไฟล์ PowerPoint เพิ่มสไลด์และรับการอ้างอิงถึงสไลด์นั้น
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างลงในสไลด์
เพิ่มรูปร่างอัตโนมัติให้กับสไลด์ เช่น รูปสี่เหลี่ยมผืนผ้าและดวงจันทร์ โดยมีขนาดที่เฉพาะเจาะจง
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## ขั้นตอนที่ 4: ซ่อนรูปร่างตามข้อความทางเลือก
ระบุข้อความทางเลือกและซ่อนรูปร่างที่ตรงกับข้อความนี้
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
บันทึกงานนำเสนอที่แก้ไขแล้วลงในดิสก์ในรูปแบบ PPTX
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## บทสรุป
ขอแสดงความยินดี! คุณได้ซ่อนรูปร่างในงานนำเสนอของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET ซึ่งเปิดโลกแห่งความเป็นไปได้ในการสร้างสไลด์แบบไดนามิกและกำหนดเองได้ด้วยโปรแกรม
---
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ .NET Core ได้หรือไม่
ใช่ Aspose.Slides รองรับ .NET Core ซึ่งให้ความยืดหยุ่นในสภาพแวดล้อมการพัฒนาของคุณ
### ฉันสามารถซ่อนรูปร่างตามเงื่อนไขอื่นๆ นอกเหนือจากข้อความทางเลือกได้หรือไม่
แน่นอน! คุณสามารถปรับแต่งตรรกะการซ่อนตามคุณลักษณะต่างๆ เช่น ประเภทรูปร่าง สี หรือตำแหน่ง
### ฉันสามารถหาเอกสาร Aspose.Slides เพิ่มเติมได้ที่ไหน
สำรวจเอกสาร [ที่นี่](https://reference.aspose.com/slides/net/) เพื่อข้อมูลเชิงลึกและตัวอย่าง
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.Slides หรือไม่
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ
### ฉันจะได้รับการสนับสนุนชุมชนสำหรับ Aspose.Slides ได้อย่างไร
เข้าร่วมชุมชน Aspose.Slides บน [ฟอรั่ม](https://forum.aspose.com/c/slides/11) เพื่อการหารือและช่วยเหลือ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}