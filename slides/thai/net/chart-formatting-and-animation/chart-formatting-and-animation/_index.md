---
title: การจัดรูปแบบแผนภูมิและภาพเคลื่อนไหวใน Aspose.Slides
linktitle: การจัดรูปแบบแผนภูมิและภาพเคลื่อนไหวใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดรูปแบบและทำให้แผนภูมิเคลื่อนไหวใน Aspose.Slides สำหรับ .NET เพื่อปรับปรุงการนำเสนอของคุณด้วยภาพที่น่าดึงดูด
weight: 10
url: /th/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


การสร้างงานนำเสนอที่น่าสนใจด้วยแผนภูมิและภาพเคลื่อนไหวแบบไดนามิกสามารถช่วยเพิ่มผลกระทบของข้อความของคุณได้อย่างมาก Aspose.Slides สำหรับ .NET ช่วยให้คุณบรรลุเป้าหมายนั้นได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างภาพเคลื่อนไหวและการจัดรูปแบบแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET เราจะแบ่งขั้นตอนออกเป็นส่วนต่างๆ ที่สามารถจัดการได้เพื่อให้แน่ใจว่าคุณจะเข้าใจแนวคิดได้อย่างถี่ถ้วน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเจาะลึกการจัดรูปแบบแผนภูมิและภาพเคลื่อนไหวด้วย Aspose.Slides คุณจะต้องมีสิ่งต่อไปนี้:

1.  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET หากคุณยังไม่ได้คุณสามารถทำได้[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/slides/net/).

2. งานนำเสนอที่มีอยู่: มีงานนำเสนอที่มีอยู่ซึ่งมีแผนภูมิที่คุณต้องการจัดรูปแบบและทำให้เคลื่อนไหว

3. ความรู้พื้นฐาน C#: ความคุ้นเคยกับ C# จะเป็นประโยชน์ในการดำเนินขั้นตอนต่างๆ

เอาล่ะ มาเริ่มกันเลย

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟีเจอร์ Aspose.Slides ในโปรเจ็กต์ C# ของคุณ ให้เพิ่มสิ่งต่อไปนี้:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## การสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ในแผนภูมิ

### ขั้นตอนที่ 1: โหลดการนำเสนอและเข้าถึงแผนภูมิ

ขั้นแรก โหลดงานนำเสนอที่มีอยู่แล้วเข้าถึงแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว ตัวอย่างนี้จะถือว่าแผนภูมิอยู่บนสไลด์แรกของงานนำเสนอของคุณ

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### ขั้นตอนที่ 2: เพิ่มภาพเคลื่อนไหวให้กับองค์ประกอบของหมวดหมู่

ตอนนี้ มาเพิ่มภาพเคลื่อนไหวให้กับองค์ประกอบของหมวดหมู่กัน ในตัวอย่างนี้ เรากำลังใช้เอฟเฟ็กต์เฟดอิน

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### ขั้นตอนที่ 3: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขลงในดิสก์

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## ซีรีย์แอนิเมชันในแผนภูมิ

### ขั้นตอนที่ 1: โหลดการนำเสนอและเข้าถึงแผนภูมิ

เช่นเดียวกับตัวอย่างก่อนหน้านี้ คุณจะโหลดงานนำเสนอและเข้าถึงแผนภูมิ

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### ขั้นตอนที่ 2: เพิ่มแอนิเมชันลงในซีรีส์

ตอนนี้ มาเพิ่มภาพเคลื่อนไหวให้กับชุดแผนภูมิกัน เรากำลังใช้เอฟเฟกต์เฟดอินที่นี่เช่นกัน

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### ขั้นตอนที่ 3: บันทึกการนำเสนอ

บันทึกงานนำเสนอที่แก้ไขแล้วด้วยซีรีส์แอนิเมชัน

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## การสร้างภาพเคลื่อนไหวองค์ประกอบซีรีส์ในแผนภูมิ

### ขั้นตอนที่ 1: โหลดการนำเสนอและเข้าถึงแผนภูมิ

เช่นเดียวกับก่อนหน้านี้ ให้โหลดงานนำเสนอและเข้าถึงแผนภูมิ

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### ขั้นตอนที่ 2: เพิ่มภาพเคลื่อนไหวให้กับองค์ประกอบซีรีส์

ในขั้นตอนนี้ คุณจะเพิ่มแอนิเมชันให้กับองค์ประกอบซีรีส์ เพื่อสร้างเอฟเฟ็กต์ภาพที่น่าประทับใจ

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

อย่าลืมบันทึกงานนำเสนอด้วยองค์ประกอบซีรีส์แอนิเมชัน

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

ยินดีด้วย! ตอนนี้คุณได้เรียนรู้วิธีจัดรูปแบบและทำให้แผนภูมิเคลื่อนไหวใน Aspose.Slides สำหรับ .NET แล้ว เทคนิคเหล่านี้สามารถทำให้การนำเสนอของคุณน่าดึงดูดและให้ข้อมูลมากขึ้น

## บทสรุป

Aspose.Slides สำหรับ .NET มอบเครื่องมืออันทรงพลังสำหรับการจัดรูปแบบแผนภูมิและแอนิเมชั่น ช่วยให้คุณสร้างงานนำเสนอที่ดึงดูดสายตาและดึงดูดผู้ชมของคุณ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะเชี่ยวชาญศิลปะการแสดงภาพเคลื่อนไหวบนแผนภูมิและปรับปรุงการนำเสนอของคุณได้

## คำถามที่พบบ่อย

### 1. ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน

 คุณสามารถเข้าถึงเอกสารได้ที่[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จาก[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. มีการทดลองใช้ฟรีหรือไม่?

 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรีที่[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่

 ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้ที่[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. ฉันจะรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้ที่ไหน

 สำหรับการสนับสนุนและคำถาม โปรดไปที่ฟอรั่ม Aspose.Slides ที่[https://forum.aspose.com/](https://forum.aspose.com/).


{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
