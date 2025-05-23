---
"description": "เรียนรู้วิธีการล้างจุดข้อมูลเฉพาะจากชุดแผนภูมิใน Java Slides ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการจัดการการแสดงภาพข้อมูลที่มีประสิทธิภาพ"
"linktitle": "เคลียร์ข้อมูลชุดแผนภูมิเฉพาะเจาะจงในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เคลียร์ข้อมูลชุดแผนภูมิเฉพาะเจาะจงในสไลด์ Java"
"url": "/th/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เคลียร์ข้อมูลชุดแผนภูมิเฉพาะเจาะจงในสไลด์ Java


## บทนำสู่การล้างข้อมูลชุดแผนภูมิเฉพาะจุดข้อมูลในสไลด์ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการล้างจุดข้อมูลเฉพาะจากชุดแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ซึ่งอาจมีประโยชน์เมื่อคุณต้องการลบจุดข้อมูลบางจุดออกจากแผนภูมิเพื่ออัปเดตหรือปรับเปลี่ยนการแสดงภาพข้อมูลของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีแผนภูมิที่คุณต้องการแก้ไข แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงแผนภูมิ

ต่อไปเราจะเข้าถึงแผนภูมิจากสไลด์ ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่ในสไลด์แรก (สไลด์ที่ดัชนี 0) คุณสามารถปรับดัชนีสไลด์ตามต้องการได้

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## ขั้นตอนที่ 3: ล้างจุดข้อมูลเฉพาะ

ตอนนี้เราจะทำซ้ำผ่านจุดข้อมูลของชุดข้อมูลแรกของแผนภูมิและล้างค่า X และ Y ของจุดข้อมูลเหล่านั้น

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

โค้ดนี้จะวนซ้ำผ่านจุดข้อมูลแต่ละจุดในซีรีส์แรก (ดัชนี 0) และตั้งค่าทั้ง X และ Y เป็น `null`การล้างจุดข้อมูลอย่างมีประสิทธิภาพ

## ขั้นตอนที่ 4: ลบจุดข้อมูลที่ถูกล้าง

เพื่อให้แน่ใจว่าจุดข้อมูลที่ถูกล้างจะถูกลบออกจากซีรีส์ เราจะล้างซีรีส์ทั้งหมด

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

โค้ดนี้จะล้างจุดข้อมูลทั้งหมดจากซีรีส์แรก

## ขั้นตอนที่ 5: บันทึกการนำเสนอที่แก้ไขแล้ว

สุดท้ายเราจะบันทึกงานนำเสนอที่ปรับเปลี่ยนแล้วลงในไฟล์ใหม่

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับจุดข้อมูลชุดแผนภูมิที่ชัดเจนและเฉพาะเจาะจงในสไลด์ Java

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

ในคู่มือนี้ คุณจะได้เรียนรู้วิธีการล้างจุดข้อมูลเฉพาะจากชุดแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ซึ่งอาจมีประโยชน์เมื่อคุณต้องอัปเดตหรือแก้ไขข้อมูลแผนภูมิแบบไดนามิกในแอปพลิเคชัน Java ของคุณ หากคุณมีคำถามเพิ่มเติมหรือต้องการความช่วยเหลือเพิ่มเติม โปรดดูที่ [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

## คำถามที่พบบ่อย

### ฉันจะลบจุดข้อมูลที่เจาะจงออกจากชุดแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการลบจุดข้อมูลเฉพาะออกจากชุดแผนภูมิใน Aspose.Slides สำหรับ Java ให้ทำตามขั้นตอนเหล่านี้:

1. โหลดงานนำเสนอ
2. เข้าถึงแผนภูมิบนสไลด์
3. ทำซ้ำผ่านจุดข้อมูลของซีรีส์ที่ต้องการและล้างค่า X และ Y ของพวกมัน
4. ล้างซีรีย์ทั้งหมดเพื่อลบจุดข้อมูลที่ถูกล้าง
5. บันทึกการนำเสนอที่ปรับเปลี่ยนแล้ว

### ฉันสามารถล้างจุดข้อมูลจากหลายชุดในแผนภูมิเดียวกันได้หรือไม่

ใช่ คุณสามารถล้างจุดข้อมูลจากชุดข้อมูลหลายชุดในแผนภูมิเดียวกันได้ โดยการวนซ้ำผ่านจุดข้อมูลของแต่ละชุดและล้างทีละจุด

### มีวิธีล้างจุดข้อมูลตามเงื่อนไขหรือเกณฑ์หรือไม่

ใช่ คุณสามารถล้างจุดข้อมูลตามเงื่อนไขได้โดยการเพิ่มตรรกะเงื่อนไขภายในลูปที่วนซ้ำผ่านจุดข้อมูล คุณสามารถตรวจสอบค่าของจุดข้อมูลและตัดสินใจว่าจะล้างหรือไม่โดยอิงตามเกณฑ์ของคุณ

### ฉันจะเพิ่มจุดข้อมูลใหม่ลงในชุดแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการเพิ่มจุดข้อมูลใหม่ลงในชุดแผนภูมิ คุณสามารถใช้ `addDataPoint` วิธีการของชุดข้อมูล เพียงสร้างจุดข้อมูลใหม่และเพิ่มลงในชุดข้อมูลโดยใช้วิธีนี้

### ฉันสามารถหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ใน [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}