---
date: '2026-01-14'
description: เรียนรู้วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่มและเพิ่มแผนภูมิลงในสไลด์ในงานนำเสนอ
  .NET โดยใช้ Aspose.Slides for Java ตามคู่มือขั้นตอนต่อขั้นตอนพร้อมตัวอย่างโค้ดเต็มรูปแบบ.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: เพิ่มแผนภูมิคอลัมน์แบบกลุ่มในสไลด์ .NET Aspose.Slides Java
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างแผนภูมิในงานนำเสนอ .NET ด้วย Aspose.Slides for Java
## บทนำ
การสร้างงานนำเสนอที่น่าสนใจมักต้องผสานการแสดงข้อมูลเชิงภาพเช่นแผนภูมิ เพื่อเพิ่มความเข้าใจและการมีส่วนร่วมของผู้ชม หากคุณเป็นนักพัฒนาที่ต้องการเพิ่มแผนภูมิที่ปรับเปลี่ยนได้และมีความยืดหยุ่นให้กับงานนำเสนอ .NET ของคุณด้วย Aspose.Slides for Java คำแนะนำนี้ถูกออกแบบมาสำหรับคุณโดยเฉพาะ เราจะเจาะลึกวิธีการเริ่มต้นงานนำเสนอ, เพิ่มประเภทแผนภูมิต่าง ๆ, จัดการข้อมูลแผนภูมิ, และจัดรูปแบบข้อมูลซีรีส์อย่างมีประสิทธิภาพ

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่าและใช้ Aspose.Slides for Java ในสภาพแวดล้อม .NET ของคุณ
- การเริ่มต้นงานนำเสนอใหม่ด้วย Aspose.Slides
- การเพิ่มและปรับแต่งแผนภูมิในสไลด์
- การจัดการ workbook ของข้อมูลแผนภูมิ
- การจัดรูปแบบข้อมูลซีรีส์ โดยเฉพาะการจัดการค่าติดลบ

การเข้าสู่ส่วนข้อกำหนดเบื้องต้นจะทำให้คุณพร้อมที่จะทำตามขั้นตอนได้อย่างง่ายดาย

## คำตอบสั้น
- **เป้าหมายหลักคืออะไร?** เพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ .NET
- **ต้องใช้ไลบรารีใด?** Aspose.Slides for Java (เวอร์ชัน 25.4 ขึ้นไป)
- **สามารถใช้ในโครงการ .NET ได้หรือไม่?** ใช่ – ไลบรารี Java ทำงานผ่านสะพาน Java‑to‑.NET
- **ต้องมีใบอนุญาตหรือไม่?** เวอร์ชันทดลองฟรีใช้งานได้สำหรับการพัฒนา; ต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ประมาณ 10‑15 นาทีสำหรับแผนภูมิพื้นฐาน

## แผนภูมิคอลัมน์แบบกลุ่มคืออะไร?
แผนภูมิคอลัมน์แบบกลุ่มจะแสดงซีรีส์ข้อมูลหลายชุดเคียงข้างกันสำหรับแต่ละประเภท ทำให้เปรียบเทียบค่าต่าง ๆ ระหว่างกลุ่มได้อย่างง่ายดาย ภาพนี้เหมาะสำหรับแดชบอร์ดธุรกิจ, รายงานประสิทธิภาพ, และสถานการณ์ใด ๆ ที่ต้องการเปรียบเทียบเมตริกหลายตัว

## ทำไมต้องเพิ่มแผนภูมิลงในสไลด์ด้วย Aspose.Slides for Java?
การใช้ Aspose.Slides ทำให้คุณสามารถสร้าง, แก้ไข, และบันทึกงานนำเสนอได้โดยไม่ต้องติดตั้ง Microsoft PowerPoint มันให้การควบคุมเต็มรูปแบบต่อประเภทแผนภูมิ, ข้อมูล, และการจัดรูปแบบ ซึ่งหมายความว่าคุณสามารถอัตโนมัติการสร้างรายงานโดยตรงจากแอปพลิเคชัน .NET ของคุณได้

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มสร้างแผนภูมิด้วย Aspose.Slides for Java เรามาดูสิ่งที่คุณต้องเตรียมพร้อมกัน

### ไลบรารีและเวอร์ชันที่ต้องการ
- **Aspose.Slides for Java**: เวอร์ชัน 25.4 หรือใหม่กว่า

### ความต้องการการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่รองรับแอปพลิเคชัน .NET
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรม Java

### ความรู้ที่จำเป็น
- คุ้นเคยกับการสร้างงานนำเสนอในบริบทของแอปพลิเคชัน .NET
- เข้าใจการจัดการ dependencies ของ Java (Maven/Gradle)

## การตั้งค่า Aspose.Slides for Java
เพื่อเริ่มใช้ Aspose.Slides คุณต้องเพิ่มเป็น dependency ในโครงการของคุณ วิธีทำมีดังนี้

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
ใส่ส่วนนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

#### ขั้นตอนการรับใบอนุญาต
- **ทดลองฟรี**: เริ่มต้นด้วยใบอนุญาตชั่วคราวเพื่อสำรวจคุณสมบัติต่าง ๆ
- **ซื้อ**: พิจารณาซื้อใบอนุญาตสำหรับการใช้งานในระดับกว้าง

#### การเริ่มต้นและการตั้งค่าเบื้องต้น
นี่คือตัวอย่างการเริ่มต้น Aspose.Slides ในโค้ดของคุณ:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
การตั้งค่านี้ทำให้การจัดการทรัพยากรเป็นไปอย่างมีประสิทธิภาพ

## คู่มือการใช้งาน
เราจะพาคุณผ่านขั้นตอนการทำงานอย่างเป็นระบบ

### การเริ่มต้นงานนำเสนอ
**ภาพรวม:**  
การสร้างอินสแตนซ์ของงานนำเสนอเป็นขั้นตอนแรกที่สำคัญสำหรับการดำเนินการต่อทั้งหมด ตัวอย่างนี้แสดงวิธีเริ่มจากศูนย์ด้วย Aspose.Slides

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
```

#### ขั้นตอนที่ 2: สร้างอ็อบเจกต์ Presentation ใหม่
นี่คือตัวอย่างการทำเช่นนั้น:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*การทำเช่นนี้ทำให้แน่ใจว่าอ็อบเจกต์ Presentation จะถูกกำจัดอย่างเหมาะสมหลังการใช้งาน ป้องกันการรั่วไหลของหน่วยความจำ*

### การเพิ่มแผนภูมิลงในสไลด์
**ภาพรวม:**  
การเพิ่มแผนภูมิลงในสไลด์ช่วยให้การแสดงข้อมูลเป็นภาพชัดเจนและน่าสนใจยิ่งขึ้น

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### ขั้นตอนที่ 2: เริ่มต้น Presentation และเพิ่มแผนภูมิ
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*ที่นี่ เราเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์แรกโดยกำหนดพิกัดและขนาดตามที่ต้องการ*

### การจัดการ Workbook ของข้อมูลแผนภูมิ
**ภาพรวม:**  
การจัดการ workbook ของข้อมูลแผนภูมิอย่างมีประสิทธิภาพทำให้คุณสามารถจัดการซีรีส์และประเภทได้อย่างราบรื่น

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### ขั้นตอนที่ 2: เข้าถึงและล้าง Data Workbook
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*การล้าง workbook เป็นสิ่งสำคัญเพื่อเริ่มต้นด้วยข้อมูลที่สะอาดเมื่อเพิ่มซีรีส์และประเภทใหม่*

### การเพิ่ม Series และ Category ลงในแผนภูมิ
**ภาพรวม:**  
ฟีเจอร์นี้แสดงวิธีการเพิ่มจุดข้อมูลที่มีความหมายโดยการจัดการซีรีส์และประเภท

#### ขั้นตอนที่ 1: เพิ่ม Series และ Category
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*การเพิ่มซีรีส์และประเภทช่วยให้การนำเสนอข้อมูลเป็นระเบียบและเข้าใจง่ายขึ้น*

### การเติมข้อมูล Series และการจัดรูปแบบ
**ภาพรวม:**  
เติมแผนภูมิของคุณด้วยจุดข้อมูลและจัดรูปแบบเพื่อเพิ่มความอ่านง่าย โดยเฉพาะเมื่อจัดการค่าติดลบ

#### ขั้นตอนที่ 1: เติมข้อมูล Series
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*ส่วนนี้แสดงวิธีเติมข้อมูลและใช้การจัดรูปแบบสีเพื่อให้การแสดงผลเป็นภาพที่ชัดเจนยิ่งขึ้น*

## ปัญหาที่พบบ่อยและวิธีแก้
- **การรั่วไหลของหน่วยความจำ:** ควรเรียก `dispose()` บนอ็อบเจกต์ `Presentation` ภายในบล็อก `finally`
- **ประเภทแผนภูมิไม่ถูกต้อง:** ตรวจสอบให้ใช้ `ChartType.ClusteredColumn` เมื่อคุณต้องการแผนภูมิคอลัมน์แบบกลุ่ม; ประเภทอื่นจะให้ผลลัพธ์ภาพที่แตกต่างกัน
- **สีค่าติดลบไม่ถูกนำไปใช้:** ตรวจสอบให้แน่ใจว่า `IDataPoint` ถูกแคสต์เป็น `Number` อย่างถูกต้องก่อนทำการเปรียบเทียบ

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ Aspose.Slides for Java ในโครงการ .NET แบบบริสุทธิ์โดยไม่ต้องใช้ Java ได้หรือไม่?**  
ตอบ: ใช่ ไลบรารีทำงานผ่านสะพาน Java‑to‑.NET ทำให้คุณเรียก API ของ Java จากภาษาที่ใช้ใน .NET ได้

**ถาม: เวอร์ชันทดลองฟรีรองรับการสร้างแผนภูมิหรือไม่?**  
ตอบ: เวอร์ชันทดลองให้ฟังก์ชันแผนภูมิเต็มรูปแบบ แต่ไฟล์ที่สร้างจะมีลายน้ำประเมินผลขนาดเล็ก

**ถาม: .NET เวอร์ชันใดบ้างที่เข้ากันได้?**  
ตอบ: ทุกเวอร์ชันของ .NET ที่สามารถทำงานร่วมกับ Java 16+ รวมถึง .NET Framework 4.6+, .NET Core 3.1+, และ .NET 5/6/7

**ถาม: จะจัดการกับงานนำเสนอขนาดใหญ่ที่มีแผนภูมิจำนวนมากอย่างไร?**  
ตอบ: ควรใช้อินสแตนซ์ `IChartDataWorkbook` เดียวกันซ้ำได้เมื่อเป็นไปได้และกำจัด `Presentation` แต่ละอันโดยเร็วเพื่อคืนหน่วยความจำ

**ถาม: สามารถส่งออกแผนภูมิเป็นภาพได้หรือไม่?**  
ตอบ: ได้ ใช้เมธอด `chart.getImage()` หรือ `chart.exportChartImage()` เพื่อรับภาพ PNG/JPEG

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-14  
**ทดสอบกับ:** Aspose.Slides for Java 25.4  
**ผู้เขียน:** Aspose  

---