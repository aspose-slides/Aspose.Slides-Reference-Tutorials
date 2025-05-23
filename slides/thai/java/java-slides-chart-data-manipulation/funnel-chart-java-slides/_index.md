---
"description": "เรียนรู้การสร้าง Funnel Charts ในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการแสดงภาพข้อมูลอย่างมีประสิทธิภาพ"
"linktitle": "แผนภูมิกรวยใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิกรวยใน Java Slides"
"url": "/th/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิกรวยใน Java Slides


## บทนำสู่การสร้างแผนภูมิกรวยใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแผนภูมิกรวยในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกรวยมีประโยชน์สำหรับการแสดงข้อมูลแบบค่อยเป็นค่อยไปหรือ "กรวย" ผ่านขั้นตอนหรือหมวดหมู่ต่างๆ เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับโค้ดต้นฉบับเพื่อช่วยให้คุณบรรลุเป้าหมายดังกล่าว

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว
- ไฟล์การนำเสนอ PowerPoint (PPTX) ที่คุณต้องการแทรกแผนภูมิกรวย

## ขั้นตอนที่ 1: นำเข้า Aspose.Slides สำหรับ Java

ขั้นแรก คุณต้องนำเข้าไลบรารี Aspose.Slides สำหรับ Java เข้าสู่โปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงที่จำเป็นลงในคอนฟิกูเรชันการสร้างของคุณแล้ว

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอและแผนภูมิ

ในขั้นตอนนี้ เราจะเริ่มการนำเสนอและเพิ่มแผนภูมิกรวยลงในสไลด์

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // เพิ่มแผนภูมิกรวยลงในสไลด์แรกที่พิกัด (50, 50) พร้อมด้วยมิติ (500, 400)
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

ขั้นต่อไป เราจะกำหนดข้อมูลสำหรับ Funnel Chart ของเรา คุณสามารถปรับแต่งหมวดหมู่และจุดข้อมูลตามความต้องการของคุณได้

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

// เพิ่มจุดข้อมูลสำหรับชุดแผนภูมิกรวย
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย เราบันทึกการนำเสนอด้วย Funnel Chart ลงในไฟล์ที่ระบุ

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้าง Funnel Chart โดยใช้ Aspose.Slides สำหรับ Java และแทรกเข้าในงานนำเสนอ PowerPoint สำเร็จแล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับ Funnel Chart ใน Java Slides

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

ในคู่มือทีละขั้นตอนนี้ เราได้สาธิตวิธีการสร้างแผนภูมิกรวยในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกรวยเป็นเครื่องมือที่มีประโยชน์สำหรับการแสดงข้อมูลตามรูปแบบความก้าวหน้าหรือการจำกัด ทำให้สามารถถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ 

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะของ Funnel Chart ได้อย่างไร?

คุณสามารถปรับแต่งลักษณะของแผนภูมิกรวยได้โดยแก้ไขคุณสมบัติต่างๆ ของแผนภูมิ เช่น สี ป้ายกำกับ และรูปแบบ โปรดดูเอกสาร Aspose.Slides เพื่อดูข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกการปรับแต่งแผนภูมิ

### ฉันสามารถเพิ่มจุดข้อมูลหรือหมวดหมู่เพิ่มเติมลงในแผนภูมิกรวยได้หรือไม่

ใช่ คุณสามารถเพิ่มจุดข้อมูลและหมวดหมู่เพิ่มเติมลงใน Funnel Chart ได้โดยขยายโค้ดที่ให้ไว้ในขั้นตอนที่ 3 เพียงเพิ่มป้ายหมวดหมู่และจุดข้อมูลเพิ่มเติมตามต้องการ

### ฉันจะเปลี่ยนตำแหน่งและขนาดของ Funnel Chart บนสไลด์ได้อย่างไร

คุณสามารถปรับตำแหน่งและขนาดของแผนภูมิกรวยได้โดยการแก้ไขพิกัดและมิติที่ให้ไว้เมื่อเพิ่มแผนภูมิลงในสไลด์ในขั้นตอนที่ 2 อัปเดตค่า (50, 50, 500, 400) ตามลำดับ

### ฉันสามารถส่งออกแผนภูมิไปยังรูปแบบอื่น เช่น PDF หรือรูปภาพได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java ช่วยให้คุณสามารถส่งออกการนำเสนอด้วย Funnel Chart เป็นรูปแบบต่างๆ ได้ เช่น PDF รูปแบบรูปภาพ และอื่นๆ อีกมากมาย คุณสามารถใช้ `SaveFormat` ตัวเลือกในการระบุรูปแบบผลลัพธ์ที่ต้องการเมื่อบันทึกงานนำเสนอ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}