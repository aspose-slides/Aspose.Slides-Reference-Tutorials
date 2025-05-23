---
"description": "สำรวจพลังของ Aspose.Slides สำหรับ .NET เชื่อมโยงรูปทรงต่างๆ ได้อย่างง่ายดายในงานนำเสนอของคุณ ยกระดับสไลด์ของคุณด้วยตัวเชื่อมต่อแบบไดนามิก"
"linktitle": "การเชื่อมต่อรูปทรงโดยใช้ตัวเชื่อมต่อในงานนำเสนอ"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "Aspose.Slides - เชื่อมต่อรูปทรงอย่างราบรื่นใน .NET"
"url": "/th/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - เชื่อมต่อรูปทรงอย่างราบรื่นใน .NET

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา ความสามารถในการเชื่อมต่อรูปทรงต่างๆ โดยใช้ตัวเชื่อมต่อจะเพิ่มความซับซ้อนให้กับสไลด์ของคุณ Aspose.Slides สำหรับ .NET ช่วยให้ผู้พัฒนาสามารถบรรลุสิ่งนี้ได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการ โดยแบ่งขั้นตอนต่างๆ ออกเป็นส่วนๆ เพื่อให้แน่ใจว่าเข้าใจได้ชัดเจน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มเรียนรู้บทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับ C# และ .NET framework
- ติดตั้ง Aspose.Slides สำหรับ .NET แล้ว ถ้ายังไม่ได้ติดตั้ง ให้ดาวน์โหลด [ที่นี่](https://releases-aspose.com/slides/net/).
- ตั้งสภาพแวดล้อมการพัฒนาไว้
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. ตั้งค่าไดเรกทอรีเอกสาร
เริ่มต้นด้วยการกำหนดไดเรกทอรีสำหรับเอกสารของคุณ:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. การสร้างคลาสการนำเสนอ
สร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อแสดงไฟล์ PPTX ของคุณ:
```csharp
using (Presentation input = new Presentation())
{
    // การเข้าถึงคอลเลกชันรูปทรงสำหรับสไลด์ที่เลือก
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. เพิ่มรูปร่างลงในสไลด์
เพิ่มรูปร่างที่จำเป็นลงในสไลด์ของคุณ เช่น วงรีและสี่เหลี่ยมผืนผ้า:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. เพิ่มรูปร่างตัวเชื่อมต่อ
รวมรูปร่างตัวเชื่อมต่อไว้ในคอลเล็กชันรูปร่างของสไลด์:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. เชื่อมต่อรูปทรงด้วยตัวเชื่อมต่อ
ระบุรูปทรงที่จะเชื่อมต่อด้วยขั้วต่อ:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. เปลี่ยนเส้นทางเชื่อมต่อ
เรียกวิธีการเปลี่ยนเส้นทางเพื่อกำหนดเส้นทางที่สั้นที่สุดโดยอัตโนมัติระหว่างรูปร่าง:
```csharp
connector.Reroute();
```
## 7. บันทึกการนำเสนอ
บันทึกการนำเสนอของคุณเพื่อดูรูปทรงที่เชื่อมต่อ:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## บทสรุป
ขอแสดงความยินดี! คุณได้เชื่อมต่อรูปทรงต่างๆ โดยใช้ตัวเชื่อมต่อในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว ปรับปรุงการนำเสนอของคุณด้วยฟีเจอร์ขั้นสูงนี้และดึงดูดผู้ฟังของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ .NET เข้ากันได้กับกรอบงาน .NET ล่าสุดหรือไม่
ใช่ Aspose.Slides สำหรับ .NET ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจถึงความเข้ากันได้กับเวอร์ชัน .NET framework ล่าสุด
### ฉันสามารถเชื่อมต่อรูปร่างมากกว่าสองรูปโดยใช้ขั้วต่อตัวเดียวได้ไหม
แน่นอน คุณสามารถเชื่อมต่อรูปร่างต่างๆ ได้หลายรูปโดยการขยายลอจิกของตัวเชื่อมต่อในโค้ดของคุณ
### มีข้อจำกัดใด ๆ เกี่ยวกับรูปร่างที่ฉันสามารถเชื่อมต่อได้หรือไม่?
Aspose.Slides สำหรับ .NET รองรับการเชื่อมต่อรูปทรงต่างๆ รวมถึงรูปทรงพื้นฐาน สมาร์ทอาร์ต และรูปทรงที่กำหนดเอง
### ฉันจะปรับแต่งลักษณะที่ปรากฏของขั้วต่อได้อย่างไร
สำรวจเอกสาร Aspose.Slides เพื่อดูวิธีการปรับแต่งรูปลักษณ์ของตัวเชื่อมต่อ เช่น สไตล์เส้นและสี
### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Slides หรือไม่
ใช่ คุณสามารถค้นหาความช่วยเหลือและแบ่งปันประสบการณ์ของคุณได้ใน [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}