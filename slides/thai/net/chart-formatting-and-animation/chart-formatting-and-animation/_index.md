---
"description": "เรียนรู้วิธีการจัดรูปแบบและสร้างภาพเคลื่อนไหวของแผนภูมิใน Aspose.Slides สำหรับ .NET เพื่อเพิ่มประสิทธิภาพการนำเสนอของคุณด้วยภาพอันน่าดึงดูดใจ"
"linktitle": "การจัดรูปแบบแผนภูมิและแอนิเมชั่นใน Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การจัดรูปแบบแผนภูมิและแอนิเมชั่นใน Aspose.Slides"
"url": "/th/net/chart-formatting-and-animation/chart-formatting-and-animation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การจัดรูปแบบแผนภูมิและแอนิเมชั่นใน Aspose.Slides


การสร้างงานนำเสนอที่น่าสนใจด้วยแผนภูมิและแอนิเมชั่นแบบไดนามิกสามารถช่วยเพิ่มผลกระทบของข้อความของคุณได้อย่างมาก Aspose.Slides สำหรับ .NET ช่วยให้คุณบรรลุเป้าหมายดังกล่าวได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการสร้างแอนิเมชั่นและจัดรูปแบบแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET เราจะแบ่งขั้นตอนออกเป็นหลายส่วนเพื่อให้จัดการได้เพื่อให้แน่ใจว่าคุณเข้าใจแนวคิดอย่างถ่องแท้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะลงลึกในการจัดรูปแบบแผนภูมิและแอนิเมชั่นด้วย Aspose.Slides คุณจะต้องมีสิ่งต่อไปนี้:

1. Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET แล้ว หากยังไม่ได้ติดตั้ง คุณสามารถทำได้ดังนี้ [ดาวน์โหลดได้ที่นี่](https://releases-aspose.com/slides/net/).

2. งานนำเสนอที่มีอยู่: มีงานนำเสนอที่มีอยู่ซึ่งประกอบด้วยแผนภูมิที่คุณต้องการจัดรูปแบบและทำให้เคลื่อนไหว

3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับ C# จะเป็นประโยชน์ในการดำเนินการตามขั้นตอนต่างๆ

ตอนนี้เรามาเริ่มกันเลยดีกว่า

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟีเจอร์ Aspose.Slides ในโครงการ C# ของคุณ ให้เพิ่มสิ่งต่อไปนี้:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่ในแผนภูมิ

### ขั้นตอนที่ 1: โหลดการนำเสนอและเข้าถึงแผนภูมิ

ขั้นแรก โหลดงานนำเสนอที่มีอยู่และเข้าถึงแผนภูมิที่คุณต้องการสร้างภาพเคลื่อนไหว ตัวอย่างนี้ถือว่าแผนภูมินั้นอยู่ในสไลด์แรกของงานนำเสนอของคุณ

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### ขั้นตอนที่ 2: เพิ่มแอนิเมชั่นให้กับองค์ประกอบหมวดหมู่

ตอนนี้เรามาเพิ่มแอนิเมชั่นให้กับองค์ประกอบหมวดหมู่กัน ในตัวอย่างนี้ เราจะใช้เอฟเฟกต์เฟดอิน

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### ขั้นตอนที่ 3: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอที่แก้ไขแล้วลงในดิสก์

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## การสร้างภาพเคลื่อนไหวของซีรีส์ในแผนภูมิ

### ขั้นตอนที่ 1: โหลดการนำเสนอและเข้าถึงแผนภูมิ

คล้ายกับตัวอย่างก่อนหน้านี้ คุณจะโหลดงานนำเสนอและเข้าถึงแผนภูมิ

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### ขั้นตอนที่ 2: เพิ่มแอนิเมชั่นลงในซีรีย์

ตอนนี้เรามาเพิ่มแอนิเมชั่นให้กับชุดแผนภูมิกัน เรากำลังใช้เอฟเฟกต์เฟดอินที่นี่ด้วย

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### ขั้นตอนที่ 3: บันทึกการนำเสนอ

บันทึกการนำเสนอที่ปรับเปลี่ยนแล้วเป็นซีรีย์แอนิเมชั่น

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## การสร้างภาพเคลื่อนไหวขององค์ประกอบซีรีส์ในแผนภูมิ

### ขั้นตอนที่ 1: โหลดการนำเสนอและเข้าถึงแผนภูมิ

เช่นเดียวกับก่อนหน้านี้ โหลดการนำเสนอและเข้าถึงแผนภูมิ

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### ขั้นตอนที่ 2: เพิ่มแอนิเมชั่นลงในองค์ประกอบซีรีส์

ในขั้นตอนนี้ คุณจะเพิ่มแอนิเมชันให้กับองค์ประกอบซีรีส์ เพื่อสร้างเอฟเฟกต์ภาพที่น่าประทับใจ

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### ขั้นตอนที่ 3: บันทึกการนำเสนอ

อย่าลืมบันทึกการนำเสนอที่มีองค์ประกอบซีรีส์แบบเคลื่อนไหว

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีการจัดรูปแบบและสร้างภาพเคลื่อนไหวของแผนภูมิใน Aspose.Slides สำหรับ .NET แล้ว เทคนิคเหล่านี้สามารถทำให้การนำเสนอของคุณน่าสนใจและให้ข้อมูลมากขึ้น

## บทสรุป

Aspose.Slides สำหรับ .NET มอบเครื่องมืออันทรงพลังสำหรับการจัดรูปแบบและแอนิเมชั่นแผนภูมิ ช่วยให้คุณสร้างงานนำเสนอที่ดึงดูดสายตาผู้ฟังได้ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถเชี่ยวชาญศิลปะของแอนิเมชั่นแผนภูมิและปรับปรุงการนำเสนอของคุณได้

## คำถามที่พบบ่อย

### 1. ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน

คุณสามารถเข้าถึงเอกสารได้ที่ [ภาษาไทย: https://reference.aspose.com/slides/net/](https://reference-aspose.com/slides/net/).

### 2. ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร

คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จาก [ภาษาไทย: https://releases.aspose.com/slides/net/](https://releases-aspose.com/slides/net/).

### 3. มีการทดลองใช้ฟรีหรือไม่?

ใช่ คุณสามารถรับรุ่นทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรีที่ [https://releases.aspose.com/](https://releases-aspose.com/).

### 4. ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่

ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้ที่ [https://purchase.aspose.com/ใบอนุญาตชั่วคราว/](https://purchase-aspose.com/temporary-license/).

### 5. ฉันจะได้รับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน

สำหรับการสนับสนุนและคำถาม โปรดไปที่ฟอรัม Aspose.Slides ได้ที่ [https://forum.aspose.com/](https://forum-aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}