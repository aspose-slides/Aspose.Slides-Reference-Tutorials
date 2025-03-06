---
title: การสร้างภาพเคลื่อนไหวองค์ประกอบซีรีส์ในแผนภูมิ
linktitle: การสร้างภาพเคลื่อนไหวองค์ประกอบซีรีส์ในแผนภูมิ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้การสร้างภาพเคลื่อนไหวชุดแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET สร้างงานนำเสนอที่น่าสนใจด้วยภาพแบบไดนามิก คำแนะนำจากผู้เชี่ยวชาญพร้อมตัวอย่างโค้ด
weight: 13
url: /th/net/chart-formatting-and-animation/animating-series-elements/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


คุณกำลังมองหาการปรับปรุงงานนำเสนอ PowerPoint ของคุณด้วยแผนภูมิและภาพเคลื่อนไหวที่สะดุดตาหรือไม่? Aspose.Slides สำหรับ .NET สามารถช่วยให้คุณบรรลุเป้าหมายนั้นได้ ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแสดงวิธีทำให้องค์ประกอบชุดข้อมูลเคลื่อนไหวในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET ไลบรารีอันทรงพลังนี้ช่วยให้คุณสร้าง จัดการ และปรับแต่งงานนำเสนอ PowerPoint โดยทางโปรแกรม ทำให้คุณควบคุมสไลด์และเนื้อหาได้อย่างเต็มที่

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะดำดิ่งสู่โลกแห่งภาพเคลื่อนไหวบนแผนภูมิด้วย Aspose.Slides สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับ .NET: คุณต้องติดตั้ง Aspose.Slides สำหรับ .NET หากคุณยังไม่มี คุณสามารถดาวน์โหลดได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/net/).

2. งานนำเสนอ PowerPoint ที่มีอยู่: คุณควรมีงานนำเสนอ PowerPoint ที่มีอยู่พร้อมแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว หากคุณยังไม่มี ให้สร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิ

เมื่อคุณมีข้อกำหนดเบื้องต้นที่จำเป็นแล้ว เรามาเริ่มสร้างภาพเคลื่อนไหวองค์ประกอบชุดข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET กันดีกว่า

## นำเข้าเนมสเปซ

ก่อนที่คุณจะเริ่มเขียนโค้ด คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides สำหรับ .NET เนมสเปซเหล่านี้จะให้การเข้าถึงคลาสและวิธีการที่จำเป็นในการสร้างภาพเคลื่อนไหว

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

 ขั้นแรก คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีอยู่ซึ่งมีแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    //รหัสของคุณสำหรับภาพเคลื่อนไหวแผนภูมิจะอยู่ที่นี่
    // เราจะกล่าวถึงสิ่งนั้นในขั้นตอนต่อๆ ไป
    
    // บันทึกการนำเสนอด้วยภาพเคลื่อนไหว
    presentation.Save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
```

## ขั้นตอนที่ 2: รับการอ้างอิงของวัตถุแผนภูมิ

คุณต้องเข้าถึงแผนภูมิภายในงานนำเสนอของคุณ เมื่อต้องการทำเช่นนี้ ขอรับการอ้างอิงไปยังวัตถุแผนภูมิ เราถือว่าแผนภูมิอยู่บนสไลด์แรก แต่คุณสามารถปรับค่านี้ได้หากแผนภูมิของคุณอยู่ในสไลด์อื่น

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## ขั้นตอนที่ 3: ทำให้องค์ประกอบซีรีส์เคลื่อนไหว

มาถึงส่วนที่น่าตื่นเต้นแล้ว - การสร้างภาพเคลื่อนไหวองค์ประกอบชุดข้อมูลในแผนภูมิของคุณ คุณสามารถเพิ่มภาพเคลื่อนไหวเพื่อทำให้องค์ประกอบปรากฏหรือหายไปในลักษณะที่ดึงดูดสายตา ในตัวอย่างนี้ เราจะทำให้องค์ประกอบต่างๆ ปรากฏขึ้นทีละรายการ

```csharp
// ทำให้แผนภูมิทั้งหมดเคลื่อนไหวเพื่อให้จางลงหลังจากภาพเคลื่อนไหวก่อนหน้า
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// ทำให้องค์ประกอบเคลื่อนไหวภายในซีรีส์ ปรับดัชนีตามความจำเป็น
for (int i = 0; i < chart.Series.Count; i++)
{
    for (int j = 0; j < chart.Series[i].DataPoints.Count; j++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีสร้างภาพเคลื่อนไหวองค์ประกอบชุดข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว ด้วยความรู้นี้ คุณสามารถสร้างงานนำเสนอ PowerPoint แบบไดนามิกและน่าสนใจที่จะดึงดูดผู้ชมของคุณได้

 Aspose.Slides for .NET เป็นเครื่องมืออันทรงพลังสำหรับการทำงานกับไฟล์ PowerPoint โดยทางโปรแกรม และเปิดโลกแห่งความเป็นไปได้ในการสร้างงานนำเสนอระดับมืออาชีพ รู้สึกอิสระที่จะสำรวจ[เอกสารประกอบ](https://reference.aspose.com/slides/net/)สำหรับคุณสมบัติขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม

## คำถามที่พบบ่อย

### 1. Aspose.Slides สำหรับ .NET ใช้งานได้ฟรีหรือไม่

 Aspose.Slides สำหรับ .NET เป็นไลบรารีเชิงพาณิชย์ แต่คุณสามารถสำรวจได้ด้วยการทดลองใช้ฟรี สำหรับการใช้งานเต็มรูปแบบ คุณจะต้องซื้อใบอนุญาตจาก[ที่นี่](https://purchase.aspose.com/buy).

### 2. ฉันสามารถทำให้องค์ประกอบอื่นๆ ใน PowerPoint เคลื่อนไหวโดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่

ใช่ Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถทำให้องค์ประกอบ PowerPoint ต่างๆ เคลื่อนไหวได้ รวมถึงรูปร่าง ข้อความ รูปภาพ และแผนภูมิ ดังที่แสดงในบทช่วยสอนนี้

### 3. การเขียนโค้ดด้วย Aspose.Slides สำหรับ .NET เหมาะสำหรับผู้เริ่มต้นหรือไม่

แม้ว่าความเข้าใจพื้นฐานเกี่ยวกับ C# และ PowerPoint จะเป็นประโยชน์ แต่ Aspose.Slides สำหรับ .NET ก็มีเอกสารและตัวอย่างที่ครอบคลุมเพื่อช่วยเหลือผู้ใช้ทุกระดับทักษะ

### 4. ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับภาษา .NET อื่นๆ เช่น VB.NET ได้หรือไม่

ได้ Aspose.Slides สำหรับ .NET สามารถใช้ได้กับ .NET ภาษาต่างๆ รวมถึง C# และ VB.NET

### 5. ฉันจะรับการสนับสนุนจากชุมชนหรือความช่วยเหลือเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้อย่างไร

 หากคุณมีคำถามหรือต้องการความช่วยเหลือ คุณสามารถไปที่[Aspose.Slides สำหรับฟอรัม .NET](https://forum.aspose.com/) เพื่อสนับสนุนชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
