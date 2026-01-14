---
date: '2026-01-14'
description: เรียนรู้วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides คู่มือทีละขั้นตอนที่ครอบคลุมการสร้างงานนำเสนอเปล่า
  การเพิ่มแผนภูมิลงในงานนำเสนอ และการจัดการซีรีส์
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เชี่ยวชาญการสร้างแผนภูมิใน Java ด้วย Aspose.Slides

## วิธีสร้างและจัดการแผนภูมิด้วย Aspose.Slides for Java

### บทนำ
การสร้างงานนำเสนอแบบไดนามิกมักเกี่ยวข้องกับการแสดงข้อมูลผ่านแผนภูมิ  
ด้วย **Aspose.Slides for Java** คุณสามารถ **สร้างแผนภูมิคอลัมน์แบบกลุ่ม** ได้อย่างง่ายดายและจัดการประเภทแผนภูมิต่าง ๆ เพื่อเพิ่มความชัดเจนและผลกระทบ  
บทเรียนนี้จะนำคุณผ่านขั้นตอนการสร้างงานนำเสนอเปล่า, การเพิ่มแผนภูคิคอลัมน์แบบกลุ่ม, การจัดการซีรีส์, และการปรับแต่งการกลับค่าจุดข้อมูล—ทั้งหมดโดยใช้ Aspose.Slides for Java  

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่า Aspose.Slides for Java
- ขั้นตอนในการ **สร้างงานนำเสนอเปล่า** และเพิ่มแผนภูมิลงในงานนำเสนอ
- เทคนิคการจัดการซีรีส์และจุดข้อมูลของแผนภูมิอย่างมีประสิทธิภาพ
- วิธีการกลับค่าจุดข้อมูลเชิงลบตามเงื่อนไขเพื่อการแสดงผลที่ดียิ่งขึ้น
- วิธีบันทึกงานนำเสนออย่างปลอดภัย  

มาดูข้อกำหนดเบื้องต้นก่อนที่เราจะเริ่มกัน

## คำตอบอย่างรวดเร็ว
- **คลาสหลักที่เริ่มต้นคืออะไร?** `Presentation` จาก `com.aspose.slides`
- **ประเภทแผนภูมิใดที่สร้างแผนภูมิคอลัมน์แบบกลุ่ม?** `ChartType.ClusteredColumn`
- **คุณเพิ่มแผนภูมิลงในสไลด์อย่างไร?** ใช้ `addChart()` บนคอลเลกชันรูปร่างของสไลด์
- **คุณสามารถกลับค่าติดลบได้หรือไม่?** ใช่, ด้วย `invertIfNegative(true)` บนจุดข้อมูล
- **ต้องการเวอร์ชันใด?** Aspose.Slides for Java 25.4 หรือใหม่กว่า

## แผนภูมิคอลัมน์แบบกลุ่มคืออะไร?
แผนภูมิคอลัมน์แบบกลุ่มจะแสดงหลายซีรีส์ของข้อมูลเคียงข้างกันสำหรับแต่ละหมวดหมู่ ทำให้เหมาะสำหรับการเปรียบเทียบค่าระหว่างกลุ่มต่าง ๆ Aspose.Slides ช่วยให้คุณสร้างแผนภูมินี้โดยโปรแกรมโดยไม่ต้องเปิด PowerPoint

## ทำไมต้องใช้ Aspose.Slides for Java เพื่อเพิ่มแผนภูมิลงในงานนำเสนอ?
- **การควบคุมเต็มรูปแบบ** บนข้อมูลแผนภูมิ, รูปลักษณ์, และการจัดวาง
- **ไม่ต้องติดตั้ง Office** บนเซิร์ฟเวอร์
- **รองรับแผนภูมิหลักทั้งหมด** รวมถึงแผนภูมิคอลัมน์แบบกลุ่ม
- **การผสานรวมง่าย** กับการสร้างด้วย Maven/Gradle

## ข้อกำหนดเบื้องต้น
ก่อนคุณเริ่ม, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **ไลบรารีที่ต้องการ:**
   - Aspose.Slides for Java (เวอร์ชัน 25.4 หรือใหม่กว่า)

2. **ข้อกำหนดการตั้งค่าสภาพแวดล้อม:**
   - เวอร์ชัน JDK ที่เข้ากันได้ (เช่น JDK 16)
   - ติดตั้ง Maven หรือ Gradle หากคุณต้องการจัดการ dependencies

3. **ความรู้เบื้องต้นที่ต้องมี:**
   - ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java
   - ความคุ้นเคยกับการจัดการ dependencies ในสภาพแวดล้อมการพัฒนาของคุณ

## การตั้งค่า Aspose.Slides for Java
เพื่อเริ่มใช้ Aspose.Slides, ทำตามขั้นตอนต่อไปนี้:

**Maven Installation:**  
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle Installation:**  
Add the following line to your `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การรับใบอนุญาต
- **ทดลองใช้ฟรี:** คุณสามารถเริ่มด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณลักษณะ  
- **ใบอนุญาตชั่วคราว:** รับใบอนุญาตชั่วคราวเพื่อเข้าถึงเต็มที่ในช่วงระยะเวลาการประเมิน  
- **ซื้อ:** พิจารณาซื้อหากพบว่าตรงกับความต้องการระยะยาวของคุณ  

### การเริ่มต้นพื้นฐาน
Below is the minimal code required to create a new presentation instance:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## คู่มือการดำเนินการ
ตอนนี้, เราจะแบ่งแต่ละฟีเจอร์ออกเป็นขั้นตอนที่จัดการได้

### การสร้างงานนำเสนอพร้อมแผนภูมิคอลัมน์แบบกลุ่ม
#### ภาพรวม
ส่วนนี้จะแสดงวิธี **สร้างงานนำเสนอเปล่า**, เพิ่ม **แผนภูมิคอลัมน์แบบกลุ่ม**, และวางตำแหน่งบนสไลด์แรก  

**ขั้นตอน:**
1. **เริ่มต้นอ็อบเจ็กต์ Presentation** – สร้าง `Presentation` ใหม่
2. **เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม** – เรียก `addChart()` พร้อมประเภทและขนาดที่เหมาะสม  

**ตัวอย่างโค้ด:**
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

### การจัดการซีรีส์ของแผนภูมิ
#### ภาพรวม
เรียนรู้วิธีลบซีรีส์เริ่มต้น, เพิ่มซีรีส์ใหม่, และเติมค่าบวกและลบลงในซีรีส์  

**ขั้นตอน:**
1. **ลบซีรีส์ที่มีอยู่** – เอาข้อมูลที่เติมไว้ล่วงหน้าออก
2. **เพิ่มซีรีส์ใหม่** – ใช้เซลล์ใน workbook เป็นชื่อซีรีส์
3. **แทรกจุดข้อมูล** – เพิ่มค่า, รวมถึงค่าติดลบ, เพื่อแสดงการกลับค่าในภายหลัง  

**ตัวอย่างโค้ด:**
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

### การกลับค่าจุดข้อมูลของซีรีส์ตามเงื่อนไข
#### ภาพรวม
โดยค่าเริ่มต้น, Aspose.Slides อาจกลับค่าติดลบ คุณสามารถควบคุมพฤติกรรมนี้ได้ทั่วโลกและต่อจุดข้อมูล  

**ขั้นตอน:**
1. **ตั้งค่าการกลับค่าทั่วโลก** – ปิดการกลับค่าอัตโนมัติสำหรับซีรีส์ทั้งหมด
2. **ใช้การกลับค่าตามเงื่อนไข** – เปิดการกลับค่าเฉพาะจุดติดลบที่ต้องการ  

**ตัวอย่างโค้ด:**
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

### ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| แผนภูมิแสดงเป็นสีขาวเปล่า | ตรวจสอบให้แน่ใจว่าดัชนีสไลด์ (`0`) มีอยู่และขนาดแผนภูมิอยู่ภายในขอบเขตของสไลด์ |
| ค่าติดลบไม่ถูกกลับค่า | ตรวจสอบว่าได้ตั้งค่า `invertIfNegative(false)` บนซีรีส์และ `invertIfNegative(true)` บนจุดข้อมูลที่เฉพาะเจาะจง |
| ข้อยกเว้นใบอนุญาต | ใช้ใบอนุญาต Aspose ที่ถูกต้องก่อนสร้างอ็อบเจ็กต์ `Presentation` |

## คำถามที่พบบ่อย

**Q: ฉันสามารถเพิ่มประเภทแผนภูมิอื่น ๆ นอกจากแผนภูมิคอลัมน์แบบกลุ่มได้หรือไม่?**  
A: ใช่, Aspose.Slides รองรับแผนภูมิเส้น, พาย, แถบ, พื้นที่, และประเภทแผนภูมิอื่น ๆ อีกมากมาย.

**Q: ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?**  
A: การทดลองใช้ฟรีทำงานสำหรับการประเมิน, แต่ต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์จริง.

**Q: ฉันจะส่งออกแผนภูมิเป็นภาพอย่างไร?**  
A: ใช้ `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` หลังจากทำการเรนเดอร์.

**Q: สามารถจัดรูปแบบแผนภูมิ (สี, ฟอนต์) ได้หรือไม่?**  
A: แน่นอน. แต่ละ `IChartSeries` และ `IChartDataPoint` มีคุณสมบัติการจัดรูปแบบให้ใช้.

**Q: ถ้าฉันต้องการเพิ่มแผนภูมิลงในไฟล์ PPTX ที่มีอยู่แล้วทำอย่างไร?**  
A: โหลดไฟล์ด้วย `new Presentation("existing.pptx")`, แล้วเพิ่มแผนภูมิลงในสไลด์ที่ต้องการ.

## สรุป
ในบทเรียนนี้, คุณได้เรียนรู้วิธี **สร้างแผนภูคิคอลัมน์แบบกลุ่ม** ใน Java, จัดการซีรีส์, และกลับค่าติดลบตามเงื่อนไขโดยใช้ Aspose.Slides. ด้วยเทคนิคเหล่านี้, คุณสามารถสร้างงานนำเสนอที่ขับเคลื่อนด้วยข้อมูลได้อย่างมีประสิทธิภาพโดยโปรแกรม

**ขั้นตอนต่อไป:**
- ทดลองใช้ประเภทแผนภูมิอื่น ๆ ที่ Aspose.Slides for Java มีให้  
- ศึกษาตัวเลือกการจัดรูปแบบขั้นสูง เช่น สีที่กำหนดเอง, ป้ายข้อมูล, และการจัดรูปแบบแกน  
- ผสานการสร้างแผนภูมิเข้าสู่กระบวนการรายงานหรือการวิเคราะห์ของคุณ  

---

**อัปเดตล่าสุด:** 2026-01-14  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}