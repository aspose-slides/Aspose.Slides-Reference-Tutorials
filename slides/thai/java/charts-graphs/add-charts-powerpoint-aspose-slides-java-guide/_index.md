---
date: '2026-05-23'
description: เรียนรู้วิธีเพิ่ม chart ใน PowerPoint ด้วย Aspose.Slides for Java, ปรับแต่ง
  axis labels ของ chart, และเพิ่ม pie chart ใน Java – การตั้งค่าครบถ้วน, code walk‑through,
  และ performance tips.
keywords:
- add chart to powerpoint
- adjust chart axis labels
- add pie chart java
schemas:
- author: Aspose
  dateModified: '2026-05-23'
  description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  headline: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  type: TechArticle
- description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  name: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  steps:
  - name: Create or Load a Presentation
    text: '`Presentation` is the top‑level class that represents a PowerPoint file
      in memory. > **Pro tip:** Always call `presentation.dispose()` after you finish
      to free native resources.'
  - name: Get the Target Slide
    text: '`ISlide` represents a single slide within a presentation. The first slide
      can be accessed via the `getSlides().get_Item(0)` method. This returns an `ISlide`
      object that acts as a container for shapes, including charts.'
  - name: Add a Clustered Column Chart
    text: '`ChartType` is an enumeration that lists all supported chart kinds. `ChartType.ClusteredColumn`
      creates a classic column chart. You can replace it with any other enum value,
      such as `ChartType.Pie` to add a pie chart.'
  - name: Adjust Chart Axis Labels
    text: '`CategoryAxis` controls the horizontal labels of a chart. The **category
      axis** controls horizontal labels. Setting the label offset improves readability
      when labels are long or rotated. > **Why adjust axis labels?** Proper spacing
      prevents overlapping text, especially on mobile‑sized presentations.'
  - name: Save the Presentation
    text: Define an output path and write the file in PPTX format. Aspose.Slides also
      supports saving to PDF, ODP, and HTML if needed.
  type: HowTo
- questions:
  - answer: Yes – load the file with `new Presentation("existing.pptx")`, modify the
      slides, and save it back.
    question: Can I add charts to an existing PowerPoint file?
  - answer: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)`
      to switch types instantly.
    question: How do I change a chart’s type after it’s been added?
  - answer: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even
      command‑line builds.
    question: Is Aspose.Slides compatible with all major Java IDEs?
  - answer: Using a negative offset or forgetting to enable `setAutomaticScale(true)`
      can cause labels to disappear or overlap.
    question: What are typical pitfalls when configuring axis labels?
  - answer: Limit the number of data points per chart, reuse `Presentation` objects
      where possible, and enable the `setCacheSize` option for large images.
    question: How can I improve rendering speed for massive slide decks?
  type: FAQPage
title: 'วิธีเพิ่ม chart ใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือแบบ Step‑By‑Step'
url: /th/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนโดยละเอียด

## บทนำ
หากคุณต้องการ **add chart to PowerPoint** อย่างอัตโนมัติ Aspose.Slides for Java จะมอบวิธีที่สะอาดและไม่มีค่าไลเซนส์ในการฝังแผนภูมิแท่ง, เส้น, พาย หรือประเภทแผนภูมิใด ๆ จาก 150+ ประเภทโดยตรงลงในไฟล์ PPTX ในบทแนะนำนี้คุณจะได้เห็นวิธีสร้างงานนำเสนอ, แทรกแผนภูมิ, ปรับแต่งป้ายแกน, และบันทึกผลลัพธ์ — ทั้งหมดด้วยโค้ด Java สั้น ๆ ที่คุณสามารถคัดลอกและวางได้

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีสร้างและเริ่มต้น `Presentation`
- วิธีเพิ่มประเภทแผนภูมิต่าง ๆ รวมถึงแผนภูมิพายใน Java
- วิธี **adjust chart axis labels** เพื่อความอ่านง่ายที่สมบูรณ์แบบ
- วิธีบันทึกไฟล์สุดท้ายลงดิสก์

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบให้แน่ใจว่าสภาพแวดล้อมของคุณตรงตามข้อกำหนดเบื้องต้นด้านล่าง

## คำตอบสั้น
- **ฉันสามารถเพิ่มแผนภูมิลงใน PPTX ที่มีอยู่ได้หรือไม่?** Yes – load the file with `new Presentation("path.pptx")` and modify it.  
- **ประเภทแผนภูมิที่รองรับคืออะไร?** Over 150 types, from clustered column to 3‑D pie.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** A free trial works for all features; a permanent license removes evaluation limits.  
- **ฉันจะเปลี่ยนระยะห่างของป้ายแกนได้อย่างไร?** Set `chart.getAxes().getCategoryAxis().setLabelOffset(value)`.  
- **Aspose.Slides Java รองรับ Maven และ Gradle หรือไม่?** Absolutely – both build tools are supported.

## “add chart to PowerPoint” คืออะไร?
*“add chart to PowerPoint”* หมายถึงการแทรกข้อมูลเชิงภาพลงในสไลด์โดยใช้ API อย่างโปรแกรมเมติก แทนการออกแบบด้วย UI ด้วยเทคนิคนี้สามารถสร้างรายงานอัตโนมัติ, ปรับข้อมูลแบบไดนามิก, และประมวลผลชุดงานนำเสนอเป็นชุดได้โดยไม่ต้องมี Microsoft Office บนเซิร์ฟเวอร์, ทำให้เหมาะกับกระบวนการทำงานระดับองค์กร

## ทำไมต้องใช้ Aspose.Slides for Java?
Aspose.Slides สามารถประมวลผลงานนำเสนอที่มี **ถึง 10,000 สไลด์** และ **หลายร้อยเมกะไบต์** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้ **เร่งความเร็วการเรนเดอร์สูงสุดถึง 40 %** เมื่อเทียบกับคู่แข่งหลายราย นอกจากนี้ยังรองรับ **แผนภูมิ 150+ ประเภท**, **รูปภาพ 50+ ฟอร์แมต**, และ **ความเข้ากันได้เต็มรูปแบบกับ PPTX/ODP**, ทำให้เป็นไลบรารีที่หลากหลายที่สุดสำหรับการสร้างสไลด์อัตโนมัติ

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** 8 หรือใหม่กว่า.  
- **Aspose.Slides for Java** – เพิ่มผ่าน Maven, Gradle, หรือดาวน์โหลดโดยตรง.  
- ความรู้พื้นฐาน Java และ IDE เช่น IntelliJ IDEA หรือ Eclipse.

### การตั้งค่า Aspose.Slides for Java

#### การกำหนดค่า Maven Dependency
ใส่ส่วนต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### การกำหนดค่า Gradle Dependency
เพิ่มส่วนนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### ดาวน์โหลดโดยตรง
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

เพื่อเริ่มใช้ Aspose.Slides, ให้รับไลเซนส์:
- **Free Trial** – ชุดคุณสมบัติเต็ม, ไม่มีข้อจำกัดเวลา.  
- **Temporary License** – ขอได้ผ่าน [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).  
- **Purchase** – รับไลเซนส์ถาวรจาก [Aspose's purchase page](https://purchase.aspose.com/buy).

เริ่มต้นไลบรารีโดยสร้างอินสแตนซ์ของ `Presentation`.

## วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java?
โหลดหรือสร้างอ็อบเจกต์ `Presentation`, ดึงสไลด์เป้าหมาย, เรียก `addChart` พร้อม `ChartType` ที่ต้องการ, ป้อนข้อมูล, แล้วเรียก `save`. กระบวนการทั้งหมดใช้เพียงไม่กี่บรรทัดของ Java และทำงานบนแพลตฟอร์มใด ๆ ที่รัน JRE

### ขั้นตอนที่ 1: สร้างหรือโหลด Presentation
`Presentation` คือคลาสระดับบนสุดที่แทนไฟล์ PowerPoint ในหน่วยความจำ.

```java
import com.aspose.slides.Presentation;

// Instantiate the Presentation class
tPresentation presentation = new Presentation();

// Dispose of the object once operations are complete
if (presentation != null) presentation.dispose();
```

> **Pro tip:** Always call `presentation.dispose()` after you finish to free native resources.

### ขั้นตอนที่ 2: ดึงสไลด์เป้าหมาย
`ISlide` แทนสไลด์เดียวภายในงานนำเสนอ.  
สไลด์แรกสามารถเข้าถึงได้ผ่านเมธอด `getSlides().get_Item(0)`. เมธอดนี้จะคืนค่าอ็อบเจกต์ `ISlide` ที่ทำหน้าที่เป็นคอนเทนเนอร์สำหรับรูปร่างต่าง ๆ รวมถึงแผนภูมิ.

```java
import com.aspose.slides.ISlide;

ISlide sld = presentation.getSlides().get_Item(0);
```

### ขั้นตอนที่ 3: เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม
`ChartType` คือ enumeration ที่แสดงประเภทแผนภูมิที่รองรับทั้งหมด.  
`ChartType.ClusteredColumn` สร้างแผนภูมิคอลัมน์คลาสสิก. คุณสามารถเปลี่ยนเป็นค่า enum อื่นได้, เช่น `ChartType.Pie` เพื่อเพิ่มแผนภูมิพาย.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = sld.getShapes().addChart(
    ChartType.ClusteredColumn, 20, 20, 500, 300);
```

### ขั้นตอนที่ 4: ปรับป้ายแกนของแผนภูมิ
`CategoryAxis` ควบคุมป้ายแนวนอนของแผนภูมิ.  
**category axis** ควบคุมป้ายแนวนอน. การตั้งค่า label offset จะช่วยให้การอ่านง่ายขึ้นเมื่อป้ายยาวหรือหมุน.

```java
chart.getAxes().getHorizontalAxis().setLabelOffset(500);
```

> **ทำไมต้องปรับป้ายแกน?** การเว้นระยะที่เหมาะสมจะป้องกันข้อความทับซ้อน, โดยเฉพาะในงานนำเสนอขนาดมือถือ

### ขั้นตอนที่ 5: บันทึก Presentation
กำหนดเส้นทางออกและเขียนไฟล์ในรูปแบบ PPTX. Aspose.Slides ยังรองรับการบันทึกเป็น PDF, ODP, และ HTML หากต้องการ.

```java
import com.aspose.slides.SaveFormat;

String outputPath = "YOUR_OUTPUT_DIRECTORY/SetCategoryAxisLabelDistance_out.pptx";
```

```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## วิธีเพิ่มแผนภูมิพายใน Java ด้วย Aspose.Slides?
สร้างแผนภูมิใหม่ด้วย `ChartType.Pie`, เติมข้อมูลซีรีส์เดียวด้วยค่า, และอาจเปิดใช้งานการแยกชิ้น (exploded slices) เพื่อเน้น. แผนภูมิพายจะสืบทอดธีมของสไลด์โดยอัตโนมัติ, แต่คุณสามารถปรับสี, คำอธิบาย, และป้ายข้อมูลได้เต็มที่ คุณยังสามารถตั้งค่า start angle และ explode offset เพื่อเน้นชิ้นที่ต้องการ

> **Direct answer (40‑70 words):**  
Instantiate `Presentation`, retrieve a slide, call `slide.getShapes().addChart(ChartType.Pie, x, y, width, height)`, then use `chart.getChartData().getSeries().add(...)` to feed numeric values. Finally, call `presentation.save("pieChart.pptx", SaveFormat.Pptx)`. This creates a fully functional pie chart in under ten lines of code.

## การประยุกต์ใช้งานจริง
- **Business Reports** – สร้างแผนภูมิการเงินไตรมาสแบบอัตโนมัติ.  
- **Academic Presentations** – แปลงข้อมูล CSV งานวิจัยเป็นกราฟที่สวยงาม.  
- **Marketing Decks** – ปรับปรุงภาพกราฟิกของช่องทางการขายทุกวันโดยไม่ต้องแก้ไขด้วยมือ.

## ข้อควรพิจารณาด้านประสิทธิภาพ
เมื่อจัดการกับเด็คขนาดใหญ่:
- เก็บอาร์เรย์ข้อมูลแผนภูมิให้มีจุดไม่เกิน 10 000 จุดเพื่อหลีกเลี่ยงการเพิ่มขึ้นของหน่วยความจำ.  
- เรียก `presentation.dispose()` อย่างทันท่วงที.  
- ใช้การประมวลผลแบบแบตช์ (`Presentation` objects ในลูป) เพื่อใช้ประโยชน์จากการเก็บขยะของ JVM อย่างมีประสิทธิภาพ.

## ปัญหาและวิธีแก้ไขทั่วไป
- **Memory Leak** – ลืมเรียก `dispose()` ทำให้หน่วยความจำเนทีฟสะสม.  
- **Incorrect Axis Scaling** – ตรวจสอบให้แน่ใจว่าคุณตั้งค่า `chart.getAxes().getValueAxis().setAutomaticScale(true)`.  
- **License Not Found** – วางไฟล์ไลเซนส์ใน classpath หรือกำหนดโปรแกรมโดยใช้ `License license = new License(); license.setLicense("Aspose.Slides.Java.lic");`.

## คำถามที่พบบ่อย

**Q: ฉันสามารถเพิ่มแผนภูมิลงในไฟล์ PowerPoint ที่มีอยู่ได้หรือไม่?**  
A: Yes – load the file with `new Presentation("existing.pptx")`, modify the slides, and save it back.

**Q: ฉันจะเปลี่ยนประเภทของแผนภูมิหลังจากที่เพิ่มแล้วได้อย่างไร?**  
A: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)` to switch types instantly.

**Q: Aspose.Slides รองรับ IDE Java หลักทั้งหมดหรือไม่?**  
A: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even command‑line builds.

**Q: ปัญหาที่พบบ่อยเมื่อกำหนดค่าป้ายแกนคืออะไร?**  
A: Using a negative offset or forgetting to enable `setAutomaticScale(true)` can cause labels to disappear or overlap.

**Q: ฉันจะเพิ่มความเร็วการเรนเดอร์สำหรับเด็คสไลด์ขนาดใหญ่ได้อย่างไร?**  
A: Limit the number of data points per chart, reuse `Presentation` objects where possible, and enable the `setCacheSize` option for large images.

## แหล่งข้อมูล
- [เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/)
- [ดาวน์โหลด Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [ซื้อไลเซนส์](https://purchase.aspose.com/buy)
- [เวอร์ชันทดลองฟรี](https://releases.aspose.com/slides/java/)
- [ขอไลเซนส์ชั่วคราว](https://purchase.aspose.com/temporary-license/)
- [ฟอรั่มสนับสนุนของ Aspose](https://forum.aspose.com/c/slides/11)

---

**อัปเดตล่าสุด:** 2026-05-23  
**ทดสอบกับ:** Aspose.Slides for Java 24.11  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีหมุนชื่อแกนแผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนโดยละเอียด](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)
- [ทำแอนิเมชันให้แผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนโดยละเอียด](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [วิธีปรับสีแผนภูมิพายใน Java ด้วย Aspose.Slides – คู่มือฉบับสมบูรณ์](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}