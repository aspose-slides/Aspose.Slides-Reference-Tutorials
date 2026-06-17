---
date: '2026-06-03'
description: เรียนรู้วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides คู่มือนี้ครอบคลุมการพึ่งพา
  Maven, ขั้นตอนการสร้างแผนภูมิ, และการจัดการข้อมูล
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: สร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides

## วิธีสร้างแผนภูมิใน Java: บทนำ
การสร้างงานนำเสนอแบบไดนามิกมักเกี่ยวข้องกับการแสดงข้อมูลผ่านแผนภูมิ ด้วย **Aspose.Slides for Java** คุณสามารถ **สร้างแผนภูมิคอลัมน์แบบกลุ่ม** ได้อย่างง่ายดาย เพิ่มความชัดเจนและสร้างผลกระทบที่แข็งแกร่งต่อผู้ชมของคุณ บทแนะนำนี้จะพาคุณผ่านการตั้งค่าไลบรารี การเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม การจัดการซีรีส์ และการกลับค่าข้อมูลลบอย่างมีเงื่อนไข

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า Aspose.Slides for Java.
- ขั้นตอนในการ **สร้างแผนภูมิคอลัมน์แบบกลุ่ม** ในงานนำเสนอของคุณ.
- เทคนิคในการจัดการซีรีส์และจุดข้อมูลของแผนภูมิ.
- วิธีการกลับค่าจุดข้อมูลที่เป็นลบอย่างมีเงื่อนไขเพื่อการแสดงผลที่ดียิ่งขึ้น.
- วิธีบันทึกงานนำเสนออย่างปลอดภัย.

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ใช้คืออะไร?** Aspose.Slides for Java.  
- **ประเภทแผนภูมิที่แสดงคืออะไร?** แผนภูมิคอลัมน์แบบกลุ่ม.  
- **ฉันสามารถกลับค่าลบได้หรือไม่?** ใช่, โดยใช้ `invertIfNegative`.  
- **เวอร์ชัน Java ที่ต้องการคืออะไร?** JDK 16 หรือใหม่กว่า.  
- **ต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ใช่, ใบอนุญาต Aspose ที่ถูกต้อง.

## แผนภูมิคอลัมน์แบบกลุ่มคืออะไร?
แผนภูมิคอลัมน์แบบกลุ่มเป็นการแสดงผลที่จัดวางซีรีส์ข้อมูลหลายชุดเคียงกันสำหรับแต่ละประเภท ทำให้สามารถเปรียบเทียบได้อย่างรวดเร็วระหว่างกลุ่มต่าง ๆ เหมาะสำหรับรายงานการเงิน แดชบอร์ดการขาย และสถานการณ์ใด ๆ ที่ต้องการเปรียบเทียบหลายเมตริกพร้อมกัน

## ทำไมต้องใช้ Aspose.Slides สำหรับการสร้างแผนภูมิ?
Aspose.Slides ช่วยให้คุณสร้างและปรับแต่งแผนภูมิได้อย่างโปรแกรมเมติก ลดความจำเป็นในการแก้ไข PowerPoint ด้วยตนเอง รองรับ **รูปแบบเข้าและออกกว่า 70+** และสามารถประมวลผลงานนำเสนอที่มี **สูงสุด 10,000 สไลด์** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้ประสิทธิภาพสูงสำหรับการรายงานขนาดใหญ่

## ข้อกำหนดเบื้องต้น
1. **ไลบรารีที่ต้องการ**  
   - Aspose.Slides for Java (เวอร์ชัน 25.4 หรือใหม่กว่า).  

2. **สภาพแวดล้อม**  
   - JDK 16 หรือใหม่กว่า.  
   - Maven หรือ Gradle สำหรับการจัดการ dependencies.  

3. **ความรู้**  
   - การเขียนโปรแกรม Java เบื้องต้น.  
   - คุ้นเคยกับเครื่องมือสร้าง (Maven/Gradle).  

## การตั้งค่า Aspose.Slides สำหรับ Java
### การติดตั้ง Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การติดตั้ง Gradle
เพิ่มบรรทัดต่อไปนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การรับใบอนุญาต
- **ทดลองใช้ฟรี:** สำรวจคุณลักษณะโดยไม่ต้องใช้ใบอนุญาต.  
- **ใบอนุญาตชั่วคราว:** ใช้ระหว่างการประเมิน.  
- **ใบอนุญาตเต็ม:** ซื้อสำหรับการใช้งานในสภาพแวดล้อมการผลิต.

### การเริ่มต้นพื้นฐาน
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## วิธีเพิ่มแผนภูคอลัมน์แบบกลุ่มลงในสไลด์?
`Presentation` เป็นคลาสหลักที่แทนไฟล์ PowerPoint โหลด `Presentation` ใหม่ เพิ่มสไลด์ แล้วเรียก `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)` การเรียกเดียวนี้จะสร้างแผนภูคอลัมน์แบบกลุ่มที่ทำงานเต็มรูปแบบและวางที่พิกัดที่ระบุ คุณสามารถเข้าถึงอ็อบเจกต์แผนภูมิเพื่อแก้ไขซีรีส์ จุดข้อมูล และสไตล์ภาพได้

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: สร้าง Presentation และเพิ่มแผนภูคอลัมน์แบบกลุ่ม
`Presentation` แทนเอกสาร PowerPoint และอนุญาตให้สร้างสไลด์ได้  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### ขั้นตอนที่ 2: จัดการซีรีส์ของแผนภูมิ
ตอนนี้เราจะลบซีรีส์เริ่มต้นใด ๆ เพิ่มซีรีส์ใหม่ และใส่ค่าบวกและลบลงไป  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### ขั้นตอนที่ 3: กลับค่าจุดข้อมูลลบอย่างมีเงื่อนไข
เมธอด `invertIfNegative` เปิดใช้งานการกลับค่าลบในซีรีส์ของแผนภูมิ  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ลืมทำการ dispose วัตถุ `Presentation` หรือไม่?** ควรเรียก `dispose()` ในบล็อก `finally` เสมอเพื่อปล่อยทรัพยากรเนทีฟ.  
- **ค่าลบไม่แสดงเป็นการกลับค่า?** ตรวจสอบให้แน่ใจว่าคุณเรียก `invertIfNegative(true)` **หลังจาก** เพิ่มจุดข้อมูล.  
- **ปัญหาขนาดแผนภูมิ:** พิกัด (X, Y) และขนาด (width, height) มีหน่วยเป็น points; ปรับให้เหมาะกับการจัดวางสไลด์ของคุณ.  

## คำถามที่พบบ่อย

**ถาม:** ฉันสามารถสร้างประเภทแผนภูมิอื่นด้วยวิธีเดียวกันได้หรือไม่?  
**ตอบ:** ใช่, เพียงเปลี่ยน `ChartType.ClusteredColumn` เป็นค่า enum `ChartType` อื่น (เช่น `Line`, `Pie`).  

**ถาม:** ฉันต้องการใบอนุญาตสำหรับการสร้างเวอร์ชันพัฒนาไหม?  
**ตอบ:** จำเป็นต้องมีใบอนุญาตชั่วคราวหรือประเมินเพื่อเข้าถึงคุณลักษณะทั้งหมด; หากไม่มี ไลบรารีจะทำงานในโหมดทดลองพร้อมข้อจำกัดของลายน้ำ.  

**ถาม:** ฉันจะส่งออกงานนำเสนอเป็น PDF หลังจากเพิ่มแผนภูมิได้อย่างไร?  
**ตอบ:** `SaveFormat.Pdf` ระบุ PDF เป็นรูปแบบการบันทึกสำหรับการบันทึกงานนำเสนอ. ใช้ `pres.save("output.pdf", SaveFormat.Pdf);` หลังจากที่คุณทำการจัดการแผนภูมิเสร็จ.  

**ถาม:** สามารถกำหนดสไตล์ให้คอลัมน์แต่ละคอลัมน์ได้หรือไม่ (สี, เส้นขอบ)?  
**ตอบ:** `IChartDataPoint` แทนจุดข้อมูลเดียวในแผนภูมิและอนุญาตให้จัดรูปแบบ แต่ละ `IChartDataPoint` มีตัวเลือกเช่น `getFillFormat().setFillType(FillType.Solid)` และ `getLineFormat()`.  

**ถาม:** ถ้าฉันต้องอัปเดตข้อมูลแผนภูมิหลังจากบันทึกงานนำเสนอแล้วจะทำอย่างไร?  
**ตอบ:** โหลดงานนำเสนอใหม่ด้วย `new Presentation("file.pptx")`, แก้ไขข้อมูลแผนภูมิ, แล้วบันทึกใหม่.  

---

**อัปเดตล่าสุด:** 2026-06-03  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างแผนภูมิคอลัมน์แบบซ้อนใน Java ด้วย Aspose.Slides – คู่มือเชิงลึก](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides – การสร้างและตรวจสอบแผนภูมิอย่างเชี่ยวชาญ](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [สร้างและจัดรูปแบบแผนภูมิใน Java ด้วย Aspose.Slides: คู่มือเชิงลึก](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}