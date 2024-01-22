---
title: Aspose.Slides - การสร้างรูปร่างกลุ่มใน .NET
linktitle: การสร้างรูปร่างกลุ่มในสไลด์การนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างรูปร่างกลุ่มใน PowerPoint ด้วย Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการนำเสนอที่ดึงดูดสายตา
type: docs
weight: 11
url: /th/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## การแนะนำ
หากคุณต้องการปรับปรุงรูปลักษณ์ที่สวยงามของสไลด์การนำเสนอของคุณและจัดระเบียบเนื้อหาได้อย่างมีประสิทธิภาพมากขึ้น การรวมรูปร่างเป็นกลุ่มถือเป็นโซลูชันที่ทรงพลัง Aspose.Slides สำหรับ .NET มอบวิธีที่ราบรื่นในการสร้างและจัดการรูปร่างกลุ่มในงานนำเสนอ PowerPoint ของคุณ ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการสร้างรูปร่างกลุ่มโดยใช้ Aspose.Slides โดยแบ่งออกเป็นขั้นตอนที่ง่ายต่อการปฏิบัติตาม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการทำงานด้วย IDE ที่เข้ากันได้กับ .NET เช่น Visual Studio
- ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ

 สร้างอินสแตนซ์ของ`Presentation` และระบุไดเร็กทอรีที่เก็บเอกสารของคุณ:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // ทำตามขั้นตอนต่อไปนี้ภายในนี้โดยใช้บล็อก
}
```

## ขั้นตอนที่ 2: เข้าถึงสไลด์แรก

ดึงสไลด์แรกจากการนำเสนอ:

```csharp
ISlide sld = pres.Slides[0];
```

## ขั้นตอนที่ 3: การเข้าถึงคอลเลกชันรูปร่าง

เข้าถึงคอลเลกชันของรูปร่างบนสไลด์:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## ขั้นตอนที่ 4: การเพิ่มรูปร่างกลุ่ม

เพิ่มรูปร่างกลุ่มลงในสไลด์:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## ขั้นตอนที่ 5: การเพิ่มรูปร่างภายในรูปร่างกลุ่ม

เติมรูปร่างกลุ่มด้วยรูปร่างแต่ละรายการ:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## ขั้นตอนที่ 6: การเพิ่มกรอบรูปร่างกลุ่ม

กำหนดกรอบสำหรับรูปร่างทั้งกลุ่ม:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

บันทึกงานนำเสนอที่แก้ไขไปยังไดเร็กทอรีที่คุณระบุ:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

ทำซ้ำขั้นตอนเหล่านี้ในแอปพลิเคชัน C# ของคุณเพื่อสร้างรูปร่างกลุ่มในสไลด์การนำเสนอของคุณโดยใช้ Aspose.Slides

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการสร้างรูปร่างกลุ่มด้วย Aspose.Slides สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับปรุงรูปลักษณ์และการจัดระเบียบของงานนำเสนอ PowerPoint ของคุณได้
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ .NET เวอร์ชันล่าสุดหรือไม่
 ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อรองรับ .NET เวอร์ชันล่าสุด ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับรายละเอียดความเข้ากันได้
### ฉันสามารถลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่
 อย่างแน่นอน! คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับคำค้นหาที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม Aspose.Slides[ฟอรั่ม](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อใบอนุญาตแบบเต็มสำหรับ Aspose.Slides ได้ที่ไหน
 คุณสามารถซื้อใบอนุญาตได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).
