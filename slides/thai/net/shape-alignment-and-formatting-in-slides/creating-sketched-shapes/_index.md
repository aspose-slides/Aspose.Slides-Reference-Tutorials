---
"description": "เรียนรู้วิธีการเพิ่มรูปทรงที่ร่างไว้อย่างสร้างสรรค์ลงในสไลด์การนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ .NET เพิ่มความน่าสนใจให้กับภาพได้อย่างง่ายดาย!"
"linktitle": "การสร้างรูปทรงแบบร่างในสไลด์การนำเสนอด้วย Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "สร้างรูปทรงที่ร่างไว้อย่างน่าทึ่งด้วย Aspose.Slides"
"url": "/th/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างรูปทรงที่ร่างไว้อย่างน่าทึ่งด้วย Aspose.Slides

## การแนะนำ
ยินดีต้อนรับสู่คู่มือทีละขั้นตอนของเราในการสร้างรูปทรงแบบร่างในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET หากคุณต้องการเพิ่มความคิดสร้างสรรค์ให้กับงานนำเสนอของคุณ รูปทรงแบบร่างจะให้ความสวยงามที่เป็นเอกลักษณ์และวาดด้วยมือ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการ โดยแบ่งขั้นตอนออกเป็นขั้นตอนง่ายๆ เพื่อให้แน่ใจว่าจะได้ประสบการณ์ที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มลงลึกในบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ด้วย IDE ที่คุณต้องการ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ .NET ของคุณ ขั้นตอนนี้จะช่วยให้คุณสามารถเข้าถึงคลาสและฟังก์ชันที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ได้
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
เริ่มต้นด้วยการสร้างโครงการ .NET ใหม่หรือเปิดโครงการที่มีอยู่แล้ว อย่าลืมรวม Aspose.Slides ไว้ในการอ้างอิงโครงการของคุณ
## ขั้นตอนที่ 2: เริ่มต้น Aspose.Slides
เริ่มต้น Aspose.Slides โดยเพิ่มโค้ดสั้นๆ ต่อไปนี้ ซึ่งจะตั้งค่าการนำเสนอและระบุเส้นทางเอาต์พุตสำหรับไฟล์การนำเสนอและรูปภาพขนาดย่อ
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // ดำเนินการตามขั้นตอนถัดไป...
}
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างที่ร่างไว้
ตอนนี้เรามาเพิ่มรูปร่างที่ร่างไว้ลงในสไลด์กัน ในตัวอย่างนี้ เราจะเพิ่มรูปสี่เหลี่ยมผืนผ้าที่มีเอฟเฟกต์ร่างแบบอิสระ
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// แปลงรูปร่างเป็นภาพร่างแบบฟรีแฮนด์
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## ขั้นตอนที่ 4: สร้างภาพขนาดย่อ
สร้างภาพขนาดย่อของสไลด์เพื่อแสดงรูปร่างที่ร่างไว้ บันทึกภาพขนาดย่อเป็นไฟล์ PNG
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกไฟล์การนำเสนอที่มีรูปร่างร่างไว้
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
เสร็จเรียบร้อย! คุณได้สร้างงานนำเสนอที่มีรูปร่างร่างโดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว
## บทสรุป
การเพิ่มรูปทรงที่ร่างไว้ในสไลด์การนำเสนอของคุณจะช่วยเพิ่มความน่าสนใจทางสายตาและดึงดูดผู้ฟังได้ ด้วย Aspose.Slides สำหรับ .NET กระบวนการนี้จะกลายเป็นเรื่องง่ายดาย ช่วยให้คุณปลดปล่อยความคิดสร้างสรรค์ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### 1. ฉันสามารถปรับแต่งเอฟเฟกต์แบบร่างได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET มีตัวเลือกการปรับแต่งต่างๆ สำหรับเอฟเฟกต์แบบร่าง โปรดดูที่ [เอกสารประกอบ](https://reference.aspose.com/slides/net/) เพื่อดูข้อมูลโดยละเอียด
### 2. มีการทดลองใช้ฟรีหรือไม่?
แน่นอน! คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรี [ที่นี่](https://releases-aspose.com/).
### 3. ฉันจะได้รับการสนับสนุนได้ที่ไหน
หากต้องการความช่วยเหลือหรือมีข้อสงสัยใด ๆ โปรดไปที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).
### 4. ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้อย่างไร
หากต้องการซื้อ Aspose.Slides สำหรับ .NET โปรดไปที่ [หน้าการซื้อ](https://purchase-aspose.com/buy).
### 5. คุณมีใบอนุญาตชั่วคราวหรือไม่?
ใช่ มีใบอนุญาตชั่วคราว [ที่นี่](https://purchase-aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}