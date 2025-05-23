---
"description": "เรียนรู้วิธีใช้คุณลักษณะ Invert If Negative ใน Aspose.Slides สำหรับ Java เพื่อปรับปรุงภาพแผนภูมิในงานนำเสนอ PowerPoint"
"linktitle": "การกลับด้านถ้าเป็นค่าลบสำหรับแต่ละซีรีส์ในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การกลับด้านถ้าเป็นค่าลบสำหรับแต่ละซีรีส์ในสไลด์ Java"
"url": "/th/java/data-manipulation/invert-if-negative-individual-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การกลับด้านถ้าเป็นค่าลบสำหรับแต่ละซีรีส์ในสไลด์ Java


## บทนำสู่การกลับด้านถ้าเป็นค่าลบสำหรับซีรีส์แต่ละซีรีส์ในสไลด์ Java

Aspose.Slides สำหรับ Java มอบเครื่องมืออันทรงพลังสำหรับทำงานกับงานนำเสนอ และฟีเจอร์ที่น่าสนใจอย่างหนึ่งก็คือความสามารถในการควบคุมวิธีการแสดงชุดข้อมูลบนแผนภูมิ ในบทความนี้ เราจะมาสำรวจวิธีการใช้ฟีเจอร์ "Invert If Negative" สำหรับชุดข้อมูลแต่ละชุดใน Java Slides ฟีเจอร์นี้ช่วยให้คุณแยกแยะจุดข้อมูลเชิงลบในแผนภูมิได้อย่างชัดเจน ทำให้การนำเสนอของคุณมีข้อมูลและน่าสนใจมากขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## การตั้งค่าโครงการของคุณ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ Java ใหม่ใน Integrated Development Environment (IDE) ที่คุณต้องการ เมื่อตั้งค่าโปรเจ็กต์แล้ว ให้ทำตามขั้นตอนเหล่านี้เพื่อนำคุณลักษณะ "Invert If Negative" ไปใช้กับซีรีส์แต่ละรายการใน Java Slides

## ขั้นตอนที่ 1: รวมไลบรารี Aspose.Slides

ขั้นแรก คุณต้องรวมไลบรารี Aspose.Slides ไว้ในโปรเจ็กต์ของคุณ คุณสามารถทำได้โดยเพิ่มไฟล์ JAR ของไลบรารีลงในคลาสพาธของโปรเจ็กต์ของคุณ ขั้นตอนนี้จะช่วยให้คุณสามารถเข้าถึงคลาสและวิธีการที่จำเป็นทั้งหมดสำหรับการทำงานกับการนำเสนอ PowerPoint ได้

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: สร้างงานนำเสนอ

ตอนนี้เรามาสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides กัน คุณสามารถกำหนดไดเรกทอรีที่คุณต้องการบันทึกงานนำเสนอได้โดยใช้ `dataDir` ตัวแปร.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มแผนภูมิ

ในขั้นตอนนี้ เราจะเพิ่มแผนภูมิลงในงานนำเสนอ โดยจะใช้แผนภูมิคอลัมน์แบบคลัสเตอร์เป็นตัวอย่าง คุณสามารถเลือกประเภทแผนภูมิต่างๆ ได้ตามความต้องการ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## ขั้นตอนที่ 4: กำหนดค่าชุดข้อมูลแผนภูมิ

ต่อไปเราจะกำหนดค่าชุดข้อมูลของแผนภูมิ เพื่อสาธิตคุณลักษณะ "ย้อนกลับหากเป็นค่าลบ" เราจะสร้างชุดข้อมูลตัวอย่างที่มีค่าทั้งบวกและลบ

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// การเพิ่มจุดข้อมูลลงในชุดข้อมูล
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## ขั้นตอนที่ 5: ใช้ "การกลับด้านถ้าเป็นค่าลบ"

ตอนนี้ เราจะใช้ฟีเจอร์ "ย้อนกลับถ้าเป็นค่าลบ" กับจุดข้อมูลจุดหนึ่ง ฟีเจอร์นี้จะย้อนกลับสีของจุดข้อมูลนั้นเมื่อเป็นค่าลบ

```java
series.get_Item(0).setInvertIfNegative(false); // อย่ากลับด้านโดยค่าเริ่มต้น
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // ย้อนกลับสีสำหรับจุดข้อมูลที่สาม
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอไปยังไดเร็กทอรีที่คุณระบุ

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการกลับด้านถ้าเป็นค่าลบสำหรับซีรีส์แต่ละรายการใน Java Slides

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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ฟีเจอร์ "Invert If Negative" สำหรับซีรีส์แต่ละซีรีส์ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ฟีเจอร์นี้ช่วยให้คุณเน้นจุดข้อมูลเชิงลบในแผนภูมิของคุณ ทำให้การนำเสนอของคุณน่าสนใจและให้ข้อมูลมากขึ้น

## คำถามที่พบบ่อย

### จุดประสงค์ของฟีเจอร์ "Invert If Negative" ใน Aspose.Slides สำหรับ Java คืออะไร

ฟีเจอร์ "Invert If Negative" ใน Aspose.Slides สำหรับ Java ช่วยให้คุณสามารถแยกแยะจุดข้อมูลเชิงลบในแผนภูมิได้อย่างชัดเจน ช่วยให้การนำเสนอของคุณให้ข้อมูลและน่าสนใจมากขึ้นโดยเน้นที่จุดข้อมูลเฉพาะ

### ฉันจะรวมไลบรารี Aspose.Slides ไว้ในโปรเจ็กต์ Java ของฉันได้อย่างไร

หากต้องการรวมไลบรารี Aspose.Slides ไว้ในโปรเจ็กต์ Java ของคุณ คุณจะต้องเพิ่มไฟล์ JAR ของไลบรารีลงใน classpath ของโปรเจ็กต์ของคุณ ซึ่งจะทำให้คุณสามารถเข้าถึงคลาสและวิธีการที่จำเป็นทั้งหมดสำหรับการทำงานกับการนำเสนอ PowerPoint ได้

### ฉันสามารถใช้แผนภูมิประเภทต่างๆ กับฟีเจอร์ "ย้อนกลับถ้าเป็นค่าลบ" ได้หรือไม่

ใช่ คุณสามารถใช้แผนภูมิประเภทต่างๆ ได้โดยใช้ฟีเจอร์ "กลับด้านหากค่าเป็นลบ" ในบทช่วยสอนนี้ เราใช้แผนภูมิคอลัมน์แบบคลัสเตอร์เป็นตัวอย่าง แต่คุณสามารถใช้ฟีเจอร์นี้กับแผนภูมิประเภทต่างๆ ได้ตามความต้องการของคุณ

### สามารถปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลที่กลับด้านได้หรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะของจุดข้อมูลที่กลับด้านได้ Aspose.Slides สำหรับ Java มีตัวเลือกในการควบคุมสีและรูปแบบของจุดข้อมูลเมื่อกลับด้านเนื่องจากการตั้งค่า "กลับด้านหากเป็นค่าลบ"

### ฉันสามารถเข้าถึงเอกสาร Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถเข้าถึงเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ [ที่นี่](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}