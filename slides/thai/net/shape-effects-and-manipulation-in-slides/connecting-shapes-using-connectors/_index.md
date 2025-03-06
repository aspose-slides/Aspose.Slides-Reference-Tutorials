---
title: Aspose.Slides - เชื่อมต่อรูปร่างได้อย่างราบรื่นใน .NET
linktitle: การเชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อในการนำเสนอ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: สำรวจพลังของ Aspose.Slides สำหรับ .NET ซึ่งเชื่อมต่อรูปร่างในการนำเสนอของคุณได้อย่างง่ายดาย ยกระดับสไลด์ของคุณด้วยตัวเชื่อมต่อแบบไดนามิก
weight: 29
url: /th/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก ความสามารถในการเชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อจะช่วยเพิ่มความซับซ้อนให้กับสไลด์ของคุณ Aspose.Slides สำหรับ .NET ช่วยให้นักพัฒนาสามารถบรรลุเป้าหมายนี้ได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการ โดยแจกแจงแต่ละขั้นตอนเพื่อให้แน่ใจว่ามีความเข้าใจที่ชัดเจน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับกรอบงาน C# และ .NET
-  ติดตั้ง Aspose.Slides สำหรับ .NET แล้ว ถ้าไม่เช่นนั้นให้ดาวน์โหลด[ที่นี่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนาที่จัดตั้งขึ้น
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. ตั้งค่าไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการกำหนดไดเร็กทอรีสำหรับเอกสารของคุณ:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. ยกตัวอย่างชั้นเรียนการนำเสนอ
สร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อแสดงไฟล์ PPTX ของคุณ:
```csharp
using (Presentation input = new Presentation())
{
    // การเข้าถึงคอลเลกชันรูปร่างสำหรับสไลด์ที่เลือก
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. เพิ่มรูปร่างให้กับสไลด์
เพิ่มรูปร่างที่จำเป็นลงในสไลด์ของคุณ เช่น วงรีและสี่เหลี่ยมผืนผ้า:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. เพิ่มรูปร่างตัวเชื่อมต่อ
รวมรูปร่างตัวเชื่อมต่อในคอลเลกชันรูปร่างของสไลด์:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. เชื่อมต่อรูปร่างด้วยตัวเชื่อมต่อ
ระบุรูปร่างที่จะเชื่อมต่อด้วยตัวเชื่อมต่อ:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. เปลี่ยนเส้นทางตัวเชื่อมต่อ
เรียกวิธีการเปลี่ยนเส้นทางเพื่อกำหนดเส้นทางที่สั้นที่สุดโดยอัตโนมัติระหว่างรูปร่าง:
```csharp
connector.Reroute();
```
## 7. บันทึกการนำเสนอ
บันทึกงานนำเสนอของคุณเพื่อดูรูปร่างที่เชื่อมต่อ:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## บทสรุป
ยินดีด้วย! คุณเชื่อมต่อรูปร่างได้สำเร็จโดยใช้ตัวเชื่อมต่อในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอของคุณด้วยฟีเจอร์ขั้นสูงนี้และดึงดูดผู้ชมของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่
ใช่ Aspose.Slides สำหรับ .NET ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าสามารถเข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ล่าสุด
### ฉันสามารถเชื่อมต่อรูปร่างมากกว่าสองรูปร่างโดยใช้ตัวเชื่อมต่อตัวเดียวได้หรือไม่
แน่นอน คุณสามารถเชื่อมต่อหลายรูปร่างได้โดยขยายตรรกะของตัวเชื่อมต่อในโค้ดของคุณ
### มีข้อจำกัดเกี่ยวกับรูปร่างที่ฉันสามารถเชื่อมต่อได้หรือไม่?
Aspose.Slides สำหรับ .NET รองรับการเชื่อมต่อรูปร่างต่างๆ รวมถึงรูปร่างพื้นฐาน ศิลปะอัจฉริยะ และรูปร่างแบบกำหนดเอง
### ฉันจะปรับแต่งรูปลักษณ์ของตัวเชื่อมต่อได้อย่างไร?
สำรวจเอกสารประกอบของ Aspose.Slides เพื่อดูวิธีการปรับแต่งรูปลักษณ์ของตัวเชื่อมต่อ เช่น สไตล์เส้นและสี
### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.Slides หรือไม่
 ใช่ คุณสามารถขอความช่วยเหลือและแบ่งปันประสบการณ์ของคุณได้ใน[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
