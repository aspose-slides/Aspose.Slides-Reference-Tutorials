---
date: '2026-03-07'
description: เรียนรู้วิธีสร้างแผนภูมิโดนัทใน Java ด้วย Aspose.Slides คู่มือขั้นตอนต่อขั้นตอนนี้ครอบคลุมการตั้งค่า
  dependency ของ Maven Aspose Slides การกำหนดค่าแผนภูมิ และการบันทึกงานนำเสนอ
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: สร้างแผนภูมิโดนัทใน Java ด้วย Aspose.Slides คู่มือ
url: /th/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิ Doughnut ด้วย Java และ Aspose.Slides Guide

## บทนำ

การสร้าง **แผนภูมิ doughnut** อย่างอัตโนมัติสามารถเปลี่ยนตัวเลขดิบให้เป็นภาพที่ดึงดูดสายตาและบอกเล่าเรื่องราวได้ทันที ใน Java, **Aspose.Slides** ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณสร้างแผนภูมิพร้อมใช้ในงานนำเสนอได้โดยไม่ต้องเปิด PowerPoint ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **สร้างแผนภูมิ doughnut ด้วย Java** อย่างเป็นขั้นตอน ตั้งแต่การตั้งค่า Maven Aspose Slides ไปจนถึงการปรับแต่ง series, categories และสุดท้ายการบันทึกงานนำเสนอ

เมื่อจบคู่มือนี้ คุณจะสามารถฝังแผนภูมิ doughnut แบบไดนามิกลงในไฟล์ PPTX ใด ๆ ได้อย่างสมบูรณ์ เหมาะสำหรับรายงาน, แดชบอร์ด หรือสไลด์เด็คอัตโนมัติ

### คำตอบสั้น
- **ใช้ไลบรารีอะไร?** Aspose.Slides for Java  
- **ภารกิจหลัก?** สร้างแผนภูมิ doughnut ในไฟล์ PPTX  
- **เพิ่มไลบรารีอย่างไร?** ใช้ Maven Aspose Slides dependency (หรือ Gradle)  
- **เวอร์ชัน Java ขั้นต่ำ?** JDK 16 หรือใหม่กว่า  
- **ปรับสีและป้ายกำกับได้หรือไม่?** ได้, API มีการควบคุมการจัดรูปแบบเต็มรูปแบบ  

## แผนภูมิ Doughnut คืออะไรและทำไมต้องใช้?

แผนภูมิ doughnut เป็นรูปแบบหนึ่งของแผนภูมิพายที่มีศูนย์ว่าง ทำให้คุณสามารถแสดงหลาย series ของข้อมูลในวงแหวนศูนย์กลางได้ ซึ่งเหมาะอย่างยิ่งสำหรับการเปรียบเทียบส่วนต่าง ๆ ของทั้งหมดในหลายหมวดหมู่ — เช่น ยอดขายตามภูมิภาคในหลายไตรมาส หรือการจัดสรรงบประมาณตามแผนกต่าง ๆ  

## ทำไมต้องใช้ Aspose.Slides for Java?

- **ไม่ต้องติดตั้ง Office** – สร้างไฟล์ PPTX บนเซิร์ฟเวอร์ใดก็ได้  
- **API ครบถ้วน** – ควบคุมประเภทแผนภูมิ, จุดข้อมูล, และการจัดรูปแบบได้เต็มที่  
- **ประสิทธิภาพสูง** – ปรับให้ทำงานได้ดีกับงานนำเสนอขนาดใหญ่  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS  

## ข้อกำหนดเบื้องต้น

- **ไลบรารีที่ต้องการ:**  
  - Aspose.Slides for Java เวอร์ชัน 25.4 หรือใหม่กว่า  

- **การตั้งค่าสภาพแวดล้อม:**  
  - JDK 16 หรือใหม่กว่า  
  - IDE ที่คุณชื่นชอบ (IntelliJ IDEA, Eclipse, NetBeans ฯลฯ)  

- **ความรู้เบื้องต้นที่จำเป็น:**  
  - การเขียนโปรแกรม Java เบื้องต้น  
  - ความคุ้นเคยกับ Maven หรือ Gradle สำหรับการจัดการ dependency  

## Maven Aspose Slides Dependency

เพิ่ม dependency ของ Maven ด้านล่างนี้ลงในไฟล์ `pom.xml` ของคุณ นี่คือ **maven aspose slides dependency** ที่จำเป็นสำหรับดึงไลบรารีเข้ามาในโปรเจกต์

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

หากคุณใช้ Gradle ให้ใช้โค้ดสคริปต์ที่เทียบเท่าด้านล่าง

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

คุณยังสามารถดาวน์โหลด JAR โดยตรงจากหน้าปล่อยอย่างเป็นทางการได้เช่นกัน:  
[ การปล่อย Aspose.Slides สำหรับ Java ](https://releases.aspose.com/slides/java/)

### การรับใบอนุญาต

เพื่อเอาเครื่องหมายลายน้ำการประเมินผลออกและเปิดใช้งานคุณสมบัติเต็มรูปแบบ:

- **ทดลองใช้ฟรี** – เริ่มต้นด้วยใบอนุญาตชั่วคราว  
- **ใบอนุญาตชั่วคราว** – ขอรับจาก [เว็บไซต์ Aspose](https://purchase.aspose.com/temporary-license/)  
- **ใบอนุญาตเชิงพาณิชย์** – ซื้อเพื่อใช้งานในระบบผลิตจริง  

ใช้ใบอนุญาตในโค้ดของคุณ:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## คู่มือการดำเนินการ

### การเริ่มต้น Presentation และการเพิ่มแผนภูมิ Doughnut

แรกเริ่ม สร้างหรือโหลดงานนำเสนอและเพิ่มแผนภูมิ doughnut ลงในสไลด์แรก

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### การกำหนดค่า Workbook ของข้อมูลแผนภูมิและการลบข้อมูลเดิม

ต่อไป ดึง workbook ที่เป็นฐานของแผนภูมิและลบ series หรือ categories ที่เป็นค่าเริ่มต้นออกทั้งหมด

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### การเพิ่ม Series ลงในแผนภูมิ

ต่อไปเราจะเพิ่มสูงสุด 15 series แต่ละ series สามารถปรับแต่งได้ — ตัวอย่างนี้ตั้งค่า explosion, ขนาดรูของ doughnut, และมุมของสไลซ์แรก

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

### การเพิ่ม Categories และ Data Points

เราจะสร้าง 15 categories และเติมข้อมูลให้แต่ละ series ด้วย data point series สุดท้ายจะได้รับการจัดรูปแบบป้ายกำกับพิเศษ

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

### การบันทึก Presentation

สุดท้าย เขียนงานนำเสนอที่อัปเดตแล้วลงดิสก์

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## ปัญหาที่พบบ่อยและวิธีแก้

- **ไม่พบใบอนุญาต** – ตรวจสอบว่าเส้นทางไปยัง `license.lic` ถูกต้องและไฟล์สามารถอ่านได้  
- **แผนภูมิเกิดเป็นสีขาว** – ตรวจสอบว่าคุณได้ลบ series/category เดิมก่อนเพิ่มใหม่หรือไม่  
- **สีไม่ถูกต้อง** – ตรวจสอบว่าได้ตั้งค่า `FillType.Solid` ทั้งสำหรับ fill และ line format แล้ว  
- **ประสิทธิภาพเมื่อมี series จำนวนมาก** – จำกัดจำนวน series/category หรือใช้เซลล์ workbook ซ้ำกัน  

## คำถามที่พบบ่อย

**ถาม: สามารถสร้างแผนภูมิ doughnut โดยไม่มีไฟล์ PPTX ที่มีอยู่ก่อนหรือไม่?**  
ตอบ: ได้, ใช้ `new Presentation()` เพื่อเริ่มจากสไลด์เปล่า  

**ถาม: Aspose.Slides รองรับการส่งออกเป็น PDF หรือไม่?**  
ตอบ: แน่นอน หลังจากสร้างแผนภูมิแล้วเรียก `pres.save("output.pdf", SaveFormat.Pdf);`  

**ถาม: จะเปลี่ยนขนาดรูของ doughnut อย่างไร?**  
ตอบ: ใช้ `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` โดยที่ value มีค่า 0‑100  

**ถาม: สามารถเพิ่มป้ายกำกับข้อมูลให้กับทุก series ไม่ใช่แค่ series สุดท้ายได้หรือ?**  
ตอบ: ได้, ย้ายบล็อกการจัดรูปแบบป้ายกำกับออกจากเงื่อนไข `if (i == ...)` แล้วนำไปใช้กับแต่ละ `dataPoint`  

**ถาม: รองรับเวอร์ชัน Java ใดบ้าง?**  
ตอบ: Aspose.Slides 25.4 รองรับ JDK 16 ขึ้นไป เวอร์ชัน JDK ที่เก่ากว่าต้องใช้ classifier ที่เหมาะสม  

---

**อัปเดตล่าสุด:** 2026-03-07  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}