---
title: แอนิเมชั่นแผนภูมิอันทรงพลังด้วย Aspose.Slides สำหรับ .NET
linktitle: การสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ในแผนภูมิ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้การสร้างภาพเคลื่อนไหวองค์ประกอบแผนภูมิใน PowerPoint ด้วย Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับการนำเสนอที่น่าทึ่ง
type: docs
weight: 11
url: /th/net/chart-formatting-and-animation/animating-categories-elements/
---

ในโลกของการนำเสนอ แอนิเมชั่นสามารถทำให้เนื้อหาของคุณดูมีชีวิตชีวา โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับแผนภูมิ Aspose.Slides สำหรับ .NET นำเสนอฟีเจอร์อันทรงพลังมากมายที่ช่วยให้คุณสามารถสร้างแอนิเมชั่นที่น่าทึ่งสำหรับแผนภูมิของคุณได้ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน คุณควรมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากยังไม่มีสามารถ Download ได้จาก[ที่นี่](https://releases.aspose.com/slides/net/).

- งานนำเสนอที่มีอยู่: คุณควรมีงานนำเสนอ PowerPoint พร้อมแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว หากคุณยังไม่มี ให้สร้างการนำเสนอตัวอย่างพร้อมแผนภูมิเพื่อการทดสอบ

ตอนนี้คุณมีทุกอย่างพร้อมแล้ว มาเริ่มสร้างภาพเคลื่อนไหวองค์ประกอบแผนภูมิเหล่านั้นกันดีกว่า!

## นำเข้าเนมสเปซ

ขั้นตอนแรกคือการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides เพิ่มเนมสเปซต่อไปนี้ในโครงการของคุณ:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // รับการอ้างอิงของวัตถุแผนภูมิ
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

ในขั้นตอนนี้ เราจะโหลดงานนำเสนอ PowerPoint ที่มีอยู่ซึ่งมีแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว จากนั้นเราเข้าถึงวัตถุแผนภูมิภายในสไลด์แรก

## ขั้นตอนที่ 2: ทำให้องค์ประกอบของหมวดหมู่เคลื่อนไหว

```csharp
// องค์ประกอบหมวดหมู่ภาพเคลื่อนไหว
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

ขั้นตอนนี้จะเพิ่มเอฟเฟ็กต์ภาพเคลื่อนไหว "จางลง" ให้กับทั้งแผนภูมิ ทำให้ปรากฏต่อจากภาพเคลื่อนไหวก่อนหน้า

ต่อไป เราจะเพิ่มภาพเคลื่อนไหวให้กับแต่ละองค์ประกอบภายในแต่ละหมวดหมู่ของแผนภูมิ นี่คือจุดที่ความมหัศจรรย์ที่แท้จริงเกิดขึ้น

## ขั้นตอนที่ 3: ทำให้แต่ละองค์ประกอบเคลื่อนไหว

เราจะแบ่งภาพเคลื่อนไหวของแต่ละองค์ประกอบในแต่ละหมวดหมู่ออกเป็นขั้นตอนต่อไปนี้:

### ขั้นตอนที่ 3.1: การสร้างภาพเคลื่อนไหวองค์ประกอบในหมวดหมู่ 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

ที่นี่ เรากำลังสร้างภาพเคลื่อนไหวให้กับแต่ละองค์ประกอบภายในหมวดหมู่ 0 ของแผนภูมิ ทำให้องค์ประกอบเหล่านั้นปรากฏขึ้นทีละรายการ เอฟเฟกต์ "ปรากฏ" ใช้สำหรับภาพเคลื่อนไหวนี้

### ขั้นตอนที่ 3.2: การสร้างภาพเคลื่อนไหวองค์ประกอบในหมวดหมู่ 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

กระบวนการนี้ทำซ้ำสำหรับหมวดหมู่ 1 โดยทำให้แต่ละองค์ประกอบเคลื่อนไหวโดยใช้เอฟเฟกต์ "ปรากฏ"

### ขั้นตอนที่ 3.3: การสร้างภาพเคลื่อนไหวองค์ประกอบในหมวดหมู่ 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

กระบวนการเดียวกันนี้ดำเนินต่อไปสำหรับหมวดหมู่ 2 โดยทำให้องค์ประกอบต่างๆ เคลื่อนไหวทีละรายการ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

```csharp
// เขียนไฟล์การนำเสนอลงดิสก์
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

ในขั้นตอนสุดท้าย เราจะบันทึกงานนำเสนอพร้อมกับภาพเคลื่อนไหวที่เพิ่มเข้ามาใหม่ ตอนนี้ องค์ประกอบแผนภูมิของคุณจะเคลื่อนไหวได้อย่างสวยงามเมื่อคุณเรียกใช้งานนำเสนอ

## บทสรุป

การสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ในแผนภูมิสามารถเพิ่มความดึงดูดสายตาให้กับงานนำเสนอของคุณได้ ด้วย Aspose.Slides สำหรับ .NET กระบวนการนี้จะตรงไปตรงมาและมีประสิทธิภาพ คุณได้เรียนรู้วิธีนำเข้าเนมสเปซ โหลดงานนำเสนอ และเพิ่มภาพเคลื่อนไหวลงในทั้งแผนภูมิและองค์ประกอบแต่ละรายการแล้ว สร้างสรรค์และทำให้การนำเสนอของคุณน่าดึงดูดยิ่งขึ้นด้วย Aspose.Slides สำหรับ .NET

## คำถามที่พบบ่อย

### 1. ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จาก[ลิงค์นี้](https://releases.aspose.com/slides/net/).

### 2. ฉันจำเป็นต้องมีประสบการณ์การเขียนโค้ดเพื่อใช้ Aspose.Slides สำหรับ .NET หรือไม่
แม้ว่าประสบการณ์การเขียนโค้ดจะมีประโยชน์ แต่ Aspose.Slides สำหรับ .NET ก็มีเอกสารประกอบและตัวอย่างที่ครอบคลุมเพื่อช่วยเหลือผู้ใช้ในทุกระดับทักษะ

### 3. ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับ PowerPoint เวอร์ชันใดก็ได้หรือไม่
Aspose.Slides สำหรับ .NET ได้รับการออกแบบมาเพื่อทำงานร่วมกับ PowerPoint เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้

### 4. ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET[ที่นี่](https://purchase.aspose.com/temporary-license/).

### 5. มีฟอรัมชุมชนสำหรับ Aspose.Slides สำหรับการรองรับ .NET หรือไม่
 ใช่ คุณสามารถค้นหาฟอรัมชุมชนที่สนับสนุนสำหรับ Aspose.Slides สำหรับ .NET[ที่นี่](https://forum.aspose.com/).
