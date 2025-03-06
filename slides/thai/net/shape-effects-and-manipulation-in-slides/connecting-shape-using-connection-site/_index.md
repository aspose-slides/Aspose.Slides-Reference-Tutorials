---
title: สร้างความเชี่ยวชาญในการเชื่อมต่อด้วย Aspose.Slides สำหรับ .NET
linktitle: การเชื่อมต่อรูปร่างโดยใช้ไซต์การเชื่อมต่อในการนำเสนอ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: สร้างสรรค์งานนำเสนอที่น่าดึงดูดใจด้วย Aspose.Slides สำหรับ .NET ที่เชื่อมโยงรูปทรงต่างๆ ได้อย่างราบรื่น ปฏิบัติตามคำแนะนำของเราเพื่อประสบการณ์ที่ราบรื่นและน่าดึงดูด
weight: 30
url: /th/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก การสร้างสไลด์ที่ดึงดูดสายตาด้วยรูปทรงที่เชื่อมโยงถึงกันถือเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ Aspose.Slides สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพในการบรรลุเป้าหมายนี้ โดยอนุญาตให้คุณเชื่อมต่อรูปร่างโดยใช้ไซต์การเชื่อมต่อ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเชื่อมต่อรูปร่างทีละขั้นตอน เพื่อให้มั่นใจว่างานนำเสนอของคุณโดดเด่นด้วยการเปลี่ยนภาพที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และ .NET
-  ติดตั้ง Aspose.Slides สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่นการตั้งค่า Visual Studio
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ
ตรวจสอบให้แน่ใจว่าคุณมีไดเร็กทอรีที่กำหนดไว้สำหรับเอกสารของคุณ หากไม่มีอยู่ ให้สร้างขึ้นใหม่:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
สร้างอินสแตนซ์คลาสการนำเสนอเพื่อแสดงไฟล์ PPTX ของคุณ:
```csharp
using (Presentation presentation = new Presentation())
{
    // รหัสของคุณสำหรับการนำเสนออยู่ที่นี่
}
```
## ขั้นตอนที่ 3: เข้าถึงและเพิ่มรูปร่าง
เข้าถึงคอลเลกชันรูปร่างสำหรับสไลด์ที่เลือกและเพิ่มรูปร่างที่จำเป็น:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## ขั้นตอนที่ 4: เข้าร่วมรูปร่างโดยใช้ตัวเชื่อมต่อ
เชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อ:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## ขั้นตอนที่ 5: ตั้งค่าไซต์การเชื่อมต่อที่ต้องการ
ระบุดัชนีไซต์การเชื่อมต่อที่ต้องการสำหรับตัวเชื่อมต่อ:
```csharp
uint wantedIndex = 6;
if (ellipse.ConnectionSiteCount > wantedIndex)
{
    connector.StartShapeConnectionSiteIndex = wantedIndex;
}
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอของคุณ
บันทึกงานนำเสนอของคุณด้วยรูปร่างที่เชื่อมต่อกัน:
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
ตอนนี้คุณเชื่อมต่อรูปร่างได้สำเร็จโดยใช้ไซต์เชื่อมต่อในงานนำเสนอของคุณ
## บทสรุป
Aspose.Slides สำหรับ .NET ทำให้กระบวนการเชื่อมต่อรูปร่างง่ายขึ้น ช่วยให้คุณสร้างงานนำเสนอที่ดึงดูดสายตาได้อย่างง่ายดาย ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถเพิ่มความดึงดูดสายตาให้กับสไลด์และถ่ายทอดข้อความของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ Visual Studio 2019 หรือไม่
ใช่ Aspose.Slides เข้ากันได้กับ Visual Studio 2019 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งเวอร์ชันที่เหมาะสมแล้ว
### ฉันสามารถเชื่อมต่อรูปร่างมากกว่าสองรูปร่างในตัวเชื่อมต่อเดียวได้หรือไม่
Aspose.Slides ช่วยให้คุณสามารถเชื่อมต่อสองรูปร่างด้วยตัวเชื่อมต่อเดียว หากต้องการเชื่อมต่อรูปร่างเพิ่มเติม คุณจะต้องมีตัวเชื่อมต่อเพิ่มเติม
### ฉันจะจัดการข้อยกเว้นขณะใช้ Aspose.Slides ได้อย่างไร
คุณสามารถใช้บล็อก try-catch เพื่อจัดการกับข้อยกเว้น อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับข้อยกเว้นเฉพาะและการจัดการข้อผิดพลาด
### มี Aspose.Slides เวอร์ชันทดลองใช้งานหรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการอภิปรายของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
