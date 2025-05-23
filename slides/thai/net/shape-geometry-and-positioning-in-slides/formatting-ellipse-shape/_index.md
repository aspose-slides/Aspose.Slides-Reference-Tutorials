---
"description": "สร้างรูปทรงวงรีที่สวยงามใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการนำเสนออย่างมืออาชีพ"
"linktitle": "การจัดรูปแบบรูปทรงวงรีในสไลด์ด้วย Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การสอนการจัดรูปแบบรูปทรงวงรีด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสอนการจัดรูปแบบรูปทรงวงรีด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
การปรับปรุงงานนำเสนอ PowerPoint ของคุณด้วยรูปทรงที่ดึงดูดสายตาถือเป็นสิ่งสำคัญในการดึงดูดผู้ฟัง รูปทรงหนึ่งที่มีลักษณะดังกล่าวคือรูปวงรี ซึ่งสามารถเพิ่มความสง่างามและความเป็นมืออาชีพให้กับสไลด์ของคุณได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการจัดรูปแบบรูปทรงวงรีใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio ลงบนเครื่องของคุณแล้ว
- Aspose.Slides สำหรับไลบรารี .NET ซึ่งคุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).
- ตรวจสอบให้แน่ใจว่าคุณมีสิทธิ์ที่จำเป็นในการสร้างและบันทึกไฟล์บนระบบของคุณ
## นำเข้าเนมสเปซ
ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ ซึ่งจะช่วยให้คุณสามารถเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ได้
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
ตอนนี้ มาแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อเป็นคำแนะนำที่ครอบคลุมเกี่ยวกับการจัดรูปแบบรูปร่างวงรีใน PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.Slides หากคุณยังไม่ได้ดาวน์โหลด คุณสามารถค้นหาลิงก์ดาวน์โหลด [ที่นี่](https://releases-aspose.com/slides/net/).
## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ตรวจสอบให้แน่ใจว่าไดเร็กทอรีที่ระบุมีอยู่หรือสร้างขึ้นใหม่หากไม่มี
## ขั้นตอนที่ 3: สร้างตัวอย่างคลาสการนำเสนอ
```csharp
using (Presentation pres = new Presentation())
{
    // โค้ดของคุณสำหรับการจัดรูปแบบรูปทรงวงรีอยู่ที่นี่
}
```
สร้างอินสแตนซ์ของ `Presentation` คลาสที่แสดงไฟล์ PowerPoint
## ขั้นตอนที่ 4: รับสไลด์แรก
```csharp
ISlide sld = pres.Slides[0];
```
เข้าถึงสไลด์แรกของการนำเสนอของคุณ
## ขั้นตอนที่ 5: เพิ่มรูปร่างอัตโนมัติของวงรี
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
แทรกรูปร่างอัตโนมัติของวงรีลงในสไลด์ โดยระบุตำแหน่งและมิติ
## ขั้นตอนที่ 6: จัดรูปแบบรูปร่างวงรี
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
นำการจัดรูปแบบไปใช้กับรูปร่างวงรี ตั้งค่าสีเติมและคุณสมบัติเส้น
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขแล้วลงในดิสก์
ปฏิบัติตามขั้นตอนเหล่านี้อย่างพิถีพิถัน แล้วคุณจะมีรูปร่างวงรีที่มีการจัดรูปแบบสวยงามในงานนำเสนอ PowerPoint ของคุณ
## บทสรุป
การใช้รูปทรงที่ดึงดูดสายตา เช่น วงรี สามารถเพิ่มความสวยงามให้กับงานนำเสนอ PowerPoint ของคุณได้อย่างมาก Aspose.Slides สำหรับ .NET ช่วยให้กระบวนการนี้ราบรื่น ช่วยให้คุณสร้างสไลด์ที่ดูเป็นมืออาชีพได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดได้หรือไม่
Aspose.Slides ช่วยให้มั่นใจได้ว่าสามารถใช้งานร่วมกับ PowerPoint เวอร์ชันต่างๆ ได้ รวมถึงเวอร์ชันล่าสุดด้วย โปรดดู [เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับรายละเอียดที่เฉพาะเจาะจง
### ฉันสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET รุ่นทดลองใช้งานฟรีได้หรือไม่
ใช่ คุณสามารถทดลองใช้งานฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
เยี่ยม [ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว
### ฉันสามารถค้นหาการสนับสนุนสำหรับแบบสอบถามที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
ขอความช่วยเหลือจากชุมชนได้ที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).
### มีตัวเลือกการซื้อโดยตรงสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
ใช่ครับ สามารถซื้อห้องสมุดได้โดยตรงครับ [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}