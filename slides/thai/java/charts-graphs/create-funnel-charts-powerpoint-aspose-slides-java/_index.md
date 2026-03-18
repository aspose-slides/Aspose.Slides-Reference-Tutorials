---
date: '2026-03-18'
description: เรียนรู้การสร้างภาพข้อมูลด้วย Java โดยการสร้างแผนภูมิกรวยใน PowerPoint
  ด้วย Aspose.Slides for Java คู่มือแบบขั้นตอนนี้จะแสดงวิธีสร้างแผนภูมิกรวย ตั้งค่าข้อมูลแผนภูมิ
  และปรับแต่งสี
keywords:
- funnel chart creation
- Aspose.Slides for Java
- PowerPoint data visualization
title: การแสดงข้อมูลด้วย Java – แผนภูมิกรวยกับ Aspose.Slides
url: /th/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างแผนภูมิ Funnel อย่างเชี่ยวชาญใน PowerPoint ด้วย Aspose.Slides for Java

## บทนำ
การสร้างงานนำเสนอที่น่าสนใจเป็นศิลปะที่ผสานการแสดงผลข้อมูล การออกแบบ และการเล่าเรื่องเข้าด้วยกัน เครื่องมือที่ทรงพลังหนึ่งที่ช่วยยกระดับงานนำเสนอของคุณคือแผนภูมิ Funnel — การแสดงภาพขั้นตอนต่าง ๆ ภายในกระบวนการหรือท่อขาย ไม่ว่าคุณจะนำเสนอรายงานธุรกิจ ไทม์ไลน์โครงการ หรือกลยุทธ์การขาย การใส่แผนภูมิ Funnel จะทำให้ข้อมูลดิบกลายเป็นเรื่องราวที่มีความหมาย

ในบทแนะนำนี้ เราจะสำรวจวิธีการสร้างและปรับแต่งแผนภูมิ Funnel ใน PowerPoint ด้วย Aspose.Slides for Java คุณจะได้เรียนรู้ขั้นตอนตั้งค่าแวดล้อม การเพิ่มแผนภูมิ Funnel ลงในสไลด์ การกำหนดข้อมูลของแผนภูมิ และการบันทึกงานนำเสนออย่างง่ายดาย หลังจากอ่านจบคุณจะพร้อมใช้ภาพกราฟิกระดับมืออาชีพเพื่อเสริมงานนำเสนอของคุณ

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides for Java ในโปรเจกต์ของคุณ
- การสร้างอินสแตนซ์ของงานนำเสนอ PowerPoint
- การเพิ่มและปรับแต่งแผนภูมิ Funnel บนสไลด์
- การจัดการข้อมูลแผนภูมิอย่างมีประสิทธิภาพ
- การบันทึกและส่งออกงานนำเสนอที่ได้รับการปรับปรุง

## คำตอบอย่างรวดเร็ว
- **ไลบรารีหลักสำหรับการแสดงผลข้อมูลใน Java คืออะไร?** Aspose.Slides for Java  
- **จะสร้างแผนภูมิ Funnel ใน PowerPoint อย่างไร?** ใช้ `addChart(ChartType.Funnel, …)` บนสไลด์  
- **เมธอดใดที่ตั้งค่าแหล่งข้อมูลของแผนภูมิ?** ทำงานกับ `IChartDataWorkbook` และ `chart.getChartData()`  
- **สามารถปรับสีของแต่ละส่วนของ Funnel ได้หรือไม่?** ได้, ตั้งค่า `FillType.Solid` และกำหนด `java.awt.Color` ที่สุ่มหรือเจาะจง  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose.Slides ที่ซื้อสำหรับการใช้งานเชิงพาณิชย์

## Java data visualization คืออะไร?
Java data visualization หมายถึงเทคนิคและไลบรารีที่ช่วยให้นักพัฒนาสามารถแปลงข้อมูลดิบให้เป็นภาพที่ชัดเจน, อินเทอร์แอคทีฟ หรือสถิติโดยตรงจากแอปพลิเคชัน Java Aspose.Slides for Java เป็นไลบรารีชั้นนำสำหรับการสร้างแผนภูมิ, ไดอะแกรม, และงานนำเสนอที่สมบูรณ์แบบโดยอัตโนมัติ

## ทำไมต้องใช้แผนภูมิ Funnel ใน PowerPoint?
แผนภูมิ Funnel ทำให้การแสดงอัตราการสูญเสียระหว่างขั้นตอนได้ง่าย — เหมาะสำหรับท่อขาย, ฟันเนลการแปลง, หรือการวิเคราะห์ประสิทธิภาพกระบวนการ ด้วย Aspose.Slides คุณจะได้ควบคุมการจัดวาง, สี, และข้อมูลได้เต็มที่โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง

## ข้อกำหนดเบื้องต้น (H2)
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมีเครื่องมือและความรู้ที่จำเป็นเพื่อทำตามบทแนะนำนี้

### ไลบรารีที่จำเป็น, เวอร์ชัน, และการพึ่งพา
เพื่อใช้งาน Aspose.Slides for Java ในโปรเจกต์ของคุณ, คุณต้องระบุเวอร์ชันของไลบรารีที่เหมาะสม ด้านล่างเป็นวิธีการตั้งค่าผ่าน Maven หรือ Gradle:

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หรือคุณสามารถดาวน์โหลดไลบรารีโดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)  

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าพัฒนาสภาพแวดล้อมของคุณมี JDK 1.6 หรือสูงกว่า เนื่องจาก Aspose.Slides ต้องการเวอร์ชันนี้เพื่อความเข้ากันได้

### ความรู้เบื้องต้นที่จำเป็น
ความคุ้นเคยกับแนวคิดการเขียนโปรแกรม Java และหลักการออกแบบงานนำเสนอพื้นฐานจะเป็นประโยชน์ แต่ไม่จำเป็น เนื่องจากเราจะอธิบายทุกขั้นตอนอย่างละเอียด

## การตั้งค่า Aspose.Slides for Java (H2)
เพื่อเริ่มใช้ Aspose.Slides ในโปรเจกต์ของคุณ, ทำตามขั้นตอนต่อไปนี้:

1. **เพิ่ม Dependency**: ใช้ Maven หรือ Gradle เพื่อรวม Aspose.Slides ตามที่แสดงด้านบน  
2. **การจัดหาใบอนุญาต**:  
   - **ทดลองใช้ฟรี**: ดาวน์โหลดใบอนุญาตชั่วคราวจาก [Aspose's website](https://purchase.aspose.com/temporary-license/) เพื่อการประเมินผล  
   - **ซื้อ**: สำหรับการใช้งานในผลิตภัณฑ์, ซื้อใบอนุญาตผ่าน [purchase page](https://purchase.aspose.com/buy)  
3. **การเริ่มต้นพื้นฐาน**: สร้างคลาส Java ใหม่และกำหนดอ็อบเจกต์งานนำเสนอของคุณ:

   ```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

การตั้งค่านี้จะทำให้คุณสามารถสร้างและจัดการงานนำเสนอด้วย Aspose.Slides ได้

## คู่มือการดำเนินการ
เราจะแบ่งการดำเนินการออกเป็นฟีเจอร์ต่าง ๆ โดยแต่ละฟีเจอร์จะเน้นที่แง่มุมเฉพาะของการสร้างแผนภูมิ Funnel ใน PowerPoint

### ฟีเจอร์ 1: การสร้างพรีเซนเทชัน (H2)

#### ภาพรวม
เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาส `Presentation` ซึ่งเป็นตัวแทนไฟล์ PowerPoint ของคุณและอนุญาตให้ทำการดำเนินการต่าง ๆ

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

**คำอธิบาย**: โค้ดนี้ทำการสร้างอ็อบเจกต์ `Presentation` ที่อ้างอิงไฟล์ PowerPoint ที่มีอยู่แล้ว บล็อก `try‑finally` ทำให้แน่ใจว่าทรัพยากรถูกปล่อยอย่างเหมาะสมด้วย `dispose()`

### ฟีเจอร์ 2: การเพิ่มแผนภูมิ Funnel ลงในสไลด์ (H2)

#### ภาพรวม
เพิ่มแผนภูมิ Funnel ไปยังสไลด์แรกของพรีเซนเทชันโดยทำตามขั้นตอนต่อไปนี้:

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

**คำอธิบาย**: เมธอด `addChart()` สร้างแผนภูมิ Funnel บนสไลด์แรก พารามิเตอร์กำหนดตำแหน่งและขนาดของแผนภูมิ

### ฟีเจอร์ 3: การล้างข้อมูลแผนภูมิ (H2)

#### ภาพรวม
ก่อนที่คุณจะใส่ข้อมูลลงในแผนภูมิ, อาจต้องล้างข้อมูลเดิมออกก่อน:

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

**คำอธิบาย**: โค้ดนี้ลบข้อมูลที่มีอยู่ก่อนหน้าในแผนภูมิ Funnel โดยการล้างหมวดหมู่และซีรีส์ทั้งหมด

### ฟีเจอร์ 4: การตั้งค่า Chart Data Workbook (H2)

#### ภาพรวม
เริ่มต้น workbook ของข้อมูลแผนภูมิเพื่อจัดการข้อมูลของคุณอย่างมีประสิทธิภาพ:

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

**คำอธิบาย**: อ็อบเจกต์ `IChartDataWorkbook` ช่วยให้คุณล้างเซลล์ที่มีอยู่, เตรียม workbook สำหรับการใส่ข้อมูลใหม่

### ฟีเจอร์ 5: การเพิ่มหมวดหมู่ลงในแผนภูมิ (H2)

#### ภาพรวม
เพิ่มหมวดหมู่ที่มีความหมายให้กับแผนภูมิ Funnel ของคุณ:

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

**คำอธิบาย**: โค้ดนี้เข้าถึง workbook ของข้อมูลและใส่ชื่อหมวดหมู่ลงในเซลล์ที่กำหนด

### ฟีเจอร์ 6: การเพิ่มซีรีส์ข้อมูลลงในแผนภูมิ (H2)

#### ภาพรวม
เติมข้อมูลซีรีส์ลงในแผนภูมิ Funnel ของคุณ:

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

**คำอธิบาย**: โค้ดนี้เพิ่มซีรีส์ข้อมูลลงในแผนภูมิ Funnel และใส่ค่าจุดข้อมูล พร้อมปรับสีเติมของแต่ละจุดข้อมูล

## กรณีการใช้งานทั่วไป & เคล็ดลับ (H2)

- **การรายงานท่อขาย** – แสดงการแปลงจากผู้สนใจจนถึงการปิดการขาย  
- **การวิเคราะห์ประสิทธิภาพกระบวนการ** – แสดงการสูญเสียในแต่ละขั้นตอนการผลิต  
- **การตรวจสอบฟันเนลการตลาด** – เปรียบเทียบผลการทำแคมเปญในช่องทางต่าง ๆ  

**เคล็ดลับ:** ใช้ค่าคงที่ `java.awt.Color` เพื่อให้สีสอดคล้องกับแบรนด์แทนการสุ่มค่า เพื่อให้ดูเป็นมืออาชีพยิ่งขึ้น

## คำถามที่พบบ่อย

**ถาม: จะเปลี่ยนทิศทางของแผนภูมิ Funnel อย่างไร?**  
ตอบ: ตั้งค่า property `ChartOrientation` ของอ็อบเจกต์ `IChart` เป็น `ChartOrientation.Vertical` หรือ `Horizontal`

**ถาม: สามารถส่งออกสไลด์เป็นภาพหลังจากเพิ่มแผนภูมิได้หรือไม่?**  
ตอบ: ได้, เรียก `pres.getSlides().get_Item(0).getThumbnail(1, 1)` แล้วบันทึก `java.awt.image.BufferedImage` ที่ได้

**ถาม: หากต้องการหมวดหมู่มากกว่าสามรายการจะทำอย่างไร?**  
ตอบ: เพียงเพิ่มหมวดหมู่เพิ่มเติมด้วย `chart.getChartData().getCategories().add(...)` พร้อมจุดข้อมูลที่สอดคล้องกัน

**ถาม: มีวิธีซ่อน legend หรือไม่?**  
ตอบ: ใช้ `chart.getChartTitle().setVisible(false)` และ `chart.getLegend().setVisible(false)`

**ถาม: จำเป็นต้องมีลิขสิทธิ์สำหรับการสร้างบิลด์การพัฒนาไหม?**  
ตอบ: ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมินผล; ใบอนุญาตเต็มจำเป็นสำหรับการใช้งานในผลิตภัณฑ์

---

**Last Updated:** 2026-03-18  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}