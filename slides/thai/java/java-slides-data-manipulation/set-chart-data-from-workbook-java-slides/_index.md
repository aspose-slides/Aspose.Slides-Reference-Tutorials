---
"description": "เรียนรู้วิธีตั้งค่าข้อมูลแผนภูมิจากเวิร์กบุ๊ก Excel ใน Java Slides โดยใช้ Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับการนำเสนอแบบไดนามิก"
"linktitle": "ตั้งค่าข้อมูลแผนภูมิจากเวิร์กบุ๊กใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าข้อมูลแผนภูมิจากเวิร์กบุ๊กใน Java Slides"
"url": "/th/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าข้อมูลแผนภูมิจากเวิร์กบุ๊กใน Java Slides


## บทนำสู่การตั้งค่าข้อมูลแผนภูมิจากเวิร์กบุ๊กใน Java Slides

Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถทำงานกับการนำเสนอ PowerPoint ได้ด้วยโปรแกรม โดยมีคุณสมบัติมากมายสำหรับการสร้าง จัดการ และจัดการสไลด์ PowerPoint ข้อกำหนดทั่วไปอย่างหนึ่งเมื่อทำงานกับการนำเสนอคือการตั้งค่าข้อมูลแผนภูมิแบบไดนามิกจากแหล่งข้อมูลภายนอก เช่น เวิร์กบุ๊ก Excel ในบทช่วยสอนนี้ เราจะสาธิตวิธีการทำสิ่งนี้โดยใช้ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้งานจริง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว
- เวิร์กบุ๊ก Excel ที่มีข้อมูลที่คุณต้องการใช้สำหรับแผนภูมิ

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

เราเริ่มต้นด้วยการสร้างการนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides สำหรับ Java

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

ขั้นต่อไป เราจะเพิ่มแผนภูมิลงในสไลด์ใดสไลด์หนึ่งในงานนำเสนอ ในตัวอย่างนี้ เราจะเพิ่มแผนภูมิวงกลม แต่คุณสามารถเลือกประเภทแผนภูมิที่เหมาะกับความต้องการของคุณได้

## ขั้นตอนที่ 3: ล้างข้อมูลแผนภูมิ

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

เราล้างข้อมูลที่มีอยู่ใดๆ จากแผนภูมิเพื่อเตรียมพร้อมสำหรับข้อมูลใหม่จากเวิร์กบุ๊ก Excel

## ขั้นตอนที่ 4: โหลดสมุดงาน Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

เราโหลดเวิร์กบุ๊ก Excel ที่มีข้อมูลที่เราต้องการใช้สำหรับแผนภูมิ แทนที่ `"book1.xlsx"` พร้อมเส้นทางไปยังไฟล์ Excel ของคุณ

## ขั้นตอนที่ 5: เขียนเวิร์กบุ๊กสตรีมไปยังข้อมูลแผนภูมิ

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

เราแปลงข้อมูลเวิร์กบุ๊ก Excel ให้เป็นสตรีมและเขียนลงในข้อมูลแผนภูมิ

## ขั้นตอนที่ 6: ตั้งค่าช่วงข้อมูลแผนภูมิ

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

เราระบุช่วงของเซลล์จากเวิร์กบุ๊ก Excel ที่ควรใช้เป็นข้อมูลสำหรับแผนภูมิ ปรับช่วงตามต้องการสำหรับข้อมูลของคุณ

## ขั้นตอนที่ 7: ปรับแต่งชุดแผนภูมิ

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของชุดแผนภูมิเพื่อให้ตรงตามความต้องการของคุณได้ ในตัวอย่างนี้ เราเปิดใช้งานสีต่างๆ ให้กับชุดแผนภูมิ

## ขั้นตอนที่ 8: บันทึกการนำเสนอ

```java
pres.save(outPath, SaveFormat.Pptx);
```

สุดท้าย เราบันทึกการนำเสนอพร้อมข้อมูลแผนภูมิที่อัปเดตไปยังเส้นทางเอาต์พุตที่ระบุ

## โค้ดต้นฉบับสมบูรณ์สำหรับชุดข้อมูลแผนภูมิจากเวิร์กบุ๊กใน Java Slides

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าข้อมูลแผนภูมิจากเวิร์กบุ๊ก Excel ใน Java Slides โดยใช้ไลบรารี Aspose.Slides สำหรับ Java โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและใช้ตัวอย่างโค้ดต้นฉบับที่ให้มา คุณสามารถผสานข้อมูลแผนภูมิแบบไดนามิกเข้ากับงานนำเสนอ PowerPoint ของคุณได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแผนภูมิในงานนำเสนอของฉันได้อย่างไร

คุณสามารถปรับแต่งลักษณะของแผนภูมิได้โดยการแก้ไขคุณสมบัติต่างๆ เช่น สี แบบอักษร ป้ายกำกับ และอื่นๆ โปรดดูข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกการปรับแต่งแผนภูมิในเอกสาร Aspose.Slides for Java

### ฉันสามารถใช้ข้อมูลจากไฟล์ Excel อื่นสำหรับแผนภูมิได้หรือไม่

ใช่ คุณสามารถใช้ข้อมูลจากไฟล์ Excel ใดๆ ได้โดยระบุเส้นทางไฟล์ที่ถูกต้องเมื่อโหลดเวิร์กบุ๊กในโค้ด

### ฉันสามารถสร้างแผนภูมิประเภทอื่นๆ อะไรได้บ้างโดยใช้ Aspose.Slides สำหรับ Java

Aspose.Slides สำหรับ Java รองรับแผนภูมิประเภทต่างๆ รวมถึงแผนภูมิแท่ง แผนภูมิเส้น แผนภูมิกระจาย และอื่นๆ คุณสามารถเลือกประเภทแผนภูมิที่เหมาะกับความต้องการแสดงข้อมูลของคุณได้มากที่สุด

### สามารถอัปเดตข้อมูลแผนภูมิแบบไดนามิกในการนำเสนอที่กำลังทำงานได้หรือไม่

ใช่ คุณสามารถอัปเดตข้อมูลแผนภูมิแบบไดนามิกในงานนำเสนอได้โดยการแก้ไขเวิร์กบุ๊กพื้นฐานแล้วรีเฟรชข้อมูลแผนภูมิ

### ฉันสามารถหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมเกี่ยวกับการทำงานกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถสำรวจตัวอย่างและทรัพยากรเพิ่มเติมได้ที่ [เว็บไซต์อาโพส](https://www.aspose.com/)นอกจากนี้ เอกสาร Aspose.Slides สำหรับ Java ยังให้คำแนะนำที่ครอบคลุมเกี่ยวกับการทำงานกับไลบรารีอีกด้วย

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}