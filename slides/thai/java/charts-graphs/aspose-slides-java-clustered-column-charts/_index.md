---
date: '2026-08-27'
description: เรียนรู้วิธีสร้าง clustered column chart ใน Java ด้วย Aspose.Slides,
  เพิ่มแผนภูมิ, ตั้งค่าสีซีรีส์อัตโนมัติ, และบันทึกงานนำเสนอเป็น PPTX.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: เรียนรู้วิธีสร้าง clustered column chart ใน Java ด้วย Aspose.Slides,
  เพิ่มแผนภูมิ, ตั้งค่าสีซีรีส์อัตโนมัติ, และบันทึกงานนำเสนอเป็น PPTX—ทั้งหมดด้วยคำแนะนำทีละขั้นตอนที่ชัดเจน
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: สร้าง clustered column chart ใน Java ด้วย Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: วิธีสร้าง clustered column chart ใน Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides

## บทนำ
การสร้างแผนภูมิคอลัมน์แบบกลุ่มโดยโปรแกรมช่วยประหยัดเวลาการจัดรูปแบบด้วยตนเองหลายชั่วโมงและรับประกันความสอดคล้องกันในหลายงานนำเสนอ ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่ม** ใน Java ด้วย Aspose.Slides, **วิธีเพิ่มแผนภูมิ**, **วิธีตั้งค่าสี**, และ **วิธีบันทึกงานนำเสนอเป็น PPTX** เราจะครอบคลุมทุกอย่างตั้งแต่การติดตั้งไลบรารีจนถึงการปรับแต่งสีเติมของซีรีส์และการบันทึกไฟล์ เพื่อให้คุณสามารถฝังการแสดงผลข้อมูลที่หลากหลายลงในสไลด์ PowerPoint ใดก็ได้

## คำตอบสั้น
- **คลาสหลักสำหรับทำงานกับงานนำเสนอคืออะไร?** `Presentation` จากแพคเกจ `com.aspose.slides`.  
- **ฉันจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มอย่างไร?** เรียก `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **สามารถตั้งค่าสีของซีรีส์โดยอัตโนมัติได้หรือไม่?** ใช่—เปิดใช้งาน `setAutomaticSeriesColor(true)` ในแต่ละซีรีส์.  
- **ควรใช้รูปแบบใดในการบันทึกไฟล์?** `SaveFormat.Pptx` สร้างไฟล์ PowerPoint มาตรฐาน.  
- **ต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** รุ่นทดลองใช้ได้สำหรับการพัฒนา; ต้องมีใบอนุญาตเต็มสำหรับการใช้งานเชิงพาณิชย์.

## แผนภูมิคอลัมน์แบบกลุ่มคืออะไร?
แผนภูมิคอลัมน์แบบกลุ่มแสดงหลายซีรีส์ของข้อมูลเคียงข้างกันสำหรับแต่ละหมวดหมู่ ทำให้เปรียบเทียบค่าระหว่างกลุ่มได้ง่าย Aspose.Slides รองรับประเภทแผนภูมินี้โดยตรงและให้คุณควบคุมทุกแง่มุมของการแสดงผลด้วยโปรแกรม

## ทำไมต้องสร้างแผนภูมิคอลัมน์แบบกลุ่มด้วย Aspose.Slides?
Aspose.Slides สามารถจัดการ **รูปแบบการนำเข้าและส่งออกกว่า 50 แบบ** และประมวลผลงานนำเสนอที่มี **หลายร้อยสไลด์** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ความมีประสิทธิภาพนี้หมายความว่าคุณสามารถสร้างชุดสไลด์ขนาดใหญ่ในสภาพแวดล้อมฝั่งเซิร์ฟเวอร์ด้วยการใช้ทรัพยากรต่ำ

## ข้อกำหนดเบื้องต้น
- **Java Development Kit** 16 หรือใหม่กว่า.  
- **Maven** หรือ **Gradle** สำหรับการจัดการ dependencies.  
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และแนวคิดเชิงวัตถุ.  

### ไลบรารีและ dependencies ที่จำเป็น
คุณต้องใช้ไลบรารี Aspose.Slides for Java (เวอร์ชัน 25.4 หรือใหม่กว่า) ไลบรารีนี้เข้ากันได้เต็มที่กับ JDK 16 และมี API ที่ครอบคลุมสำหรับการจัดการแผนภูมิ

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
IDE ของคุณ (IntelliJ IDEA, Eclipse, VS Code) ต้องตั้งค่าให้คอมไพล์โค้ด Java 16 และแก้ไข dependencies ของ Maven/Gradle

### ความรู้เบื้องต้นที่จำเป็น
ความเข้าใจโครงสร้างสไลด์ PowerPoint และคำศัพท์พื้นฐานของแผนภูมิ (ซีรีส์, หมวดหมู่, จุดข้อมูล) จะช่วยให้คุณตามตัวอย่างได้เร็วขึ้น

## การตั้งค่า Aspose.Slides สำหรับ Java
รวมไลบรารีเข้ากับโปรเจกต์ของคุณโดยใช้วิธีใดวิธีหนึ่งต่อไปนี้

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

**Direct download** – ดาวน์โหลด JAR จากหน้าปล่อยอย่างเป็นทางการ: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### ขั้นตอนการรับใบอนุญาต
- **Free trial** – ลงทะเบียนบนเว็บไซต์ Aspose เพื่อรับไฟล์ใบอนุญาตชั่วคราว.  
- **Temporary license** – ขอใบอนุญาต 30 วันสำหรับชุดทดสอบขนาดใหญ่.  
- **Full license** – ซื้อเพื่อการใช้งานผลิตภัณฑ์ไม่จำกัด.

**การเริ่มต้นและตั้งค่าเบื้องต้น**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม?
`Presentation` แทนไฟล์ PowerPoint ในหน่วยความจำ.  

**คำตอบโดยตรง:**  
สร้างอ็อบเจกต์ `Presentation` ซึ่งแทนไฟล์ PowerPoint ในหน่วยความจำ, ดึงสไลด์แรก, และเรียก `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)` การเรียกเดียวนี้จะใส่แผนภูมิคอลัมน์แบบกลุ่มที่ทำงานเต็มรูปแบบ พร้อมสำหรับการใส่ข้อมูล และวางไว้ที่พิกัดที่ระบุบนสไลด์.

### คุณลักษณะ 1: สร้างแผนภูมิคอลัมน์แบบกลุ่ม
คลาส `Presentation` แทนไฟล์ PowerPoint ในหน่วยความจำและให้การเข้าถึงสไลด์, รูปร่าง, และอ็อบเจกต์แผนภูมิ

**ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**ขั้นตอนที่ 2: เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**ขั้นตอนที่ 3: ทำความสะอาดทรัพยากร**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## วิธีตั้งค่าสีสำหรับแผนภูมิ?
`Series` แทนชุดของจุดข้อมูลภายในแผนภูมิ.  

**คำตอบโดยตรง:**  
หลังจากสร้างแผนภูมิแล้ว, ดึงข้อมูลแผนภูมิด้วย `chart.getChartData()` และวนลูปแต่ละอ็อบเจกต์ `Series` สำหรับแต่ละซีรีส์, เรียก `setAutomaticSeriesColor(true)` บนซีรีส์แม่ Aspose.Slides จะกำหนดสีที่แตกต่างและตัดกันจากพาเลตของมันให้แต่ละซีรีส์โดยอัตโนมัติ เพื่อให้เห็นชัดเจนโดยไม่ต้องเลือกสีด้วยตนเอง.

### คุณลักษณะ 2: ตั้งค่าสีเติมอัตโนมัติของซีรีส์
`IChart` เป็นอินเทอร์เฟซที่แทนรูปแผนภูมิ; มีเมธอด `getChartData()` สำหรับการจัดการซีรีส์.

**ขั้นตอนที่ 1: เข้าถึงแผนภูมิและวนลูปซีรีส์**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**ขั้นตอนที่ 2: การจัดการทรัพยากร**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## วิธีบันทึกงานนำเสนอเป็น PPTX?
`save` เขียนงานนำเสนอไปยังไฟล์ในรูปแบบที่เลือก.  

**คำตอบโดยตรง:**  
กำหนดเส้นทางไฟล์ผลลัพธ์เช่น `"output/ClusteredColumnChart.pptx"` แล้วเรียก `presentation.save(outputPath, SaveFormat.Pptx)` เมธอด `save` จะทำการซีเรียลไลซ์สไลด์เด็คทั้งหมดรวมถึงรูปร่าง, แผนภูมิ, และทรัพยากรเป็นไฟล์ PPTX มาตรฐานที่สามารถเปิดด้วย PowerPoint 2010 หรือใหม่กว่า รวมถึงผู้ชมออนไลน์หลายตัว.

### คุณลักษณะ 3: บันทึกงานนำเสนอลงดิสก์
การบันทึกด้วย `SaveFormat.Pptx` จะสร้างไฟล์ที่เข้ากันได้กับ PowerPoint 2010 ขึ้นไปและผู้ชมออนไลน์ส่วนใหญ่.

**ขั้นตอนที่ 1: กำหนดเส้นทางผลลัพธ์**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**ขั้นตอนที่ 2: บันทึกงานนำเสนอ**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## การประยุกต์ใช้ในทางปฏิบัติ
- **Financial reporting** – เปรียบเทียบรายได้ไตรมาสตามสายผลิตภัณฑ์.  
- **Marketing analytics** – แสดงผลการทำแคมเปญตามภูมิภาค.  
- **Project management** – แสดงความเร็วของสปรินท์หรือการจัดสรรทรัพยากรระหว่างทีม.  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ทำลายอ็อบเจกต์ `Presentation` อย่างทันท่วงทีเพื่อปล่อยทรัพยากรเนทีฟ.  
- ใช้ `presentation.getSlides().removeUnusedResources()` ก่อนบันทึกเพื่อทำให้ไฟล์มีขนาดเล็กลง.  
- เติมข้อมูลซีรีส์ของแผนภูมิด้วยคอลเลกชันที่มีน้ำหนักเบา (เช่น `ArrayList<Double>`) เพื่อรักษาการใช้หน่วยความจำน้อย.

## สรุป
ตอนนี้คุณรู้วิธี **สร้างแผนภูมิคอลัมน์แบบกลุ่ม**, ตั้งค่าสีโดยอัตโนมัติ, และ **บันทึกงานนำเสนอเป็น PPTX** ด้วย Aspose.Slides สำหรับ Java ขั้นตอนเหล่านี้ทำให้คุณสร้างสไลด์ที่ขับเคลื่อนด้วยข้อมูลโดยโปรแกรม ลดการทำงานด้วยมือที่ซ้ำซ้อนและรับประกันความสอดคล้องของการแสดงผลในองค์กรของคุณ.

**ขั้นตอนต่อไป:**  
สำรวจการปรับแต่งขั้นสูงเช่น ป้ายข้อมูล, การจัดรูปแบบแกน, และการผูกข้อมูลแบบไดนามิกจากฐานข้อมูลหรือไฟล์ CSV เพื่อเพิ่มคุณค่าให้กับงานนำเสนอของคุณ.

## คำถามที่พบบ่อย
**Q: ฉันสามารถใช้โค้ดนี้ในเว็บแอปพลิเคชันได้หรือไม่?**  
A: ใช่—Aspose.Slides เป็นแพลตฟอร์มอิสระและทำงานในสภาพแวดล้อมเซิร์ฟเวอร์ที่ใช้ Java ใดก็ได้ รวมถึง Spring Boot และ Jakarta EE.

**Q: ไลบรารีนี้รองรับประเภทแผนภูมิอื่น ๆ หรือไม่?**  
A: แน่นอน. enum `ChartType` มี Pie, Bar, Line, Area, Radar และอื่น ๆ อีกมาก

**Q: ถ้าโฟลเดอร์ผลลัพธ์ไม่มีอยู่?**  
A: ตรวจสอบให้แน่ใจว่าได้สร้างไดเรกทอรีล่วงหน้าหรือใช้ `Files.createDirectories(Paths.get(folder))` เพื่อหลีกเลี่ยง `FileNotFoundException`.

**Q: ฉันจะจัดการกับชุดข้อมูลขนาดใหญ่ (หลายพันจุด) อย่างไร?**  
A: เติมซีรีส์โดยใช้ Streaming API หรือการแทรกเป็นชุด, และพิจารณาปิดการเคลื่อนไหวของแผนภูมิเพื่อเพิ่มความเร็วในการเรนเดอร์.

**Q: ฉันจะหาโค้ดตัวอย่างเพิ่มเติมได้จากที่ไหน?**  
A: เยี่ยมชมเอกสารอย่างเป็นทางการและคลังตัวอย่าง: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## แหล่งข้อมูล
- **เอกสาร:** [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **อ้างอิง:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **ดาวน์โหลด:** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **ซื้อ:** [Buy a License](https://purchase.aspose.com/buy)  
- **ทดลองใช้ฟรี:** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **ใบอนุญาตชั่วคราว:** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **สนับสนุน:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**อัปเดตล่าสุด:** 2026-08-27  
**ทดสอบกับ:** Aspose.Slides 25.4 (JDK 16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างแผนภูมิ PowerPoint Java – บันทึกงานนำเสนอพร้อมแผนภูมิด้วย Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [aspose slides maven dependency: เพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอด้วย Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [เพิ่มแอนิเมชันให้แผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนโดยละเอียด](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}