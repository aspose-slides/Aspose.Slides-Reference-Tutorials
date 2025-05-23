---
"description": "เพิ่มประสิทธิภาพการนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET! เรียนรู้ขั้นตอนทีละขั้นตอนในการเติมรูปทรงด้วยไล่ระดับสี ดาวน์โหลดรุ่นทดลองใช้งานฟรีได้แล้ววันนี้!"
"linktitle": "การเติมรูปร่างด้วยการไล่ระดับสีในสไลด์การนำเสนอโดยใช้ Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "สร้างการไล่ระดับสีอันน่าทึ่งใน PowerPoint ด้วย Aspose.Slides"
"url": "/th/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างการไล่ระดับสีอันน่าทึ่งใน PowerPoint ด้วย Aspose.Slides

## การแนะนำ
การสร้างสไลด์นำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญในการดึงดูดและรักษาความสนใจของผู้ชม ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการปรับปรุงสไลด์ของคุณโดยการเติมรูปทรงวงรีด้วยการไล่ระดับสีโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio ลงบนเครื่องของคุณแล้ว
- Aspose.Slides สำหรับไลบรารี .NET ดาวน์โหลดเลย [ที่นี่](https://releases-aspose.com/slides/net/).
- ไดเร็กทอรีโครงการสำหรับจัดระเบียบไฟล์ของคุณ
## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ ให้รวมเนมสเปซที่จำเป็นสำหรับ Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: สร้างงานนำเสนอ
เริ่มต้นด้วยการสร้างงานนำเสนอใหม่โดยใช้ไลบรารี Aspose.Slides:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // รหัสของคุณอยู่ที่นี่...
}
```
## ขั้นตอนที่ 2: เพิ่มรูปทรงวงรี
แทรกรูปวงรีลงในสไลด์แรกของการนำเสนอของคุณ:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## ขั้นตอนที่ 3: ใช้การจัดรูปแบบไล่ระดับสี
ระบุว่ารูปร่างควรจะถูกเติมด้วยการไล่ระดับสีและกำหนดลักษณะของการไล่ระดับสี:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## ขั้นตอนที่ 4: เพิ่มจุดหยุดการไล่ระดับสี
กำหนดสีและตำแหน่งของจุดหยุดการไล่ระดับสี:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอของคุณด้วยรูปร่างที่เติมด้วยการไล่ระดับสีที่เพิ่มเข้ามาใหม่:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
ทำซ้ำขั้นตอนเหล่านี้ในโค้ด C# ของคุณ โดยตรวจสอบให้แน่ใจว่ามีลำดับและค่าพารามิเตอร์ที่ถูกต้อง ซึ่งจะทำให้ได้ไฟล์นำเสนอที่มีรูปร่างวงรีที่สวยงามและเต็มไปด้วยการไล่ระดับสี
## บทสรุป
ด้วย Aspose.Slides สำหรับ .NET คุณสามารถยกระดับความสวยงามของงานนำเสนอของคุณได้อย่างง่ายดาย เมื่อทำตามคำแนะนำนี้ คุณจะได้เรียนรู้วิธีการเติมรูปทรงด้วยไล่ระดับสี ซึ่งจะทำให้สไลด์ของคุณดูเป็นมืออาชีพและน่าสนใจ
---
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้การไล่ระดับสีกับรูปร่างอื่นๆ นอกจากวงรีได้หรือไม่
A: แน่นอน! Aspose.Slides สำหรับ .NET รองรับการเติมแบบไล่ระดับสำหรับรูปร่างต่างๆ เช่น รูปสี่เหลี่ยมผืนผ้า รูปหลายเหลี่ยม และอื่นๆ อีกมากมาย
### ถาม: ฉันสามารถหาตัวอย่างเพิ่มเติมและเอกสารโดยละเอียดได้ที่ไหน
ก. สำรวจ [เอกสาร Aspose.Slides สำหรับ .NET](https://reference.aspose.com/slides/net/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม
### ถาม: มีรุ่นทดลองใช้งานฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
A: ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ถาม: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
ก. ขอความช่วยเหลือและมีส่วนร่วมกับชุมชน [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
A: แน่นอน คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}