---
title: กลับค่าถ้าเป็นลบสำหรับแต่ละซีรี่ส์ใน Java Slides
linktitle: กลับค่าถ้าเป็นลบสำหรับแต่ละซีรี่ส์ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีใช้ฟีเจอร์ Invert If Negative ใน Aspose.Slides สำหรับ Java เพื่อปรับปรุงภาพแผนภูมิในงานนำเสนอ PowerPoint
weight: 11
url: /th/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กลับค่าถ้าเป็นลบสำหรับแต่ละซีรี่ส์ใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการกลับด้านถ้าเป็นลบสำหรับแต่ละซีรี่ส์ใน Java Slides

Aspose.Slides for Java มีเครื่องมืออันทรงพลังในการทำงานกับการนำเสนอ และฟีเจอร์ที่น่าสนใจอย่างหนึ่งก็คือความสามารถในการควบคุมวิธีแสดงชุดข้อมูลบนแผนภูมิ ในบทความนี้ เราจะสำรวจวิธีใช้ฟีเจอร์ "Invert If Negative" สำหรับแต่ละซีรี่ส์ใน Java Slides คุณลักษณะนี้ช่วยให้คุณสามารถแยกแยะจุดข้อมูลเชิงลบในแผนภูมิได้อย่างชัดเจน ทำให้การนำเสนอของคุณมีข้อมูลและน่าสนใจมากขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## การตั้งค่าโครงการของคุณ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ Java ใหม่ใน Integrated Development Environment (IDE) ที่คุณต้องการ เมื่อตั้งค่าโปรเจ็กต์ของคุณแล้ว ให้ทำตามขั้นตอนเหล่านี้เพื่อใช้ฟีเจอร์ "Invert If Negative" สำหรับแต่ละซีรีส์ใน Java Slides

## ขั้นตอนที่ 1: รวมไลบรารี Aspose.Slides

ขั้นแรก คุณต้องรวมไลบรารี Aspose.Slides ไว้ในโปรเจ็กต์ของคุณ คุณสามารถทำได้โดยการเพิ่มไฟล์ JAR ไลบรารีลงใน classpath ของโปรเจ็กต์ของคุณ ขั้นตอนนี้ช่วยให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและวิธีการที่จำเป็นทั้งหมดในการทำงานกับงานนำเสนอ PowerPoint

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: สร้างงานนำเสนอ

 ตอนนี้เรามาสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides คุณสามารถกำหนดไดเร็กทอรีที่คุณต้องการบันทึกงานนำเสนอโดยใช้`dataDir` ตัวแปร.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มแผนภูมิ

ในขั้นตอนนี้ เราจะเพิ่มแผนภูมิลงในงานนำเสนอ เราจะใช้แผนภูมิคอลัมน์แบบกลุ่มเป็นตัวอย่าง คุณสามารถเลือกประเภทแผนภูมิที่แตกต่างกันได้ตามความต้องการของคุณ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## ขั้นตอนที่ 4: กำหนดค่าชุดข้อมูลแผนภูมิ

ต่อไป เราจะกำหนดค่าชุดข้อมูลของแผนภูมิ เพื่อสาธิตคุณลักษณะ "Invert If Negative" เราจะสร้างชุดข้อมูลตัวอย่างที่มีทั้งค่าบวกและค่าลบ

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// การเพิ่มจุดข้อมูลให้กับซีรีส์
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## ขั้นตอนที่ 5: ใช้ "Invert If Negative"

ตอนนี้ เราจะใช้ฟีเจอร์ "Invert If Negative" กับจุดข้อมูลจุดใดจุดหนึ่ง การดำเนินการนี้จะแปลงสีของจุดข้อมูลเฉพาะนั้นเมื่อเป็นค่าลบ

```java
series.get_Item(0).setInvertIfNegative(false); // อย่ากลับด้านโดยค่าเริ่มต้น
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // สลับสีของจุดข้อมูลที่สาม
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอลงในไดเร็กทอรีที่คุณระบุ

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับการกลับด้านหากเป็นค่าลบสำหรับแต่ละซีรี่ส์ใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ฟีเจอร์ "Invert If Negative" สำหรับแต่ละซีรี่ส์ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณลักษณะนี้ช่วยให้คุณสามารถเน้นจุดข้อมูลเชิงลบในแผนภูมิของคุณ ทำให้การนำเสนอของคุณดูน่าดึงดูดและให้ข้อมูลมากขึ้น

## คำถามที่พบบ่อย

### จุดประสงค์ของฟีเจอร์ "Invert If Negative" ใน Aspose.Slides สำหรับ Java คืออะไร

คุณลักษณะ "Invert If Negative" ใน Aspose.Slides สำหรับ Java ช่วยให้คุณสามารถแยกแยะจุดข้อมูลเชิงลบในแผนภูมิได้อย่างชัดเจน ช่วยให้การนำเสนอของคุณมีข้อมูลและมีส่วนร่วมมากขึ้นโดยการเน้นจุดข้อมูลเฉพาะ

### ฉันจะรวมไลบรารี Aspose.Slides ในโปรเจ็กต์ Java ของฉันได้อย่างไร

หากต้องการรวมไลบรารี Aspose.Slides ในโปรเจ็กต์ Java ของคุณ คุณต้องเพิ่มไฟล์ JAR ไลบรารีลงใน classpath ของโปรเจ็กต์ของคุณ ซึ่งช่วยให้คุณเข้าถึงคลาสและวิธีการที่จำเป็นทั้งหมดในการทำงานกับงานนำเสนอ PowerPoint

### ฉันสามารถใช้แผนภูมิประเภทต่างๆ กับฟีเจอร์ "กลับด้านหากเป็นค่าลบ" ได้หรือไม่

ได้ คุณสามารถใช้แผนภูมิประเภทต่างๆ ได้โดยใช้คุณลักษณะ "กลับด้านหากเป็นค่าลบ" ในบทช่วยสอนนี้ เราใช้แผนภูมิคอลัมน์แบบกลุ่มเป็นตัวอย่าง แต่คุณสามารถใช้คุณลักษณะนี้กับแผนภูมิประเภทต่างๆ ได้ตามความต้องการของคุณ

### เป็นไปได้ไหมที่จะปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลกลับหัว?

ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลกลับหัวได้ Aspose.Slides for Java มีตัวเลือกในการควบคุมสีและรูปแบบของจุดข้อมูลเมื่อมีการกลับด้านเนื่องจากการตั้งค่า "กลับด้านหากเป็นค่าลบ"

### ฉันจะเข้าถึงเอกสาร Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถเข้าถึงเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่[ที่นี่](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
