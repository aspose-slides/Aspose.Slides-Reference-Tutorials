---
title: แผนภูมิช่องทางใน Java Slides
linktitle: แผนภูมิช่องทางใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้การสร้างแผนภูมิกรวยในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการแสดงภาพข้อมูลที่มีประสิทธิภาพ
weight: 18
url: /th/java/chart-data-manipulation/funnel-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างแผนภูมิช่องทางใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างแผนภูมิกรวยในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิช่องทางมีประโยชน์ในการแสดงภาพข้อมูลที่แคบลงเรื่อยๆ หรือ "ช่องทาง" ผ่านขั้นตอนหรือหมวดหมู่ต่างๆ เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ดเพื่อช่วยให้คุณบรรลุเป้าหมายนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งและตั้งค่า Aspose.Slides สำหรับไลบรารี Java ในโครงการของคุณ
- ไฟล์งานนำเสนอ PowerPoint (PPTX) ที่คุณต้องการแทรกแผนภูมิกรวย

## ขั้นตอนที่ 1: นำเข้า Aspose.Slides สำหรับ Java

ขั้นแรก คุณต้องนำเข้าไลบรารี Aspose.Slides สำหรับ Java ไปยังโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการขึ้นต่อกันที่จำเป็นให้กับการกำหนดค่าบิวด์ของคุณ

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอและแผนภูมิ

ในขั้นตอนนี้ เราจะเริ่มต้นการนำเสนอและเพิ่มแผนภูมิกรวยลงในสไลด์

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    //เพิ่มแผนภูมิกรวยลงในสไลด์แรกที่พิกัด (50, 50) พร้อมขนาด (500, 400)
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## ขั้นตอนที่ 3: กำหนดข้อมูลแผนภูมิ

ต่อไป เราจะกำหนดข้อมูลสำหรับแผนภูมิช่องทางของเรา คุณสามารถปรับแต่งหมวดหมู่และจุดข้อมูลได้ตามความต้องการของคุณ

```java
// ล้างข้อมูลแผนภูมิที่มีอยู่
wb.clear(0);

// กำหนดหมวดหมู่สำหรับแผนภูมิ
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// เพิ่มจุดข้อมูลสำหรับชุดแผนภูมิช่องทาง
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายนี้ เราจะบันทึกการนำเสนอด้วย Funnel Chart ลงในไฟล์ที่ระบุ

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณสร้างแผนภูมิกรวยสำเร็จโดยใช้ Aspose.Slides สำหรับ Java และแทรกลงในงานนำเสนอ PowerPoint

## กรอกซอร์สโค้ดสำหรับแผนภูมิช่องทางใน Java Slides

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## บทสรุป

ในคำแนะนำทีละขั้นตอนนี้ เราได้สาธิตวิธีการสร้างแผนภูมิกรวยในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกรวยเป็นเครื่องมือที่มีค่าสำหรับการแสดงข้อมูลเป็นภาพซึ่งเป็นไปตามรูปแบบความก้าวหน้าหรือรูปแบบที่แคบลง ทำให้ง่ายต่อการถ่ายทอดข้อมูลอย่างมีประสิทธิภาพ 

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งรูปลักษณ์ของแผนภูมิช่องทางได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิช่องทางได้โดยการแก้ไขคุณสมบัติแผนภูมิต่างๆ เช่น สี ป้ายกำกับ และสไตล์ โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกการปรับแต่งแผนภูมิ

### ฉันสามารถเพิ่มจุดข้อมูลหรือหมวดหมู่เพิ่มเติมลงในแผนภูมิช่องทางได้หรือไม่

ได้ คุณสามารถเพิ่มจุดข้อมูลเพิ่มเติมและหมวดหมู่ลงในแผนภูมิช่องทางได้โดยขยายโค้ดที่ให้ไว้ในขั้นตอนที่ 3 เพียงเพิ่มป้ายกำกับหมวดหมู่และจุดข้อมูลเพิ่มเติมตามต้องการ

### ฉันจะเปลี่ยนตำแหน่งและขนาดของแผนภูมิกรวยบนสไลด์ได้อย่างไร

คุณสามารถปรับตำแหน่งและขนาดของแผนภูมิช่องทางได้โดยแก้ไขพิกัดและขนาดที่ให้ไว้เมื่อเพิ่มแผนภูมิลงในสไลด์ในขั้นตอนที่ 2 อัปเดตค่า (50, 50, 500, 400) ตามนั้น

### ฉันสามารถส่งออกแผนภูมิเป็นรูปแบบต่างๆ เช่น PDF หรือรูปภาพได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java ช่วยให้คุณสามารถส่งออกงานนำเสนอด้วยแผนภูมิกรวยเป็นรูปแบบต่างๆ รวมถึง PDF รูปแบบรูปภาพ และอื่นๆ คุณสามารถใช้`SaveFormat` ตัวเลือกเพื่อระบุรูปแบบผลลัพธ์ที่ต้องการเมื่อบันทึกงานนำเสนอ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
