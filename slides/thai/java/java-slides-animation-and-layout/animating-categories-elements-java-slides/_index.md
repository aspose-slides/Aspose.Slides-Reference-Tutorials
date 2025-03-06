---
title: การสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ใน Java Slides
linktitle: การสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เพิ่มประสิทธิภาพการนำเสนอ Java ของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีทำให้องค์ประกอบหมวดหมู่เคลื่อนไหวในสไลด์ PowerPoint ทีละขั้นตอน
weight: 10
url: /th/java/animation-and-layout/animating-categories-elements-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะให้ซอร์สโค้ดและคำอธิบายเพื่อช่วยให้คุณบรรลุผลแอนิเมชั่นนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Slides สำหรับ Java API แล้ว
- งานนำเสนอ PowerPoint ที่มีอยู่ซึ่งมีแผนภูมิ คุณจะเคลื่อนไหวองค์ประกอบหมวดหมู่ของแผนภูมินี้

## ขั้นตอนที่ 1: นำเข้าไลบรารี Aspose.Slides

ในการเริ่มต้น ให้นำเข้าไลบรารี Aspose.Slides ไปยังโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดและเพิ่มไลบรารีลงใน classpath ของโปรเจ็กต์ของคุณได้ ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าการขึ้นต่อกันที่จำเป็นแล้ว

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 ในโค้ดนี้ เราจะโหลดงานนำเสนอ PowerPoint ที่มีอยู่ซึ่งมีแผนภูมิที่คุณต้องการทำให้เคลื่อนไหว แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: รับการอ้างอิงไปยังวัตถุแผนภูมิ

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

เราได้รับการอ้างอิงถึงวัตถุแผนภูมิในสไลด์แรกของการนำเสนอ ปรับดัชนีสไลด์ (`get_Item(0)`) และดัชนีรูปร่าง (`get_Item(0)`) ตามความจำเป็นเพื่อเข้าถึงแผนภูมิเฉพาะของคุณ

## ขั้นตอนที่ 4: ทำให้องค์ประกอบหมวดหมู่เคลื่อนไหว

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

เราทำให้องค์ประกอบของหมวดหมู่เคลื่อนไหวภายในแผนภูมิ โค้ดนี้จะเพิ่มเอฟเฟกต์จางลงในทั้งแผนภูมิ จากนั้นเพิ่มเอฟเฟกต์ "ปรากฏ" ให้กับแต่ละองค์ประกอบภายในแต่ละหมวดหมู่ ปรับประเภทเอฟเฟกต์และประเภทย่อยตามต้องการ

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วพร้อมแผนภูมิภาพเคลื่อนไหวลงในไฟล์ใหม่ แทนที่`"AnimatingCategoriesElements_out.pptx"` ด้วยชื่อไฟล์เอาต์พุตที่คุณต้องการ


## กรอกซอร์สโค้ดสำหรับการสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ใน Java Slides
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// รับการอ้างอิงของวัตถุแผนภูมิ
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// องค์ประกอบหมวดหมู่ภาพเคลื่อนไหว
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// เขียนไฟล์การนำเสนอลงดิสก์
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

คุณสร้างภาพเคลื่อนไหวองค์ประกอบหมวดหมู่ในสไลด์ Java ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ให้ซอร์สโค้ดที่จำเป็นและคำอธิบายเพื่อให้ได้เอฟเฟกต์ภาพเคลื่อนไหวในงานนำเสนอ PowerPoint ของคุณ ทดลองใช้เอฟเฟกต์และการตั้งค่าต่างๆ เพื่อปรับแต่งแอนิเมชั่นของคุณเพิ่มเติม

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งเอฟเฟกต์ภาพเคลื่อนไหวได้อย่างไร?

 คุณสามารถปรับแต่งเอฟเฟ็กต์ภาพเคลื่อนไหวได้โดยการเปลี่ยน`EffectType` และ`EffectSubtype` พารามิเตอร์เมื่อเพิ่มเอฟเฟกต์ให้กับองค์ประกอบแผนภูมิ โปรดดูเอกสารประกอบ Aspose.Slides สำหรับ Java สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับเอฟเฟกต์ภาพเคลื่อนไหวที่มีอยู่

### ฉันสามารถใช้ภาพเคลื่อนไหวเหล่านี้กับแผนภูมิประเภทอื่นได้หรือไม่

ได้ คุณสามารถใช้ภาพเคลื่อนไหวที่คล้ายกันกับแผนภูมิประเภทอื่นๆ ได้โดยการแก้ไขโค้ดเพื่อกำหนดเป้าหมายองค์ประกอบแผนภูมิเฉพาะที่คุณต้องการทำให้เคลื่อนไหว ปรับโครงสร้างลูปและพารามิเตอร์ให้เหมาะสม

### ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้อย่างไร

 สำหรับเอกสารที่ครอบคลุมและแหล่งข้อมูลเพิ่มเติม โปรดไปที่[Aspose.Slides สำหรับการอ้างอิง Java API](https://reference.aspose.com/slides/java/) - คุณยังสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
