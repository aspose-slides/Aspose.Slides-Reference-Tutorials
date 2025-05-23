---
"description": "เรียนรู้วิธีตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java สร้างการนำเสนอแบบไดนามิกด้วยการรวมข้อมูล Excel"
"linktitle": "ตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides"
"url": "/th/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides


## บทนำสู่การตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides โดยใช้ Aspose.Slides คุณจะได้เรียนรู้วิธีสร้างงานนำเสนอ PowerPoint ที่มีแผนภูมิที่อ้างอิงข้อมูลจากเวิร์กบุ๊ก Excel ภายนอก เมื่ออ่านคู่มือนี้จบ คุณจะเข้าใจอย่างชัดเจนว่าจะผสานข้อมูลภายนอกเข้ากับงานนำเสนอ Java Slides ของคุณได้อย่างไร

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้งานจริง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว
- เวิร์กบุ๊ก Excel ที่มีข้อมูลที่คุณต้องการอ้างอิงในการนำเสนอของคุณ

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

ขั้นต่อไป เราจะแทรกแผนภูมิวงกลมเข้าไปในงานนำเสนอ คุณสามารถปรับแต่งประเภทและตำแหน่งของแผนภูมิได้ตามต้องการ

## ขั้นตอนที่ 3: เข้าถึงสมุดงานภายนอก

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

ในการเข้าถึงสมุดงานภายนอก เราใช้ `setExternalWorkbook` วิธีการและระบุเส้นทางไปยังเวิร์กบุ๊ก Excel ซึ่งประกอบด้วยข้อมูล

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

เราผูกแผนภูมิกับข้อมูลจากเวิร์กบุ๊กภายนอกโดยระบุการอ้างอิงเซลล์สำหรับชุดและหมวดหมู่

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

สุดท้าย เราบันทึกการนำเสนอด้วยการอ้างอิงเวิร์กบุ๊กภายนอกเป็นไฟล์ PowerPoint

## โค้ดต้นฉบับสมบูรณ์สำหรับการตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides

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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการตั้งค่าเวิร์กบุ๊กภายนอกใน Java Slides โดยใช้ Aspose.Slides ตอนนี้คุณสามารถสร้างการนำเสนอที่อ้างอิงข้อมูลจากเวิร์กบุ๊ก Excel แบบไดนามิกได้ ซึ่งช่วยเพิ่มความยืดหยุ่นและการโต้ตอบของสไลด์ของคุณ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร?

สามารถติดตั้ง Aspose.Slides สำหรับ Java ได้โดยเพิ่มไลบรารีลงในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose และทำตามคำแนะนำในการติดตั้งที่ระบุไว้ในเอกสารประกอบ

### ฉันสามารถใช้แผนภูมิประเภทต่างๆ กับเวิร์กบุ๊กภายนอกได้หรือไม่

ใช่ คุณสามารถใช้แผนภูมิประเภทต่างๆ ที่รองรับโดย Aspose.Slides และเชื่อมโยงกับข้อมูลจากเวิร์กบุ๊กภายนอกได้ กระบวนการอาจแตกต่างกันเล็กน้อย ขึ้นอยู่กับประเภทแผนภูมิที่คุณเลือก

### จะเกิดอะไรขึ้นถ้าโครงสร้างข้อมูลของเวิร์กบุ๊กภายนอกของฉันมีการเปลี่ยนแปลง?

หากโครงสร้างข้อมูลของเวิร์กบุ๊กภายนอกของคุณมีการเปลี่ยนแปลง คุณอาจจำเป็นต้องอัปเดตการอ้างอิงเซลล์ในโค้ด Java เพื่อให้แน่ใจว่าข้อมูลแผนภูมิยังคงถูกต้อง

### Aspose.Slides เข้ากันได้กับ Java เวอร์ชันล่าสุดได้หรือไม่

Aspose.Slides สำหรับ Java ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าเข้ากันได้กับ Java เวอร์ชันล่าสุด โปรดตรวจสอบการอัปเดตและใช้ไลบรารีเวอร์ชันล่าสุดเพื่อประสิทธิภาพและความเข้ากันได้ที่เหมาะสมที่สุด

### ฉันสามารถเพิ่มแผนภูมิหลายรายการโดยอ้างอิงถึงสมุดงานภายนอกเดียวกันได้หรือไม่

ใช่ คุณสามารถเพิ่มแผนภูมิหลายรายการลงในงานนำเสนอของคุณ โดยทั้งหมดอ้างอิงถึงเวิร์กบุ๊กภายนอกเดียวกัน เพียงทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ซ้ำสำหรับแผนภูมิแต่ละรายการที่คุณต้องการสร้าง

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}