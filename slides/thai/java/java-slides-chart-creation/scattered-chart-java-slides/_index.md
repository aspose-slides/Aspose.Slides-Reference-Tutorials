---
title: แผนภูมิกระจัดกระจายใน Java Slides
linktitle: แผนภูมิกระจัดกระจายใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิกระจายใน Java โดยใช้ Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด Java สำหรับการแสดงข้อมูลเป็นภาพในการนำเสนอ
type: docs
weight: 11
url: /th/java/chart-creation/scattered-chart-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับแผนภูมิกระจายใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างแผนภูมิกระจายโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกระจายมีประโยชน์ในการแสดงจุดข้อมูลเป็นภาพบนระนาบสองมิติ เราจะให้คำแนะนำทีละขั้นตอนและรวมซอร์สโค้ด Java ไว้เพื่อความสะดวกของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. [Aspose.Slides สำหรับ Java](https://products.aspose.com/slides/java) ติดตั้งแล้ว
2. ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรก นำเข้าไลบรารีที่จำเป็นและสร้างงานนำเสนอใหม่

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// สร้างงานนำเสนอใหม่
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มสไลด์และสร้างแผนภูมิกระจาย

 จากนั้น เพิ่มสไลด์และสร้างแผนภูมิกระจายบนสไลด์ เราจะใช้`ScatterWithSmoothLines`ประเภทแผนภูมิในตัวอย่างนี้

```java
// รับสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);

// การสร้างแผนภูมิกระจาย
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## ขั้นตอนที่ 3: เตรียมข้อมูลแผนภูมิ

ตอนนี้ เรามาเตรียมข้อมูลสำหรับแผนภูมิกระจายของเรากันดีกว่า เราจะเพิ่มสองชุด โดยแต่ละชุดจะมีจุดข้อมูลหลายจุด

```java
// รับดัชนีแผ่นงานข้อมูลแผนภูมิเริ่มต้น
int defaultWorksheetIndex = 0;

// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// ลบชุดสาธิต
chart.getChartData().getSeries().clear();

// เพิ่มชุดแรก
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// ใช้แผนภูมิชุดแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// เพิ่มจุดข้อมูลลงในชุดแรก
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// แก้ไขประเภทของซีรีส์
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // เปลี่ยนขนาดเครื่องหมาย
series.getMarker().setSymbol(MarkerStyleType.Star); // เปลี่ยนสัญลักษณ์เครื่องหมาย

// ใช้ชุดแผนภูมิที่สอง
series = chart.getChartData().getSeries().get_Item(1);

// เพิ่มจุดข้อมูลลงในชุดข้อมูลที่สอง
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// เปลี่ยนสไตล์มาร์กเกอร์สำหรับซีรีส์ที่สอง
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอด้วยแผนภูมิกระจายเป็นไฟล์ PPTX

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณสร้างแผนภูมิกระจายโดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ตอนนี้คุณสามารถปรับแต่งตัวอย่างนี้เพิ่มเติมเพื่อให้เหมาะกับข้อมูลเฉพาะและข้อกำหนดการออกแบบของคุณ

## กรอกซอร์สโค้ดสำหรับแผนภูมิที่กระจัดกระจายใน Java Slides
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//การสร้างแผนภูมิเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// รับดัชนีแผ่นงานข้อมูลแผนภูมิเริ่มต้น
int defaultWorksheetIndex = 0;
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// ลบชุดสาธิต
chart.getChartData().getSeries().clear();
// เพิ่มซีรีส์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// ใช้แผนภูมิชุดแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// เพิ่มจุดใหม่ (1:3) ที่นั่น
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// เพิ่มจุดใหม่ (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// แก้ไขประเภทของซีรีส์
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// การเปลี่ยนเครื่องหมายชุดแผนภูมิ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// ใช้แผนภูมิชุดที่สอง
series = chart.getChartData().getSeries().get_Item(1);
// เพิ่มจุดใหม่ (5:2) ที่นั่น
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// เพิ่มจุดใหม่ (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// เพิ่มจุดใหม่ (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// เพิ่มจุดใหม่ (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// การเปลี่ยนเครื่องหมายชุดแผนภูมิ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้แนะนำคุณตลอดขั้นตอนการสร้างแผนภูมิกระจายโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกระจายเป็นเครื่องมือที่มีประสิทธิภาพสำหรับการแสดงจุดข้อมูลในพื้นที่สองมิติ ทำให้วิเคราะห์และทำความเข้าใจความสัมพันธ์ของข้อมูลที่ซับซ้อนได้ง่ายขึ้น

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 หากต้องการเปลี่ยนประเภทแผนภูมิ ให้ใช้`setType` วิธีการชุดแผนภูมิและระบุประเภทแผนภูมิที่ต้องการ ตัวอย่างเช่น,`series.setType(ChartType.Line)` จะเปลี่ยนชุดข้อมูลเป็นแผนภูมิเส้น

### ฉันจะปรับแต่งขนาดและรูปแบบของมาร์กเกอร์ได้อย่างไร

 คุณสามารถเปลี่ยนขนาดและรูปแบบของมาร์กเกอร์ได้โดยใช้`getMarker` บนอนุกรมแล้วกำหนดคุณสมบัติขนาดและสัญลักษณ์ ตัวอย่างเช่น:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

สำรวจตัวเลือกการปรับแต่งเพิ่มเติมได้ตามสบายในเอกสาร Aspose.Slides สำหรับ Java

 อย่าลืมเปลี่ยน`"Your Document Directory"` พร้อมเส้นทางจริงที่คุณต้องการบันทึกการนำเสนอ