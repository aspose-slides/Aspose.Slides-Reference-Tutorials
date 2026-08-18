---
date: '2026-06-03'
description: เรียนรู้วิธีสร้างแผนภูมิในงานนำเสนอ .NET และเพิ่มแผนภูมิลงในสไลด์ด้วย
  Aspose.Slides for Java. ปฏิบัติตามคู่มือ step‑by‑step นี้เพื่อ data visualization.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: สร้างแผนภูมิใน .NET ด้วย Aspose.Slides for Java
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิใน .NET ด้วย Aspose.Slides for Java

## บทนำ
การสร้างงานนำเสนอที่น่าสนใจมักต้องรวมการแสดงข้อมูลเชิงภาพเช่นแผนภูมิ เพื่อเพิ่มความเข้าใจและการมีส่วนร่วมของผู้ชม. **หากคุณต้องการสร้างแผนภูมิใน .NET** Aspose.Slides for Java ให้ API ที่ทรงพลังและไม่จำกัดภาษา ซึ่งทำงานอย่างราบรื่นภายในแอปพลิเคชัน .NET. ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีการเริ่มต้นงานนำเสนอ, เพิ่มประเภทแผนภูมิต่าง ๆ, จัดการ workbook ข้อมูลของแผนภูมิ, และจัดรูปแบบข้อมูลซีรีส์ รวมถึงการจัดการค่าติดลบ. เมื่อจบคุณจะสามารถสร้างแผนภูมิในไฟล์งานนำเสนอโดยอัตโนมัติและเพิ่มแผนภูมิลงในสไลด์ด้วยเพียงไม่กี่บรรทัดของโค้ด.

## คำตอบสั้น
- **เป้าหมายหลักคืออะไร?** สร้างแผนภูมิในงานนำเสนอ .NET ด้วย Aspose.Slides for Java.  
- **ต้องการเวอร์ชันของไลบรารีใด?** Aspose.Slides for Java 25.4 หรือใหม่กว่า.  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถใช้ Maven หรือ Gradle ได้หรือไม่?** ได้—ระบบการสร้างทั้งสองแบบได้รับการสนับสนุน.  
- **มีประเภทแผนภูมิใดบ้าง?** คอลัมน์แบบกลุ่ม, เส้น, พาย, แถบ, พื้นที่, และอื่น ๆ.

## วิธีสร้างแผนภูมิในงานนำเสนอ .NET ด้วย Aspose.Slides for Java?
`Presentation` class แทนไฟล์ PowerPoint และให้เมธอดสำหรับจัดการสไลด์ของมัน. โหลดอ็อบเจ็กต์ `Presentation` ใหม่, เรียก `slides.addEmptySlide()` เพื่อรับสไลด์, จากนั้นใช้ `slide.getShapes().addChart()` เพื่อแทรกประเภทแผนภูมิที่ต้องการที่พิกัดที่คุณระบุ. หลังจากเพิ่มแผนภูมิแล้ว, เติมข้อมูลใน workbook ของแผนภูมิกับซีรีส์และหมวดหมู่, ใช้การจัดรูปแบบใด ๆ (เช่นสีสำหรับค่าติดลบ), และสุดท้ายบันทึกงานนำเสนอเป็นไฟล์ .pptx. กระบวนการนี้ทำให้คุณ **สร้างแผนภูมิใน .NET** ด้วยชุดคำสั่ง API ที่กระชับ.

## Aspose.Slides for Java คืออะไร?
Aspose.Slides for Java เป็น API ข้ามแพลตฟอร์มที่ช่วยให้นักพัฒนาสามารถสร้าง, แก้ไข, และเรนเดอร์ไฟล์ PowerPoint โดยไม่ต้องใช้ Microsoft Office. รองรับ **50+ input and output formats** และสามารถประมวลผลงานนำเสนอที่มีสไลด์หลายพันสไลด์โดยคงการใช้หน่วยความจำต่ำกว่า 200 MB.

## ทำไมต้องใช้ Aspose.Slides for Java ในโครงการ .NET?
Aspose.Slides for Java ทำงานบน Java Virtual Machine และสามารถเรียกใช้จาก .NET ผ่าน native wrapper, ให้ผู้พัฒนา .NET เข้าถึงเครื่องมือสร้างแผนภูมิที่พัฒนามาแล้ว, การประมวลผลประสิทธิภาพสูงของชุดข้อมูลขนาดใหญ่, และความเข้ากันได้เต็มรูปแบบกับโค้ด Java ที่มีอยู่โดยไม่ต้องเขียนตรรกะใหม่.

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มสร้างแผนภูมิด้วย Aspose.Slides for Java, มาดูสิ่งที่คุณต้องการกัน:

### ไลบรารีและเวอร์ชันที่ต้องการ
- **Aspose.Slides for Java**: Version 25.4 or later.

### ความต้องการการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่รองรับแอปพลิเคชัน .NET.  
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรม Java.

### ความรู้เบื้องต้นที่จำเป็น
- ความคุ้นเคยกับการสร้างงานนำเสนอในบริบทของแอปพลิเคชัน .NET.  
- ความเข้าใจเกี่ยวกับการพึ่งพา Java และการจัดการของมัน (Maven/Gradle).

## การตั้งค่า Aspose.Slides for Java
เพื่อเริ่มใช้ Aspose.Slides, คุณต้องรวมเป็น dependency ในโปรเจกต์ของคุณ. นี่คือวิธีทำ:

### Maven
ส่วนโค้ด dependency ของ Maven จะเพิ่ม Aspose.Slides for Java ลงในโปรเจกต์ของคุณ.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
ใส่บรรทัดนี้ในไฟล์ `build.gradle` ของคุณเพื่อดึงไลบรารีจาก Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### ขั้นตอนการรับไลเซนส์
- **Free Trial**: เริ่มต้นด้วยไลเซนส์ชั่วคราวเพื่อสำรวจคุณสมบัติ.  
- **Purchase**: ซื้อไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์โดยไม่มีข้อจำกัด.

#### การเริ่มต้นและการตั้งค่าพื้นฐาน
`Slides` initialization requires setting the license and creating a `Presentation` instance.

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

การตั้งค่านี้ทำให้การจัดการทรัพยากรเป็นไปอย่างมีประสิทธิภาพ.

## คู่มือการใช้งาน
เราจะพาคุณผ่านการใช้งานฟีเจอร์ต่าง ๆ ทีละขั้นตอน.

### การเริ่มต้น Presentation
**ภาพรวม:**  
การสร้างอินสแตนซ์ของงานนำเสนอเป็นการตั้งค่าพื้นฐานสำหรับการดำเนินการต่อไปทั้งหมด. ฟีเจอร์นี้แสดงวิธีเริ่มจากศูนย์โดยใช้ Aspose.Slides.

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
`Presentation` และคลาสที่เกี่ยวข้องเป็นส่วนหนึ่งของเนมสเปซ `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์ Presentation ใหม่
สร้างอ็อบเจ็กต์ `Presentation` และห่อหุ้มด้วยบล็อก try‑with‑resources เพื่อรับประกันการปลดปล่อย.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*สิ่งนี้ทำให้แน่ใจว่าอ็อบเจ็กต์ presentation ถูกปลดปล่อยอย่างเหมาะสมหลังการใช้, ป้องกันการรั่วของหน่วยความจำ.*

### การเพิ่มแผนภูมิลงในสไลด์
**ภาพรวม:**  
การเพิ่มแผนภูมิลงในสไลด์ของคุณสามารถทำให้การแสดงข้อมูลเป็นภาพมีประสิทธิภาพและดึงดูดมากขึ้น.

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
คลาส `Chart` แทนรูปร่างแผนภูมิที่สามารถวางบนสไลด์และปรับแต่งได้.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### ขั้นตอนที่ 2: เริ่มต้น Presentation และเพิ่มแผนภูมิ
สร้างสไลด์, จากนั้นเรียก `addChart` ด้วย `ChartType.ClusteredColumn` และตำแหน่งและขนาดที่ต้องการ.

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

*ที่นี่, เราเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์แรกที่พิกัดและขนาดที่ระบุ.*

### การจัดการ Chart Data Workbook
**ภาพรวม:**  
การจัดการ workbook ข้อมูลของแผนภูมิอย่างมีประสิทธิภาพทำให้คุณสามารถจัดการซีรีส์และหมวดหมู่ได้อย่างราบรื่น.

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
`IChartDataWorkbook` ให้การเข้าถึง workbook แบบ Excel ที่อยู่เบื้องหลังที่ใช้โดยแผนภูมิ.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### ขั้นตอนที่ 2: เข้าถึงและล้าง Data Workbook
ดึง workbook จากแผนภูมิและล้างข้อมูลที่มีอยู่ทั้งหมดเพื่อเริ่มต้นใหม่.

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

*การล้าง workbook เป็นสิ่งสำคัญเพื่อเริ่มต้นด้วยสภาพแห้งใหม่เมื่อเพิ่มซีรีส์และหมวดหมู่ใหม่.*

### การเพิ่ม Series และ Categories ลงในแผนภูมิ
**ภาพรวม:**  
ฟีเจอร์นี้แสดงวิธีการเพิ่มจุดข้อมูลที่มีความหมายโดยการจัดการซีรีส์และหมวดหมู่.

#### ขั้นตอนที่ 1: เพิ่ม Series และ Categories
ใช้ `chart.getChartData().getSeries().add()` และ `chart.getChartData().getCategories().add()` เพื่อกำหนดโครงสร้าง.

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

*การเพิ่มซีรีส์และหมวดหมู่ทำให้การนำเสนอข้อมูลเป็นระเบียบมากขึ้น.*

### การเติมข้อมูล Series และการจัดรูปแบบ
**ภาพรวม:**  
เติมข้อมูลจุดในแผนภูมิของคุณและจัดรูปแบบการแสดงผลเพื่อเพิ่มความอ่านง่าย, โดยเฉพาะเมื่อจัดการค่าติดลบ.

#### ขั้นตอนที่ 1: เติมข้อมูล Series
กำหนดค่าตัวเลขให้กับแต่ละเซลล์ใน workbook และใช้สีเติมสีแดงสำหรับตัวเลขติดลบ.

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

*ส่วนนี้แสดงวิธีการเติมข้อมูลและใช้การจัดรูปแบบสีเพื่อการมองเห็นที่ดียิ่งขึ้น.*

## ปัญหาทั่วไปและวิธีแก้
- **LicenseNotFoundException** – ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ไลเซนส์ถูกต้องและไฟล์สามารถเข้าถึงได้ในระหว่างรันไทม์.  
- **NullPointerException on chart data** – ควรล้าง workbook ก่อนเพิ่มซีรีส์ใหม่เสมอเพื่อหลีกเลี่ยงข้อมูลที่เหลืออยู่.  
- **Chart not rendering in .NET** – ตรวจสอบว่าคุณใช้เวอร์ชัน Aspose.Slides JAR ที่เข้ากันได้กับ .NET และว่ารันไทม์ Java ถูกตั้งค่าอย่างถูกต้องในโปรเจกต์ .NET ของคุณ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างแผนภูมิในไฟล์งานนำเสนอโดยไม่มี GUI ได้หรือไม่?**  
A: ใช่, Aspose.Slides for Java ทำงานแบบ headless อย่างเต็มที่และทำงานบนเซิร์ฟเวอร์โดยไม่มีส่วนประกอบกราฟิกใด ๆ.

**Q: .NET เวอร์ชันใดบ้างที่รองรับ?**  
A: รองรับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5, และ .NET 6 ทั้งหมด.

**Q: ฉันสามารถเพิ่มประเภทแผนภูมิได้กี่ประเภท?**  
A: มีประเภทแผนภูมิมากกว่า 20 ประเภท รวมถึงคอลัมน์, เส้น, พาย, พื้นที่, และแผนภูมิโรบิน.

**Q: สามารถจัดรูปแบบจุดข้อมูลแต่ละจุดได้หรือไม่?**  
A: แน่นอน – คุณสามารถตั้งค่าสีเติม, เส้นขอบ, และมาร์คเกอร์สำหรับแต่ละจุดข้อมูลผ่าน API `IDataPoint`.

**Q: จำเป็นต้องแปลงอ็อบเจ็กต์ Java เป็นประเภท .NET ด้วยตนเองหรือไม่?**  
A: ไม่, wrapper .NET ของ Aspose.Slides for Java จะจัดการการแปลงประเภทโดยอัตโนมัติ.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีฝังแผนภูมิในงานนำเสนอ .NET ด้วย Aspose.Slides เพื่อการแสดงข้อมูลที่มีประสิทธิภาพ](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [วิธีดึงประเภทแหล่งข้อมูลแผนภูมิด้วย Aspose.Slides สำหรับ .NET - แผนภูมิและกราฟ](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [การสร้างและจัดการ Series ของแผนภูมิด้วย Aspose.Slides .NET เพื่อการแสดงข้อมูลที่มีประสิทธิภาพ](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}