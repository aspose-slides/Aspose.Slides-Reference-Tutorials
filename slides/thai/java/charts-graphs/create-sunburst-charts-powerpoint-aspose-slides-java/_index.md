---
date: '2026-07-17'
description: เรียนรู้วิธีเพิ่ม Sunburst Charts ใน PowerPoint ด้วย Aspose Slides for
  Java คู่มือแบบขั้นตอนครอบคลุมการตั้งค่า การสร้างแผนภูมิ การปรับแต่ง และกรณีใช้งานจริง
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: วิธีเพิ่ม Sunburst Charts ใน PowerPoint ด้วย Aspose Slides for Java.
  ทำตามบทแนะนำนี้เพื่อกำหนดค่าห้องสมุด สร้างแผนภูมิ ปรับแต่งจุดข้อมูล และนำไปใช้ในโครงการจริง
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: วิธีเพิ่ม Sunburst Charts ใน PowerPoint ด้วย Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: วิธีเพิ่ม Sunburst Charts ใน PowerPoint ด้วย Aspose (Java)
url: /th/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเพิ่มแผนภูมิ Sunburst ใน PowerPoint ด้วย Aspose (Java)

## บทนำ

การเพิ่มแผนภูมิ Sunburst ลงในสไลด์ PowerPoint สามารถเปลี่ยนตารางข้อมูลแบนให้กลายเป็นโครงสร้างภาพที่น่าสนใจได้ทันที ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีเพิ่ม Sunburst** ใน PowerPoint ด้วย Aspose.Slides for Java ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการปรับสีและป้ายกำกับอย่างละเอียด ไม่ว่าคุณจะสร้างแดชบอร์ดการขาย, การแยกงานโครงการ, หรือชุดสไลด์เพื่อการศึกษา ขั้นตอนต่อไปนี้จะให้โซลูชันพร้อมใช้งานสำหรับการผลิต

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีกำหนดค่า Aspose.Slides ในโครงการ Maven หรือ Gradle  
- วิธีสร้างการนำเสนอใหม่และแทรกแผนภูมิ Sunburst  
- วิธีปรับแต่งจุดข้อมูล, ป้ายกำกับ, และสีเติม  
- สถานการณ์จริงที่แผนภูมิ Sunburst โดดเด่น  

มาเริ่มกันและดูว่าการเปลี่ยนข้อมูลโครงสร้างดิบให้เป็นภาพ PowerPoint ที่สวยงามนั้นง่ายแค่ไหน

## คำตอบสั้น
- **ไลบรารีหลัก?** Aspose.Slides for Java  
- **ประเภทแผนภูมิที่รองรับ?** Sunburst (radial hierarchical)  
- **เวอร์ชัน Java ขั้นต่ำ?** JDK 16  
- **เวลาการทำงานโดยทั่วไป?** 10‑15 minutes for a basic chart  
- **ต้องการไลเซนส์สำหรับการผลิตหรือไม่?** Yes, a valid Aspose license  

## Sunburst Chart คืออะไร?
แผนภูมิ Sunburst เป็นแผนภาพรัศมีที่แสดงข้อมูลเชิงลำดับชั้นโดยการซ้อนวงแหวนออกจากจุดศูนย์กลาง มันเหมาะอย่างยิ่งสำหรับการแสดงความสัมพันธ์หลายระดับ เช่น โครงสร้างองค์กร, ประเภทสินค้า, หรือโครงสร้างไฟล์ ระบบแต่ละวงแหวนที่อยู่ในศูนย์กลางแสดงระดับของลำดับชั้น และขนาดของแต่ละส่วนสะท้อนค่าปริมาณของมัน ทำให้ผู้ชมเข้าใจโครงสร้างและขนาดได้อย่างรวดเร็ว

## ทำไมต้องใช้ Aspose.Slides for Java?
Aspose.Slides รองรับ **ประเภทแผนภูมิ 50+** และสามารถจัดการการนำเสนอด้วย **สูงสุด 10,000 สไลด์** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ให้ประสิทธิภาพสูงสำหรับการรายงานระดับองค์กร มันทำงานข้ามแพลตฟอร์ม, มี API ครอบคลุมอย่างกว้างขวาง, และรวมตัวเลือกไลเซนส์ที่แข็งแรงซึ่งลบข้อจำกัดการประเมิน ทำให้เหมาะสำหรับสภาพแวดล้อมการผลิต

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** 16 หรือใหม่กว่า  
- **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขที่รองรับ Java ใดก็ได้  
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และเครื่องมือสร้าง Maven/Gradle  

## การตั้งค่า Aspose.Slides for Java

### การพึ่งพา Maven
เพิ่มอาร์ติแฟคต์ Aspose.Slides Maven ลงใน `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การพึ่งพา Gradle
If you prefer Gradle, include the following line in `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
คุณยังสามารถดาวน์โหลดไฟล์ JAR ล่าสุดโดยตรงจากหน้าการปล่อยอย่างเป็นทางการ: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การรับไลเซนส์
To run without evaluation limits, obtain a license:
- **Free trial** – ไลเซนส์ชั่วคราวสำหรับการประเมินอย่างรวดเร็ว.  
- **Temporary license** – ขอรับจาก [Aspose website](https://purchase.aspose.com/temporary-license).  
- **Full purchase** – ซื้อการสมัครสมาชิกเพื่อการใช้งานการผลิตไม่จำกัด.  

### การเริ่มต้นพื้นฐาน
คลาส `Presentation` เป็นจุดเริ่มต้นสำหรับการสร้างหรือเปิดไฟล์ PowerPoint.
```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## คู่มือการใช้งาน

### วิธีเพิ่มแผนภูมิ Sunburst ลงในงานนำเสนอ PowerPoint ด้วย Aspose.Slides for Java?
โหลด `Presentation` ใหม่, เพิ่มสไลด์, แทรก `IChart` ชนิด `ChartType.Sunburst`, แล้วเรียก `save`. รูปแบบสามขั้นตอนสั้นนี้สร้างแผนภูมิ Sunburst ที่ทำงานเต็มรูปแบบพร้อมสำหรับการปรับแต่งต่อไป

#### ขั้นตอนที่ 1: เริ่มต้น Presentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### ขั้นตอนที่ 2: เพิ่มแผนภูมิ Sunburst
The `IChart` interface defines a chart object that can be placed on any slide. Here we add a sunburst chart at coordinates (100, 100) with a size of 450 × 400 points.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### ขั้นตอนที่ 3: บันทึก Presentation
ควรบันทึกการเปลี่ยนแปลงของคุณเสมอโดยเรียก `save`. คุณสามารถเลือก PPTX, PDF หรือรูปแบบเอาต์พุตใดก็ได้จาก 50+ ที่รองรับ.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### แก้ไขจุดข้อมูลในแผนภูมิ

#### ภาพรวม
คุณสามารถปรับแต่งแต่ละส่วนของ Sunburst — ป้ายกำกับ, สี, และการมองเห็น — ผ่านคอลเลกชันของจุดข้อมูลของแผนภูมิ

#### ขั้นตอนที่ 1: เข้าถึงคอลเลกชันจุดข้อมูล
ซีรีส์แรกของแผนภูมิมีคอลเลกชันของอ็อบเจ็กต์ `IChartDataPoint` ที่แทนแต่ละส่วน.
```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### ขั้นตอนที่ 2: แสดงค่าของจุดข้อมูลเฉพาะ
ตั้งค่า `IsValueShown` เป็น `true` บนจุดข้อมูลที่ต้องการเพื่อแสดงค่าตัวเลขของมันโดยตรงบนส่วน.
```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### ขั้นตอนที่ 3: ปรับรูปแบบป้ายกำกับ
ปรับการมองเห็นของป้ายกำกับ, สีฟอนต์, และพื้นหลังเพื่อเพิ่มความอ่านง่าย.
```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### ขั้นตอนที่ 4: ตั้งค่าสีเติมสำหรับจุดข้อมูล
ปรับสีเติมของแต่ละส่วนให้ตรงกับพาเลตสีของแบรนด์คุณหรือเพื่อเน้นส่วนสำคัญ.
```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### ขั้นตอนที่ 5: บันทึกการนำเสนอที่แก้ไข
บันทึกแผนภูมิที่ปรับแต่งแล้วโดยบันทึกการนำเสนออีกครั้ง.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## การประยุกต์ใช้งานจริง

1. **Business Analytics** – แสดงการขายตามภูมิภาค → สายผลิตภัณฑ์ → SKU ในมุมมองรัศมีเดียว.  
2. **Project Management** – แสดงโครงสร้างการแบ่งงาน, ขุดลึกจากขั้นตอนไปยังงานและงานย่อย.  
3. **Education** – ทำแผนผังลำดับชั้นของหลักสูตร, เช่น ภาควิชา → คอร์ส → โมดูล.  

## พิจารณาด้านประสิทธิภาพ

- **Memory Efficiency:** Aspose.Slides สตรีมข้อมูล, ดังนั้นแม้ชุดสไลด์ 500 หน้า ที่มีหลายแผนภูมิก็ยังใช้หน่วยความจำต่ำกว่า 200 MB.  
- **Garbage Collection:** ปล่อยอ็อบเจ็กต์สไลด์ (`slide.dispose()`) เมื่อไม่ต้องการแล้วเพื่อหลีกเลี่ยงการรั่วไหลของหน่วยความจำ.  

## คำถามที่พบบ่อย

**Q: Sunburst Chart คืออะไร?**  
A: Sunburst Chart แสดงข้อมูลเชิงลำดับชั้นในวงแหวนศูนย์กลาง, โดยแต่ละวงแสดงระดับของลำดับชั้น.

**Q: ฉันจะติดตั้ง Aspose.Slides for Java ด้วย Maven อย่างไร?**  
A: เพิ่มการพึ่งพา Maven ที่แสดงในส่วน “Maven Dependency” ลงใน `pom.xml` ของคุณและรัน `mvn clean install`.

**Q: ฉันสามารถปรับแต่งประเภทแผนภูมิอื่น ๆ ด้วย Aspose.Slides ได้หรือไม่?**  
A: ได้, ไลบรารีรองรับแผนภูมิมากกว่า 50 ประเภท, รวมถึง column, line, pie, และ radar charts.

**Q: การนำเสนอของฉันไม่บันทึก—ฉันควรตรวจสอบอะไร?**  
A: ตรวจสอบว่าเส้นทางไฟล์ถูกต้อง, โฟลเดอร์มีอยู่, และคุณมีสิทธิ์เขียน. นอกจากนี้ให้แน่ใจว่าได้เรียกเมธอด `Presentation.save()`.

**Q: ฉันจะหาแนวทางหรือ ตัวอย่างเพิ่มเติมได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose forum](https://forum.aspose.com/c/slides/11) หรือดู [Aspose.Slides reference](https://reference.aspose.com/slides/java/).

## แหล่งข้อมูล
- **เอกสาร:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **อ้างอิง (ตัวพิมพ์เล็ก):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **ฟอรั่มชุมชน:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **ดาวน์โหลด:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**อัปเดตล่าสุด:** 2026-07-17  
**ทดสอบด้วย:** Aspose.Slides for Java 24.12  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [วิธีเพิ่มแผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอน](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [ทำแอนิเมชันแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอน](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [สร้างแผนภูมิใน Java ด้วย Aspose.Slides – เพิ่มและตรวจสอบแผนภูมิ](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}