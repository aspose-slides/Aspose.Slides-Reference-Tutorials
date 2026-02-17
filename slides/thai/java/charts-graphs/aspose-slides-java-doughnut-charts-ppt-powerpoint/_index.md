---
date: '2026-02-17'
description: เรียนรู้วิธีสร้างแผนภูมิโดนัทใน PowerPoint ด้วย Aspose.Slides for Java
  และเพิ่มจุดข้อมูลของแผนภูมิโดยโปรแกรมมิ่ง ทำตามขั้นตอนง่าย ๆ และตัวอย่างโค้ด
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: สร้างแผนภูมิแบบโดนัทใน PowerPoint ด้วย Aspose.Slides สำหรับ Java
url: /th/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิโดนัท PowerPoint ด้วย Aspose.Slides for Java

## Introduction
การสร้างงานนำเสนอที่น่าสนใจมักต้องการมากกว่าข้อความและรูปภาพ; แผนภูมิสามารถเสริมการเล่าเรื่องได้อย่างมากโดยการแสดงข้อมูลอย่างมีประสิทธิภาพ อย่างไรก็ตาม นักพัฒนาจำนวนมากพบความยากลำบากในการผสานฟีเจอร์แผนภูมิแบบไดนามิกเข้าไปในไฟล์ PowerPoint ผ่านโปรแกรม คำแนะนำนี้จะแสดงวิธี **สร้างแผนภูมิโดนัท PowerPoint** ด้วย Aspose.Slides for Java—เครื่องมือที่ทรงพลังซึ่งผสมผสานความยืดหยุ่นและความง่ายในการใช้งาน

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการเริ่มต้นงานนำเสนอด้วย Aspose.Slides for Java
- คำแนะนำขั้นตอน‑ต่อ‑ขั้นตอนในการเพิ่มแผนภูมิโดนัทลงในสไลด์ของคุณ
- การกำหนดค่าจุดข้อมูลและการปรับแต่งคุณสมบัติลเบล
- การบันทึกงานนำเสนอที่แก้ไขแล้วด้วยความแม่นยำสูง

มาดูกันว่าคุณจะใช้คุณลักษณะเหล่านี้เพื่อยกระดับงานนำเสนอของคุณอย่างไร ก่อนเริ่มต้น โปรดแน่ใจว่าคุณคุ้นเคยกับแนวคิดพื้นฐานของการเขียนโปรแกรม Java

## Quick Answers
- **ไลบรารีใดที่สร้างแผนภูมิโดนัท PowerPoint?** Aspose.Slides for Java  
- **ฉันสามารถเพิ่มจุดข้อมูลของแผนภูมิผ่านโปรแกรมได้หรือไม่?** ได้, ใช้ chart API  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose.Slides ที่ถูกต้อง  
- **รองรับเวอร์ชัน Java ใดบ้าง?** Java 8 ขึ้นไป (แสดงตัวอย่าง JDK 16 classifier)  
- **สามารถเพิ่มซีรีส์ได้กี่ชุด?** ตัวอย่างเพิ่มได้สูงสุด 15 ชุด, แต่คุณสามารถปรับเพิ่มได้ตามต้องการ  

## What is a doughnut chart in PowerPoint?
แผนภูมิโดนัทเป็นรูปแบบหนึ่งของแผนภูมิพายที่มีศูนย์กลางเป็นรูพรุน ทำให้คุณสามารถแสดงหลายชุดข้อมูลในรูปแบบที่กระชับและสวยงาม เหมาะสำหรับการแสดงความสัมพันธ์ส่วน‑ต่อ‑ทั้งหมดพร้อมคงความเรียบง่ายของการออกแบบ

## Why use Aspose.Slides for Java to create doughnut charts?
- **การควบคุมเต็มรูปแบบ** บนลักษณะของแผนภูมิ, ข้อมูลและการจัดวางโดยไม่ต้องเปิด PowerPoint  
- **ไม่มี COM interop** – ทำงานได้บนทุกแพลตฟอร์มที่รองรับ Java  
- **ประสิทธิภาพสูง** สำหรับการสร้างสไลด์จำนวนมากหรือการรวมกับเว็บเซอร์วิส  
- **การปรับแต่งหลากหลาย** เช่น การระเบิดชิ้น, ขนาดรู, มุมของสไลซ์, และการจัดรูปแบบป้ายชื่อ  

## Prerequisites
- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  
- Maven หรือ Gradle สำหรับการจัดการ dependencies  
- ลิขสิทธิ์ Aspose.Slides for Java ที่ถูกต้อง (มีรุ่นทดลองฟรี)

## Setting Up Aspose.Slides for Java
เลือกตัวจัดการ dependencies ที่เหมาะกับโครงการของคุณ

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หากคุณต้องการดาวน์โหลดโดยตรง ให้เยี่ยมชมหน้า [เวอร์ชัน Aspose.Slides for Java](https://releases.aspose.com/slides/java/)  

### License Acquisition
คุณสามารถเริ่มต้นด้วยรุ่นทดลองฟรีเพื่อสำรวจฟีเจอร์ของ Aspose.Slides สำหรับการใช้งานต่อเนื่อง ให้ซื้อใบอนุญาตหรือขอใบอนุญาตชั่วคราวจาก [เว็บไซต์ของ Aspose](https://purchase.aspose.com/temporary-license/) ทำตามคำแนะนำเพื่อกำหนดค่า environment และเริ่มต้นใช้งาน Aspose.Slides ในแอปพลิเคชันของคุณ

## How to create doughnut chart PowerPoint using Aspose.Slides for Java
ต่อไปนี้เป็นคำแนะนำครบถ้วนแบบขั้นตอน‑ต่อ‑ขั้นตอน แต่ละบล็อกโค้ดจะมีคำอธิบายก่อนหน้าเพื่อให้คุณเข้าใจสิ่งที่กำลังเกิดขึ้น

### Step 1: Initialize the presentation
แรกเริ่ม โหลดไฟล์ PPTX ที่มีอยู่หรือสร้างไฟล์ใหม่ ซึ่งจะเตรียมคอลเลกชันสไลด์สำหรับการแก้ไขต่อไป

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Step 2: Add a doughnut chart to the slide
เราจะเพิ่มรูปแผนภูมิ, ลบซีรีส์/ประเภทค่าเริ่มต้นทั้งหมด, และตั้งค่าลักษณะพื้นฐานของแผนภูมิ

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

### Step 3: Add chart data points and customize labels
ที่นี่เราจะเติมประเภท, เพิ่มจุดข้อมูลสำหรับแต่ละซีรีส์, และปรับแต่งลักษณะของป้ายชื่อ นี่คือจุดที่คีย์เวิร์ด **add chart data points** มีบทบาท

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

### Step 4: Save the updated presentation
สุดท้าย บันทึกการเปลี่ยนแปลงลงไฟล์ PPTX ใหม่

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Practical Applications
แผนภูมิโดนัทสามารถนำไปใช้ในสถานการณ์จริงหลายรูปแบบ:
- **รายงานการเงิน:** แสดงการจัดสรรงบประมาณหรือการแบ่งค่าใช้จ่าย  
- **การวิเคราะห์ตลาด:** แสดงส่วนแบ่งตลาดของคู่แข่งต่าง ๆ  
- **ผลสำรวจ:** นำเสนอข้อมูลการสำรวจแบบจำแนกหมวดหมู่ในรูปแบบกระชับ  
- **การสร้างแดชบอร์ด:** ผสานกับการดึงข้อมูลจากฐานข้อมูลเพื่อสร้างสไลด์ที่อัปเดตแบบเรียลไทม์  

## Performance Considerations
- **Dispose resources**: เรียก `pres.dispose()` เมื่อทำงานเสร็จเพื่อคืนหน่วยความจำเนทีฟ  
- **Limit chart count**: การเพิ่มแผนภูมิหลายร้อยชิ้นอาจทำให้ใช้หน่วยความจำเพิ่มขึ้น; ควรประมวลผลเป็นชุดถ้าจำเป็น  
- **Use streaming**: สำหรับชุดข้อมูลขนาดใหญ่ ให้เติม workbook โดยตรงจากสตรีมแทนการใช้อาเรย์ในหน่วยความจำ  

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| **Chart appears blank** | Data cells not populated correctly | Verify that `workBook.getCell(...)` references the correct row/column indices. |
| **Labels overlap** | Too many categories in limited space | Increase `DoughnutHoleSize` or adjust `FirstSliceAngle`. |
| **OutOfMemoryError** | Large presentations without disposing | Call `pres.dispose()` after saving and consider increasing JVM heap size. |

## Frequently Asked Questions

**Q: ฉันสามารถใช้ Aspose.Slides for Java ในแอปพลิเคชันเชิงพาณิชย์ได้หรือไม่?**  
A: ได้, แต่ต้องมีลิขสิทธิ์เชิงพาณิชย์ที่ถูกต้อง รุ่นทดลองฟรีมีให้ใช้เพื่อประเมินผล  

**Q: จะเพิ่มซีรีส์มากกว่า 15 ชุดได้อย่างไร?**  
A: เพิ่มขอบเขตของลูปในขั้นตอน “Add Doughnut Chart” และตรวจสอบให้ workbook มีแถวเพียงพอ  

**Q: สามารถเปลี่ยนขนาดรูของโดนัทหลังจากสร้างได้หรือไม่?**  
A: ได้, เรียก `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` ก่อนบันทึกไฟล์  

**Q: ฉันสามารถส่งออกแผนภูมิเป็นรูปภาพแทน PPTX ได้หรือไม่?**  
A: แน่นอน ใช้ `chart.getImage()` แล้วบันทึก `java.awt.image.BufferedImage` ในรูปแบบที่ต้องการ  

**Q: Aspose.Slides รองรับแผนภูมิที่มีแอนิเมชันหรือไม่?**  
A: สามารถเพิ่มแอนิเมชันผ่าน API `ISlide.getTimeline()` แต่เกินขอบเขตของบทแนะนำนี้  

## Conclusion
คุณได้เรียนรู้วิธีการ **สร้างแผนภูมิโดนัท PowerPoint** อย่างครบถ้วนพร้อมพร้อมใช้งานในระดับผลิตด้วย Aspose.Slides for Java รวมถึงวิธี **add chart data points**, การปรับแต่งป้ายชื่อ, และการจัดการประสิทธิภาพ ทดลองปรับสี, แหล่งข้อมูล, และประเภทแผนภูมิต่าง ๆ เพื่อทำให้งานนำเสนอของคุณโดดเด่นยิ่งขึ้น  

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}