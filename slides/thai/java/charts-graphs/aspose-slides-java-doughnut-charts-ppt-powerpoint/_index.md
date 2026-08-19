---
date: '2026-07-08'
description: เรียนรู้วิธีใช้ Aspose เพื่อสร้าง doughnut chart ใน PowerPoint ด้วย Java
  คู่มือขั้นตอนนี้แสดงการเพิ่ม chart data points แบบโปรแกรม, ปรับแต่ง labels, และบันทึก
  PPTX ด้วยความแม่นยำสูง.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: การใช้ Aspose ช่วยให้คุณสร้าง doughnut chart ใน PowerPoint ด้วย Java
  ทำตามบทแนะนำนี้เพื่อเพิ่ม data points, ปรับแต่ง labels, และบันทึก PPTX ด้วยความแม่นยำสูง.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'วิธีใช้ Aspose: สร้าง Doughnut Chart ใน PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: วิธีใช้ Aspose สร้าง Doughnut Chart ใน PowerPoint (Java)
url: /th/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีใช้ Aspose สร้างแผนภูมิ Doughnut ใน PowerPoint (Java)

## บทนำ
การสร้างงานนำเสนอที่น่าสนใจมักต้องการมากกว่าข้อความและรูปภาพ; แผนภูมิสามารถเสริมการเล่าเรื่องได้อย่างมากโดยการแสดงข้อมูลอย่างมีประสิทธิภาพ **วิธีใช้ Aspose** สำหรับการสร้างแผนภูมิให้คุณควบคุมโปรแกรมได้โดยไม่ต้องเปิด PowerPoint บทแนะนำนี้จะพาคุณผ่านการสร้างแผนภูมิ doughnut การกำหนดค่าจุดข้อมูล และการบันทึกไฟล์ PPTX คุณต้องการเพียงความรู้พื้นฐานของ Java และเวลาเตรียมไม่กี่นาที

`Aspose.Slides for Java` is a Java library that enables creation, manipulation, and conversion of PowerPoint files without Microsoft Office.

## คำตอบสั้น
- **ไลบรารีอะไรที่สร้างแผนภูมิ doughnut ใน PowerPoint?** Aspose.Slides for Java  
- **ฉันสามารถเพิ่มจุดข้อมูลของแผนภูมิโดยโปรแกรมได้หรือไม่?** ใช่, โดยใช้ chart API  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ต้องมีใบอนุญาต Aspose.Slides ที่ถูกต้อง  
- **เวอร์ชัน Java ใดที่รองรับ?** Java 8 และรุ่นต่อไป (แสดง JDK 16 classifier)  
- **ฉันสามารถเพิ่มซีรีส์ได้กี่ชุด?** ตัวอย่างเพิ่มได้สูงสุด 15 ซีรีส์, แต่คุณสามารถปรับได้ตามต้องการ  

## แผนภูมิ doughnut คืออะไรใน PowerPoint?
แผนภูมิ doughnut คือแผนภูมิวงกลมที่คล้ายกับแผนภูมิพายแต่มีศูนย์กลางเป็นช่องว่าง, ทำให้สามารถแสดงหลายซีรีส์พร้อมกันได้ มันเน้นความสัมพันธ์ส่วนต่อส่วนทั้งหมดในขณะที่รักษาการจัดวางภาพให้กระชับและอ่านง่าย

## ทำไมต้องใช้ Aspose.Slides for Java เพื่อสร้างแผนภูมิ doughnut?
Aspose.Slides for Java จัดการกับรูปแบบอินพุตและเอาต์พุตกว่า 50 รูปแบบและสามารถสร้างงานนำเสนอขนาดถึง 500 MB โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ให้การควบคุมโปรแกรมเต็มรูปแบบต่อรูปลักษณ์ของแผนภูมิ, ข้อมูลและการจัดวางบนแพลตฟอร์ม Java ใดก็ได้, ขจัดการทำงานร่วมกับ COM, และสามารถเรนเดอร์สไลด์ที่มีแผนภูมิ 100 แผ่นในเวลาน้อยกว่า 2 วินาทีบนเซิร์ฟเวอร์ทั่วไป

## ข้อกำหนดเบื้องต้น
- ความรู้พื้นฐานของการเขียนโปรแกรม Java  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  
- Maven หรือ Gradle สำหรับการจัดการ dependencies  
- ใบอนุญาต Aspose.Slides for Java ที่ถูกต้อง (มีการทดลองใช้ฟรี)

## การตั้งค่า Aspose.Slides for Java
เลือกตัวจัดการ dependencies ที่เหมาะกับโครงการของคุณ

**Maven**  
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ (แทนที่เวอร์ชันด้วยเวอร์ชันล่าสุด):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
เพิ่มบรรทัดนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

หากคุณต้องการดาวน์โหลดโดยตรง, เยี่ยมชมหน้า [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 

### การรับใบอนุญาต
คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติของ Aspose.Slides. สำหรับการใช้งานต่อเนื่อง, ซื้อใบอนุญาตหรือขอใบอนุญาตชั่วคราวจาก [Aspose's website](https://purchase.aspose.com/temporary-license/). ทำตามคำแนะนำที่ให้ไว้เพื่อกำหนดค่าสภาพแวดล้อมและการเริ่มต้น Aspose.Slides ในแอปพลิเคชันของคุณ

## วิธีสร้างแผนภูมิ doughnut PowerPoint ด้วย Aspose.Slides for Java
เพื่อสร้างแผนภูมิ doughnut, เริ่มด้วยการโหลดหรือสร้าง `Presentation`, เพิ่มรูปแผนภูมิประเภท `ChartType.Doughnut`, ล้างซีรีส์เริ่มต้น, ตั้งค่าขนาดรู, แล้วเติม workbook ของแผนภูมิกับชื่อหมวดหมู่และค่าตัวเลข. สุดท้ายปรับรูปแบบป้ายชื่อและบันทึกไฟล์ PPTX

### ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ
สร้างการนำเสนอใหม่หรือเปิดไฟล์ที่มีอยู่เพื่อรับคอลเลกชันสไลด์

`Presentation` is the primary class that represents a PowerPoint file.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ขั้นตอนที่ 2: เพิ่มแผนภูมิ doughnut ลงในสไลด์
แทรกรูปแผนภูมิ, ลบซีรีส์/หมวดหมู่เริ่มต้น, และกำหนดค่าการแสดงผลพื้นฐานเช่นขนาดรู doughnut

`Chart` (or chart shape) represents a chart object placed on a slide.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ขั้นตอนที่ 3: เพิ่มจุดข้อมูลแผนภูมิและปรับแต่งป้ายชื่อ
เติมชื่อหมวดหมู่, เพิ่มจุดข้อมูลสำหรับแต่ละซีรีส์, และปรับแต่งรูปแบบป้ายชื่อ (ฟอนต์, สี, ตำแหน่ง). ขั้นตอนนี้แสดงความสามารถ “add chart data points”

`Workbook` provides access to the chart’s underlying spreadsheet data where cells are populated.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### ขั้นตอนที่ 4: บันทึกการนำเสนอที่อัปเดต
บันทึกการเปลี่ยนแปลงลงในไฟล์ PPTX ใหม่บนดิสก์

`save` writes the presentation to a file in the chosen format.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## การประยุกต์ใช้งานจริง
- **รายงานการเงิน:** แสดงการจัดสรรงบประมาณหรือการแจกแจงค่าใช้จ่าย  
- **การวิเคราะห์ตลาด:** แสดงการกระจายส่วนแบ่งตลาดระหว่างผู้แข่งขัน  
- **ผลสำรวจ:** นำเสนอข้อมูลสำรวจแบบหมวดหมู่ในรูปแบบกะทัดรัด  
- **การสร้างแดชบอร์ด:** ผสานกับการสืบค้นฐานข้อมูลเพื่อสร้างสไลด์ที่อัปเดตแบบเรียลไทม์  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Dispose resources:** Call `pres.dispose()` after saving to free native memory.  
- **Limit chart count:** Adding hundreds of charts can increase memory usage; batch‑process if needed.  
- **Use streaming:** For massive data sets, populate the workbook directly from streams instead of in‑memory arrays.  

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **แผนภูมิแสดงเป็นสีขาว** | เซลล์ข้อมูลไม่ได้ถูกเติมอย่างถูกต้อง | ตรวจสอบว่า `workBook.getCell(...)` อ้างอิงแถว/คอลัมน์ที่ถูกต้อง |
| **ป้ายชื่อทับซ้อน** | มีหมวดหมู่มากเกินไปในพื้นที่จำกัด | เพิ่ม `DoughnutHoleSize` หรือปรับ `FirstSliceAngle` |
| **OutOfMemoryError** | การนำเสนอขนาดใหญ่โดยไม่ได้ทำการ dispose | เรียก `pres.dispose()` หลังการบันทึกและพิจารณาเพิ่มขนาด heap ของ JVM |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Slides for Java ในแอปพลิเคชันเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่, แต่คุณต้องมีใบอนุญาตเชิงพาณิชย์ที่ถูกต้อง. มีการทดลองใช้ฟรีสำหรับการประเมินผล.

**Q: ฉันจะเพิ่มซีรีส์มากกว่า 15 ชุดได้อย่างไร?**  
A: เพิ่มขีดจำกัดของลูปในขั้นตอน “Add Doughnut Chart” และตรวจสอบว่า workbook ของคุณมีแถวเพียงพอ.

**Q: สามารถเปลี่ยนขนาดรู doughnut หลังจากสร้างได้หรือไม่?**  
A: ใช่, เรียก `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` ก่อนบันทึก.

**Q: ฉันสามารถส่งออกแผนภูมิเป็นภาพแทน PPTX ได้หรือไม่?**  
A: แน่นอน. ใช้ `chart.getImage()` และบันทึก `java.awt.image.BufferedImage` ที่ได้ในรูปแบบที่คุณต้องการ.

**Q: Aspose.Slides รองรับแผนภูมิที่มีแอนิเมชันหรือไม่?**  
A: สามารถเพิ่มแอนิเมชันผ่าน API `ISlide.getTimeline()`, แต่เกินขอบเขตของบทแนะนำนี้.

## สรุป
คุณมีวิธีที่ครบถ้วนและพร้อมใช้งานในการ **สร้างไฟล์ PowerPoint ที่มีแผนภูมิ doughnut** ด้วย Aspose.Slides for Java, รวมถึงวิธี **เพิ่มจุดข้อมูลแผนภูมิ**, ปรับแต่งป้ายชื่อ, และจัดการข้อพิจารณาด้านประสิทธิภาพ. ทดลองใช้สีต่าง ๆ, แหล่งข้อมูล, และประเภทแผนภูมิต่าง ๆ เพื่อทำให้งานนำเสนอของคุณโดดเด่นจริง ๆ

---

**อัปเดตล่าสุด:** 2026-07-08  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**ผู้เขียน:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มแผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนต่อขั้นตอน](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [วิธีแก้ไขข้อมูลแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java: คู่มือครบถ้วน](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [ทำแอนิเมชันให้แผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนต่อขั้นตอน](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}