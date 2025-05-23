---
"description": "เรียนรู้วิธีสร้างภาพเคลื่อนไหวให้กับองค์ประกอบในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนที่ครอบคลุมนี้พร้อมโค้ดต้นฉบับเพื่อปรับปรุงการนำเสนอของคุณ"
"linktitle": "การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบซีรีส์ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบซีรีส์ใน Java Slides"
"url": "/th/java/animation-and-layout/animating-series-elements-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบซีรีส์ใน Java Slides


## การแนะนำการสร้างแอนิเมชันองค์ประกอบซีรีส์ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการสร้างภาพเคลื่อนไหวขององค์ประกอบในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ภาพเคลื่อนไหวสามารถทำให้การนำเสนอของคุณน่าสนใจและให้ข้อมูลมากขึ้น ในตัวอย่างนี้ เราจะเน้นที่การสร้างภาพเคลื่อนไหวของแผนภูมิในสไลด์ PowerPoint

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว
- การนำเสนอ PowerPoint ที่มีอยู่พร้อมแผนภูมิที่คุณต้องการสร้างภาพเคลื่อนไหว
- การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

ขั้นแรก คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีแผนภูมิที่คุณต้องการให้เคลื่อนไหว แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## ขั้นตอนที่ 2: รับการอ้างอิงแผนภูมิ

เมื่อโหลดงานนำเสนอเสร็จแล้ว ให้รับการอ้างอิงไปยังแผนภูมิที่คุณต้องการสร้างภาพเคลื่อนไหว ในตัวอย่างนี้ เราจะถือว่าแผนภูมิอยู่ในสไลด์แรก

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## ขั้นตอนที่ 3: เพิ่มเอฟเฟ็กต์แอนิเมชัน

ตอนนี้เรามาเพิ่มเอฟเฟ็กต์แอนิเมชันให้กับองค์ประกอบแผนภูมิกัน เราจะใช้ `slide.getTimeline().getMainSequence().addEffect()` วิธีการระบุว่าแผนภูมิควรแสดงภาพเคลื่อนไหวอย่างไร

```java
// สร้างภาพเคลื่อนไหวให้กับแผนภูมิทั้งหมด
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// สร้างภาพเคลื่อนไหวให้กับองค์ประกอบแต่ละชุดของซีรีส์ (คุณสามารถปรับแต่งส่วนนี้เองได้)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

ในโค้ดด้านบนนี้ เราจะสร้างภาพเคลื่อนไหวให้กับแผนภูมิทั้งหมดโดยใช้เอฟเฟกต์ "Fade" ก่อน จากนั้น เราจะวนซ้ำผ่านชุดข้อมูลและจุดต่างๆ ในแผนภูมิ และใช้เอฟเฟกต์ "Appear" กับแต่ละองค์ประกอบ คุณสามารถปรับแต่งประเภทภาพเคลื่อนไหวและทริกเกอร์ได้ตามต้องการ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่ปรับเปลี่ยนพร้อมแอนิเมชันลงในไฟล์ใหม่

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการสร้างแอนิเมชันองค์ประกอบซีรีส์ใน Java Slides

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
	// สร้างแอนิเมชั่นองค์ประกอบซีรีส์
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

คุณได้เรียนรู้วิธีการสร้างแอนิเมชั่นให้กับองค์ประกอบในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แล้ว แอนิเมชั่นสามารถเพิ่มประสิทธิภาพให้กับการนำเสนอของคุณและทำให้ดูน่าสนใจยิ่งขึ้น ปรับแต่งเอฟเฟกต์แอนิเมชั่นและทริกเกอร์ให้เหมาะกับความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งแอนิเมชั่นสำหรับองค์ประกอบแผนภูมิแต่ละองค์ประกอบได้อย่างไร

คุณสามารถปรับแต่งแอนิเมชั่นสำหรับองค์ประกอบแผนภูมิแต่ละองค์ประกอบได้โดยแก้ไขประเภทแอนิเมชั่นและทริกเกอร์ในโค้ด ในตัวอย่างของเรา เราใช้เอฟเฟกต์ "ปรากฏ" แต่คุณสามารถเลือกจากประเภทแอนิเมชั่นต่างๆ เช่น "จางลง" "บินเข้ามา" เป็นต้น และระบุทริกเกอร์ที่แตกต่างกัน เช่น "เมื่อคลิก" "หลังจากก่อนหน้า" หรือ "พร้อมกับก่อนหน้า"

### ฉันสามารถใช้แอนิเมชั่นกับวัตถุอื่นในสไลด์ PowerPoint ได้หรือไม่

ใช่ คุณสามารถใช้แอนิเมชั่นกับวัตถุต่างๆ ในสไลด์ PowerPoint ได้ ไม่ใช่แค่แผนภูมิเท่านั้น ใช้ `addEffect` วิธีการระบุวัตถุที่คุณต้องการสร้างภาพเคลื่อนไหวและคุณสมบัติภาพเคลื่อนไหวที่ต้องการ

### ฉันจะรวม Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของฉันได้อย่างไร

หากต้องการรวม Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของคุณ คุณต้องรวมไลบรารีไว้ในเส้นทางการสร้างของคุณหรือใช้เครื่องมือการจัดการการอ้างอิง เช่น Maven หรือ Gradle โปรดดูคำแนะนำในการรวมโดยละเอียดในเอกสาร Aspose.Slides

### มีวิธีดูตัวอย่างแอนิเมชั่นในแอพพลิเคชัน PowerPoint หรือไม่

ใช่ หลังจากบันทึกการนำเสนอแล้ว คุณสามารถเปิดในแอปพลิเคชัน PowerPoint เพื่อดูตัวอย่างแอนิเมชันและปรับแต่งเพิ่มเติมหากจำเป็น PowerPoint มีโหมดดูตัวอย่างสำหรับจุดประสงค์นี้

### มีตัวเลือกแอนิเมชันขั้นสูงเพิ่มเติมใน Aspose.Slides สำหรับ Java หรือไม่

ใช่ Aspose.Slides สำหรับ Java นำเสนอตัวเลือกแอนิเมชันขั้นสูงมากมาย รวมถึงเส้นทางการเคลื่อนไหว การกำหนดเวลา และแอนิเมชันแบบโต้ตอบ คุณสามารถสำรวจเอกสารประกอบและตัวอย่างที่ Aspose.Slides จัดเตรียมไว้เพื่อนำแอนิเมชันขั้นสูงไปใช้กับงานนำเสนอของคุณได้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}