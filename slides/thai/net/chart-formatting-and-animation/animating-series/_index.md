---
title: สร้างซีรีย์แผนภูมิเคลื่อนไหวด้วย Aspose.Slides สำหรับ .NET
linktitle: ซีรีย์แอนิเมชันในแผนภูมิ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีทำให้ชุดแผนภูมิเคลื่อนไหวด้วย Aspose.Slides สำหรับ .NET ดึงดูดผู้ชมของคุณด้วยการนำเสนอแบบไดนามิก เริ่มตอนนี้เลย!
weight: 12
url: /th/net/chart-formatting-and-animation/animating-series/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


คุณกำลังมองหาวิธีเพิ่มพิซซ่าให้กับงานนำเสนอของคุณด้วยแผนภูมิแบบเคลื่อนไหวอยู่ใช่ไหม? Aspose.Slides สำหรับ .NET พร้อมแล้วที่จะทำให้แผนภูมิของคุณมีชีวิตชีวา ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีทำให้ซีรีส์เคลื่อนไหวในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET แต่ก่อนที่เราจะดำดิ่งลงสู่การดำเนินการ เรามาพูดถึงข้อกำหนดเบื้องต้นกันก่อน

## ข้อกำหนดเบื้องต้น

หากต้องการทำให้ซีรีส์เคลื่อนไหวในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET ได้สำเร็จ คุณจะต้องมีสิ่งต่อไปนี้:

### 1. Aspose.Slides สำหรับ .NET Library

 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว หากคุณยังไม่มี คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเว็บไซต์ .NET](https://releases.aspose.com/slides/net/).

### 2. การนำเสนอที่มีอยู่พร้อมแผนภูมิ

เตรียมงานนำเสนอ PowerPoint (PPTX) ด้วยแผนภูมิที่มีอยู่ที่คุณต้องการทำให้เคลื่อนไหว

ตอนนี้เรามีข้อกำหนดเบื้องต้นครอบคลุมแล้ว เรามาแบ่งกระบวนการออกเป็นชุดขั้นตอนเพื่อทำให้ชุดแผนภูมิเคลื่อนไหว


## ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น

คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณเพื่อทำงานกับ Aspose.Slides สำหรับ .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอที่มีอยู่

ในขั้นตอนนี้ ให้โหลดงานนำเสนอ PowerPoint (PPTX) ที่มีอยู่ซึ่งมีแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // รหัสของคุณอยู่ที่นี่
}
```

## ขั้นตอนที่ 3: รับการอ้างอิงของวัตถุแผนภูมิ

หากต้องการทำงานกับแผนภูมิในงานนำเสนอ คุณจะต้องมีการอ้างอิงถึงวัตถุแผนภูมิ:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## ขั้นตอนที่ 4: ทำให้ซีรีส์เคลื่อนไหว

ตอนนี้ได้เวลาเพิ่มเอฟเฟ็กต์ภาพเคลื่อนไหวให้กับชุดแผนภูมิของคุณแล้ว เราจะเพิ่มเอฟเฟ็กต์จางลงในทั้งแผนภูมิ และทำให้แต่ละชุดปรากฏทีละรายการ

```csharp
// ทำให้แผนภูมิเคลื่อนไหว
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// เพิ่มภาพเคลื่อนไหวในแต่ละซีรีส์
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## ขั้นตอนที่ 5: บันทึกงานนำเสนอที่แก้ไข

เมื่อคุณเพิ่มเอฟเฟ็กต์ภาพเคลื่อนไหวลงในแผนภูมิแล้ว ให้บันทึกงานนำเสนอที่แก้ไขลงในดิสก์

```csharp
//บันทึกงานนำเสนอที่แก้ไข
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณสร้างซีรีส์แอนิเมชันในแผนภูมิได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET

## บทสรุป

ในบทช่วยสอนนี้ เราได้แนะนำคุณตลอดกระบวนการสร้างแอนิเมชันซีรีส์ในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET ด้วยไลบรารีอันทรงพลังนี้ คุณสามารถสร้างงานนำเสนอที่น่าสนใจและมีชีวิตชีวาที่ดึงดูดผู้ชมของคุณได้

 หากคุณมีคำถามหรือต้องการความช่วยเหลือเพิ่มเติม อย่าลังเลที่จะติดต่อชุมชน Aspose.Slides บน[ฟอรั่มการสนับสนุน](https://forum.aspose.com/).

## คำถามที่พบบ่อย

### ฉันสามารถทำให้องค์ประกอบแผนภูมิอื่นๆ เคลื่อนไหวนอกเหนือจากซีรี่ส์โดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถทำให้องค์ประกอบแผนภูมิต่างๆ เคลื่อนไหวได้ รวมถึงจุดข้อมูล แกน และคำอธิบายแผนภูมิ โดยใช้ Aspose.Slides สำหรับ .NET

### Aspose.Slides สำหรับ .NET เข้ากันได้กับ PowerPoint เวอร์ชันล่าสุดหรือไม่
Aspose.Slides สำหรับ .NET รองรับ PowerPoint เวอร์ชันต่างๆ รวมถึง PowerPoint 2007 และใหม่กว่า ทำให้มั่นใจได้ถึงความเข้ากันได้กับเวอร์ชันล่าสุด

### ฉันสามารถปรับแต่งเอฟเฟ็กต์ภาพเคลื่อนไหวสำหรับแผนภูมิแต่ละชุดแยกกันได้หรือไม่
ได้ คุณสามารถปรับแต่งเอฟเฟ็กต์แอนิเมชันสำหรับแผนภูมิแต่ละชุดเพื่อสร้างงานนำเสนอที่มีเอกลักษณ์และน่าสนใจได้

### มีรุ่นทดลองใช้สำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถทดลองใช้ห้องสมุดโดยทดลองใช้ฟรีจาก[Aspose.Slides สำหรับเว็บไซต์ .NET](https://releases.aspose.com/).

### ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถรับใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้จากหน้าการซื้อ[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
