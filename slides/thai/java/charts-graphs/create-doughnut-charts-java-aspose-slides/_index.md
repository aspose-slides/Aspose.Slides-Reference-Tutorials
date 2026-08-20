---
date: '2026-08-16'
description: เรียนรู้วิธีเพิ่ม doughnut chart ใน Java ด้วย Aspose.Slides คู่มือขั้นตอนนี้ครอบคลุมการตั้งค่า
  Maven dependency, การกำหนดค่า chart, colors, labels และการบันทึกไฟล์ PPTX
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: วิธีเพิ่ม doughnut chart ใน Java ด้วย Aspose.Slides ทำตามคู่มือนี้เพื่อตั้งค่า
  Maven, ปรับแต่ง colors, labels และสร้างไฟล์ PPTX
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: วิธีเพิ่ม doughnut chart ใน Java ด้วย Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: วิธีเพิ่ม doughnut chart ใน Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเพิ่มแผนภูมิโดนัทใน Java ด้วย Aspose.Slides

## บทนำ

การสร้าง **doughnut chart** ด้วยโปรแกรมสามารถเปลี่ยนตัวเลขดิบให้กลายเป็นภาพที่ดึงดูดสายตาและบอกเล่าเรื่องราวได้ทันที ใน Java, **Aspose.Slides** ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณสร้างแผนภูมิพร้อมนำเสนอได้โดยไม่ต้องเปิด PowerPoint ในบทแนะนำนี้คุณจะได้เรียนรู้ **how to add doughnut** แผนภูมิลงในไฟล์ PPTX ทีละขั้นตอน—ตั้งแต่การตั้งค่า Maven Aspose Slides dependency ไปจนถึงการปรับแต่ง series, categories, colors, และ labels และสุดท้ายการบันทึกงานนำเสนอ

เมื่อจบคู่มือนี้คุณจะสามารถฝังแผนภูมิ doughnut แบบไดนามิกลงในไฟล์ PPTX ใดก็ได้ เหมาะสำหรับรายงาน, แดชบอร์ด หรือชุดสไลด์อัตโนมัติ

### คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ใช้คืออะไร?** Aspose.Slides for Java  
- **งานหลักคืออะไร?** Add a doughnut chart in a PPTX file  
- **วิธีเพิ่มไลบรารี?** Use the Maven Aspose Slides dependency (or Gradle)  
- **เวอร์ชัน Java ขั้นต่ำ?** JDK 16 or higher  
- **ฉันสามารถปรับสีและป้ายกำกับได้หรือไม่?** Yes, the API provides full formatting control  

## แผนภูมิ doughnut คืออะไรและทำไมต้องใช้?

แผนภูมิ doughnut เป็นรูปแบบหนึ่งของแผนภูมิวงกลมที่มีศูนย์ว่างอยู่ ทำให้สามารถแสดงหลาย series ของข้อมูลเป็นวงแหวนศูนย์กลาง **มันแสดงส่วนของทั้งหมดในหลายหมวดหมู่พร้อมรักษาพื้นที่ไว้สำหรับข้อมูลเพิ่มเติมในศูนย์กลาง** สิ่งนี้ทำให้เหมาะสำหรับการเปรียบเทียบยอดขายตามภูมิภาคในหลายไตรมาส, การจัดสรรงบประมาณตามแผนก, หรือสถานการณ์ใด ๆ ที่ต้องแสดงข้อมูลสัดส่วนเชิงลำดับขั้น

## ทำไมต้องใช้ Aspose.Slides สำหรับ Java?

คุณสามารถเพิ่มแผนภูมิ doughnut ได้โดยไม่ต้องติดตั้ง Microsoft Office และไลบรารีสามารถประมวลผล **รูปแบบอินพุตและเอาต์พุตกว่า 50 +** พร้อมจัดการงานนำเสนอที่มีจำนวนสไลด์เกิน 500 สไลด์ Aspose.Slides ให้ **การเรนเดอร์เร็วขึ้นถึง 3×** เมื่อเทียบกับการทำออโตเมชัน Office ดั้งเดิมบนฮาร์ดแวร์เดียวกัน และทำงานบน Windows, Linux และ macOS ประโยชน์ที่วัดได้เหล่านี้หมายความว่าคุณสามารถสร้างชุดสไลด์ขนาดใหญ่บนเซิร์ฟเวอร์แบบไม่มี UI ด้วยประสิทธิภาพที่คาดการณ์ได้

## ข้อกำหนดเบื้องต้น

- **ไลบรารีที่ต้องการ**  
  - Aspose.Slides for Java 25.4 หรือใหม่กว่า (ไลบรารีที่ทำให้คุณสามารถเพิ่มแผนภูมิ doughnut ได้)  

- **สภาพแวดล้อม**  
  - JDK 16 หรือสูงกว่า ติดตั้งบนเครื่องของคุณ  
  - IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans  

- **ความรู้**  
  - ความเข้าใจพื้นฐานของไวยากรณ์ Java และแนวคิดเชิงวัตถุ  
  - ความคุ้นเคยกับ Maven หรือ Gradle สำหรับการจัดการ dependencies  

## การพึ่งพา Maven Aspose Slides

เพิ่มการพึ่งพา Maven ด้านล่างนี้ในไฟล์ `pom.xml` ของคุณ นี่คือ **maven aspose slides dependency** ที่คุณต้องใช้เพื่อดึงไลบรารีเข้ามาในโปรเจกต์ของคุณ

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

หากคุณต้องการใช้ Gradle ให้ใช้โค้ดตัวอย่างที่เทียบเท่าด้านล่าง

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

คุณยังสามารถดาวน์โหลดไฟล์ JAR โดยตรงจากหน้าปล่อยอย่างเป็นทางการ:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### การรับใบอนุญาต

เพื่อเอาน้ำลายน้ำการประเมินค่าออกและเปิดใช้งานฟีเจอร์ทั้งหมด:

- **ทดลองใช้ฟรี** – เริ่มต้นด้วยใบอนุญาตชั่วคราว.  
- **ใบอนุญาตชั่วคราว** – ขอรับจาก [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **ใบอนุญาตเชิงพาณิชย์** – ซื้อเพื่อการใช้งานในผลิตภัณฑ์.

ใช้ใบอนุญาตในโค้ดของคุณ:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## คู่มือการดำเนินการ

### การเริ่มต้น Presentation และเพิ่มแผนภูมิ doughnut

Presentation คือคลาสของ Aspose.Slides ที่แทนการนำเสนอ PowerPoint. โหลดไฟล์ PPTX ที่มีอยู่หรือสร้างอ็อบเจกต์ `Presentation` ใหม่ แล้วเพิ่มแผนภูมิ doughnut ไปยังสไลด์แรก

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### การกำหนดค่า workbook ของข้อมูลแผนภูมิและล้างข้อมูลที่มีอยู่

workbook คือสเปรดชีตภายในที่เก็บข้อมูลของแผนภูมิ. รับ workbook ที่สนับสนุนแผนภูมิแล้วล้าง series หรือ categories เริ่มต้นใด ๆ เพื่อเริ่มจากศูนย์

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### การเพิ่ม series ไปยังแผนภูมิ

series แสดงชุดของจุดข้อมูลที่พล็อตบนแผนภูมิ. คุณสามารถเพิ่มได้สูงสุด 15 series. แต่ละ series สามารถปรับแต่งได้—ในที่นี้เราตั้งค่า explosion, ขนาดของรู doughnut, และมุมของชิ้นแรก

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### การเพิ่ม categories และ data points

categories คือป้ายกำกับสำหรับแต่ละจุดข้อมูลตามแกนของแผนภูมิ. สร้าง 15 categories และเติมข้อมูลให้แต่ละ series ด้วย data point. series สุดท้ายจะได้รับการจัดรูปแบบป้ายพิเศษ

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### การปรับแต่งสีและป้ายข้อมูล

`FillType.Solid` ระบุสีเติมแบบทึบสำหรับองค์ประกอบของแผนภูมิ. ตั้งค่าสีเติมแบบทึบให้แต่ละ series และเปิดใช้งานป้ายข้อมูล. สำหรับ series สุดท้ายเรายังเปลี่ยนสีฟอนต์ของป้ายด้วย

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### การบันทึก Presentation

`save` เขียน Presentation ไปยังไฟล์ในรูปแบบที่เลือก. เขียน Presentation ที่อัปเดตลงดิสก์ในรูปแบบ PPTX หรือส่งออกเป็น PDF หากต้องการ

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## ปัญหาทั่วไปและวิธีแก้

- **ไม่พบใบอนุญาต** – ตรวจสอบว่าเส้นทางไปยัง `license.lic` ถูกต้องและไฟล์สามารถอ่านได้.  
- **แผนภูมิแสดงเป็นสีขาว** – ตรวจสอบว่าคุณได้ล้าง series/categories ที่มีอยู่ก่อนเพิ่มใหม่.  
- **สีไม่ถูกต้อง** – ยืนยันว่า `FillType.Solid` ถูกตั้งค่าสำหรับทั้ง fill และ line format.  
- **ประสิทธิภาพกับ series จำนวนมาก** – จำกัดจำนวน series/categories หรือใช้เซลล์ workbook ซ้ำเพื่อควบคุมการใช้หน่วยความจำ.  

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างแผนภูมิ doughnut ได้โดยไม่ต้องมีไฟล์ PPTX ที่มีอยู่ก่อนหรือไม่?**  
A: ใช่, สร้าง `new Presentation()` เพื่อเริ่มจากชุดสไลด์เปล่า แล้วเพิ่มแผนภูมิตามที่แสดงด้านบน

**Q: Aspose.Slides รองรับการส่งออกเป็น PDF หรือไม่?**  
A: แน่นอน. หลังจากสร้างแผนภูมิแล้วเรียก `pres.save("output.pdf", SaveFormat.Pdf);` เพื่อรับเวอร์ชัน PDF ของสไลด์

**Q: ฉันจะเปลี่ยนขนาดของรู doughnut ได้อย่างไร?**  
A: ใช้ `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` โดยที่ `value` มีค่าตั้งแต่ 0 ถึง 100

**Q: สามารถเพิ่มป้ายข้อมูลให้กับทุก series ได้หรือไม่, ไม่ใช่แค่ series สุดท้าย?**  
A: ได้, ย้ายบล็อกการจัดรูปแบบป้ายออกจากเงื่อนไข `if (i == ...)` แล้วนำไปใช้กับแต่ละ `dataPoint`

**Q: เวอร์ชันของ Java ที่รองรับคืออะไร?**  
A: Aspose.Slides 25.4 รองรับ JDK 16 และใหม่กว่า. JDK รุ่นก่อนต้องใช้ classifier ที่เหมาะสมใน Maven dependency

---

**อัปเดตล่าสุด:** 2026-08-16  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides สำหรับ Java: คู่มือขั้นตอนต่อขั้นตอน](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [วิธีปรับแต่งสีแผนภูมิวงกลมใน Java ด้วย Aspose.Slides – คู่มือครบถ้วน](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [ทำแอนิเมชันให้ Categories ของแผนภูมิ PowerPoint ด้วย Aspose.Slides สำหรับ Java | คู่มือขั้นตอนต่อขั้นตอน](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}