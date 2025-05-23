---
"description": "แผนภูมิหลักที่ทับซ้อนกันใน Java Slides ด้วย Aspose.Slides สำหรับ Java เรียนรู้ทีละขั้นตอนเกี่ยวกับการปรับแต่งภาพแผนภูมิเพื่อการนำเสนอที่น่าทึ่ง"
"linktitle": "ตั้งค่าการทับซ้อนของชุดแผนภูมิในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าการทับซ้อนของชุดแผนภูมิในสไลด์ Java"
"url": "/th/java/data-manipulation/set-chart-series-overlap-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าการทับซ้อนของชุดแผนภูมิในสไลด์ Java


## การแนะนำการทับซ้อนของชุดแผนภูมิในสไลด์ Java

ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกเข้าไปในโลกที่น่าสนใจของการจัดการการทับซ้อนของชุดแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API อันทรงพลัง ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนแบบทีละขั้นตอนนี้จะช่วยให้คุณมีความรู้และซอร์สโค้ดที่จำเป็นในการเชี่ยวชาญงานสำคัญนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java
- Aspose.Slides สำหรับไลบรารี Java
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณเลือก

ตอนนี้เรามีเครื่องมือพร้อมแล้ว มาดำเนินการตั้งค่าการทับซ้อนของชุดแผนภูมิกัน

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก เราต้องสร้างงานนำเสนอที่เราจะเพิ่มแผนภูมิ คุณสามารถกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณได้ดังนี้:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

เราจะเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในการนำเสนอของเราโดยใช้โค้ดต่อไปนี้:

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## ขั้นตอนที่ 3: การปรับการทับซ้อนของซีรีส์

ในการตั้งค่าการทับซ้อนของซีรีส์ เราจะตรวจสอบว่าปัจจุบันตั้งค่าเป็นศูนย์หรือไม่ จากนั้นจึงปรับแต่งตามต้องการ:

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
if (series.get_Item(0).getOverlap() == 0)
{
    // การตั้งค่าซีรีย์ทับซ้อน
    series.get_Item(0).getParentSeriesGroup().setOverlap((byte) -30);
}
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

ในที่สุดเราจะบันทึกการนำเสนอที่แก้ไขของเราไปยังไดเร็กทอรีที่ระบุ:

```java
presentation.save(dataDir + "SetChartSeriesOverlap_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการทับซ้อนของชุดแผนภูมิในสไลด์ Java

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// การเพิ่มแผนภูมิ
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	if (series.get_Item(0).getOverlap() == 0)
	{
		// การตั้งค่าซีรีย์ทับซ้อน
		series.get_Item(0).getParentSeriesGroup().setOverlap((byte) -30);
	}
	// เขียนไฟล์การนำเสนอลงดิสก์
	presentation.save(dataDir + "SetChartSeriesOverlap_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีตั้งค่าการทับซ้อนของชุดแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ทักษะนี้ถือเป็นทักษะที่มีค่าเมื่อทำงานกับการนำเสนอ เนื่องจากช่วยให้คุณปรับแต่งแผนภูมิให้ตรงตามข้อกำหนดเฉพาะได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการเปลี่ยนประเภทแผนภูมิ คุณสามารถใช้ `ChartType` การนับเมื่อเพิ่มแผนภูมิ เพียงแทนที่ `ChartType.ClusteredColumn` ด้วยประเภทแผนภูมิที่ต้องการ เช่น `ChartType.Line` หรือ `ChartType-Pie`.

### มีตัวเลือกการปรับแต่งแผนภูมิอื่น ๆ อะไรอีกบ้าง

Aspose.Slides สำหรับ Java มีตัวเลือกการปรับแต่งแผนภูมิมากมาย คุณสามารถปรับแต่งชื่อแผนภูมิ ป้ายข้อมูล สี และอื่นๆ ได้ โปรดดูข้อมูลโดยละเอียดในเอกสารประกอบ

### Aspose.Slides สำหรับ Java เหมาะกับการนำเสนออย่างมืออาชีพหรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้างและจัดการงานนำเสนอ ไลบรารีนี้ใช้กันอย่างแพร่หลายในงานระดับมืออาชีพเพื่อสร้างสไลด์โชว์คุณภาพสูงพร้อมฟีเจอร์ขั้นสูง

### ฉันสามารถสร้างการนำเสนอแบบอัตโนมัติโดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่

แน่นอน! Aspose.Slides สำหรับ Java มี API สำหรับการสร้างงานนำเสนอตั้งแต่ต้นหรือแก้ไขงานนำเสนอที่มีอยู่ คุณสามารถทำให้กระบวนการสร้างงานนำเสนอทั้งหมดเป็นแบบอัตโนมัติเพื่อประหยัดเวลาและความพยายาม

### ฉันสามารถหาทรัพยากรและตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

สำหรับเอกสารและตัวอย่างที่ครอบคลุม โปรดไปที่หน้าอ้างอิง Aspose.Slides สำหรับ Java: [เอกสารอ้างอิง API ของ Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}