---
"description": "เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยแอนิเมชั่นแบบซีรีส์ใน Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราพร้อมตัวอย่างโค้ดต้นฉบับเพื่อสร้างแอนิเมชั่น PowerPoint ที่น่าสนใจ"
"linktitle": "การสร้างแอนิเมชั่นซีรีย์ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การสร้างแอนิเมชั่นซีรีย์ใน Java Slides"
"url": "/th/java/animation-and-layout/animating-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างแอนิเมชั่นซีรีย์ใน Java Slides


## บทนำสู่การสร้างแอนิเมชันซีรีส์ใน Aspose.Slides สำหรับ Java

ในคู่มือนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแอนิเมชั่นซีรีส์ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API ไลบรารีนี้ช่วยให้คุณทำงานกับการนำเสนอ PowerPoint ได้ด้วยโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Aspose.Slides สำหรับไลบรารี Java
- การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีอยู่ซึ่งประกอบด้วยแผนภูมิ แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์การนำเสนอ 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงแผนภูมิ

ต่อไปเราจะเข้าถึงแผนภูมิภายในงานนำเสนอ ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่ในสไลด์แรกและเป็นรูปร่างแรกในสไลด์นั้น

```java
// รับการอ้างอิงไปยังวัตถุแผนภูมิ
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## ขั้นตอนที่ 3: เพิ่มแอนิเมชั่น

ตอนนี้เรามาเพิ่มแอนิเมชั่นให้กับซีรีส์ภายในแผนภูมิกัน เราจะใช้เอฟเฟกต์เฟดอินและทำให้ซีรีส์แต่ละชุดปรากฏขึ้นทีละชุด

```java
// สร้างภาพเคลื่อนไหวให้กับแผนภูมิทั้งหมด
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// เพิ่มแอนิเมชั่นให้กับแต่ละซีรีส์ (โดยสมมติว่ามี 4 ซีรีส์)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

ในโค้ดด้านบน เราใช้เอฟเฟ็กต์เฟดอินสำหรับแผนภูมิทั้งหมด จากนั้นใช้ลูปเพื่อเพิ่มเอฟเฟ็กต์ "ปรากฏ" ให้กับแต่ละชุดทีละชุด

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอที่แก้ไขแล้วลงในดิสก์

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการสร้างแอนิเมชันซีรีส์ใน Aspose.Slides สำหรับ Java

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์การนำเสนอ 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// รับการอ้างอิงของวัตถุแผนภูมิ
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// สร้างแอนิเมชั่นซีรีย์
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

คุณสร้างแอนิเมชั่นซีรีส์ในแผนภูมิ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java วิธีนี้จะทำให้การนำเสนอของคุณน่าสนใจและน่ามองมากขึ้น สำรวจตัวเลือกแอนิเมชั่นเพิ่มเติมและปรับแต่งการนำเสนอของคุณตามต้องการ

## คำถามที่พบบ่อย

### ฉันจะควบคุมลำดับการแอนิเมชั่นซีรีย์ได้อย่างไร

เพื่อควบคุมลำดับของแอนิเมชั่นซีรีส์ ให้ใช้ `EffectTriggerType.AfterPrevious` พารามิเตอร์เมื่อเพิ่มเอฟเฟกต์ ซึ่งจะทำให้แอนิเมชั่นซีรีส์แต่ละเรื่องเริ่มหลังจากซีรีส์ก่อนหน้าจบลง

### ฉันสามารถใช้แอนิเมชั่นที่แตกต่างกันกับแต่ละซีรีย์ได้หรือไม่

ใช่ คุณสามารถใช้แอนิเมชั่นที่แตกต่างกันกับแต่ละซีรีส์ได้โดยระบุ `EffectType` และ `EffectSubtype` ค่าเมื่อทำการใส่เอฟเฟ็กต์

### จะเกิดอะไรขึ้นหากการนำเสนอของฉันมีมากกว่า 4 ชุด?

คุณสามารถขยายลูปในขั้นตอนที่ 3 เพื่อเพิ่มแอนิเมชั่นสำหรับชุดข้อมูลทั้งหมดในแผนภูมิของคุณได้ เพียงปรับเงื่อนไขของลูปให้เหมาะสม

### ฉันจะกำหนดระยะเวลาและความล่าช้าของแอนิเมชั่นได้อย่างไร

คุณสามารถปรับแต่งระยะเวลาและความล่าช้าของแอนิเมชันได้โดยตั้งค่าคุณสมบัติของเอฟเฟกต์แอนิเมชัน ตรวจสอบเอกสาร Aspose.Slides สำหรับ Java เพื่อดูรายละเอียดเกี่ยวกับตัวเลือกการปรับแต่งที่มีให้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}