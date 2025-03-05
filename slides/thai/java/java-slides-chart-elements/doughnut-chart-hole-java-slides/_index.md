---
title: หลุมแผนภูมิโดนัทใน Java Slides
linktitle: หลุมแผนภูมิโดนัทใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สร้างแผนภูมิโดนัทด้วยขนาดรูที่กำหนดเองใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับการปรับแต่งแผนภูมิ
type: docs
weight: 11
url: /th/java/chart-elements/doughnut-chart-hole-java-slides/
---

## รู้เบื้องต้นเกี่ยวกับแผนภูมิโดนัทที่มีรูใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างแผนภูมิโดนัทที่มีรูโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการพร้อมตัวอย่างซอร์สโค้ด

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: สร้างแผนภูมิโดนัท

```java
try {
    // สร้างแผนภูมิโดนัทบนสไลด์แรก
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // กำหนดขนาดของรูในแผนภูมิโดนัท (เป็นเปอร์เซ็นต์)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // บันทึกการนำเสนอลงดิสก์
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // กำจัดวัตถุการนำเสนอ
    if (presentation != null) presentation.dispose();
}
```

## ขั้นตอนที่ 4: เรียกใช้โค้ด

 เรียกใช้โค้ด Java ใน IDE หรือโปรแกรมแก้ไขข้อความของคุณเพื่อสร้างแผนภูมิโดนัทที่มีขนาดรูที่ระบุ ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` พร้อมเส้นทางจริงที่คุณต้องการบันทึกการนำเสนอ

## กรอกซอร์สโค้ดสำหรับรูแผนภูมิโดนัทใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// เขียนงานนำเสนอลงดิสก์
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

 ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างแผนภูมิโดนัทที่มีรูโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งขนาดของรูได้โดยการปรับ`setDoughnutHoleSize` พารามิเตอร์วิธีการ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของส่วนแผนภูมิได้อย่างไร

 หากต้องการเปลี่ยนสีของส่วนแผนภูมิ คุณสามารถใช้`setDataPointsInLegend` วิธีการบน`IChart` object และกำหนดสีที่ต้องการให้กับจุดข้อมูลแต่ละจุด

### ฉันสามารถเพิ่มป้ายกำกับให้กับส่วนแผนภูมิโดนัทได้หรือไม่

 ได้ คุณสามารถเพิ่มป้ายกำกับให้กับส่วนแผนภูมิโดนัทได้โดยใช้`setDataPointsLabelValue` วิธีการบน`IChart` วัตถุ.

### เป็นไปได้ไหมที่จะเพิ่มชื่อลงในแผนภูมิ?

 แน่นอน! คุณสามารถเพิ่มชื่อให้กับแผนภูมิโดยใช้`setTitle` วิธีการบน`IChart` วัตถุและระบุข้อความชื่อที่ต้องการ