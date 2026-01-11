---
date: '2026-01-11'
description: เรียนรู้วิธีใช้ Aspose Slides สำหรับ Java, เพิ่มเครื่องหมายรูปภาพในแผนภูมิ,
  และกำหนดค่า Aspose Slides Maven dependency เพื่อสร้างภาพแผนภูมิแบบกำหนดเอง.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'วิธีใช้ Aspose Slides Java: เพิ่มเครื่องหมายรูปภาพในแผนภูมิ'
url: /th/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีใช้ Aspose Slides Java: เพิ่มเครื่องหมายรูปภาพในแผนภูมิ

## บทนำ
การสร้างงานนำเสนอที่ดูสวยงามเป็นกุญแจสำคัญของการสื่อสารที่มีประสิทธิภาพ และแผนภูมิเป็นเครื่องมือที่ทรงพลังในการสื่อข้อมูลซับซ้อนอย่างกระชับ เมื่อคุณสงสัย **how to use Aspose** เพื่อทำให้แผนภูมิของคุณโดดเด่น เครื่องหมายรูปภาพแบบกำหนดเองคือคำตอบ เครื่องหมายมาตรฐานอาจดูทั่วไป แต่ด้วย Aspose.Slides for Java คุณสามารถแทนที่ด้วยรูปภาพใดก็ได้—ทำให้แต่ละจุดข้อมูลเป็นที่จดจำทันที

ในบทแนะนำนี้ เราจะเดินผ่านกระบวนการทั้งหมดของการเพิ่มเครื่องหมายรูปภาพในแผนภูมิเส้น ตั้งแต่การตั้งค่า **Aspose Slides Maven dependency** ไปจนถึงการโหลดรูปภาพและนำไปใช้กับจุดข้อมูล เมื่อจบคุณจะคุ้นเคยกับ **how to add markers** วิธี **add images to chart** series และคุณจะมีตัวอย่างโค้ดที่พร้อมรัน

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า Aspose.Slides for Java (รวมถึง Maven/Gradle)
- การสร้างงานนำเสนอและแผนภูมิพื้นฐาน
- การเพิ่มเครื่องหมายรูปภาพในจุดข้อมูลของแผนภูมิ
- การกำหนดขนาดและสไตล์ของเครื่องหมายเพื่อการแสดงผลที่ดีที่สุด

พร้อมที่จะยกระดับแผนภูมิของคุณหรือยัง? มาดำดิ่งเข้าสู่ข้อกำหนดเบื้องต้นก่อนเริ่มกันเลย!

### คำตอบอย่างรวดเร็ว
- **What is the primary purpose?** เพิ่มเครื่องหมายรูปภาพแบบกำหนดเองในจุดข้อมูลของแผนภูมิ.  
- **Which library is required?** Aspose.Slides for Java (Maven/Gradle).  
- **Do I need a license?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; ต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง.  
- **Which Java version is supported?** JDK 16 หรือใหม่กว่า.  
- **Can I use any image format?** ได้—PNG, JPEG, BMP, ฯลฯ ตราบใดที่ไฟล์เข้าถึงได้.

### ข้อกำหนดเบื้องต้น
เพื่อทำตามบทแนะนำนี้ คุณจะต้องมี:
1. **Aspose.Slides for Java Library** – รับได้ผ่าน Maven, Gradle หรือดาวน์โหลดโดยตรง.  
2. **Java Development Environment** – ติดตั้ง JDK 16 หรือใหม่กว่า.  
3. **Basic Java Programming Knowledge** – ความคุ้นเคยกับไวยากรณ์และแนวคิดของ Java จะเป็นประโยชน์.

## Aspose Slides Maven Dependency คืออะไร?
Maven dependency จะดึงไบนารีที่เหมาะสมสำหรับเวอร์ชัน Java ของคุณ การเพิ่มลงใน `pom.xml` ของคุณจะทำให้ไลบรารีพร้อมใช้งานในระหว่างการคอมไพล์และรันไทม์

### การติดตั้ง Maven
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การติดตั้ง Gradle
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### ขั้นตอนการรับใบอนุญาต
- **Free Trial** – เริ่มต้นด้วยใบอนุญาตชั่วคราวเพื่อสำรวจคุณลักษณะ.  
- **Temporary License** – ปลดล็อกความสามารถขั้นสูงขณะทดสอบ.  
- **Purchase** – รับใบอนุญาตเต็มสำหรับโครงการเชิงพาณิชย์.

## การเริ่มต้นและตั้งค่าพื้นฐาน
ขั้นแรก สร้างอ็อบเจ็กต์ `Presentation` อ็อบเจ็กต์นี้แทนไฟล์ PowerPoint ทั้งหมดและจะเก็บแผนภูมิของเรา

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
ด้านล่างเป็นขั้นตอนแบบละเอียดของการเพิ่มเครื่องหมายรูปภาพในแผนภูมิ แต่ละบล็อกโค้ดมาพร้อมกับคำอธิบายเพื่อให้คุณเข้าใจ **ทำไม** แต่ละบรรทัดจึงสำคัญ

### ขั้นตอนที่ 1: สร้าง Presentation ใหม่พร้อมแผนภูมิ
We add a line chart with default markers to the first slide.

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
We clear any default series and add our own series, preparing the worksheet for custom data points.

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

### ขั้นตอนที่ 3: เพิ่มเครื่องหมายรูปภาพในจุดข้อมูลของแผนภูมิ  
Here we demonstrate **how to add markers** using pictures. Replace the placeholder paths with the actual location of your images.

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

### ขั้นตอนที่ 4: กำหนดขนาดเครื่องหมายและบันทึก Presentation  
We adjust the marker style for better visibility and write the final PPTX file.

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

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **FileNotFoundException** – ตรวจสอบว่าเส้นทางรูปภาพ (`YOUR_DOCUMENT_DIRECTORY/...`) ถูกต้องและไฟล์มีอยู่.  
- **LicenseException** – ตรวจสอบว่าคุณได้ตั้งค่าใบอนุญาต Aspose ที่ถูกต้องก่อนเรียกใช้ API ใด ๆ ในการผลิต.  
- **Marker Not Visible** – เพิ่มค่า `setMarkerSize` หรือใช้รูปภาพความละเอียดสูงกว่าเพื่อการแสดงผลที่ชัดเจนขึ้น.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ภาพ PNG แทน JPEG สำหรับเครื่องหมายได้หรือไม่?**  
A: ใช่, รูปแบบภาพใด ๆ ที่ Aspose.Slides รองรับ (PNG, JPEG, BMP, GIF) สามารถใช้เป็นเครื่องหมายได้.

**Q: ฉันต้องการใบอนุญาตสำหรับแพ็กเกจ Maven/Gradle หรือไม่?**  
A: ใบอนุญาตชั่วคราวเพียงพอสำหรับการพัฒนาและการทดสอบ; ใบอนุญาตเต็มจำเป็นสำหรับการจัดจำหน่ายเชิงพาณิชย์.

**Q: สามารถเพิ่มรูปภาพที่แตกต่างกันให้กับแต่ละจุดข้อมูลในซีรีส์เดียวกันได้หรือไม่?**  
A: แน่นอน. ในตัวอย่าง `AddImageMarkers` เราสลับระหว่างสองรูปภาพ, แต่คุณสามารถโหลดรูปภาพเฉพาะสำหรับแต่ละจุดได้.

**Q: `aspose slides maven dependency` มีผลต่อขนาดของโครงการอย่างไร?**  
A: แพ็กเกจ Maven จะรวมเฉพาะไบนารีที่จำเป็นสำหรับ JDK เวอร์ชันที่เลือก, ทำให้ขนาดโดยรวมอยู่ในระดับที่สมเหตุสมผล. คุณยังสามารถใช้เวอร์ชัน **no‑dependencies** หากกังวลเรื่องขนาด.

**Q: รองรับเวอร์ชัน Java ใดบ้าง?**  
A: Aspose.Slides for Java รองรับ JDK 8 ถึง JDK 21. ตัวอย่างใช้ JDK 16, แต่คุณสามารถปรับ classifier ให้สอดคล้องได้.

## สรุป
โดยทำตามคู่มือนี้ คุณจะรู้ **how to use Aspose** เพื่อเพิ่มความสวยงามให้กับแผนภูมิด้วยเครื่องหมายรูปภาพแบบกำหนดเอง, วิธีกำหนดค่า **Aspose Slides Maven dependency**, และวิธี **add images to chart** series เพื่อให้ได้ลุคที่เรียบหรูและเป็นมืออาชีพ. ทดลองใช้ไอคอน, ขนาด, และประเภทแผนภูมิต่าง ๆ เพื่อสร้างงานนำเสนอที่โดดเด่นจริง ๆ.

---

**อัปเดตล่าสุด:** 2026-01-11  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}