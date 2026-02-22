---
date: '2026-02-22'
description: เรียนรู้วิธีสร้างแผนภูมิคอลัมน์แบบซ้อนใน Java ด้วย Aspose.Slides การสอนนี้ครอบคลุมการใช้
  Aspose Slides Maven dependency การเพิ่มแผนภูมิแบบซ้อนเปอร์เซ็นต์ การจัดรูปแบบป้ายข้อมูลของแผนภูมิ
  และการบันทึกงานนำเสนอเป็นไฟล์ PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: วิธีสร้างแผนภูมิคอลัมน์แบบซ้อนใน Java ด้วย Aspose.Slides – คู่มือครบถ้วน
url: /th/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิคอลัมน์ซ้อนใน Java ด้วย Aspose.Slides – คู่มือฉบับสมบูรณ์

## บทนำ

ยกระดับการนำเสนอของคุณด้วยการผสานภาพข้อมูลเชิงลึกโดยใช้พลังของ Aspose.Slides for Java ในคู่มือนี้คุณจะ **สร้างสไลด์แผนภูมิคอลัมน์ซ้อนเปอร์เซ็นต์** ที่ดูเป็นมืออาชีพ ไม่ว่าจะเป็นการเตรียมรายงานธุรกิจหรือการแสดงสถิติของโครงการ เมื่อจบบทเรียนนี้คุณจะสามารถ:

- ตั้งค่าสภาพแวดล้อมด้วยการพึ่งพา Aspose Slides Maven
- สร้างงานนำเสนอจากศูนย์
- **เพิ่มแผนภูมิคอลัมน์ซ้อนเปอร์เซ็นต์** และปรับแต่งลักษณะการแสดงผล
- **จัดรูปแบบป้ายข้อมูลของแผนภูมิ** และ **เปลี่ยนรูปแบบแกนแนวตั้ง**
- **บันทึกงานนำเสนอเป็น PPTX** ด้วยบรรทัดโค้ดเดียว

มาผ่านแต่ละขั้นตอนเพื่อให้คุณเริ่มสร้างการนำเสนอที่น่าสนใจได้ทันที

## คำตอบอย่างรวดเร็ว
- **ต้องใช้ไลบรารีอะไร?** การพึ่งพา Maven/Gradle `aspose-slides` (ดู “aspose slides maven dependency” ด้านล่าง)  
- **ใช้ประเภทแผนภูมิใด?** `ChartType.PercentsStackedColumn` สำหรับแผนภูมิคอลัมน์ซ้อนเปอร์เซ็นต์  
- **จะเปลี่ยนรูปแบบตัวเลขของแกนอย่างไร?** ใช้ `IAxis.setNumberFormat()` และปิดการเชื่อมโยงกับแหล่งข้อมูล  
- **สามารถปรับแต่งป้ายข้อมูลได้หรือไม่?** ได้ – วนลูปผ่านอ็อบเจกต์ `IChartDataPoint` แล้วตั้งค่า `ITextFrame` ที่กำหนดเอง  
- **จะบันทึกไฟล์อย่างไร?** เรียก `presentation.save("output.pptx", SaveFormat.Pptx)`

## แผนภูมิคอลัมน์ซ้อนคืออะไร?
แผนภูมิคอลัมน์ซ้อนแสดงหลายชุดข้อมูลที่ซ้อนกันในคอลัมน์แนวตั้ง เมื่อใช้รูปแบบ **เปอร์เซ็นต์‑ซ้อน** แต่ละคอลัมน์จะรวมเป็น 100 % เสมอ ทำให้เปรียบเทียบส่วนแบ่งสัดส่วนระหว่างหมวดหมู่ได้ง่าย

## ทำไมต้องใช้ Aspose.Slides สำหรับ Java?
Aspose.Slides ให้ API แบบ pure‑Java ที่ทำงานบนทุกแพลตฟอร์มโดยไม่ต้องติดตั้ง Microsoft Office ให้การควบคุมแผนภูมิอย่างละเอียด รองรับรูปแบบไฟล์หลากหลาย และช่วยให้คุณสร้างงานนำเสนอโดยอัตโนมัติ – เหมาะสำหรับการรายงานอัตโนมัติหรือการสร้างเอกสารบนเซิร์ฟเวอร์

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK):** 8 หรือสูงกว่า  
- **IDE:** IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไข Java ใด ๆ  
- **Build Tool:** Maven หรือ Gradle (ไม่บังคับแต่แนะนำ)  
- **ความรู้พื้นฐาน Java** – ควรคุ้นเคยกับคลาสและเมธอด  

## การตั้งค่า Aspose.Slides สำหรับ Java
เริ่มต้นโดยเพิ่มไลบรารี Aspose.Slides เข้าในโปรเจกต์ของคุณ

### การพึ่งพา Maven ของ Aspose Slides
เพิ่มโค้ดต่อไปนี้ในไฟล์ `pom.xml` (นี่คือ **aspose slides maven dependency** ที่คุณต้องใช้):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ทางเลือก Gradle
หากคุณใช้ Gradle ให้เพิ่มบรรทัดนี้ใน `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลด JAR ล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)  

### การรับใบอนุญาต
คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติของ Aspose.Slides หากต้องการลบข้อจำกัดการประเมินผล ให้พิจารณาใบอนุญาตชั่วคราวหรือใบอนุญาตที่ซื้อแล้ว

- **ทดลองใช้ฟรี:** เข้าถึงฟีเจอร์ที่จำกัดโดยไม่มีค่าใช้จ่ายทันที  
- **ใบอนุญาตชั่วคราว:** ขอได้จาก [Aspose’s site](https://purchase.aspose.com/temporary-license/)  
- **การซื้อ:** เยี่ยมชมหน้าการซื้อเพื่อรับการเข้าถึงเต็มรูปแบบ  

### การเริ่มต้นพื้นฐาน
นี่คือตัวอย่างโค้ดสั้น ๆ ที่แสดงวิธีสร้างอ็อบเจกต์ `Presentation`:

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
ขั้นแรกเราจะสร้างงานนำเสนอเปล่าและตรวจสอบว่ามีสไลด์อยู่

#### ขั้นตอนที่ 1: เริ่มต้นอ็อบเจกต์ Presentation
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

### เพิ่มแผนภูมิคอลัมน์ซ้อนเปอร์เซ็นต์ลงในสไลด์
**ภาพรวม:**  
ต่อไปเราจะวาง **แผนภูมิคอลัมน์ซ้อนเปอร์เซ็นต์** บนสไลด์แรก

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

#### ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### ปรับแต่งรูปแบบตัวเลขของแกนแผนภูมิ
**ภาพรวม:**  
เพื่อความอ่านง่าย เราจะ **เปลี่ยนรูปแบบแกนแนวตั้ง** ให้แสดงเป็นเปอร์เซ็นต์

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
เราจะเติมข้อมูลตัวอย่างลงในแผนภูมิ

#### ขั้นตอนที่ 1: เริ่มต้น Presentation และแผนภูมิ
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

### จัดรูปแบบสีเติมของซีรีส์
**ภาพรวม:**  
ให้แต่ละซีรีส์มีสีที่แตกต่างกันเพื่อให้อ่านง่ายขึ้น

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

### จัดรูปแบบป้ายข้อมูล
**ภาพรวม:**  
ตอนนี้เราจะ **จัดรูปแบบป้ายข้อมูลของแผนภูมิ** ให้แสดงข้อความที่กำหนดเอง

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
- **แผนภูม้าว่างเปล่า:** ตรวจสอบว่าคุณได้เพิ่มอย่างน้อยหนึ่งซีรีส์และจุดข้อมูลก่อนบันทึก  
- **ตัวเลขบนแกนไม่แสดงเป็นเปอร์เซ็นต์:** อย่าลืมตั้งค่า `verticalAxis.setNumberFormatLinkedToSource(false)` มิฉะนั้นรูปแบบที่กำหนดเองจะถูกละเลย  
- **ข้อความการประเมินผลของใบอนุญาต:** โหลดไฟล์ใบอนุญาตที่ถูกต้องก่อนสร้างอ็อบเจกต์ `Presentation` เพื่อปิดการแสดงแบนเนอร์การประเมินผล  

## คำถามที่พบบ่อย

**ถาม: สามารถใช้โค้ดนี้กับ Java 11 หรือใหม่กว่าได้หรือไม่?**  
ตอบ: ได้ ไลบรารีรองรับ JDK 8+; เพียงใช้ classifier ที่เหมาะสม (เช่น `jdk16` สำหรับ JDK 16 หรือใหม่กว่า)

**ถาม: จะส่งออกแผนภูมิเป็นภาพแทน PPTX อย่างไร?**  
ตอบ: ใช้ `chart.getImage().save("chart.png", ImageFormat.Png);` หลังจากเพิ่มแผนภูมิเข้าในสไลด์

**ถาม: สามารถเพิ่ม legend ให้กับแผนภูมิคอลัมน์ซ้อนได้หรือไม่?**  
ตอบ: แน่นอน เรียก `chart.getChartTitle().addTextFrameForOverriding("My Chart");` แล้วกำหนดค่า `chart.getLegend()` ตามต้องการ

**ถาม: หากต้องการอัปเดตข้อมูลหลังจากสร้างงานนำเสนอแล้วทำอย่างไร?**  
ตอบ: สามารถแก้ไขเซลล์ใน `ChartDataWorkbook` แล้วเรียก `chart.refresh();` เพื่อให้การเปลี่ยนแปลงแสดงผล

**ถาม: Aspose.Slides ทำงานบนเซิร์ฟเวอร์ Linux หรือไม่?**  
ตอบ: ใช่ ไลบรารีเป็น pure Java จึงทำงานบน OS ใดก็ได้ที่มี JRE ที่เข้ากันได้

## สรุป
โดยทำตามคู่มือนี้คุณได้เรียนรู้วิธี **สร้างแผนภูมิคอลัมน์ซ้อน** ในงานนำเสนอด้วย Aspose.Slides for Java ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการปรับสไตล์ภาพอย่างละเอียด ทดลองใช้ชุดข้อมูล สี และรูปแบบป้ายต่าง ๆ เพื่อทำให้รายงานของคุณโดดเด่นจริง ๆ

---

**อัปเดตล่าสุด:** 2026-02-22  
**ทดสอบด้วย:** Aspose.Slides 25.4 (classifier jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}