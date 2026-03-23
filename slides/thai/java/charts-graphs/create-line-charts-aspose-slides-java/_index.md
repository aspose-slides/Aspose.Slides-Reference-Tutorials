---
date: '2026-03-23'
description: เรียนรู้วิธีใช้ Aspose.Slides for Java เพื่อสร้างแผนภูมิเส้นพร้อมเครื่องหมาย
  เพิ่มชุดข้อมูลที่สอง และจัดการข้อมูลที่เป็นค่า null ในงานนำเสนอ PowerPoint
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'วิธีใช้ Aspose.Slides สำหรับ Java: สร้างแผนภูมิเส้นพร้อมเครื่องหมายเริ่มต้น'
url: /th/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิเส้นด้วยเครื่องหมายเริ่มต้นโดยใช้ Aspose.Slides for Java

## บทนำ
หากคุณกำลังสงสัย **วิธีใช้ Aspose** เพื่ออัตโนมัติการสร้าง PowerPoint คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายการสร้าง **แผนภูมิเส้นพร้อมเครื่องหมาย**, การเพิ่มชุดข้อมูลที่สอง, และการจัดการข้อมูล null — ทั้งหมดด้วย Aspose.Slides for Java เมื่อเสร็จคุณจะได้โค้ดสั้นที่พร้อมรันซึ่งสร้างแผนภูมิดูเป็นมืออาชีพโดยไม่ต้องเปิด PowerPoint ด้วยตนเอง

### คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Slides for Java (แนะนำให้ใช้เวอร์ชันล่าสุด)  
- **สามารถเพิ่มชุดข้อมูลที่สองได้หรือไม่?** ได้ – API อนุญาตให้เพิ่มหลายชุดข้อมูลได้อย่างง่ายดาย  
- **จุดข้อมูล null จะถูกจัดการอย่างไร?** ใช้ `null` ในค่าของเซลล์; แผนภูมิจะข้ามจุดนั้นไป  
- **ต้องใช้ Maven หรือไม่?** ทั้ง Maven และ Gradle ทำงานได้; ดูส่วน *aspose slides maven* ด้านล่าง  
- **ต้องมีลิขสิทธิ์หรือไม่?** ทดลองใช้ฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง

## วิธีใช้ Aspose.Slides for Java เพื่อสร้างแผนภูมิเส้น
การสร้างแผนภูมิโดยโปรแกรมช่วยคุณประหยัดเวลาหลายชั่วโมงจากการจัดรูปแบบด้วยตนเองและรับประกันความสอดคล้องในทุกงานนำเสนอ ไม่ว่าคุณจะสร้างฟีเจอร์ **create powerpoint chart** ในเครื่องมือรายงานหรือสร้างสไลด์เด็คแบบอัตโนมัติ Aspose.Slides ให้คุณควบคุมทั้งหมดจากโค้ด Java

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนาของคุณพร้อม:

1. **ไลบรารีและการพึ่งพา**
   - ไลบรารี Aspose.Slides for Java (แนะนำเวอร์ชัน 25.4) – ครอบคลุมสถานการณ์ *aspose slides maven*  
   - Java Development Kit (JDK) เวอร์ชัน 16 หรือสูงกว่า
2. **การตั้งค่าสภาพแวดล้อม**
   - IDE ที่รองรับ Maven หรือ Gradle  
   - ไฟล์ลิขสิทธิ์ Aspose ที่ถูกต้อง หากคุณต้องการรันโค้ดนอกโหมดทดลอง
3. **ความรู้พื้นฐานที่ต้องมี**
   - การเขียนโปรแกรม Java เบื้องต้น  
   - ความคุ้นเคยกับไฟล์ build ของ Maven หรือ Gradle

## การตั้งค่า Aspose.Slides for Java
### Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
ใส่โค้ดต่อไปนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

**ขั้นตอนการรับลิขสิทธิ์:**
- สำหรับการทดลองฟรี ให้เยี่ยมชม [free trial page](https://releases.aspose.com/slides/java/)  
- เพื่อรับลิขสิทธิ์ชั่วคราว ให้ไปที่ [temporary license page](https://purchase.aspose.com/temporary-license/)  
- ซื้อลิขสิทธิ์เต็มรูปแบบผ่าน [purchase portal](https://purchase.aspose.com/buy)

**การเริ่มต้นพื้นฐาน:**
ต่อไปนี้เป็นวิธีการเริ่มต้น Aspose.Slides ในแอปพลิเคชัน Java ของคุณ:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

ตอนนี้มาเริ่มสร้างแผนภูมิกันเลย!

## คู่มือการทำงาน
### ฟีเจอร์ 1: การสร้างแผนภูมิกับเครื่องหมายเริ่มต้น
ส่วนนี้จะแสดงวิธีสร้าง **แผนภูมิเส้นพร้อมเครื่องหมาย** ซึ่งเหมาะสำหรับการเน้นจุดข้อมูลแต่ละจุดบนเส้นแนวโน้ม

#### การเพิ่มแผนภูมิเส้น
เพื่อเพิ่มแผนภูมิเส้นพร้อมเครื่องหมาย:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### การล้างชุดข้อมูลและหมวดหมู่
เพื่อเริ่มต้นใหม่:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### ฟีเจอร์ 2: การเพิ่มชุดข้อมูลและหมวดหมู่
การเพิ่มชุดข้อมูลและหมวดหมู่เป็นสิ่งสำคัญสำหรับการเติมข้อมูลที่มีความหมายให้กับแผนภูมิของคุณ

#### การสร้างชุดข้อมูลใหม่
เพื่อเพิ่มชุดข้อมูลใหม่ชื่อ "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### การเติมหมวดหมู่และจุดข้อมูล
เพื่อเพิ่มหมวดหมู่และจุดข้อมูลที่สอดคล้องกัน:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### ฟีเจอร์ 3: การเพิ่มชุดข้อมูลที่สองและเติมจุดข้อมูล
การเพิ่มชุดข้อมูลเพิ่มเติมช่วยให้การวิเคราะห์ภาพของคุณลึกซึ้งยิ่งขึ้น

#### การสร้างและเติมชุดข้อมูลที่สอง
เพื่อเพิ่ม "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### ฟีเจอร์ 4: การกำหนดค่าตัวอธิบายแผนภูมิ
การกำหนดค่าตัวอธิบายช่วยเพิ่มความอ่านง่ายของแผนภูมิ โดยเฉพาะเมื่อคุณ **เพิ่มชุดข้อมูลที่สอง**

#### การปรับตั้งค่าตัวอธิบาย
เพื่อกำหนดค่า:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### ฟีเจอร์ 5: การบันทึกงานนำเสนอ
เมื่อแผนภูมิของคุณพร้อมแล้ว คุณจะต้อง **create powerpoint chart** ไฟล์ที่สามารถแชร์หรือแก้ไขต่อได้

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## การประยุกต์ใช้งานจริง
1. **รายงานธุรกิจ:** ใช้แผนภูมิเส้นพร้อมเครื่องหมายเพื่อแสดงแนวโน้มการเงินตามไตรมาส  
2. **การวิเคราะห์ข้อมูล:** แสดงข้อมูลการทดลองที่แต่ละเครื่องหมายเน้นจุดวัดผล  
3. **สื่อการศึกษา:** สร้างสไลด์บรรยายที่แสดงการเปลี่ยนแปลงขั้นตอนต่อขั้นตอนของกระบวนการ  
4. **การจัดการโครงการ:** ติดตามมิลสโตนบนไทม์ไลน์ด้วยเครื่องหมายที่ชัดเจนสำหรับวันที่สำคัญ  
5. **การนำเสนอการตลาด:** แสดงจุดพุ่งของแคมเปญด้วยสัญลักษณ์เครื่องหมายที่เด่นชัด

## ปัญหาที่พบบ่อยและวิธีแก้
- **จุดข้อมูล null ทำให้เกิดข้อผิดพลาด:** ส่ง `null` เป็นค่าของเซลล์ (ตามตัวอย่าง) – Aspose จะละเว้นจุดนั้นโดยอัตโนมัติ  
- **แผนภูมิเกิดขึ้นโดยไม่มีเครื่องหมาย:** ตรวจสอบให้ใช้ `ChartType.LineWithMarkers` แทน `ChartType.Line`  
- **ตัวอธิบายทับข้อมูล:** ตั้งค่า `chart.getLegend().setOverlay(false)` เพื่อให้ตัวอธิบายแยกจากข้อมูล

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้วิธีนี้สร้างแผนภูมิในเว็บเซอร์วิสได้หรือไม่?**  
ตอบ: ได้เลย ไลบรารีทำงานได้ในสภาพแวดล้อม Java ใด ๆ รวมถึงแอปพลิเคชันฝั่งเซิร์ฟเวอร์

**ถาม: ต้องมีลิขสิทธิ์สำหรับการสร้างบิลด์การพัฒนาไหม?**  
ตอบ: การทดลองฟรีใช้ได้สำหรับการพัฒนาและทดสอบ แต่ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง

**ถาม: Aspose จัดการกับชุดข้อมูลขนาดใหญ่อย่างไร?**  
ตอบ: API สตรีมข้อมูลอย่างมีประสิทธิภาพ; อย่างไรก็ตามควรจำกัดจำนวนจุดข้อมูลเพื่อหลีกเลี่ยงไฟล์ขนาดใหญ่

**ถาม: มีการสนับสนุนประเภทแผนภูมิอื่น ๆ หรือไม่?**  
ตอบ: มี – Aspose.Slides รองรับแผนภูมิแท่ง, พาย, กระจาย และอื่น ๆ อีกหลายประเภท

**ถาม: สามารถปรับแต่งรูปแบบและสีของเครื่องหมายได้หรือไม่?**  
ตอบ: สามารถแก้ไขรูปแบบเครื่องหมายได้ผ่านคุณสมบัติ `Marker` ของแต่ละจุดข้อมูล

## สรุป
คุณได้เรียนรู้ **วิธีใช้ Aspose** เพื่อสร้างแผนภูมิเส้นพร้อมเครื่องหมายเริ่มต้น, เพิ่มชุดข้อมูลที่สอง, จัดการข้อมูล null, และบันทึกผลลัพธ์เป็นไฟล์ PowerPoint เทคนิคเหล่านี้ช่วยให้คุณอัตโนมัติการสร้างรายงาน, ปรับปรุงการเล่าเรื่องข้อมูล, และรักษาความสอดคล้องของการนำเสนอ

สำหรับการเรียนรู้เพิ่มเติม สำรวจ [official documentation](https://docs.aspose.com/slides/java/) หรือเข้าร่วมฟอรั่มชุมชนเช่น Stack Overflow

---

**Last Updated:** 2026-03-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}