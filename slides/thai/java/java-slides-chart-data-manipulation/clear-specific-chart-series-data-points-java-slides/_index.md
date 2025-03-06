---
title: ล้างข้อมูลจุดข้อมูลชุดแผนภูมิเฉพาะใน Java Slides
linktitle: ล้างข้อมูลจุดข้อมูลชุดแผนภูมิเฉพาะใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีล้างจุดข้อมูลเฉพาะจากชุดแผนภูมิใน Java Slides ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการจัดการการแสดงข้อมูลอย่างมีประสิทธิภาพ
weight: 15
url: /th/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ล้างข้อมูลจุดข้อมูลชุดแผนภูมิเฉพาะใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการล้างข้อมูลจุดข้อมูลชุดแผนภูมิเฉพาะใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการล้างจุดข้อมูลเฉพาะจากชุดแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สิ่งนี้มีประโยชน์เมื่อคุณต้องการลบจุดข้อมูลบางจุดออกจากแผนภูมิเพื่ออัปเดตหรือแก้ไขการแสดงภาพข้อมูลของคุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

 ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีแผนภูมิที่คุณต้องการแก้ไข แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงแผนภูมิ

ต่อไป เราจะเข้าถึงแผนภูมิจากสไลด์ ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่บนสไลด์แรก (สไลด์ที่ดัชนี 0) คุณสามารถปรับดัชนีสไลด์ได้ตามต้องการ

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## ขั้นตอนที่ 3: ล้างจุดข้อมูลเฉพาะ

ตอนนี้ เราจะวนซ้ำจุดข้อมูลของชุดแรกของแผนภูมิ และล้างค่า X และ Y ของจุดเหล่านั้น

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

 โค้ดนี้จะวนซ้ำแต่ละจุดข้อมูลในชุดแรก (ดัชนี 0) และตั้งค่าทั้ง X และ Y เป็น`null`การล้างจุดข้อมูลอย่างมีประสิทธิภาพ

## ขั้นตอนที่ 4: ลบจุดข้อมูลที่เคลียร์

เพื่อให้แน่ใจว่าจุดข้อมูลที่ล้างจะถูกลบออกจากชุด เราจะล้างชุดข้อมูลทั้งหมด

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

รหัสนี้จะล้างจุดข้อมูลทั้งหมดจากชุดแรก

## ขั้นตอนที่ 5: บันทึกงานนำเสนอที่แก้ไข

สุดท้ายนี้ เราจะบันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ใหม่

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดให้สมบูรณ์เพื่อล้างข้อมูลจุดข้อมูลชุดแผนภูมิเฉพาะใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
try
{
	ISlide sl = pres.getSlides().get_Item(0);
	IChart chart = (IChart) sl.getShapes().get_Item(0);
	for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
	{
		dataPoint.getXValue().getAsCell().setValue(null);
		dataPoint.getYValue().getAsCell().setValue(null);
	}
	chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
	pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

 ในคู่มือนี้ คุณได้เรียนรู้วิธีล้างจุดข้อมูลเฉพาะจากชุดแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สิ่งนี้มีประโยชน์เมื่อคุณต้องการอัปเดตหรือแก้ไขข้อมูลแผนภูมิแบบไดนามิกในแอปพลิเคชัน Java ของคุณ หากคุณมีคำถามเพิ่มเติมหรือต้องการความช่วยเหลือเพิ่มเติม โปรดดูที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).

## คำถามที่พบบ่อย

### ฉันจะลบจุดข้อมูลเฉพาะออกจากชุดแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการลบจุดข้อมูลเฉพาะออกจากชุดแผนภูมิใน Aspose.Slides สำหรับ Java ให้ทำตามขั้นตอนเหล่านี้:

1. โหลดงานนำเสนอ
2. เข้าถึงแผนภูมิบนสไลด์
3. วนซ้ำจุดข้อมูลของชุดข้อมูลที่ต้องการ และล้างค่า X และ Y
4. ล้างข้อมูลทั้งชุดเพื่อลบจุดข้อมูลที่ล้างออก
5. บันทึกงานนำเสนอที่แก้ไข

### ฉันสามารถล้างจุดข้อมูลจากหลายชุดในแผนภูมิเดียวกันได้หรือไม่

ได้ คุณสามารถล้างจุดข้อมูลจากหลายชุดในแผนภูมิเดียวกันได้โดยการวนซ้ำจุดข้อมูลของแต่ละชุดและล้างทีละจุด

### มีวิธีล้างจุดข้อมูลตามเงื่อนไขหรือเกณฑ์หรือไม่?

ได้ คุณสามารถล้างจุดข้อมูลตามเงื่อนไขได้โดยการเพิ่มตรรกะตามเงื่อนไขภายในลูปที่วนซ้ำผ่านจุดข้อมูล คุณสามารถตรวจสอบค่าของจุดข้อมูลและตัดสินใจว่าจะล้างข้อมูลเหล่านั้นหรือไม่ตามเกณฑ์ของคุณ

### ฉันจะเพิ่มจุดข้อมูลใหม่ลงในชุดแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java ได้อย่างไร

 หากต้องการเพิ่มจุดข้อมูลใหม่ลงในชุดแผนภูมิ คุณสามารถใช้`addDataPoint` วิธีการของซีรีส์ เพียงสร้างจุดข้อมูลใหม่และเพิ่มลงในซีรีส์โดยใช้วิธีนี้

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ใน[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
