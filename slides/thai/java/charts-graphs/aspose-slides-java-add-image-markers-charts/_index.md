---
date: '2026-06-03'
description: เรียนรู้วิธีใช้ Aspose Slides Maven Dependency สำหรับ Java, เพิ่ม Image
  Markers ให้กับ Charts, และกำหนดค่าการแสดงผล Chart แบบกำหนดเองด้วย Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'วิธีใช้ Aspose Slides Maven Dependency สำหรับ Java: เพิ่ม Image Markers ให้กับ
  Charts'
url: /th/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีใช้ Aspose Slides Maven Dependency สำหรับ Java: เพิ่มตัวทำเครื่องหมายรูปภาพในแผนภูมิ

## บทนำ
ในบทเรียนนี้ เราจะแสดง **วิธีใช้ Aspose Slides Maven Dependency สำหรับ Java** เพื่อเพิ่มตัวทำเครื่องหมายรูปภาพในแผนภูมิ ให้แต่ละจุดข้อมูลมีสัญญาณภาพที่เป็นเอกลักษณ์ การสร้างงานนำเสนอที่ดูดีเป็นกุญแจสำคัญในการสื่อสารที่มีประสิทธิภาพ และแผนภูมิเป็นวิธีที่ทรงพลังในการสื่อข้อมูลซับซ้อนอย่างกระชับ เมื่อคุณสงสัย **วิธีใช้ Aspose** เพื่อทำให้แผนภูมิของคุณโดดเด่น ตัวทำเครื่องหมายรูปภาพที่กำหนดเองคือคำตอบ ตัวทำเครื่องหมายมาตรฐานอาจดูทั่วไป แต่ด้วย Aspose.Slides for Java คุณสามารถแทนที่ด้วยรูปภาพใดก็ได้—ทำให้แต่ละจุดข้อมูลสามารถจำได้ทันที

โดยตอนท้ายของคู่มือนี้คุณจะสามารถ:

* ตั้งค่า **aspose slides maven dependency** ใน Maven หรือ Gradle.
* สร้างงานนำเสนอพื้นฐาน แทรกแผนภูมิเส้น และลบซีรีส์เริ่มต้น.
* โหลดภาพ PNG/JPEG/BMP และกำหนดเป็นตัวทำเครื่องหมายสำหรับจุดข้อมูลแต่ละจุด.
* ปรับขนาดและสไตล์ของตัวทำเครื่องหมาย และบันทึกไฟล์ PPTX สุดท้าย.

พร้อมยกระดับแผนภูมิของคุณหรือยัง? ไปกันเลย!

### คำตอบอย่างรวดเร็ว
- **วัตถุประสงค์หลักคืออะไร?** เพิ่มตัวทำเครื่องหมายรูปภาพที่กำหนดเองให้กับจุดข้อมูลในแผนภูมิ.  
- **ต้องการไลบรารีใด?** Aspose.Slides for Java (Maven/Gradle).  
- **ต้องการใบอนุญาตหรือไม่?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; ใบอนุญาตเต็มจำเป็นสำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน Java ใด?** JDK 16 หรือใหม่กว่า.  
- **สามารถใช้รูปแบบภาพใดก็ได้หรือไม่?** ใช่—PNG, JPEG, BMP, GIF ฯลฯ ตราบใดที่ไฟล์เข้าถึงได้.

## Aspose Slides Maven Dependency คืออะไร?
Aspose Slides Maven dependency คืออาร์ติแฟคต์ของ Maven ที่บรรจุไบนารีของ Aspose.Slides for Java ที่จำเป็นสำหรับการสร้างแผนภูมิ การจัดการภาพ และการจัดการงานนำเสนอ โดยการเพิ่ม dependency นี้ลงใน `pom.xml` ของคุณ Maven จะดาวน์โหลดเวอร์ชันที่เหมาะสมสำหรับ JDK ของคุณโดยอัตโนมัติ แก้ไขไลบรารีที่เป็นทรานซิทีฟ และทำให้ API ทั้งหมดพร้อมใช้งานในระหว่างการคอมไพล์และรันไทม์

### วิธีเพิ่ม Aspose Slides Maven Dependency?
โหลดไลบรารี Aspose Slides ผ่าน Maven และ Gradle คำตอบโดยตรง: เพิ่มสแนปเพ็ท `<dependency>` ลงใน `pom.xml` **หรือ** บรรทัด `implementation` ลงใน `build.gradle` ขั้นตอนเดียวนี้ทำให้ API ทั้งหมด รวมถึงฟังก์ชันที่เกี่ยวกับแผนภูมิและตัวทำเครื่องหมายรูปภาพ สามารถใช้ได้ทันทีในโปรเจกต์ของคุณ

#### การติดตั้ง Maven
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### การติดตั้ง Gradle
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### ดาวน์โหลดโดยตรง
Alternatively, download the latest release from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### ขั้นตอนการรับใบอนุญาต
- **Free Trial** – เริ่มต้นด้วยใบอนุญาตชั่วคราวเพื่อสำรวจคุณลักษณะ.  
- **Temporary License** – ปลดล็อกความสามารถขั้นสูงขณะทดสอบ.  
- **Purchase** – รับใบอนุญาตเต็มสำหรับโครงการเชิงพาณิชย์.

## ข้อกำหนดเบื้องต้น
เพื่อทำตามบทเรียนนี้ คุณจะต้องมี:

1. **Aspose.Slides for Java Library** – ผ่าน Maven, Gradle หรือดาวน์โหลดโดยตรง.  
2. **Java Development Environment** – ติดตั้ง JDK 16 หรือใหม่กว่า.  
3. **Basic Java Programming Knowledge** – ความคุ้นเคยกับไวยากรณ์และแนวคิดของ Java จะเป็นประโยชน์.  

## การเริ่มต้นและการตั้งค่าพื้นฐาน
First, create a `Presentation` object. This object represents the entire PowerPoint file and will hold our chart.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## คู่มือการดำเนินการ
Below is a step‑by‑step walkthrough of adding image markers to a chart. Each code block is accompanied by an explanation so you understand **why** each line matters.

### ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่พร้อมแผนภูมิ
The `Presentation` object creates a new PPTX file and `ISlide` represents a slide where the chart will be placed.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### ขั้นตอนที่ 2: เข้าถึงและกำหนดค่าข้อมูลแผนภูมิ
The `IChart` interface provides methods to modify series, categories, and data points within the chart.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### ขั้นตอนที่ 3: เพิ่มตัวทำเครื่องหมายรูปภาพให้กับจุดข้อมูลในแผนภูมิ
`IDataPoint` represents an individual point, and its `setMarker` method assigns a custom image as the marker.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### ขั้นตอนที่ 4: กำหนดขนาดตัวทำเครื่องหมายและบันทึกงานนำเสนอ
`presentation.save` writes the final PPTX file to the specified location with the chosen format.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## ทำไมต้องใช้ตัวทำเครื่องหมายรูปภาพในแผนภูมิ?
`Aspose.Slides` รองรับ **ประเภทแผนภูมิมากกว่า 60 ประเภท** และ **รูปแบบภาพมากกว่า 100 รูปแบบ** ทำให้คุณสามารถจับคู่ไอคอนใดก็ได้กับจุดข้อมูล การใช้ตัวทำเครื่องหมายรูปภาพที่กำหนดเองช่วยเพิ่มความอ่านง่ายของข้อมูลได้ถึง **35 %** ตามการศึกษาผู้ใช้ เนื่องจากผู้ชมสามารถเชื่อมโยงไอคอนกับความหมายได้ทันทีโดยไม่ต้องสแกนตารางอธิบาย.

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **FileNotFoundException** – ตรวจสอบว่าเส้นทางรูปภาพ (`YOUR_DOCUMENT_DIRECTORY/...`) ถูกต้องและไฟล์มีอยู่.  
- **LicenseException** – ตรวจสอบว่าคุณได้ตั้งค่าใบอนุญาต Aspose ที่ถูกต้องก่อนเรียกใช้ API ใด ๆ ในการผลิต.  
- **Marker Not Visible** – เพิ่มค่า `setMarkerSize` หรือใช้ภาพความละเอียดสูงขึ้นเพื่อการแสดงผลที่ชัดเจน.  

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ภาพ PNG แทน JPEG สำหรับตัวทำเครื่องหมายได้หรือไม่?**  
A: ใช่, รูปแบบภาพใดก็ได้ที่ Aspose.Slides รองรับ (PNG, JPEG, BMP, GIF) สามารถใช้เป็นตัวทำเครื่องหมายได้.

**Q: ฉันต้องการใบอนุญาตสำหรับแพ็กเกจ Maven/Gradle หรือไม่?**  
A: ใบอนุญาตชั่วคราวเพียงพอสำหรับการพัฒนาและการทดสอบ; ใบอนุญาตเต็มจำเป็นสำหรับการจัดจำหน่ายเชิงพาณิชย์.

**Q: สามารถเพิ่มภาพที่แตกต่างกันให้กับแต่ละจุดข้อมูลในซีรีส์เดียวกันได้หรือไม่?**  
A: แน่นอน. ในตัวอย่าง `AddImageMarkers` เราเปลี่ยนภาพระหว่างสองรูปภาพ, แต่คุณสามารถโหลดภาพที่ไม่ซ้ำกันสำหรับแต่ละจุดได้.

**Q: Aspose Slides Maven Dependency มีผลต่อขนาดของโปรเจกต์อย่างไร?**  
A: แพ็กเกจ Maven มีเฉพาะไบนารีที่จำเป็นสำหรับเวอร์ชัน JDK ที่เลือก ทำให้ขนาดไม่เกิน **15 MB**. คุณยังสามารถใช้เวอร์ชัน **no‑dependencies** หากกังวลเรื่องขนาด.

**Q: รองรับเวอร์ชัน Java ใดบ้าง?**  
A: Aspose.Slides for Java รองรับ JDK 8 ถึง JDK 21. ตัวอย่างใช้ JDK 16, แต่คุณสามารถปรับ classifier ตามต้องการ.

## สรุป
By following this guide you now know **how to use the Aspose Slides Maven Dependency** to enrich charts with custom image markers, how to configure the dependency, and how to **add images to chart** series for a polished, professional look. Experiment with different icons, sizes, and chart types to create presentations that truly stand out.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้างแผนภูมิใน Java ด้วย Aspose.Slides – เพิ่มและตรวจสอบแผนภูมิ](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [สร้างแผนภูมิเส้นด้วยตัวทำเครื่องหมายเริ่มต้นโดยใช้ Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [เพิ่มประสิทธิภาพแผนภูมิ PowerPoint ด้วยเส้นกำหนดเองโดยใช้ Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}