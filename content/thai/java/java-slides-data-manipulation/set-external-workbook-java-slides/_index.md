---
title: ตั้งค่าสมุดงานภายนอกใน Java Slides
linktitle: ตั้งค่าสมุดงานภายนอกใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าสมุดงานภายนอกใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java สร้างงานนำเสนอแบบไดนามิกด้วยการผสานรวมข้อมูล Excel
type: docs
weight: 19
url: /th/java/data-manipulation/set-external-workbook-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าสมุดงานภายนอกใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีตั้งค่าสมุดงานภายนอกใน Java Slides โดยใช้ Aspose.Slides คุณจะได้เรียนรู้วิธีสร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิที่อ้างอิงข้อมูลจากสมุดงาน Excel ภายนอก ในตอนท้ายของคู่มือนี้ คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการรวมข้อมูลภายนอกเข้ากับงานนำเสนอ Java Slides ของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกการนำไปใช้งาน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- เพิ่ม Aspose.Slides สำหรับไลบรารี Java ในโครงการของคุณ
- เวิร์กบุ๊ก Excel ที่มีข้อมูลที่คุณต้องการอ้างอิงในงานนำเสนอของคุณ

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

เราเริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

ต่อไป เราจะแทรกแผนภูมิวงกลมลงในงานนำเสนอ คุณสามารถปรับแต่งประเภทแผนภูมิและตำแหน่งได้ตามต้องการ

## ขั้นตอนที่ 3: เข้าถึงสมุดงานภายนอก

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 ในการเข้าถึงสมุดงานภายนอก เราใช้`setExternalWorkbook` และระบุเส้นทางไปยังสมุดงาน Excel ที่มีข้อมูล

## ขั้นตอนที่ 4: ผูกข้อมูลแผนภูมิ

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

เราผูกแผนภูมิกับข้อมูลจากสมุดงานภายนอกโดยระบุการอ้างอิงเซลล์สำหรับชุดข้อมูลและหมวดหมู่

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

สุดท้ายนี้ เราจะบันทึกงานนำเสนอโดยมีการอ้างอิงสมุดงานภายนอกเป็นไฟล์ PowerPoint

## กรอกซอร์สโค้ดสำหรับตั้งค่าสมุดงานภายนอกใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าสมุดงานภายนอกใน Java Slides โดยใช้ Aspose.Slides ตอนนี้คุณสามารถสร้างงานนำเสนอที่อ้างอิงข้อมูลจากสมุดงาน Excel แบบไดนามิก ซึ่งช่วยเพิ่มความยืดหยุ่นและการโต้ตอบของสไลด์ของคุณ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

Aspose.Slides for Java สามารถติดตั้งได้โดยการเพิ่มไลบรารีลงในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ

### ฉันสามารถใช้แผนภูมิประเภทต่างๆ กับสมุดงานภายนอกได้หรือไม่

ได้ คุณสามารถใช้แผนภูมิประเภทต่างๆ ที่ Aspose.Slides รองรับ และผูกเข้ากับข้อมูลจากสมุดงานภายนอกได้ กระบวนการอาจแตกต่างกันเล็กน้อยขึ้นอยู่กับประเภทแผนภูมิที่คุณเลือก

### จะเกิดอะไรขึ้นหากโครงสร้างข้อมูลของเวิร์กบุ๊กภายนอกของฉันเปลี่ยนแปลง

หากโครงสร้างของข้อมูลสมุดงานภายนอกของคุณเปลี่ยนแปลง คุณอาจต้องอัปเดตการอ้างอิงเซลล์ในโค้ด Java ของคุณเพื่อให้แน่ใจว่าข้อมูลแผนภูมิยังคงถูกต้อง

### Aspose.Slides เข้ากันได้กับ Java เวอร์ชันล่าสุดหรือไม่

Aspose.Slides สำหรับ Java ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าสามารถใช้งานร่วมกับ Java เวอร์ชันล่าสุดได้ อย่าลืมตรวจสอบการอัปเดตและใช้ไลบรารีเวอร์ชันล่าสุดเพื่อประสิทธิภาพและความเข้ากันได้สูงสุด

### ฉันสามารถเพิ่มแผนภูมิหลายแผนภูมิที่อ้างอิงสมุดงานภายนอกเดียวกันได้หรือไม่

ได้ คุณสามารถเพิ่มแผนภูมิได้หลายแผนภูมิในงานนำเสนอของคุณ โดยทั้งหมดอ้างอิงเวิร์กบุ๊กภายนอกเดียวกัน เพียงทำซ้ำขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้สำหรับแต่ละแผนภูมิที่คุณต้องการสร้าง