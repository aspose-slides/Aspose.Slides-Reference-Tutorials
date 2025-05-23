---
"description": "เพิ่มประสิทธิภาพการนำเสนอ Java ของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีสร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่ในสไลด์ PowerPoint ทีละขั้นตอน"
"linktitle": "การสร้างแอนิเมชั่นให้กับองค์ประกอบหมวดหมู่ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การสร้างแอนิเมชั่นให้กับองค์ประกอบหมวดหมู่ใน Java Slides"
"url": "/th/java/animation-and-layout/animating-categories-elements-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างแอนิเมชั่นให้กับองค์ประกอบหมวดหมู่ใน Java Slides


## การแนะนำการสร้างแอนิเมชันองค์ประกอบหมวดหมู่ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการสร้างแอนิเมชันองค์ประกอบหมวดหมู่ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะให้โค้ดต้นฉบับและคำอธิบายแก่คุณเพื่อช่วยให้คุณสร้างเอฟเฟกต์แอนิเมชันนี้ได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Slides สำหรับ Java API แล้ว
- การนำเสนอ PowerPoint ที่มีอยู่ซึ่งประกอบด้วยแผนภูมิ คุณจะทำให้องค์ประกอบหมวดหมู่ของแผนภูมิเคลื่อนไหวได้

## ขั้นตอนที่ 1: นำเข้าไลบรารี Aspose.Slides

ในการเริ่มต้น ให้โหลดไลบรารี Aspose.Slides เข้าสู่โปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดและเพิ่มไลบรารีลงใน classpath ของโปรเจ็กต์ของคุณได้ ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าการอ้างอิงที่จำเป็นแล้ว

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

ในโค้ดนี้ เราโหลดการนำเสนอ PowerPoint ที่มีอยู่ซึ่งประกอบด้วยแผนภูมิที่คุณต้องการสร้างภาพเคลื่อนไหว แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: รับการอ้างอิงถึงวัตถุแผนภูมิ

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

เราได้รับการอ้างอิงถึงวัตถุแผนภูมิในสไลด์แรกของการนำเสนอ ปรับดัชนีสไลด์ (`get_Item(0)`) และดัชนีรูปร่าง (`get_Item(0)`) ตามความจำเป็นเพื่อเข้าถึงแผนภูมิเฉพาะของคุณ

## ขั้นตอนที่ 4: สร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

เราสร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่ต่างๆ ภายในแผนภูมิ โค้ดนี้จะเพิ่มเอฟเฟกต์การจางลงให้กับแผนภูมิทั้งหมด จากนั้นจึงเพิ่มเอฟเฟกต์ "ปรากฏ" ให้กับแต่ละองค์ประกอบในแต่ละหมวดหมู่ ปรับประเภทเอฟเฟกต์และประเภทย่อยตามต้องการ

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

สุดท้าย ให้บันทึกการนำเสนอที่แก้ไขแล้วพร้อมแผนภูมิเคลื่อนไหวไปยังไฟล์ใหม่ แทนที่ `"AnimatingCategoriesElements_out.pptx"` พร้อมชื่อไฟล์เอาท์พุตที่คุณต้องการ


## โค้ดต้นฉบับที่สมบูรณ์สำหรับการสร้างแอนิเมชันองค์ประกอบหมวดหมู่ใน Java Slides
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
	// สร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่
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

คุณสร้างแอนิเมชั่นองค์ประกอบหมวดหมู่ในสไลด์ Java ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะให้โค้ดต้นฉบับและคำอธิบายที่จำเป็นแก่คุณเพื่อสร้างเอฟเฟกต์แอนิเมชั่นนี้ในงานนำเสนอ PowerPoint ของคุณ ทดลองใช้เอฟเฟกต์และการตั้งค่าต่างๆ เพื่อปรับแต่งแอนิเมชั่นของคุณเพิ่มเติม

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งเอฟเฟ็กต์แอนิเมชันได้อย่างไร

คุณสามารถปรับแต่งเอฟเฟกต์แอนิเมชันได้โดยการเปลี่ยนแปลง `EffectType` และ `EffectSubtype` พารามิเตอร์เมื่อเพิ่มเอฟเฟกต์ให้กับองค์ประกอบแผนภูมิ โปรดดูเอกสาร Aspose.Slides สำหรับ Java เพื่อดูรายละเอียดเพิ่มเติมเกี่ยวกับเอฟเฟกต์แอนิเมชันที่มีให้

### ฉันสามารถนำแอนิเมชั่นเหล่านี้ไปใช้กับแผนภูมิประเภทอื่นได้หรือไม่

ใช่ คุณสามารถนำแอนิเมชั่นที่คล้ายกันไปใช้กับแผนภูมิประเภทอื่น ๆ ได้โดยแก้ไขโค้ดเพื่อกำหนดเป้าหมายไปที่องค์ประกอบแผนภูมิเฉพาะที่คุณต้องการให้แอนิเมชั่น ปรับโครงสร้างและพารามิเตอร์ของลูปให้เหมาะสม

### ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้อย่างไร

สำหรับเอกสารประกอบที่ครอบคลุมและทรัพยากรเพิ่มเติม โปรดไปที่ [เอกสารอ้างอิง API ของ Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/). คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}