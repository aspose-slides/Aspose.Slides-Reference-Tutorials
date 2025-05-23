---
"description": "เรียนรู้วิธีการดึงข้อมูลขนาดพื้นที่ของแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java พัฒนาทักษะการทำงานอัตโนมัติของ PowerPoint ของคุณ"
"linktitle": "รับความกว้างและความสูงจากพื้นที่พล็อตแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รับความกว้างและความสูงจากพื้นที่พล็อตแผนภูมิใน Java Slides"
"url": "/th/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รับความกว้างและความสูงจากพื้นที่พล็อตแผนภูมิใน Java Slides


## การแนะนำ

แผนภูมิเป็นวิธีที่มีประสิทธิภาพในการแสดงข้อมูลในงานนำเสนอ PowerPoint บางครั้งคุณอาจจำเป็นต้องทราบขนาดของพื้นที่พล็อตของแผนภูมิด้วยเหตุผลต่างๆ เช่น การปรับขนาดหรือการเปลี่ยนตำแหน่งองค์ประกอบภายในแผนภูมิ คู่มือนี้จะสาธิตวิธีการรับความกว้างและความสูงของพื้นที่พล็อตโดยใช้ Java และ Aspose.Slides สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถทำได้โดยรวมไลบรารีไว้ในส่วนที่ต้องพึ่งพาของโปรเจ็กต์ของคุณหรือโดยการเพิ่มไฟล์ JAR ด้วยตนเอง

## ขั้นตอนที่ 2: การสร้างงานนำเสนอ PowerPoint

เริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint และเพิ่มสไลด์เข้าไป ซึ่งจะทำหน้าที่เป็นคอนเทนเนอร์สำหรับแผนภูมิของเรา

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

แทนที่ `"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิ

ตอนนี้เรามาเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในสไลด์กัน เราจะตรวจสอบเค้าโครงของแผนภูมิด้วย

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

โค้ดนี้จะสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ตำแหน่ง (100, 100) พร้อมมิติ (500, 350)

## ขั้นตอนที่ 4: การรับขนาดพื้นที่แปลง

ในการดึงข้อมูลความกว้างและความสูงของพื้นที่พล็อตแผนภูมิ เราสามารถใช้โค้ดดังต่อไปนี้:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

ตอนนี้ตัวแปร `x`- `y`- `w`, และ `h` ประกอบด้วยค่าพิกัด X พิกัด Y ความกว้าง และความสูงของพื้นที่พล็อตตามลำดับ

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอด้วยแผนภูมิ

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

อย่าลืมเปลี่ยน `"Chart_out.pptx"` พร้อมชื่อไฟล์เอาท์พุตที่คุณต้องการ

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการรับความกว้างและความสูงจากพื้นที่พล็อตแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// บันทึกการนำเสนอด้วยแผนภูมิ
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทความนี้ เราได้กล่าวถึงวิธีการรับความกว้างและความสูงของพื้นที่พล็อตของแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API ข้อมูลนี้อาจมีประโยชน์เมื่อคุณต้องปรับเปลี่ยนเค้าโครงของแผนภูมิในงานนำเสนอ PowerPoint แบบไดนามิก

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิเป็นอย่างอื่นที่นอกเหนือจากคอลัมน์แบบคลัสเตอร์ได้อย่างไร

คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแทนที่ `ChartType.ClusteredColumn` โดยมีการระบุชนิดแผนภูมิตามต้องการ เช่น `ChartType.Line` หรือ `ChartType-Pie`.

### ฉันสามารถปรับเปลี่ยนคุณสมบัติอื่น ๆ ของแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับเปลี่ยนคุณสมบัติต่างๆ ของแผนภูมิได้ เช่น ข้อมูล ป้ายกำกับ และการจัดรูปแบบ โดยใช้ Aspose.Slides for Java API โปรดดูรายละเอียดเพิ่มเติมในเอกสารประกอบ

### Aspose.Slides สำหรับ Java เหมาะกับการใช้งาน PowerPoint แบบอัตโนมัติระดับมืออาชีพหรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังสำหรับการทำงานอัตโนมัติของ PowerPoint ในแอปพลิเคชัน Java โดยมีคุณสมบัติที่ครอบคลุมสำหรับการทำงานกับงานนำเสนอ สไลด์ รูปร่าง แผนภูมิ และอื่นๆ อีกมากมาย

### ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้อย่างไร

คุณสามารถค้นหาเอกสารประกอบและตัวอย่างเพิ่มเติมได้ที่หน้าเอกสารประกอบ Aspose.Slides สำหรับ Java [ที่นี่](https://reference-aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}