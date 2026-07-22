---
date: '2026-07-22'
description: เรียนรู้ Aspose Slides Maven Dependency เพื่อสร้าง stacked column chart
  ใน Java, เพิ่ม data labels, เปลี่ยนรูปแบบตัวเลขของ vertical axis, และส่งออกผลลัพธ์เป็นไฟล์
  PPTX
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency ช่วยให้คุณสร้าง stacked column chart
  ใน Java, ปรับแต่ง data labels, ปรับรูปแบบ vertical axis, และบันทึกเป็น PPTX – ทั้งหมดด้วยโค้ดสั้นกระชับพร้อมใช้งานในผลิตภัณฑ์
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart ใน Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart ใน Java'
url: /th/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การพึ่งพา Maven ของ Aspose Slides: แผนภูมิคอลัมน์แบบซ้อนใน Java

## บทนำ

ยกระดับงานนำเสนอของคุณด้วยการผสานการแสดงข้อมูลเชิงลึกด้วยพลังของ **Aspose.Slides for Java**. ในคู่มือนี้คุณจะ **สร้างแผนภูมิคอลัมน์แบบซ้อน** ที่ดูเป็นมืออาชีพ ไม่ว่าจะเป็นการเตรียมรายงานธุรกิจหรือการแสดงสถิติของโครงการ. เมื่อจบบทเรียนนี้คุณจะสามารถ:

- ตั้งค่าสภาพแวดล้อมของคุณด้วย **Aspose Slides Maven dependency**
- สร้างงานนำเสนอจากศูนย์
- **เพิ่มแผนภูมิเปอร์เซ็นต์‑ซ้อน** และปรับแต่งลักษณะของมัน
- **จัดรูปแบบป้ายข้อมูลของแผนภูมิ** และ **เปลี่ยนรูปแบบตัวเลขของแกนแนวตั้ง**
- **บันทึกงานนำเสนอเป็นไฟล์ PPTX** ด้วยบรรทัดโค้ดเดียว

## คำตอบสั้น

- **ต้องการไลบรารีอะไร?** เพิ่มการพึ่งพา Maven/Gradle `aspose-slides` (ดู “Aspose Slides Maven Dependency” ด้านล่าง).  
- **ประเภทแผนภูมิใดที่สร้างมุมมองแบบซ้อน?** ใช้ `ChartType.PercentsStackedColumn` สำหรับแผนภูมิคอลัมน์แบบเปอร์เซ็นต์‑ซ้อน.  
- **ฉันจะเปลี่ยนรูปแบบตัวเลขของแกนได้อย่างไร?** เรียก `IAxis.setNumberFormat()` และตั้งค่า `setNumberFormatLinkedToSource(false)`.  
- **ฉันสามารถปรับแต่งป้ายข้อมูลได้หรือไม่?** ได้ – ทำการวนลูปแต่ละ `IChartDataPoint` และกำหนด `ITextFrame` ที่กำหนดเอง.  
- **ฉันจะบันทึกไฟล์อย่างไร?** เรียก `presentation.save("output.pptx", SaveFormat.Pptx)`.

## แผนภูมิคอลัมน์แบบซ้อนคืออะไร?

แผนภูมิคอลัมน์แบบซ้อนแสดงข้อมูลหลายซีรีส์ที่ซ้อนกันในแนวตั้งในแต่ละคอลัมน์ของหมวดหมู่, โดยรูปแบบ **percentage‑stacked** จะทำให้แต่ละคอลัมน์เป็น 100 % เพื่อการเปรียบเทียบสัดส่วนที่ง่ายขึ้น. รูปแบบนี้ช่วยให้ผู้ชมประเมินได้อย่างรวดเร็วว่าคอมโพเนนต์แต่ละส่วนมีส่วนร่วมต่อทั้งหมดอย่างไรในแต่ละหมวดหมู่, ทำให้แนวโน้มและขนาดสัมพัทธ์ชัดเจนทันที.

## ทำไมต้องใช้ Aspose.Slides for Java?

Aspose.Slides for Java ช่วยให้คุณสร้าง, แก้ไข, และแปลงไฟล์ PowerPoint **โดยไม่ต้องใช้ Microsoft Office** และรองรับ **รูปแบบผลลัพธ์กว่า 50+** บน Windows, Linux, และ macOS. ไลบรารีทำงานเต็มที่บน JRE, ทำให้สามารถทำอัตโนมัติบนเซิร์ฟเวอร์และการรายงานที่มีปริมาณสูง. นอกจากนี้ยังให้การควบคุมระดับละเอียดต่อวัตถุแผนภูมิ, รูปแบบสไลด์, และคุณสมบัติของเอกสาร, ทำให้เหมาะสำหรับการสร้างงานนำเสนอระดับองค์กร.

## ข้อกำหนดเบื้องต้น

- **Java Development Kit (JDK):** 8 หรือสูงกว่า  
- **IDE:** IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขที่รองรับ Java ใดก็ได้  
- **เครื่องมือสร้าง:** Maven หรือ Gradle (ไม่บังคับแต่แนะนำ)  
- **ความรู้พื้นฐานของ Java** – คุณควรคุ้นเคยกับคลาสและเมธอด  

## การตั้งค่า Aspose.Slides for Java

เพื่อเริ่มต้น, เพิ่มไลบรารี Aspose.Slides ลงในโปรเจกต์ของคุณ.

### การพึ่งพา Maven ของ Aspose Slides

เพิ่มส่วนต่อไปนี้ในไฟล์ `pom.xml` ของคุณ (นี่คือ **aspose slides maven dependency** ที่คุณต้องการ):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ทางเลือก Gradle

หากคุณต้องการใช้ Gradle, ให้เพิ่มบรรทัดนี้ในไฟล์ `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง

หรือคุณสามารถดาวน์โหลด JAR ล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การรับใบอนุญาต

คุณสามารถเริ่มต้นด้วยการทดลองใช้งานฟรีเพื่อสำรวจคุณสมบัติของ Aspose.Slides. เพื่อขจัดข้อจำกัดการประเมิน, พิจารณาได้รับใบอนุญาตชั่วคราวหรือซื้อใบอนุญาต.

- **Free Trial:** เข้าถึงคุณสมบัติจำกัดโดยไม่มีค่าใช้จ่ายทันที.  
- **Temporary License:** ขอผ่าน [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Purchase:** เยี่ยมชมหน้าการซื้อเพื่อเข้าถึงเต็มรูปแบบ.

### การเริ่มต้นพื้นฐาน

`Presentation` คือคลาสหลักของ Aspose.Slides ที่แทนไฟล์ PowerPoint ในหน่วยความจำ. ตัวอย่างโค้ดขนาดเล็กต่อไปนี้แสดงวิธีสร้างอ็อบเจ็กต์ `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## คู่มือการดำเนินการ

### สร้างงานนำเสนอและเพิ่มสไลด์

**ภาพรวม:**  
แรกสุด, เราจะสร้างงานนำเสนอเปล่าและตรวจสอบว่ามีสไลด์อยู่.

#### ขั้นตอนที่ 1: เริ่มต้นอ็อบเจ็กต์ Presentation

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### ขั้นตอนที่ 2: บันทึกงานนำเสนอ

```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### เพิ่มแผนภูมิเปอร์เซ็นต์ซ้อนลงในสไลด์

**ภาพรวม:**  
ต่อไปเราจะวาง **แผนภูมิเปอร์เซ็นต์ซ้อน** ลงบนสไลด์แรก.

`ChartType.PercentsStackedColumn` ระบุประเภทแผนภูมิคอลัมน์แบบเปอร์เซ็นต์‑ซ้อน.

#### ขั้นตอนที่ 1: เริ่มต้นและเข้าถึงสไลด์

```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### ขั้นตอนที่ 2: เพิ่มแผนภูมิลงสไลด์

```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### กำหนดรูปแบบตัวเลขของแกนแผนภูมิ

**ภาพรวม:**  
เพื่อความอ่านง่ายขึ้น เราจะ **เปลี่ยนรูปแบบของแกนแนวตั้ง** ให้แสดงเป็นเปอร์เซ็นต์.

`IAxis` คืออินเทอร์เฟซที่แทนแกนของแผนภูมิ, ให้การปรับรูปแบบและสเกล.

#### ขั้นตอนที่ 1: เพิ่มและเข้าถึงแผนภูมิ

```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### ขั้นตอนที่ 2: ตั้งค่ารูปแบบตัวเลขที่กำหนดเอง

```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### เพิ่มซีรีส์และจุดข้อมูลลงในแผนภูมิ

**ภาพรวม:**  
เราจะเติมข้อมูลตัวอย่างลงในแผนภูมิ.

#### ขั้นตอนที่ 1: เริ่มต้นงานนำเสนอและแผนภูมิ

```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### ขั้นตอนที่ 2: เพิ่มซีรีส์ข้อมูล

```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### กำหนดสีเติมของซีรีส์

**ภาพรวม:**  
ให้แต่ละซีรีส์มีสีที่แตกต่างกันเพื่อทำให้แผนภูมิง่ายต่อการอ่าน.

#### ขั้นตอนที่ 1: เริ่มต้นและเข้าถึงแผนภูมิ

```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### ขั้นตอนที่ 2: ตั้งค่าสีเติม

```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### กำหนดรูปแบบป้ายข้อมูล

**ภาพรวม:**  
ตอนนี้เราจะ **จัดรูปแบบป้ายข้อมูลของแผนภูมิ** ให้แสดงข้อความที่กำหนดเอง.

`IChartDataPoint` แทนจุดข้อมูลแต่ละจุดในซีรีส์ของแผนภูมิ, และ `ITextFrame` เก็บข้อความป้าย.

#### ขั้นตอนที่ 1: เข้าถึงซีรีส์และจุดข้อมูลของแผนภูมิ

```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### ขั้นตอนที่ 2: ปรับแต่งป้ายข้อมูล

```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## ปัญหาทั่วไปและวิธีแก้

- **แผนภูมิแสดงว่างเปล่า:** ตรวจสอบว่าคุณได้เพิ่มอย่างน้อยหนึ่งซีรีส์และจุดข้อมูลก่อนบันทึก.  
- **ตัวเลขของแกนไม่แสดงเป็นเปอร์เซ็นต์:** จำไว้ว่าให้ตั้งค่า `verticalAxis.setNumberFormatLinkedToSource(false)`; มิฉะนั้นรูปแบบที่กำหนดเองจะถูกละเลย.  
- **ข้อความการประเมินใบอนุญาต:** ใช้ไฟล์ใบอนุญาตที่ถูกต้องก่อนสร้างอ็อบเจ็กต์ `Presentation` เพื่อปิดข้อความประเมิน.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้โค้ดนี้กับ Java 11 หรือใหม่กว่าได้หรือไม่?**  
**ตอบ:** ใช่. ไลบรารีรองรับ JDK 8+; เพียงใช้ classifier ที่เหมาะสม (เช่น `jdk16` สำหรับ JDK 16 หรือใหม่กว่า).

**ถาม: ฉันจะส่งออกแผนภูมิเป็นภาพแทน PPTX ได้อย่างไร?**  
**ตอบ:** ใช้ `chart.getImage().save("chart.png", ImageFormat.Png);` หลังจากเพิ่มแผนภูมิลงสไลด์.

**ถาม: สามารถเพิ่มคำอธิบาย (legend) ให้กับแผนภูมิคอลัมน์แบบซ้อนได้หรือไม่?**  
**ตอบ:** แน่นอน. เรียก `chart.getChartTitle().addTextFrameForOverriding("My Chart");` และกำหนดค่า `chart.getLegend()` ตามต้องการ.

**ถาม: ถ้าฉันต้องการอัปเดตข้อมูลหลังจากสร้างงานนำเสนอแล้วจะทำอย่างไร?**  
**ตอบ:** คุณสามารถแก้ไขเซลล์ใน `ChartDataWorkbook` แล้วเรียก `chart.refresh();` เพื่อให้การเปลี่ยนแปลงแสดงผล.

**ถาม: Aspose.Slides ทำงานบนเซิร์ฟเวอร์ Linux ได้หรือไม่?**  
**ตอบ:** ใช่. ไลบรารีเป็น Java แท้และทำงานบน OS ใดก็ได้ที่มี JRE ที่เข้ากันได้.

## สรุป

โดยทำตามคู่มือนี้คุณได้เรียนรู้วิธี **สร้างแผนภูมิคอลัมน์แบบซ้อน** ใน Java ด้วย **Aspose Slides Maven dependency**, ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการปรับสไตล์ภาพอย่างละเอียด. ทดลองใช้ชุดข้อมูล, สี, และรูปแบบป้ายที่แตกต่างเพื่อทำให้รายงานของคุณโดดเด่นจริงๆ.

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [วิธีตั้งค่ารูปแบบตัวเลขในจุดข้อมูลของแผนภูมิโดยใช้ Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [วิธีเพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}