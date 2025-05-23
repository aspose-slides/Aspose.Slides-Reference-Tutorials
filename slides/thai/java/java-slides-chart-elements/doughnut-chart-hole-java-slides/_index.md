---
"description": "สร้างแผนภูมิโดนัทพร้อมขนาดรูที่กำหนดเองใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการปรับแต่งแผนภูมิ"
"linktitle": "รูแผนภูมิโดนัทในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รูแผนภูมิโดนัทในสไลด์ Java"
"url": "/th/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รูแผนภูมิโดนัทในสไลด์ Java


## การแนะนำแผนภูมิโดนัทที่มีรูในสไลด์ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการสร้างแผนภูมิโดนัทที่มีรูโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการพร้อมตัวอย่างโค้ดต้นฉบับ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

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
    // สร้างแผนภูมิโดนัทในสไลด์แรก
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // กำหนดขนาดของรูในแผนภูมิโดนัท (เป็นเปอร์เซ็นต์)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // บันทึกการนำเสนอลงในดิสก์
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // กำจัดวัตถุนำเสนอ
    if (presentation != null) presentation.dispose();
}
```

## ขั้นตอนที่ 4: รันโค้ด

เรียกใช้โค้ด Java ใน IDE หรือโปรแกรมแก้ไขข้อความของคุณเพื่อสร้างแผนภูมิโดนัทที่มีขนาดรูตามที่กำหนด อย่าลืมเปลี่ยน `"Your Document Directory"` ด้วยเส้นทางจริงที่คุณต้องการบันทึกการนำเสนอ

## โค้ดต้นฉบับสมบูรณ์สำหรับช่องแผนภูมิโดนัทในสไลด์ Java

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// เขียนการนำเสนอลงดิสก์
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีสร้างแผนภูมิโดนัทที่มีรูโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับขนาดของรูได้โดยปรับ `setDoughnutHoleSize` พารามิเตอร์วิธีการ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของส่วนต่างๆ ของแผนภูมิได้อย่างไร?

หากต้องการเปลี่ยนสีของส่วนแผนภูมิ คุณสามารถใช้ `setDataPointsInLegend` วิธีการบน `IChart` วัตถุและตั้งค่าสีที่ต้องการให้กับจุดข้อมูลแต่ละจุด

### ฉันสามารถเพิ่มป้ายกำกับให้กับส่วนแผนภูมิโดนัทได้หรือไม่

ใช่ คุณสามารถเพิ่มป้ายกำกับให้กับส่วนแผนภูมิโดนัทได้โดยใช้ `setDataPointsLabelValue` วิธีการบน `IChart` วัตถุ.

### สามารถเพิ่มชื่อเรื่องให้กับแผนภูมิได้หรือไม่?

แน่นอน! คุณสามารถเพิ่มชื่อเรื่องให้กับแผนภูมิได้โดยใช้ `setTitle` วิธีการบน `IChart` วัตถุและจัดเตรียมข้อความชื่อเรื่องที่ต้องการ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}