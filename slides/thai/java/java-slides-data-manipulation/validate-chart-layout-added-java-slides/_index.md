---
title: ตรวจสอบเค้าโครงแผนภูมิที่เพิ่มใน Java Slides
linktitle: ตรวจสอบเค้าโครงแผนภูมิที่เพิ่มใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: การตรวจสอบเค้าโครงแผนภูมิหลักใน PowerPoint ด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีจัดการแผนภูมิโดยทางโปรแกรมเพื่อการนำเสนอที่น่าทึ่ง
weight: 10
url: /th/java/data-manipulation/validate-chart-layout-added-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตรวจสอบเค้าโครงแผนภูมิที่เพิ่มใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการตรวจสอบความถูกต้องของเค้าโครงแผนภูมิใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการตรวจสอบเค้าโครงแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ไลบรารีนี้ช่วยให้คุณสามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ทำให้ง่ายต่อการจัดการและตรวจสอบองค์ประกอบต่างๆ รวมถึงแผนภูมิด้วย

## ขั้นตอนที่ 1: การเริ่มต้นการนำเสนอ

 ขั้นแรก เราต้องเริ่มต้นวัตถุการนำเสนอและโหลดงานนำเสนอ PowerPoint ที่มีอยู่ แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ (`test.pptx` ในตัวอย่างนี้)

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

 ต่อไป เราจะเพิ่มแผนภูมิลงในงานนำเสนอ ในตัวอย่างนี้ เรากำลังเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ แต่คุณสามารถเปลี่ยนได้`ChartType` ตามความจำเป็น.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## ขั้นตอนที่ 3: ตรวจสอบเค้าโครงแผนภูมิ

 ตอนนี้ เราจะตรวจสอบเค้าโครงแผนภูมิโดยใช้`validateChartLayout()` วิธี. เพื่อให้แน่ใจว่าแผนภูมิถูกจัดวางอย่างเหมาะสมภายในสไลด์

```java
chart.validateChartLayout();
```

## ขั้นตอนที่ 4: การดึงข้อมูลตำแหน่งและขนาดแผนภูมิ

หลังจากตรวจสอบเค้าโครงแผนภูมิแล้ว คุณอาจต้องการดึงข้อมูลเกี่ยวกับตำแหน่งและขนาด เราสามารถรับพิกัด X และ Y จริงได้ รวมถึงความกว้างและความสูงของพื้นที่ลงจุดของแผนภูมิ

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

 สุดท้ายนี้อย่าลืมบันทึกงานนำเสนอที่แก้ไขแล้ว ในตัวอย่างนี้ เรากำลังบันทึกเป็น`Result.pptx`แต่คุณสามารถระบุชื่อไฟล์อื่นได้หากต้องการ

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## ซอร์สโค้ดที่สมบูรณ์สำหรับตรวจสอบเค้าโครงแผนภูมิที่เพิ่มใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// กำลังบันทึกการนำเสนอ
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เจาะลึกโลกแห่งการทำงานกับแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราได้ครอบคลุมขั้นตอนสำคัญในการตรวจสอบเค้าโครงแผนภูมิ เรียกดูตำแหน่งและขนาด และบันทึกงานนำเสนอที่แก้ไข นี่เป็นบทสรุปโดยย่อ:

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 หากต้องการเปลี่ยนประเภทแผนภูมิ เพียงแทนที่`ChartType.ClusteredColumn`ด้วยประเภทกราฟที่ต้องการใน`addChart()` วิธี.

### ฉันสามารถปรับแต่งข้อมูลแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับแต่งข้อมูลแผนภูมิได้โดยการเพิ่มและแก้ไขชุดข้อมูล หมวดหมู่ และค่า โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับรายละเอียดเพิ่มเติม

### จะทำอย่างไรถ้าฉันต้องการแก้ไขคุณสมบัติแผนภูมิอื่นๆ

คุณสามารถเข้าถึงคุณสมบัติแผนภูมิต่างๆ และปรับแต่งได้ตามความต้องการของคุณ สำรวจเอกสารประกอบของ Aspose.Slides เพื่อดูข้อมูลที่ครอบคลุมเกี่ยวกับการจัดการแผนภูมิ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
