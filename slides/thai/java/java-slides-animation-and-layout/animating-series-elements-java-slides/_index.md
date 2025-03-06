---
title: การสร้างภาพเคลื่อนไหวองค์ประกอบซีรีส์ใน Java Slides
linktitle: การสร้างภาพเคลื่อนไหวองค์ประกอบซีรีส์ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีทำให้องค์ประกอบชุดเคลื่อนไหวในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนที่ครอบคลุมพร้อมซอร์สโค้ดเพื่อปรับปรุงการนำเสนอของคุณ
weight: 12
url: /th/java/animation-and-layout/animating-series-elements-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างภาพเคลื่อนไหวองค์ประกอบซีรีส์ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการสร้างภาพเคลื่อนไหวองค์ประกอบชุดในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แอนิเมชั่นสามารถทำให้การนำเสนอของคุณน่าสนใจและให้ข้อมูลมากขึ้น ในตัวอย่างนี้ เราจะเน้นที่การทำให้แผนภูมิเคลื่อนไหวในสไลด์ PowerPoint

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Slides สำหรับไลบรารี Java แล้ว
- งานนำเสนอ PowerPoint ที่มีอยู่พร้อมแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว
- ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

 ขั้นแรก คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## ขั้นตอนที่ 2: รับการอ้างอิงไปยังแผนภูมิ

เมื่อโหลดงานนำเสนอแล้ว รับข้อมูลอ้างอิงไปยังแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่บนสไลด์แรก

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## ขั้นตอนที่ 3: เพิ่มเอฟเฟกต์ภาพเคลื่อนไหว

 ตอนนี้ มาเพิ่มเอฟเฟ็กต์ภาพเคลื่อนไหวให้กับองค์ประกอบแผนภูมิกัน เราจะใช้`slide.getTimeline().getMainSequence().addEffect()` วิธีการระบุว่าแผนภูมิควรเคลื่อนไหวอย่างไร

```java
// ทำให้แผนภูมิทั้งหมดเคลื่อนไหว
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// ทำให้องค์ประกอบแต่ละชุดเคลื่อนไหว (คุณสามารถปรับแต่งส่วนนี้ได้)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

ในโค้ดด้านบน ขั้นแรกเราจะทำให้ทั้งแผนภูมิเคลื่อนไหวด้วยเอฟเฟกต์ "จางลง" จากนั้น เราวนซ้ำชุดข้อมูลและจุดต่างๆ ภายในแผนภูมิ และใช้เอฟเฟกต์ "ปรากฏ" กับแต่ละองค์ประกอบ คุณสามารถปรับแต่งประเภทภาพเคลื่อนไหวและทริกเกอร์ได้ตามต้องการ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วพร้อมภาพเคลื่อนไหวลงในไฟล์ใหม่

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## ซอร์สโค้ดที่สมบูรณ์สำหรับการสร้างภาพเคลื่อนไหวองค์ประกอบซีรีส์ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// โหลดงานนำเสนอ
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// รับการอ้างอิงของวัตถุแผนภูมิ
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// ทำให้องค์ประกอบซีรีส์เคลื่อนไหว
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// เขียนไฟล์การนำเสนอลงดิสก์
	presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

คุณได้เรียนรู้วิธีสร้างภาพเคลื่อนไหวองค์ประกอบชุดในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แอนิเมชั่นสามารถปรับปรุงการนำเสนอของคุณและทำให้พวกเขาน่าดึงดูดยิ่งขึ้น ปรับแต่งเอฟเฟ็กต์ภาพเคลื่อนไหวและทริกเกอร์ให้เหมาะกับความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งภาพเคลื่อนไหวสำหรับองค์ประกอบแผนภูมิแต่ละรายการได้อย่างไร

คุณสามารถปรับแต่งภาพเคลื่อนไหวสำหรับองค์ประกอบแผนภูมิแต่ละรายการได้โดยการแก้ไขประเภทภาพเคลื่อนไหวและทริกเกอร์ในโค้ด ในตัวอย่างของเรา เราใช้เอฟเฟกต์ "ปรากฏ" แต่คุณสามารถเลือกประเภทภาพเคลื่อนไหวได้หลากหลาย เช่น "จางลง" "บินเข้า" ฯลฯ และระบุทริกเกอร์ที่แตกต่างกัน เช่น "เมื่อคลิก" "หลังจากก่อนหน้า" หรือ "กับก่อนหน้า"

### ฉันสามารถนำภาพเคลื่อนไหวไปใช้กับวัตถุอื่นในสไลด์ PowerPoint ได้หรือไม่

 ใช่ คุณสามารถนำภาพเคลื่อนไหวไปใช้กับวัตถุต่างๆ ในสไลด์ PowerPoint ได้ ไม่ใช่แค่แผนภูมิเท่านั้น ใช้`addEffect` วิธีการระบุวัตถุที่คุณต้องการให้เคลื่อนไหวและคุณสมบัติภาพเคลื่อนไหวที่ต้องการ

### ฉันจะรวม Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของฉันได้อย่างไร

หากต้องการรวม Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของคุณ คุณต้องรวมไลบรารีไว้ในพาธบิวด์ของคุณหรือใช้เครื่องมือการจัดการการพึ่งพาเช่น Maven หรือ Gradle โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับคำแนะนำในการผสานรวมโดยละเอียด

### มีวิธีดูตัวอย่างภาพเคลื่อนไหวในแอปพลิเคชัน PowerPoint หรือไม่?

ได้ หลังจากบันทึกงานนำเสนอแล้ว คุณสามารถเปิดในแอปพลิเคชัน PowerPoint เพื่อดูตัวอย่างภาพเคลื่อนไหวและทำการปรับเปลี่ยนเพิ่มเติมได้หากจำเป็น PowerPoint มีโหมดแสดงตัวอย่างเพื่อจุดประสงค์นี้

### มีตัวเลือกภาพเคลื่อนไหวขั้นสูงเพิ่มเติมใน Aspose.Slides สำหรับ Java หรือไม่

ใช่ Aspose.Slides สำหรับ Java มีตัวเลือกภาพเคลื่อนไหวขั้นสูงมากมาย รวมถึงเส้นทางการเคลื่อนไหว การกำหนดเวลา และภาพเคลื่อนไหวแบบโต้ตอบ คุณสามารถสำรวจเอกสารและตัวอย่างที่ Aspose.Slides จัดเตรียมไว้ให้เพื่อใช้ภาพเคลื่อนไหวขั้นสูงในการนำเสนอของคุณ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
