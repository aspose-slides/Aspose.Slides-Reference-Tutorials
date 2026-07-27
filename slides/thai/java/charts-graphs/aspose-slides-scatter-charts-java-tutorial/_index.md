---
date: '2026-07-27'
description: วิธีปรับแต่งแผนภูมิด้วย Aspose.Slides for Java. เรียนรู้การสร้างแผนภูมิ
  PowerPoint, ปรับสไตล์ชุดข้อมูลกระจาย, และบันทึกงานนำเสนออย่างมีประสิทธิภาพ.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: วิธีปรับแต่งแผนภูมิด้วย Aspose.Slides for Java. คู่มือนี้แสดงวิธีสร้างแผนภูมิ
  PowerPoint, ปรับสไตล์จุดกระจาย, และส่งออกงานนำเสนอ.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'วิธีปรับแต่งแผนภูมิ: แผนภูมิกระจาย Aspose ใน Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'วิธีปรับแต่งแผนภูมิ: แผนภูมิกระจาย Aspose ใน Java'
url: /th/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ปรับแต่งแผนภูมิกระจาย Aspose ใน Java

ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีการปรับแต่งแผนภูมิ** — โดยเฉพาะแผนภูมิกระจาย — โดยใช้ไลบรารี Aspose.Slides for Java ที่ทรงพลัง เราจะเดินผ่านการตั้งค่าโครงการ การสร้างแผนภูมิกระจาย การปรับแต่งประเภทซีรีส์และเครื่องหมาย แล้วบันทึกงานนำเสนอในที่สุด เมื่อเสร็จสิ้น คุณจะสามารถสร้างแผนภูมิกระจายที่ดูเป็นมืออาชีพโดยอัตโนมัติและปรับแต่งรายละเอียดภาพทุกอย่างให้ตรงกับแบรนด์หรือความต้องการรายงานของคุณ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Slides for Java (v25.4+).  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 8 หรือสูงกว่า.  
- **ฉันสามารถเปลี่ยนรูปแบบเครื่องหมายได้หรือไม่?** ใช่ – ใช้ `MarkerStyleType` เพื่อเลือกดาว, วงกลม ฯลฯ.  
- **ฉันจะบันทึกไฟล์อย่างไร?** เรียก `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **ต้องการใบอนุญาตหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.

## วิธีการปรับแต่งแผนภูมิใน Java ด้วย Aspose.Slides?
`Presentation` เป็นคลาสของ Aspose.Slides ที่แสดงไฟล์ PowerPoint ทั้งหมดในหน่วยความจำ โหลด `Presentation` ใหม่ เพิ่มแผนภูมิกระจายบนสไลด์แรก ตั้งค่าชนิดซีรีส์และสไตล์เครื่องหมาย แล้วเรียก `save` กระบวนการเดียวนี้สร้างแผนภูมิที่มีสไตล์ครบถ้วนในไม่กี่บรรทัดของโค้ด Java พร้อมนำไปใส่ในสไลด์ PowerPoint ใดก็ได้

## อะไรคือ “customize scatter chart aspose”?
การปรับแต่งแผนภูมิกระจายด้วย Aspose หมายถึงการกำหนดข้อมูล ลักษณะ และพฤติกรรมของแผนภูมิด้วยโปรแกรม—ทุกอย่างตั้งแต่พิกัดจุดถึงสัญลักษณ์เครื่องหมาย—โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง วิธีนี้เหมาะสำหรับการรายงานอัตโนมัติ การนำเสนอที่ขับเคลื่อนด้วยข้อมูล หรือสถานการณ์ใด ๆ ที่คุณต้องการการสร้างภาพที่ทำซ้ำได้และมีคุณภาพสูง

## ทำไมต้องปรับแต่งแผนภูมิกระจายด้วย Aspose.Slides?
Aspose.Slides มอบการควบคุมแบบโปรแกรมเต็มรูปแบบแก่ผู้พัฒนาในการกำหนดลักษณะของแผนภูมิ ทำให้สามารถสร้างภาพที่มีคุณภาพสูงโดยอัตโนมัติ ผสานรวมอย่างราบรื่นกับกระบวนการรายงาน และสามารถปรับแต่งทุกองค์ประกอบภาพโดยไม่ต้องเปิด PowerPoint ด้วยตนเอง ซึ่งช่วยประหยัดเวลาและรับประกันความสอดคล้องในทุกการนำเสนอ

- **Full control** – ปรับเปลี่ยนประเภทซีรีส์, สไตล์เครื่องหมาย, สี และอื่น ๆ ผ่านโค้ด Java.  
- **Automation** – สร้างแผนภูมิจำนวนหลายสิบรายการแบบเรียลไทม์สำหรับแดชบอร์ดหรือรายงานแบบชุด.  
- **Cross‑platform** – ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java ไม่ต้องติดตั้ง Office.  
- **Performance** – API ที่มีน้ำหนักเบาซึ่งประมวลผล **150+ ชนิดแผนภูมิ** และจัดการงานนำเสนอหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.

## ข้อกำหนดเบื้องต้น

เพื่อทำตามขั้นตอน โปรดตรวจสอบว่าคุณมี:

- **Aspose.Slides for Java** (v25.4 หรือใหม่กว่า).  
- **Java Development Kit (JDK)** 8 + ติดตั้งแล้ว.  
- Maven หรือ Gradle สำหรับการจัดการ dependencies (หรือคุณสามารถดาวน์โหลด JAR ด้วยตนเอง).  
- ความรู้พื้นฐานของ Java และคุ้นเคยกับเครื่องมือสร้างที่คุณเลือกใช้.

## การตั้งค่า Aspose.Slides สำหรับ Java

รวมไลบรารีเข้ากับโครงการของคุณโดยใช้หนึ่งในวิธีต่อไปนี้

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หรือรับเวอร์ชันล่าสุดจาก [Aspose Releases](https://releases.aspose.com/slides/java/).

#### การรับใบอนุญาต
- **Free Trial** – การประเมินผล 30‑วัน.  
- **Temporary License** – ระยะเวลาทดสอบต่อเนื่อง.  
- **Full License** – การใช้งานในผลิตภัณฑ์พร้อมการสนับสนุนระดับพรีเมียม.

## คู่มือขั้นตอนการปรับแต่งแผนภูมิกระจาย Aspose

### 1️⃣ เตรียมโฟลเดอร์สำหรับไฟล์งานนำเสนอของคุณ
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*ทำไมเรื่องนี้สำคัญ:* การตรวจสอบให้โฟลเดอร์ผลลัพธ์มีอยู่แล้วจะป้องกัน `FileNotFoundException` เมื่อคุณบันทึก PPTX ภายหลัง.

### 2️⃣ สร้างงานนำเสนอใหม่และดึงสไลด์แรก
`Presentation` แสดงเอกสาร PowerPoint และให้เข้าถึงสไลด์และรูปร่างได้.  
คลาส `Presentation` แสดงไฟล์ PowerPoint ทั้งหมดในหน่วยความจำ.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ เพิ่มแผนภูมิกระจายพร้อมเส้นเรียบ
`ChartType.ScatterWithSmoothLines` สร้างแผนภูมิกระจายที่จุดต่าง ๆ เชื่อมต่อด้วยเส้นเรียบ.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ ลบซีรีส์เริ่มต้นทั้งหมดและเพิ่มของคุณเอง
`IChartSeries` แสดงชุดข้อมูลภายในแผนภูมิ.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ เติมข้อมูลจุดลงในซีรีส์แรก
`addDataPointForScatterSeries` เพิ่มจุด X‑Y เดียวลงในซีรีส์กระจาย.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ ปรับแต่งประเภทซีรีส์และลักษณะเครื่องหมาย
`Marker` ควบคุมสัญลักษณ์ภาพที่ใช้สำหรับแต่ละจุดข้อมูลในซีรีส์ของแผนภูมิ.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ บันทึกงานนำเสนอ
`save` เขียนงานนำเสนอลงไฟล์ในรูปแบบที่ระบุ.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## กรณีการใช้งานทั่วไปสำหรับแผนภูมิกระจายที่ปรับแต่ง
- **Financial dashboards** – แสดงราคาหุ้นเทียบกับปริมาณ.  
- **Scientific research** – แสดงการวัดผลการทดลองพร้อมเครื่องหมายความคลาดเคลื่อน.  
- **Project management** – เปรียบเทียบความพยายามที่วางแผนกับความเป็นจริงในแต่ละงาน.

## เคล็ดลับประสิทธิภาพ
- เรียก `pres.dispose()` หลังจากบันทึกเพื่อปล่อยหน่วยความจำเนทีฟ.  
- สำหรับชุดข้อมูลขนาดใหญ่ ให้เติมข้อมูลลงใน workbook ก่อนแล้วจึงผูกซีรีส์เพื่อหลีกเลี่ยงการรีเฟรช UI ซ้ำหลายครั้ง.  
- ใช้ `IChartDataWorkbook` ตัวเดียวซ้ำเมื่อเพิ่มหลายซีรีส์เพื่อรักษาการใช้หน่วยความจำให้ต่ำ.

## คำถามที่พบบ่อย

**Q: ฉันจะเปลี่ยนสีของเครื่องหมายได้อย่างไร?**  
A: ใช้ `series.getMarker().getFillFormat().setFillColor(Color)` โดยที่ `Color` เป็นอ็อบเจกต์ `java.awt.Color` เช่น `Color.RED`.

**Q: ฉันสามารถเพิ่มซีรีส์มากกว่าสองชุดในแผนภูมิกระจายได้หรือไม่?**  
A: ได้. เรียก `chart.getChartData().getSeries().add(...)` สำหรับแต่ละซีรีส์เพิ่มเติมและเติมจุดของมันตามที่ต้องการ.

**Q: สามารถตั้งค่าตำนานแบบกำหนดเองสำหรับแต่ละซีรีส์ได้หรือไม่?**  
A: แน่นอน. หลังจากสร้างซีรีส์ ให้เรียก `series.getLegend().setText("Your Legend Text")` เพื่อแทนที่ชื่อเริ่มต้น.

**Q: ฉันจะส่งออกแผนภูมิเป็นภาพแทน PPTX ได้อย่างไร?**  
A: เรียก `chart.getImage().save("chart.png", ImageFormat.Png)` หลังจากกำหนดค่าแผนภูมิแล้ว. วิธีนี้จะสร้างไฟล์ PNG แยกออกมา.

**Q: ถ้าฉันต้องการทำให้จุดกระจายเคลื่อนไหวได้จะทำอย่างไร?**  
A: Aspose.Slides รองรับเอฟเฟกต์การเคลื่อนไหว. ใช้ `chart.getTimeline().getMainSequence().addEffect(...)` เพื่อเพิ่มการเคลื่อนไหวแบบเข้าหรือเน้นให้กับแผนภูมิหรือแต่ละซีรีส์.

---

**อัปเดตล่าสุด:** 2026-07-27  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้างและปรับแต่งแผนภูมิ PowerPoint ใน Java ด้วย Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [วิธีสร้างแผนภูมิบับเบิลใน PowerPoint ด้วย Aspose.Slides for Java (บทแนะนำ)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [สร้างและปรับแต่งแผนภูมิพร้อมเส้นแนวโน้มใน Aspose.Slides for Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}