---
title: สร้างรูปทรงร่างที่น่าทึ่งด้วย Aspose.Slides
linktitle: การสร้างรูปทรงร่างในสไลด์การนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มรูปร่างที่ร่างอย่างสร้างสรรค์ให้กับสไลด์การนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ .NET เพิ่มความน่าดึงดูดสายตาได้อย่างง่ายดาย!
type: docs
weight: 13
url: /th/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนของเราเกี่ยวกับการสร้างรูปร่างที่ร่างไว้ในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET หากคุณต้องการเพิ่มความคิดสร้างสรรค์ให้กับงานนำเสนอของคุณ รูปร่างที่ร่างไว้จะมอบสุนทรียศาสตร์ที่มีเอกลักษณ์และวาดด้วยมือ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการ โดยแบ่งออกเป็นขั้นตอนง่ายๆ เพื่อให้แน่ใจว่าจะได้รับประสบการณ์ที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ด้วย IDE ที่คุณต้องการ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ .NET ของคุณ ขั้นตอนนี้ช่วยให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและฟังก์ชันที่จำเป็นสำหรับการทำงานกับ Aspose.Slides
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
เริ่มต้นด้วยการสร้างโปรเจ็กต์ .NET ใหม่หรือเปิดโปรเจ็กต์ที่มีอยู่ ตรวจสอบให้แน่ใจว่าได้รวม Aspose.Slides ในการอ้างอิงโครงการของคุณ
## ขั้นตอนที่ 2: เริ่มต้น Aspose.Slides
เริ่มต้น Aspose.Slides โดยเพิ่มข้อมูลโค้ดต่อไปนี้ ซึ่งจะตั้งค่าการนำเสนอและระบุเส้นทางเอาต์พุตสำหรับไฟล์การนำเสนอและรูปภาพขนาดย่อ
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // ทำตามขั้นตอนต่อไป...
}
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างที่ร่างไว้
ตอนนี้ มาเพิ่มรูปร่างที่ร่างไว้ลงในสไลด์กันดีกว่า ในตัวอย่างนี้ เราจะเพิ่มสี่เหลี่ยมที่มีเอฟเฟกต์สเก็ตช์ภาพด้วยมือเปล่า
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// แปลงรูปร่างเป็นภาพร่างสไตล์ด้วยมือเปล่า
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## ขั้นตอนที่ 4: สร้างภาพขนาดย่อ
สร้างภาพขนาดย่อของสไลด์เพื่อให้เห็นภาพรูปร่างที่ร่างไว้ บันทึกภาพขนาดย่อเป็นไฟล์ PNG
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกไฟล์งานนำเสนอด้วยรูปร่างที่ร่างไว้
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
แค่นั้นแหละ! คุณสร้างงานนำเสนอด้วยรูปทรงที่ร่างไว้โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว
## บทสรุป
การเพิ่มรูปร่างที่ร่างไว้ลงในสไลด์การนำเสนอของคุณสามารถเพิ่มความน่าดึงดูดทางสายตาและดึงดูดผู้ชมของคุณได้ ด้วย Aspose.Slides สำหรับ .NET กระบวนการจะตรงไปตรงมา ช่วยให้คุณปลดปล่อยความคิดสร้างสรรค์ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### 1. ฉันสามารถปรับแต่งเอฟเฟ็กต์ที่ร่างไว้ได้หรือไม่?
 ใช่ Aspose.Slides สำหรับ .NET มีตัวเลือกการปรับแต่งที่หลากหลายสำหรับเอฟเฟ็กต์ที่ร่างไว้ อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับข้อมูลโดยละเอียด
### 2. มีการทดลองใช้ฟรีหรือไม่?
 แน่นอน! คุณสามารถสำรวจ Aspose.Slides สำหรับ .NET รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### 3. ฉันจะรับการสนับสนุนได้ที่ไหน?
 สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ โปรดไปที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. ฉันจะซื้อ Aspose.Slides สำหรับ .NET ได้อย่างไร
 หากต้องการซื้อ Aspose.Slides สำหรับ .NET โปรดไปที่[หน้าซื้อ](https://purchase.aspose.com/buy).
### 5. คุณมีใบอนุญาตชั่วคราวหรือไม่?
 ใช่ มีใบอนุญาตชั่วคราวให้ใช้งาน[ที่นี่](https://purchase.aspose.com/temporary-license/).