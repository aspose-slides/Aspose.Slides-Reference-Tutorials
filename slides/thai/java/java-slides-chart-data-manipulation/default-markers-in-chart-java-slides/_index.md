---
"description": "เรียนรู้วิธีสร้าง Java Slides โดยใช้มาร์กเกอร์เริ่มต้นในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "เครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides"
"url": "/th/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides


## การแนะนำการใช้เครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการสร้างแผนภูมิโดยใช้เครื่องหมายเริ่มต้นโดยใช้ Aspose.Slides สำหรับ Java เครื่องหมายเริ่มต้นคือสัญลักษณ์หรือรูปร่างที่เพิ่มลงในจุดข้อมูลในแผนภูมิเพื่อเน้นจุดข้อมูลเหล่านั้น เราจะสร้างแผนภูมิเส้นโดยใช้เครื่องหมายเพื่อแสดงข้อมูล

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก ให้สร้างงานนำเสนอและเพิ่มสไลด์เข้าไป จากนั้นจึงเพิ่มแผนภูมิลงในสไลด์

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิเส้นพร้อมเครื่องหมาย

ตอนนี้เรามาเพิ่มแผนภูมิเส้นพร้อมเครื่องหมายลงในสไลด์กัน เราจะล้างข้อมูลเริ่มต้นทั้งหมดออกจากแผนภูมิด้วย

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## ขั้นตอนที่ 3: เติมข้อมูลแผนภูมิ

เราจะเติมข้อมูลตัวอย่างลงในแผนภูมิ ในตัวอย่างนี้ เราจะสร้างชุดข้อมูลสองชุดที่มีจุดข้อมูลและหมวดหมู่

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

// ซีรี่ย์ 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// การเติมข้อมูลชุด
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## ขั้นตอนที่ 4: ปรับแต่งแผนภูมิ

คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้ เช่น การเพิ่มคำอธิบายและปรับเปลี่ยนลักษณะที่ปรากฏ

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอพร้อมแผนภูมิไปยังตำแหน่งที่คุณต้องการ

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้างแผนภูมิเส้นที่มีเครื่องหมายเริ่มต้นโดยใช้ Aspose.Slides สำหรับ Java แล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับเครื่องหมายเริ่มต้นในแผนภูมิใน Java Slides

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
            //มาดูแผนภูมิชุดที่สองกัน
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
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

ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีสร้าง Java Slides ด้วยเครื่องหมายเริ่มต้นในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java เราได้ครอบคลุมกระบวนการทั้งหมดตั้งแต่การตั้งค่าการนำเสนอไปจนถึงการปรับแต่งรูปลักษณ์ของแผนภูมิและการบันทึกผลลัพธ์

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสัญลักษณ์เครื่องหมายได้อย่างไร

คุณสามารถปรับแต่งสัญลักษณ์เครื่องหมายได้โดยการตั้งค่ารูปแบบเครื่องหมายสำหรับจุดข้อมูลแต่ละจุด ใช้ `IDataPoint.setMarkerStyle()` เพื่อเปลี่ยนสัญลักษณ์เครื่องหมาย

### ฉันจะปรับสีของแผนภูมิได้อย่างไร?

หากต้องการปรับเปลี่ยนสีของแผนภูมิ คุณสามารถใช้ `IChartSeriesFormat` และ `IShapeFillFormat` อินเทอร์เฟซสำหรับตั้งค่าคุณสมบัติการเติมและเส้น

### ฉันสามารถเพิ่มป้ายกำกับลงในจุดข้อมูลได้หรือไม่

ใช่ คุณสามารถเพิ่มป้ายกำกับลงในจุดข้อมูลโดยใช้ `IDataPoint.getLabel()` วิธีการและปรับแต่งตามความจำเป็น

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}