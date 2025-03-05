---
title: การจัดรูปแบบบทช่วยสอนรูปร่างวงรีด้วย Aspose.Slides สำหรับ .NET
linktitle: การจัดรูปแบบรูปร่างวงรีในสไลด์ด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: สร้างรูปร่างวงรีที่น่าทึ่งใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการนำเสนออย่างมืออาชีพ
type: docs
weight: 11
url: /th/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/
---
## การแนะนำ
การปรับปรุงงานนำเสนอ PowerPoint ของคุณด้วยรูปทรงที่ดึงดูดสายตาถือเป็นสิ่งสำคัญในการดึงดูดผู้ชมของคุณ รูปร่างหนึ่งดังกล่าวคือวงรีซึ่งสามารถเพิ่มความสง่างามและความเป็นมืออาชีพให้กับสไลด์ของคุณ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการจัดรูปแบบรูปร่างวงรีใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  Aspose.Slides สำหรับไลบรารี .NET ซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- ตรวจสอบให้แน่ใจว่าคุณมีสิทธิ์ที่จำเป็นในการสร้างและบันทึกไฟล์ในระบบของคุณ
## นำเข้าเนมสเปซ
ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับ Aspose.Slides
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
ตอนนี้ เราจะแจกแจงตัวอย่างออกเป็นหลายขั้นตอนเพื่อดูคำแนะนำที่ครอบคลุมเกี่ยวกับการจัดรูปแบบรูปร่างวงรีใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
 สร้างโครงการ C# ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.Slides หากคุณยังไม่ได้ดาวน์โหลด คุณสามารถดูลิงก์ดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
## ขั้นตอนที่ 2: กำหนดไดเร็กทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ตรวจสอบให้แน่ใจว่าไดเร็กทอรีที่ระบุมีอยู่หรือสร้างขึ้นหากไม่มี
## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ
```csharp
using (Presentation pres = new Presentation())
{
    // รหัสของคุณสำหรับการจัดรูปแบบรูปร่างวงรีอยู่ที่นี่
}
```
 สร้างอินสแตนซ์ของ`Presentation` คลาสซึ่งเป็นตัวแทนของไฟล์ PowerPoint
## ขั้นตอนที่ 4: รับสไลด์แรก
```csharp
ISlide sld = pres.Slides[0];
```
เข้าถึงสไลด์แรกของงานนำเสนอของคุณ
## ขั้นตอนที่ 5: เพิ่ม Ellipse AutoShape
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
แทรกรูปร่างอัตโนมัติวงรีลงบนสไลด์ โดยระบุตำแหน่งและขนาดของสไลด์
## ขั้นตอนที่ 6: จัดรูปแบบรูปร่างวงรี
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
ใช้การจัดรูปแบบกับรูปร่างวงรี ตั้งค่าสีเติมและคุณสมบัติของเส้น
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขลงในดิสก์
ทำตามขั้นตอนเหล่านี้อย่างพิถีพิถัน และคุณจะมีรูปทรงวงรีที่จัดรูปแบบอย่างสวยงามในงานนำเสนอ PowerPoint ของคุณ
## บทสรุป
การผสมผสานรูปร่างที่ดึงดูดสายตา เช่น วงรี จะช่วยเพิ่มความสวยงามให้กับงานนำเสนอ PowerPoint ของคุณได้อย่างมาก Aspose.Slides สำหรับ .NET ทำให้กระบวนการนี้ราบรื่น ช่วยให้คุณสร้างสไลด์ที่ดูเป็นมืออาชีพได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดหรือไม่
Aspose.Slides รับประกันความเข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ รวมถึงเวอร์ชันล่าสุดด้วย อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับรายละเอียดเฉพาะ
### ฉันสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET รุ่นทดลองใช้ฟรีได้หรือไม่
 ใช่ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 เยี่ยม[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราว
### ฉันจะรับการสนับสนุนสำหรับคำค้นหาที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
 ขอความช่วยเหลือจากชุมชนได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### มีตัวเลือกการซื้อโดยตรงสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถซื้อห้องสมุดได้โดยตรง[ที่นี่](https://purchase.aspose.com/buy).