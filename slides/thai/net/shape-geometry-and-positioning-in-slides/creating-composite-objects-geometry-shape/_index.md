---
title: การเรียนรู้รูปทรงเรขาคณิตเชิงประกอบในการนำเสนอ
linktitle: การสร้างวัตถุคอมโพสิตในรูปทรงเรขาคณิตด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างงานนำเสนอที่น่าทึ่งด้วยรูปทรงเรขาคณิตแบบผสมโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อผลลัพธ์ที่น่าประทับใจ
weight: 14
url: /th/net/shape-geometry-and-positioning-in-slides/creating-composite-objects-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ปลดล็อกพลังของ Aspose.Slides สำหรับ .NET เพื่อปรับปรุงการนำเสนอของคุณโดยการสร้างวัตถุคอมโพสิตในรูปทรงเรขาคณิต บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างสไลด์ที่ดึงดูดสายตาด้วยรูปทรงเรขาคณิตที่ซับซ้อนโดยใช้ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
-  ติดตั้ง Aspose.Slides สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย Visual Studio หรือเครื่องมือการพัฒนา C# อื่นๆ
## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณเพื่อใช้ประโยชน์จากฟังก์ชัน Aspose.Slides รวมเนมสเปซต่อไปนี้ไว้ที่จุดเริ่มต้นของโค้ดของคุณ:
```csharp
using System.IO;
using Aspose.Slides.Export;
```
ตอนนี้ เราจะแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดขั้นตอนการสร้างวัตถุคอมโพสิตในรูปทรงเรขาคณิตโดยใช้ Aspose.Slides สำหรับ .NET:
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
string resultPath = Path.Combine(dataDir, "GeometryShapeCompositeObjects.pptx");
```
ในขั้นตอนนี้ เราจะเริ่มต้นสภาพแวดล้อมโดยการตั้งค่าไดเร็กทอรีและเส้นทางผลลัพธ์สำหรับการนำเสนอของเรา
## ขั้นตอนที่ 2: สร้างการนำเสนอและรูปทรงเรขาคณิต
```csharp
using (Presentation pres = new Presentation())
{
    // สร้างรูปทรงใหม่
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
ที่นี่ เราสร้างงานนำเสนอใหม่และเพิ่มสี่เหลี่ยมผืนผ้าเป็นรูปทรงเรขาคณิต
## ขั้นตอนที่ 3: กำหนดเส้นทางเรขาคณิต
```csharp
// สร้างเส้นทางเรขาคณิตแรก
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.MoveTo(0, 0);
geometryPath0.LineTo(shape.Width, 0);
geometryPath0.LineTo(shape.Width, shape.Height / 3);
geometryPath0.LineTo(0, shape.Height / 3);
geometryPath0.CloseFigure();
// สร้างเส้นทางเรขาคณิตที่สอง
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.MoveTo(0, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height);
geometryPath1.LineTo(0, shape.Height);
geometryPath1.CloseFigure();
```
ในขั้นตอนนี้ เรากำหนดเส้นทางเรขาคณิตสองเส้นทางที่จะประกอบเป็นรูปทรงเรขาคณิตของเรา
## ขั้นตอนที่ 4: ตั้งค่าเรขาคณิตรูปร่าง
```csharp
// ตั้งค่ารูปทรงเรขาคณิตเป็นองค์ประกอบของเส้นทางเรขาคณิตสองเส้นทาง
shape.SetGeometryPaths(new GeometryPath[] { geometryPath0, geometryPath1 });
```
ตอนนี้ เราตั้งค่าเรขาคณิตของรูปร่างเป็นองค์ประกอบของเส้นทางเรขาคณิตทั้งสองที่กำหนดไว้ก่อนหน้านี้
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```csharp
// บันทึกการนำเสนอ
pres.Save(resultPath, SaveFormat.Pptx);
}
```
สุดท้าย เราจะบันทึกงานนำเสนอด้วยรูปทรงเรขาคณิตแบบผสม
## บทสรุป
ยินดีด้วย! คุณสร้างวัตถุคอมโพสิตในรูปทรงเรขาคณิตได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET ทดลองใช้รูปทรงและเส้นทางต่างๆ เพื่อทำให้งานนำเสนอของคุณมีชีวิตชีวา
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Slides กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
Aspose.Slides รองรับภาษาการเขียนโปรแกรมที่หลากหลาย รวมถึง Java และ Python อย่างไรก็ตาม บทช่วยสอนนี้เน้นที่ C#
### ถาม: ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 สำรวจ[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/net/) สำหรับข้อมูลและตัวอย่างที่ครอบคลุม
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถลองใช้ Aspose.Slides สำหรับ .NET ด้วย[ทดลองฟรี](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนหรือถามคำถามได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและช่วยเหลือชุมชน
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวได้หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
