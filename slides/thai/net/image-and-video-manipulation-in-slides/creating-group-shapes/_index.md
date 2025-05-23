---
"description": "เรียนรู้วิธีการสร้างรูปร่างกลุ่มใน PowerPoint ด้วย Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อสร้างงานนำเสนอที่ดึงดูดสายตา"
"linktitle": "การสร้างรูปร่างกลุ่มในสไลด์การนำเสนอด้วย Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "Aspose.Slides - การสร้างรูปทรงกลุ่มใน .NET"
"url": "/th/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - การสร้างรูปทรงกลุ่มใน .NET

## การแนะนำ
หากคุณต้องการเพิ่มความสวยงามให้กับสไลด์การนำเสนอของคุณและจัดระเบียบเนื้อหาได้อย่างมีประสิทธิภาพมากขึ้น การรวมรูปร่างกลุ่มเป็นโซลูชันที่มีประสิทธิภาพ Aspose.Slides สำหรับ .NET มอบวิธีการสร้างและจัดการรูปร่างกลุ่มในงานนำเสนอ PowerPoint ของคุณได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำกระบวนการสร้างรูปร่างกลุ่มโดยใช้ Aspose.Slides โดยแบ่งขั้นตอนออกเป็นขั้นตอนที่ทำตามได้ง่าย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มเรียนรู้บทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides แล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์](https://releases-aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการทำงานด้วย IDE ที่เข้ากันได้กับ .NET เช่น Visual Studio
- ความรู้พื้นฐานเกี่ยวกับ C#: ทำความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ขั้นตอนที่ 1: สร้างตัวอย่างคลาสการนำเสนอ

สร้างอินสแตนซ์ของ `Presentation` คลาสและระบุไดเร็กทอรีที่เก็บเอกสารของคุณ:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // ดำเนินการตามขั้นตอนต่อไปนี้ภายในบล็อคการใช้งานนี้
}
```

## ขั้นตอนที่ 2: เข้าถึงสไลด์แรก

ดึงข้อมูลสไลด์แรกจากการนำเสนอ:

```csharp
ISlide sld = pres.Slides[0];
```

## ขั้นตอนที่ 3: การเข้าถึงคอลเลกชันรูปร่าง

เข้าถึงคอลเลกชันรูปทรงบนสไลด์:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## ขั้นตอนที่ 4: การเพิ่มรูปร่างกลุ่ม

เพิ่มรูปร่างกลุ่มลงในสไลด์:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## ขั้นตอนที่ 5: การเพิ่มรูปร่างภายในรูปร่างกลุ่ม

เติมรูปร่างกลุ่มด้วยรูปร่างแต่ละรูปร่าง:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## ขั้นตอนที่ 6: การเพิ่มกรอบรูปทรงกลุ่ม

กำหนดกรอบสำหรับรูปร่างกลุ่มทั้งหมด:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

บันทึกการนำเสนอที่แก้ไขแล้วไปยังไดเร็กทอรีที่คุณระบุ:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

ทำซ้ำขั้นตอนเหล่านี้ในแอปพลิเคชัน C# ของคุณเพื่อสร้างรูปร่างกลุ่มในสไลด์การนำเสนอของคุณโดยใช้ Aspose.Slides ได้สำเร็จ

## บทสรุป
ในบทช่วยสอนนี้ เราจะมาสำรวจขั้นตอนการสร้างรูปร่างกลุ่มด้วย Aspose.Slides สำหรับ .NET โดยทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับปรุงความสวยงามและการจัดระเบียบของงานนำเสนอ PowerPoint ของคุณได้
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับ .NET เวอร์ชันล่าสุดหรือไม่
ใช่ Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อรองรับเวอร์ชัน .NET ล่าสุด ตรวจสอบ [เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับรายละเอียดความเข้ากันได้
### ฉันสามารถทดลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่?
แน่นอน! คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถค้นหาการสนับสนุนสำหรับแบบสอบถามที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
เยี่ยมชม Aspose.Slides [ฟอรั่ม](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการหารือของชุมชน
### ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
คุณสามารถรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถซื้อลิขสิทธิ์เต็มรูปแบบสำหรับ Aspose.Slides ได้จากที่ใด
คุณสามารถซื้อใบอนุญาตได้จาก [หน้าการซื้อ](https://purchase-aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}