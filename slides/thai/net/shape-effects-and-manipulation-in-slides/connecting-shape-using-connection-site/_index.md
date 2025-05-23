---
"description": "สร้างงานนำเสนอที่น่าดึงดูดด้วย Aspose.Slides สำหรับ .NET โดยเชื่อมโยงรูปทรงต่างๆ เข้าด้วยกันอย่างราบรื่น ปฏิบัติตามคำแนะนำของเราเพื่อประสบการณ์ที่ราบรื่นและน่าดึงดูด"
"linktitle": "การเชื่อมต่อรูปทรงโดยใช้ไซต์การเชื่อมต่อในงานนำเสนอ"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การเรียนรู้การเชื่อมต่อรูปร่างด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/"
"weight": 30
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้การเชื่อมต่อรูปร่างด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา การสร้างสไลด์ที่ดึงดูดสายตาด้วยรูปทรงที่เชื่อมต่อกันถือเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังเพื่อให้บรรลุเป้าหมายนี้โดยให้คุณเชื่อมต่อรูปทรงต่างๆ โดยใช้ไซต์การเชื่อมต่อ บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการเชื่อมต่อรูปทรงต่างๆ ทีละขั้นตอน เพื่อให้แน่ใจว่าการนำเสนอของคุณโดดเด่นด้วยการเปลี่ยนภาพที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และ .NET
- ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/net/).
- มีการตั้งค่าสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น Visual Studio
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ
ตรวจสอบให้แน่ใจว่าคุณมีไดเร็กทอรีที่กำหนดไว้สำหรับเอกสารของคุณ หากไม่มี ให้สร้างขึ้นใหม่:
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
    // โค้ดสำหรับการนำเสนอของคุณอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: เข้าถึงและเพิ่มรูปร่าง
เข้าถึงคอลเลกชันรูปทรงสำหรับสไลด์ที่เลือกและเพิ่มรูปทรงที่จำเป็น:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## ขั้นตอนที่ 4: รวมรูปทรงต่างๆ โดยใช้ตัวเชื่อมต่อ
เชื่อมต่อรูปทรงโดยใช้ตัวเชื่อมต่อ:
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
บันทึกการนำเสนอของคุณด้วยรูปทรงที่เชื่อมต่อ:
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
ตอนนี้คุณได้เชื่อมต่อรูปร่างโดยใช้ไซต์การเชื่อมต่อในการนำเสนอของคุณสำเร็จแล้ว
## บทสรุป
Aspose.Slides สำหรับ .NET ทำให้กระบวนการเชื่อมต่อรูปทรงต่างๆ ง่ายขึ้น ช่วยให้คุณสร้างงานนำเสนอที่น่าสนใจได้อย่างง่ายดาย เพียงทำตามคำแนะนำทีละขั้นตอนนี้ คุณก็สามารถเพิ่มความสวยงามให้กับสไลด์และถ่ายทอดข้อความของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ Visual Studio 2019 หรือไม่
ใช่ Aspose.Slides เข้ากันได้กับ Visual Studio 2019 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งเวอร์ชันที่เหมาะสมแล้ว
### ฉันสามารถเชื่อมต่อรูปร่างมากกว่าสองรูปในขั้วต่อเดียวได้ไหม
Aspose.Slides ช่วยให้คุณเชื่อมต่อรูปทรงสองรูปด้วยตัวเชื่อมต่อตัวเดียว หากต้องการเชื่อมต่อรูปทรงเพิ่มเติม คุณจะต้องใช้ตัวเชื่อมต่อเพิ่มเติม
### ฉันจะจัดการข้อยกเว้นในระหว่างใช้ Aspose.Slides ได้อย่างไร
คุณสามารถใช้บล็อก try-catch เพื่อจัดการข้อยกเว้น โปรดดูที่ [เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับข้อยกเว้นที่เฉพาะเจาะจงและการจัดการข้อผิดพลาด
### มี Aspose.Slides เวอร์ชันทดลองใช้งานหรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides ได้จากที่ไหน
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการหารือของชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}