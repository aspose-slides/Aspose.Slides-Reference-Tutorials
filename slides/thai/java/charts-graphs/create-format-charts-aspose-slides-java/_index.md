---
date: '2026-08-27'
description: เรียนรู้วิธีเพิ่ม grid lines ในแผนภูมิด้วย Java โดยใช้ Aspose.Slides,
  จัดรูปแบบ axes, titles, และส่งออกแผนภูมิเส้น PowerPoint ที่สวยงาม
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: เรียนรู้วิธีเพิ่ม grid lines ในแผนภูมิด้วย Java โดยใช้ Aspose.Slides,
  จัดรูปแบบ axes, titles, และส่งออกแผนภูมิเส้น PowerPoint ที่สวยงาม
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: วิธีเพิ่ม grid lines ในแผนภูมิด้วย Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: วิธีเพิ่ม grid lines ในแผนภูมิด้วย Aspose.Slides for Java
url: /th/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มเส้นกริดในแผนภูมิด้วย Aspose.Slides for Java

## บทนำ
หากคุณต้องการ **เพิ่มเส้นกริดในแผนภูมิ** ในงานนำเสนอ PowerPoint ด้วยโปรแกรม, Aspose.Slides for Java จะมอบ API ที่สะอาดและเต็มคุณลักษณะ ไม่ว่าคุณจะกำลังเตรียมรายงานธุรกิจรายไตรมาส, การบรรยายทางวิชาการ, หรือสไลด์ขายที่ขับเคลื่อนด้วยข้อมูล, คุณสามารถสร้างแผนภูมิเส้น, ปรับแต่งทุกองค์ประกอบภาพ, และบันทึกผลลัพธ์ในไม่กี่วินาที—โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง.

## คำตอบสั้น
- **ไลบรารีที่สร้างแผนภูมิใน Java คืออะไร?** Aspose.Slides for Java.
- **ประเภทแผนภูมิที่คู่มือนี้ครอบคลุมคืออะไร?** แผนภูมิเส้นพร้อมเครื่องหมายและเส้นกริด.
- **ฉันต้องมีใบอนุญาตเพื่อรันตัวอย่างหรือไม่?** ใบอนุญาตชั่วคราวฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.
- **IDE ใดที่ฉันสามารถใช้ได้?** IDE Java ใดก็ได้ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans.
- **องค์ประกอบของแผนภูมิถูกจัดรูปแบบอย่างไร?** โดยใช้การเรียก API แบบ fluent สำหรับหัวเรื่อง, แกน, เส้นกริด, คำอธิบาย, และสีพื้นหลัง.

## วิธีเพิ่มเส้นกริดในแผนภูมิด้วย Java โดยใช้ Aspose.Slides
โหลด `Presentation` ใหม่, แทรกสไลด์, เพิ่มแผนภูมิเส้น, แล้วเปิดใช้งานเส้นกริดหลักบนแกนแนวตั้ง – ทั้งหมดในโค้ดน้อยกว่า 10 บรรทัด คำตอบโดยตรงนี้แสดงลำดับที่ต้องใช้อย่างชัดเจน เพื่อให้คุณคัดลอก‑วางและเห็นแผนภูมิที่จัดรูปแบบเต็มรูปแบบทันที.

### คำนิยาม anchor
`Presentation` คือคลาสหลักของ Aspose.Slides ที่แสดงไฟล์ PowerPoint ในหน่วยความจำ; การดำเนินการระดับสไลด์ทั้งหมดเริ่มจากอ็อบเจ็กต์นี้.

## แผนภูมิเส้นคืออะไรและทำไมต้องใช้ Aspose.Slides?
แผนภูมิเส้นแสดงชุดข้อมูลที่เชื่อมต่อด้วยเส้นตรง ทำให้แนวโน้มตามเวลาเห็นได้ทันที Aspose.Slides รองรับ **มากกว่า 50 ประเภทแผนภูมิ** และสามารถจัดการ **ได้ถึง 10,000 จุดข้อมูลต่อชุด** โดยไม่มีการชะลอที่สังเกตได้ ให้คุณได้ประสิทธิภาพระดับองค์กรสำหรับชุดข้อมูลขนาดใหญ่.

### คำนิยาม anchor
`Chart` คืออ็อบเจ็กต์ระดับบนของ Aspose.Slides สำหรับแผนภูมิใด ๆ; มันเก็บชุดข้อมูล, หมวดหมู่, และข้อมูลการจัดรูปแบบ.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8+** ติดตั้งแล้ว.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans ฯลฯ).
- **Aspose.Slides for Java** library เพิ่มผ่าน Maven หรือ Gradle (ดูส่วน *aspose.slides maven dependency* ด้านล่าง).

### การพึ่งพา Maven (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การพึ่งพา Gradle
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

หรือดาวน์โหลด JAR ล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

## การรับใบอนุญาต (ใช้ใบอนุญาต aspose)
- รับ **ใบอนุญาตทดลองใช้งานฟรี** จากหน้า [free trial license](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบ.
- ซื้อใบอนุญาตเต็มจาก [Aspose's official site](https://purchase.aspose.com/buy) สำหรับการใช้งานในสภาพแวดล้อมจริง.

## การตั้งค่า Aspose.Slides for Java
1. เพิ่มการพึ่งพา Maven หรือ Gradle ที่แสดงด้านบนลงในโปรเจกต์ของคุณ.
2. โหลดไฟล์ใบอนุญาต **ก่อน** สร้างอ็อบเจ็กต์ `Presentation` ใด ๆ เพื่อให้ฟีเจอร์ทั้งหมดเปิดใช้งาน.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## การดำเนินการแบบขั้นตอน

### ขั้นตอนที่ 1: สร้างไดเรกทอรีผลลัพธ์ (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*ทำไมเรื่องนี้สำคัญ:* การตรวจสอบให้โฟลเดอร์มีอยู่ป้องกัน `FileNotFoundException` เมื่อคุณบันทึกงานนำเสนอในภายหลัง.

### ขั้นตอนที่ 2: เพิ่มสไลด์และแทรกแผนภูมิเส้น
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*คำอธิบาย:* นี้สร้างสไลด์ใหม่และวาง **แผนภูมิเส้นพร้อมเครื่องหมาย** ที่ตำแหน่งที่กำหนด.

### ขั้นตอนที่ 3: เพิ่มหัวเรื่องแผนภูมิ (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*เคล็ดลับ:* การใช้หัวเรื่องหนาและสีเทาทำให้แผนภูมิดูเด่นทันที.

### ขั้นตอนที่ 4: จัดรูปแบบแกนและเพิ่มเส้นกริด (add grid lines)
#### การจัดรูปแบบแกนแนวตั้ง
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*ทำไมเรื่องนี้สำคัญ:* เส้นกริดที่ชัดเจนและป้ายหมุนช่วยเพิ่มความอ่านง่าย โดยเฉพาะเมื่อจุดข้อมูลหนาแน่น.

#### การจัดรูปแบบแกนแนวนอน
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### ขั้นตอนที่ 5: ปรับแต่งคำอธิบาย (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### ขั้นตอนที่ 6: ตั้งค่าสีพื้นหลัง (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### ขั้นตอนที่ 7: บันทึกงานนำเสนอ
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*ผลลัพธ์:* คุณจะได้ไฟล์ PowerPoint (`FormattedChart_out.pptx`) ที่มีแผนภูมิเส้นที่จัดรูปแบบเต็มรูปแบบ.

## การประยุกต์ใช้งาน (generate line chart powerpoint)
- **รายงานธุรกิจ:** แสดงแนวโน้มรายได้รายไตรมาสด้วยเส้นกริดที่คมชัด.
- **การบรรยายทางวิชาการ:** แสดงข้อมูลการทดลองหลายช่วงเวลา.
- **ข้อเสนอโปรเจกต์:** เน้นความคืบหน้าของไมล์สโตนและเส้นโค้งการคาดการณ์.
- **การวิเคราะห์การตลาด:** นำเสนอแนวโน้ม ROI ของแคมเปญเคียงข้างกับข้อมูลคู่แข่ง.
- **การรวมเข้ากับแดชบอร์ด:** ส่งออกการวิเคราะห์แบบเรียลไทม์ไปยัง PowerPoint สำหรับการประชุมผู้มีส่วนได้ส่วนเสีย.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ:** เรียก `presentation.dispose()` หลังการบันทึกเพื่อปลดปล่อยทรัพยากรเนทีฟโดยเร็ว.
- **ชุดข้อมูลขนาดใหญ่:** Aspose.Slides ประมวลผลแผนภูมิที่มีจุดข้อมูลหลายพันโดยใช้การสตรีมมิ่ง ทำให้การใช้หน่วยความจำอยู่ต่ำกว่า 100 MB บนเซิร์ฟเวอร์ทั่วไป.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **ไม่ได้ใช้ใบอนุญาต** | โหลดใบอนุญาตทดลองหรือเต็ม **ก่อน** ที่อ็อบเจ็กต์ `Presentation` ใด ๆ ถูกสร้าง. |
| **แผนภูมิแสดงเป็นสีขาว** | ตรวจสอบว่าหน้าสไลด์มีอย่างน้อยหนึ่งชุดข้อมูล; เพิ่มชุดข้อมูลผ่าน `chart.getChartData().getSeries().add(...)` หากจำเป็น. |
| **ไฟล์ไม่ถูกบันทึก** | ตรวจสอบว่าไดเรกทอรีผลลัพธ์มีอยู่ (ดูขั้นตอน 1). |
| **สีไม่ถูกนำไปใช้** | ใช้ค่าคงที่ `java.awt.Color` หรือ enum `PresetColor` เพื่อให้การแสดงสีเชื่อถือได้. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างประเภทแผนภูมิอื่น ๆ นอกจากแผนภูมิเส้นได้หรือไม่?**  
A: ใช่, Aspose.Slides รองรับแผนภูมิแท่ง, พาย, กระจาย, เรดาร์, และมากกว่า 50 ประเภทแผนภูมิเพิ่มเติม.

**Q: ฉันจะเพิ่มชุดข้อมูลหลายชุดในแผนภูมิเส้นได้อย่างไร?**  
A: ใช้ `chart.getChartData().getSeries().add(...)` เพื่อแทรกชุดข้อมูลเพิ่มเติมก่อนทำการจัดรูปแบบ.

**Q: สามารถส่งออกแผนภูมิเป็นภาพได้หรือไม่?**  
A: แน่นอน. เรนเดอร์สไลด์เป็น PNG, JPEG หรือ SVG ด้วย `presentation.save("slide.png", SaveFormat.Png)`.

**Q: ฉันต้องมีใบอนุญาตแบบชำระเงินสำหรับการพัฒนาหรือไม่?**  
A: ใบอนุญาตชั่วคราวฟรีเพียงพอสำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมจริง.

**Q: รองรับเวอร์ชัน Java ใดบ้าง?**  
A: ไลบรารีทำงานกับ JDK 8 ถึง JDK 22; เลือก classifier ที่เหมาะสม (เช่น `jdk16`) เมื่อเพิ่มการพึ่งพา Maven/Gradle.

---

**อัปเดตล่าสุด:** 2026-08-27  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
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
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## บทแนะนำที่เกี่ยวข้อง

- [aspose slides maven dependency: เพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนโดยละเอียด](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [สร้างและปรับแต่งเส้นแนวโน้มของแผนภูมิ Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}