---
"description": "เรียนรู้วิธีสร้างแผนภูมิแบบกระจายใน Java โดยใช้ Aspose.Slides คำแนะนำแบบทีละขั้นตอนพร้อมโค้ดต้นฉบับ Java สำหรับการแสดงภาพข้อมูลในงานนำเสนอ"
"linktitle": "แผนภูมิแบบกระจายใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิแบบกระจายใน Java Slides"
"url": "/th/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิแบบกระจายใน Java Slides


## บทนำเกี่ยวกับแผนภูมิแบบกระจายใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแผนภูมิแบบกระจายโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิแบบกระจายมีประโยชน์สำหรับการแสดงภาพจุดข้อมูลบนระนาบสองมิติ เราจะให้คำแนะนำทีละขั้นตอนและรวมโค้ดต้นฉบับของ Java ไว้เพื่อความสะดวกของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. [Aspose.Slides สำหรับ Java](https://products.aspose.com/slides/java) ติดตั้งแล้ว
2. การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรก นำเข้าไลบรารีที่จำเป็น และสร้างงานนำเสนอใหม่

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// สร้างการนำเสนอใหม่
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มสไลด์และสร้างแผนภูมิแบบกระจาย

ขั้นตอนต่อไปคือการเพิ่มสไลด์และสร้างแผนภูมิแบบกระจายบนสไลด์นั้น เราจะใช้ `ScatterWithSmoothLines` ประเภทแผนภูมิในตัวอย่างนี้

```java
// รับสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);

// การสร้างแผนภูมิแบบกระจาย
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## ขั้นตอนที่ 3: เตรียมข้อมูลแผนภูมิ

ตอนนี้เรามาเตรียมข้อมูลสำหรับแผนภูมิกระจายของเรากัน เราจะเพิ่มชุดข้อมูลสองชุด โดยแต่ละชุดมีจุดข้อมูลหลายจุด

```java
// การรับดัชนีเวิร์กชีตข้อมูลแผนภูมิเริ่มต้น
int defaultWorksheetIndex = 0;

// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// ลบซีรีย์สาธิต
chart.getChartData().getSeries().clear();

// เพิ่มซีรีย์แรก
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// มาดูแผนภูมิชุดแรกกัน
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// เพิ่มจุดข้อมูลลงในชุดแรก
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// แก้ไขประเภทของซีรีย์
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // เปลี่ยนขนาดเครื่องหมาย
series.getMarker().setSymbol(MarkerStyleType.Star); // เปลี่ยนสัญลักษณ์เครื่องหมาย

// มาดูแผนภูมิชุดที่ 2 กัน
series = chart.getChartData().getSeries().get_Item(1);

// เพิ่มจุดข้อมูลลงในซีรีส์ที่สอง
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// เปลี่ยนรูปแบบมาร์กเกอร์สำหรับซีรีส์ที่สอง
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกการนำเสนอด้วยแผนภูมิแบบกระจายลงในไฟล์ PPTX

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้าง Scatter Chart โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ตอนนี้คุณสามารถปรับแต่งตัวอย่างนี้เพิ่มเติมเพื่อให้เหมาะกับข้อมูลเฉพาะและข้อกำหนดด้านการออกแบบของคุณ

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิแบบกระจายใน Java Slides
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// การสร้างแผนภูมิเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// การรับดัชนีเวิร์กชีตข้อมูลแผนภูมิเริ่มต้น
int defaultWorksheetIndex = 0;
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// ลบซีรีย์สาธิต
chart.getChartData().getSeries().clear();
// เพิ่มซีรีย์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// เริ่มต้นด้วยชุดแผนภูมิแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// เพิ่มจุดใหม่ (1:3) ที่นั่น
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// เพิ่มจุดใหม่ (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// แก้ไขประเภทของซีรีย์
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// การเปลี่ยนแปลงเครื่องหมายชุดแผนภูมิ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// มาดูแผนภูมิชุดที่สองกัน
series = chart.getChartData().getSeries().get_Item(1);
// เพิ่มจุดใหม่ (5:2) ที่นั่น
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// เพิ่มจุดใหม่ (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// เพิ่มจุดใหม่ (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// เพิ่มจุดใหม่ (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// การเปลี่ยนแปลงเครื่องหมายชุดแผนภูมิ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแผนภูมิแบบกระจายโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิแบบกระจายเป็นเครื่องมือที่มีประสิทธิภาพสำหรับการแสดงภาพจุดข้อมูลในพื้นที่สองมิติ ทำให้วิเคราะห์และทำความเข้าใจความสัมพันธ์ของข้อมูลที่ซับซ้อนได้ง่ายขึ้น

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร

หากต้องการเปลี่ยนประเภทแผนภูมิ ให้ใช้ `setType` วิธีการบนชุดแผนภูมิและระบุประเภทแผนภูมิที่ต้องการ ตัวอย่างเช่น `series.setType(ChartType.Line)` จะเปลี่ยนชุดข้อมูลให้เป็นแผนภูมิเส้น

### ฉันจะปรับขนาดและรูปแบบของเครื่องหมายได้อย่างไร

คุณสามารถเปลี่ยนขนาดและรูปแบบของเครื่องหมายได้โดยใช้ `getMarker` วิธีการบนซีรีส์แล้วกำหนดขนาดและคุณสมบัติสัญลักษณ์ ตัวอย่างเช่น:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

อย่าลังเลที่จะสำรวจตัวเลือกการปรับแต่งเพิ่มเติมในเอกสาร Aspose.Slides สำหรับ Java

อย่าลืมเปลี่ยน `"Your Document Directory"` ด้วยเส้นทางจริงที่คุณต้องการบันทึกการนำเสนอ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}