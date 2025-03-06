---
title: เครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides
linktitle: เครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้าง Java Slides ด้วยมาร์กเกอร์เริ่มต้นในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
weight: 16
url: /th/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับเครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างแผนภูมิด้วยมาร์กเกอร์เริ่มต้นโดยใช้ Aspose.Slides สำหรับ Java เครื่องหมายเริ่มต้นคือสัญลักษณ์หรือรูปร่างที่เพิ่มลงในจุดข้อมูลในแผนภูมิเพื่อไฮไลท์ เราจะสร้างแผนภูมิเส้นพร้อมเครื่องหมายเพื่อแสดงภาพข้อมูล

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก มาสร้างงานนำเสนอและเพิ่มสไลด์ลงไป จากนั้นเราจะเพิ่มแผนภูมิลงในสไลด์

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิเส้นด้วยเครื่องหมาย

ตอนนี้ เรามาเพิ่มแผนภูมิเส้นที่มีเครื่องหมายลงในสไลด์กันดีกว่า นอกจากนี้เรายังจะล้างข้อมูลเริ่มต้นออกจากแผนภูมิด้วย

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## ขั้นตอนที่ 3: เติมข้อมูลแผนภูมิ

เราจะเติมแผนภูมิด้วยข้อมูลตัวอย่าง ในตัวอย่างนี้ เราจะสร้างชุดข้อมูล 2 ชุดพร้อมจุดข้อมูลและหมวดหมู่

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// ชุดที่ 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// ชุดที่ 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// กำลังเติมข้อมูลซีรีส์
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## ขั้นตอนที่ 4: ปรับแต่งแผนภูมิ

คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้ เช่น การเพิ่มคำอธิบายและการปรับรูปลักษณ์

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอพร้อมแผนภูมิไปยังตำแหน่งที่คุณต้องการ

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้สร้างแผนภูมิเส้นพร้อมเครื่องหมายเริ่มต้นโดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับมาร์กเกอร์เริ่มต้นในแผนภูมิใน Java Slides

```java
        // เส้นทางไปยังไดเร็กทอรีเอกสาร
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //ใช้แผนภูมิชุดที่สอง
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //กำลังเติมข้อมูลซีรีส์
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## บทสรุป

ในบทช่วยสอนที่ครอบคลุมนี้ คุณได้เรียนรู้วิธีสร้าง Java Slides ด้วยเครื่องหมายเริ่มต้นในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java เราครอบคลุมกระบวนการทั้งหมดตั้งแต่การตั้งค่าการนำเสนอไปจนถึงการปรับแต่งรูปลักษณ์ของแผนภูมิและการบันทึกผลลัพธ์

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสัญลักษณ์มาร์กเกอร์ได้อย่างไร?

คุณสามารถปรับแต่งสัญลักษณ์มาร์กเกอร์ได้โดยการตั้งค่าสไตล์มาร์กเกอร์สำหรับจุดข้อมูลแต่ละจุด ใช้`IDataPoint.setMarkerStyle()` เพื่อเปลี่ยนสัญลักษณ์เครื่องหมาย

### ฉันจะปรับสีของแผนภูมิได้อย่างไร

 หากต้องการแก้ไขสีของแผนภูมิ คุณสามารถใช้`IChartSeriesFormat` และ`IShapeFillFormat` อินเทอร์เฟซเพื่อตั้งค่าคุณสมบัติการเติมและเส้น

### ฉันสามารถเพิ่มป้ายกำกับให้กับจุดข้อมูลได้หรือไม่

 ใช่ คุณสามารถเพิ่มป้ายกำกับให้กับจุดข้อมูลได้โดยใช้`IDataPoint.getLabel()` วิธีการและปรับแต่งได้ตามต้องการ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
