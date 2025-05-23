---
"description": "เรียนรู้วิธีสร้างภาพเคลื่อนไหวให้กับแผนภูมิด้วย Aspose.Slides สำหรับ .NET ดึงดูดผู้ฟังด้วยการนำเสนอแบบไดนามิก เริ่มต้นเลยตอนนี้!"
"linktitle": "การสร้างภาพเคลื่อนไหวของซีรีส์ในแผนภูมิ"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "สร้างแอนิเมชั่นแผนภูมิชุดด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/net/chart-formatting-and-animation/animating-series/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างแอนิเมชั่นแผนภูมิชุดด้วย Aspose.Slides สำหรับ .NET


คุณกำลังมองหาวิธีเพิ่มความมีชีวิตชีวาให้กับงานนำเสนอของคุณด้วยแผนภูมิเคลื่อนไหวอยู่หรือเปล่า Aspose.Slides สำหรับ .NET พร้อมที่จะช่วยให้แผนภูมิของคุณมีชีวิตชีวาขึ้นมา ในคู่มือทีละขั้นตอนนี้ เราจะแสดงให้คุณเห็นถึงวิธีการสร้างภาพเคลื่อนไหวของซีรีส์ในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET แต่ก่อนที่เราจะลงรายละเอียด เรามาทำความเข้าใจกับข้อกำหนดเบื้องต้นกันก่อน

## ข้อกำหนดเบื้องต้น

หากต้องการสร้างแอนิเมชั่นชุดในแผนภูมิได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET คุณจะต้องมีสิ่งต่อไปนี้:

### 1. Aspose.Slides สำหรับไลบรารี .NET

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดจาก [Aspose.Slides สำหรับเว็บไซต์ .NET](https://releases-aspose.com/slides/net/).

### 2. การนำเสนอที่มีอยู่พร้อมแผนภูมิ

เตรียมการนำเสนอ PowerPoint (PPTX) ด้วยแผนภูมิที่มีอยู่ที่คุณต้องการสร้างภาพเคลื่อนไหว

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว มาแบ่งกระบวนการออกเป็นขั้นตอนต่างๆ เพื่อสร้างภาพเคลื่อนไหวให้กับแผนภูมิกัน


## ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น

คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณเพื่อทำงานกับ Aspose.Slides สำหรับ .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอที่มีอยู่

ในขั้นตอนนี้ โหลดงานนำเสนอ PowerPoint ที่มีอยู่ (PPTX) ของคุณซึ่งประกอบด้วยแผนภูมิที่คุณต้องการสร้างภาพเคลื่อนไหว

```csharp
// เส้นทางสู่ไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์การนำเสนอ 
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // รหัสของคุณอยู่ที่นี่
}
```

## ขั้นตอนที่ 3: รับการอ้างอิงของวัตถุแผนภูมิ

ในการทำงานกับแผนภูมิในงานนำเสนอของคุณ คุณจะต้องได้รับการอ้างอิงไปยังวัตถุแผนภูมิ:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## ขั้นตอนที่ 4: สร้างแอนิเมชั่นซีรีย์

ตอนนี้ถึงเวลาเพิ่มเอฟเฟกต์แอนิเมชันให้กับชุดแผนภูมิของคุณแล้ว เราจะเพิ่มเอฟเฟกต์การเฟดอินให้กับแผนภูมิทั้งหมด และทำให้แต่ละชุดปรากฏขึ้นทีละชุด

```csharp
// สร้างภาพเคลื่อนไหวให้กับแผนภูมิ
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// เพิ่มแอนิเมชั่นให้กับแต่ละซีรีย์
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอที่แก้ไขแล้ว

เมื่อคุณเพิ่มเอฟเฟ็กต์แอนิเมชันลงในแผนภูมิแล้ว ให้บันทึกการนำเสนอที่ปรับเปลี่ยนแล้วลงในดิสก์

```csharp
// บันทึกการนำเสนอที่แก้ไขแล้ว
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณสร้างแอนิเมชั่นซีรีส์ในแผนภูมิได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET

## บทสรุป

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการสร้างแอนิเมชั่นซีรีส์ในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET ด้วยไลบรารีอันทรงพลังนี้ คุณสามารถสร้างงานนำเสนอที่น่าสนใจและมีชีวิตชีวาที่จะดึงดูดผู้ฟังของคุณได้

หากคุณมีคำถามหรือต้องการความช่วยเหลือเพิ่มเติม โปรดอย่าลังเลที่จะติดต่อชุมชน Aspose.Slides [ฟอรั่มสนับสนุน](https://forum-aspose.com/).

## คำถามที่พบบ่อย

### ฉันสามารถสร้างภาพเคลื่อนไหวองค์ประกอบแผนภูมิอื่นๆ นอกเหนือจากชุดข้อมูลโดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถสร้างภาพเคลื่อนไหวให้กับองค์ประกอบแผนภูมิต่างๆ รวมถึงจุดข้อมูล แกน และคำอธิบาย โดยใช้ Aspose.Slides สำหรับ .NET

### Aspose.Slides สำหรับ .NET เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดได้หรือไม่
Aspose.Slides สำหรับ .NET รองรับ PowerPoint เวอร์ชันต่างๆ มากมาย รวมถึง PowerPoint 2007 และรุ่นใหม่กว่า ซึ่งรับประกันความเข้ากันได้กับเวอร์ชันล่าสุดส่วนใหญ่

### ฉันสามารถปรับแต่งเอฟเฟ็กต์แอนิเมชันสำหรับแต่ละชุดแผนภูมิได้ทีละรายการหรือไม่
ใช่ คุณสามารถปรับแต่งเอฟเฟกต์แอนิเมชันสำหรับชุดแผนภูมิแต่ละชุดเพื่อสร้างการนำเสนอที่ไม่ซ้ำใครและน่าดึงดูดได้

### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ .NET หรือไม่
ใช่ คุณสามารถทดลองใช้งานห้องสมุดได้ด้วยการทดลองใช้ฟรีจาก [Aspose.Slides สำหรับเว็บไซต์ .NET](https://releases-aspose.com/).

### ฉันสามารถซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ใด
คุณสามารถรับใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้จากหน้าการซื้อ [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}