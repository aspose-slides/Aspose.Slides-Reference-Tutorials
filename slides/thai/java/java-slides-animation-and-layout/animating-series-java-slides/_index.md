---
title: การสร้างภาพเคลื่อนไหวใน Java Slides
linktitle: การสร้างภาพเคลื่อนไหวใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยชุดภาพเคลื่อนไหวใน Aspose.Slides สำหรับ Java ทำตามคำแนะนำทีละขั้นตอนพร้อมตัวอย่างซอร์สโค้ดเพื่อสร้างภาพเคลื่อนไหว PowerPoint ที่น่าสนใจ
weight: 11
url: /th/java/animation-and-layout/animating-series-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างภาพเคลื่อนไหวใน Aspose.Slides สำหรับ Java

ในคู่มือนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างภาพเคลื่อนไหวซีรีส์ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API ไลบรารีนี้ช่วยให้คุณสามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Aspose.Slides สำหรับไลบรารี Java
- ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

 ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีอยู่ซึ่งมีแผนภูมิ แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงแผนภูมิ

ต่อไปเราจะเข้าถึงแผนภูมิภายในการนำเสนอ ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่บนสไลด์แรกและเป็นรูปร่างแรกบนสไลด์นั้น

```java
// รับการอ้างอิงถึงวัตถุแผนภูมิ
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## ขั้นตอนที่ 3: เพิ่มภาพเคลื่อนไหว

ตอนนี้ มาเพิ่มภาพเคลื่อนไหวให้กับซีรีส์ภายในแผนภูมิกันดีกว่า เราจะใช้เอฟเฟ็กต์เฟดอินและทำให้แต่ละซีรีส์ปรากฏต่อกัน

```java
// ทำให้แผนภูมิทั้งหมดเคลื่อนไหว
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// เพิ่มภาพเคลื่อนไหวในแต่ละซีรีส์ (สมมติว่ามี 4 ซีรีส์)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

ในโค้ดด้านบน เราใช้เอฟเฟกต์เฟดอินสำหรับทั้งแผนภูมิ จากนั้นใช้การวนซ้ำเพื่อเพิ่มเอฟเฟกต์ "ปรากฏ" ให้กับแต่ละซีรีส์ทีละรายการ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขลงในดิสก์

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับซีรีย์แอนิเมชั่นใน Aspose.Slides สำหรับ Java

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// รับการอ้างอิงของวัตถุแผนภูมิ
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// สร้างภาพเคลื่อนไหวให้กับซีรีส์
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// เขียนงานนำเสนอที่แก้ไขแล้วลงดิสก์
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

คุณมีซีรีส์แอนิเมชั่นในแผนภูมิ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java สิ่งนี้สามารถทำให้การนำเสนอของคุณน่าดึงดูดและดึงดูดสายตามากขึ้น สำรวจตัวเลือกภาพเคลื่อนไหวเพิ่มเติมและปรับแต่งการนำเสนอของคุณตามต้องการ

## คำถามที่พบบ่อย

### ฉันจะควบคุมลำดับภาพเคลื่อนไหวของซีรีส์ได้อย่างไร

 หากต้องการควบคุมลำดับภาพเคลื่อนไหวของซีรีส์ ให้ใช้`EffectTriggerType.AfterPrevious` พารามิเตอร์เมื่อเพิ่มเอฟเฟกต์ ซึ่งจะทำให้แอนิเมชันแต่ละซีรีส์เริ่มต้นหลังจากแอนิเมชันก่อนหน้าเสร็จสิ้น

### ฉันสามารถใช้แอนิเมชั่นที่แตกต่างกันกับแต่ละซีรีส์ได้หรือไม่?

 ได้ คุณสามารถใช้ภาพเคลื่อนไหวที่แตกต่างกันกับแต่ละซีรีส์ได้โดยการระบุที่แตกต่างกัน`EffectType` และ`EffectSubtype` ค่าเมื่อเพิ่มเอฟเฟกต์

### จะเกิดอะไรขึ้นถ้างานนำเสนอของฉันมีมากกว่าสี่ชุด?

คุณสามารถขยายการวนซ้ำในขั้นตอนที่ 3 เพื่อเพิ่มภาพเคลื่อนไหวสำหรับซีรีส์ทั้งหมดในแผนภูมิของคุณ เพียงปรับสภาพลูปให้เหมาะสม

### ฉันจะปรับแต่งระยะเวลาและดีเลย์ของแอนิเมชั่นได้อย่างไร

คุณสามารถปรับแต่งระยะเวลาและความล่าช้าของภาพเคลื่อนไหวได้โดยการตั้งค่าคุณสมบัติของเอฟเฟ็กต์ภาพเคลื่อนไหว ตรวจสอบเอกสารประกอบ Aspose.Slides สำหรับ Java เพื่อดูรายละเอียดเกี่ยวกับตัวเลือกการปรับแต่งที่มีอยู่
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
