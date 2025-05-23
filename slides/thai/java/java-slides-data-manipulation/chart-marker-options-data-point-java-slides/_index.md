---
"description": "เพิ่มประสิทธิภาพ Java Slides ของคุณด้วยตัวเลือก Custom Chart Marker เรียนรู้การปรับปรุงจุดข้อมูลด้วยภาพโดยใช้ Aspose.Slides สำหรับ Java สำรวจคำแนะนำทีละขั้นตอนและคำถามที่พบบ่อย"
"linktitle": "ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Java Slides"
"url": "/th/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Java Slides


## การแนะนำตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Java Slides

เมื่อต้องสร้างงานนำเสนอที่มีประสิทธิภาพ ความสามารถในการปรับแต่งและจัดการเครื่องหมายแผนภูมิบนจุดข้อมูลสามารถสร้างความแตกต่างได้ ด้วย Aspose.Slides สำหรับ Java คุณสามารถแปลงแผนภูมิของคุณให้กลายเป็นองค์ประกอบที่ไดนามิกและดึงดูดสายตาได้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกในส่วนของการเขียนโค้ด ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java
- Aspose.Slides สำหรับไลบรารี Java
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ Java (IDE)
- ตัวอย่างเอกสารนำเสนอ (เช่น "Test.pptx")

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ขั้นแรก ให้แน่ใจว่าคุณได้ติดตั้งเครื่องมือที่จำเป็นและพร้อมใช้งานแล้ว สร้างโปรเจ็กต์ Java ใน IDE ของคุณและนำเข้าไลบรารี Aspose.Slides สำหรับ Java

## ขั้นตอนที่ 2: การโหลดงานนำเสนอ

ในการเริ่มต้น ให้โหลดเอกสารตัวอย่างการนำเสนอของคุณ ในโค้ดที่ให้มา เราถือว่าเอกสารมีชื่อว่า "Test.pptx"

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## ขั้นตอนที่ 3: การสร้างแผนภูมิ

ตอนนี้เรามาสร้างแผนภูมิในงานนำเสนอกัน เราจะใช้แผนภูมิเส้นพร้อมเครื่องหมายในตัวอย่างนี้

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## ขั้นตอนที่ 4: การทำงานกับข้อมูลแผนภูมิ

ในการจัดการข้อมูลแผนภูมิ เราจำเป็นต้องเข้าถึงเวิร์กบุ๊กข้อมูลแผนภูมิและเตรียมชุดข้อมูล เราจะล้างชุดข้อมูลเริ่มต้นและเพิ่มข้อมูลที่กำหนดเองของเรา

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## ขั้นตอนที่ 5: การเพิ่มเครื่องหมายที่กำหนดเอง

ขั้นตอนที่น่าตื่นเต้นคือการปรับแต่งเครื่องหมายบนจุดข้อมูล เราจะใช้รูปภาพเป็นเครื่องหมายในตัวอย่างนี้

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// การเพิ่มเครื่องหมายที่กำหนดเองลงในจุดข้อมูล
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// ทำซ้ำสำหรับจุดข้อมูลอื่น ๆ
// -

// การเปลี่ยนแปลงขนาดเครื่องหมายชุดแผนภูมิ
series.getMarker().setSize(15);
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

เมื่อคุณปรับแต่งเครื่องหมายแผนภูมิของคุณแล้ว ให้บันทึกการนำเสนอเพื่อดูการเปลี่ยนแปลงที่เกิดขึ้น

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับตัวเลือกเครื่องหมายแผนภูมิบนจุดข้อมูลใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//การสร้างแผนภูมิเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//การรับดัชนีเวิร์กชีตข้อมูลแผนภูมิเริ่มต้น
int defaultWorksheetIndex = 0;
//การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//ลบซีรีย์สาธิต
chart.getChartData().getSeries().clear();
//เพิ่มซีรีย์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//ตั้งค่ารูปภาพ
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//ตั้งค่ารูปภาพ
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//เริ่มต้นด้วยชุดแผนภูมิแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//เพิ่มจุดใหม่ (1:3) ที่นั่น
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//การเปลี่ยนแปลงเครื่องหมายชุดแผนภูมิ
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## บทสรุป

ด้วย Aspose.Slides สำหรับ Java คุณสามารถยกระดับการนำเสนอของคุณได้โดยปรับแต่งเครื่องหมายแผนภูมิบนจุดข้อมูล วิธีนี้ช่วยให้คุณสร้างสไลด์ที่สวยงามและให้ข้อมูลที่ดึงดูดผู้ชมได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนขนาดเครื่องหมายสำหรับจุดข้อมูลได้อย่างไร

หากต้องการเปลี่ยนขนาดเครื่องหมายสำหรับจุดข้อมูล ให้ใช้ `series.getMarker().setSize()` วิธีการและระบุขนาดที่ต้องการเป็นอาร์กิวเมนต์

### ฉันสามารถใช้รูปภาพเป็นเครื่องหมายที่กำหนดเองได้หรือไม่

ใช่ คุณสามารถใช้รูปภาพเป็นเครื่องหมายที่กำหนดเองสำหรับจุดข้อมูลได้ ตั้งค่าประเภทการเติมเป็น `FillType.Picture` และให้ภาพที่คุณต้องการใช้

### Aspose.Slides สำหรับ Java เหมาะกับการสร้างแผนภูมิแบบไดนามิกหรือไม่

แน่นอน! Aspose.Slides สำหรับ Java มีความสามารถมากมายในการสร้างแผนภูมิแบบไดนามิกและโต้ตอบได้สำหรับงานนำเสนอของคุณ

### ฉันสามารถปรับแต่งด้านอื่นๆ ของแผนภูมิโดยใช้ Aspose.Slides ได้หรือไม่

ใช่ คุณสามารถปรับแต่งด้านต่างๆ ของแผนภูมิได้ รวมถึงชื่อ แกน ป้ายข้อมูล และอื่นๆ โดยใช้ Aspose.Slides สำหรับ Java

### ฉันสามารถเข้าถึงเอกสารและดาวน์โหลด Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถหาเอกสารประกอบได้ที่ [ที่นี่](https://reference.aspose.com/slides/java/) และดาวน์โหลดห้องสมุดได้ที่ [ที่นี่](https://releases-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}