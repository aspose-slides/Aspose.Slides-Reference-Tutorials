---
date: '2026-08-01'
description: เรียนรู้วิธีใช้ Aspose Slides license เพื่อสร้างและปรับแต่ง pie charts
  ใน Java presentations. ทำตามคำแนะนำ step‑by‑step เพื่อ configure pie chart data
  และเพิ่ม chart slides อย่างมีประสิทธิภาพ.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: เรียนรู้วิธีใช้ Aspose Slides license เพื่อสร้างและปรับแต่ง pie charts
  ใน Java presentations. ทำตามคำแนะนำ step‑by‑step เพื่อ configure pie chart data
  และเพิ่ม chart slides อย่างมีประสิทธิภาพ.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: สร้าง Pie Charts ใน Java ด้วย Aspose Slides License
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: สร้าง Pie Charts ใน Java ด้วย Aspose Slides License
url: /th/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิวงกลมในงานนำเสนอ Java ด้วย Aspose.Slides

## บทนำ

หากคุณต้องการสร้างงานนำเสนอที่ดูเป็นมืออาชีพ **ใบอนุญาต Aspose Slides** จะมอบพลังให้คุณสร้างและจัดรูปแบบแผนภูมิด้วยโปรแกรม ในคู่มือนี้คุณจะได้เรียนรู้วิธีสร้างแผนภูมิวงกลม ตั้งค่าข้อมูลของมัน และฝังลงในสไลด์ Java — ทั้งหมดโดยไม่ต้องพึ่งพา Microsoft PowerPoint เราจะพาคุณผ่านการตั้งค่า การไหลของโค้ด และเคล็ดลับการปฏิบัติที่ดีที่สุด เพื่อให้คุณสามารถส่งมอบรายงานภาพที่สวยงามในเวลาไม่กี่นาที

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides for Java พร้อมใบอนุญาตที่ถูกต้อง
- ขั้นตอนการสร้างและปรับแต่งแผนภูมิวงกลม
- วิธีตั้งค่าข้อมูลแผนภูมิวงกลมและเพิ่มสไลด์แผนภูมิ
- ข้อผิดพลาดทั่วไปและเทคนิคการเพิ่มประสิทธิภาพ

เริ่มต้นด้วยการยืนยันว่าสภาพแวดล้อมของคุณพร้อมใช้งานแล้ว

## คำตอบด่วน
- **ใบอนุญาต Aspose Slides ทำอะไรได้บ้าง?** การสร้างแผนภูมิเต็มรูปแบบ การส่งออกเป็น PDF/HTML และการลบลายน้ำ
- **ต้องใช้ Java เวอร์ชันใด?** JDK 16 หรือใหม่กว่า
- **ต้องใช้ Maven หรือ Gradle หรือไม่?** ใช้ได้ทั้งสอง; ไลบรารีพร้อมให้บริการผ่านทั้งสองระบบ
- **แผนภูมิวงกลมสามารถเก็บข้อมูลได้กี่จุด?** สูงสุด 10 000 จุดโดยไม่มีปัญหาเรื่องหน่วยความจำ
- **สามารถส่งออกสไลด์เป็นภาพได้หรือไม่?** ได้ – รองรับ PNG, JPEG, SVG และรูปแบบอื่น ๆ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบว่าคุณมี:
- **ไลบรารีที่จำเป็น:** Aspose.Slides for Java (เวอร์ชัน 25.4 หรือใหม่กว่า) – เวอร์ชันนี้รองรับรูปแบบไฟล์ล่าสุดและการปรับประสิทธิภาพ
- **การตั้งค่าสภาพแวดล้อม:** JDK 16+ ติดตั้งและกำหนดค่าใน IDE หรือระบบ build ของคุณ
- **ความรู้พื้นฐาน:** ความคุ้นเคยกับ Java, Maven หรือ Gradle, และแนวคิดการเขียนโปรแกรมเชิงวัตถุ

## การตั้งค่า Aspose.Slides for Java

เพื่อใช้ Aspose.Slides for Java ให้เพิ่มเข้าในโครงการของคุณ ตัวอย่างการเพิ่ม dependency ด้วยเครื่องมือ build ที่นิยมใช้ที่สุด:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**ดาวน์โหลดโดยตรง:** คุณยังสามารถดาวน์โหลด JAR ล่าสุดจาก [การปล่อย Aspose.Slides for Java](https://releases.aspose.com/slides/java/)  

### การรับใบอนุญาต

Aspose มีการให้ทดลองใช้ฟรีที่เปิดใช้งานคุณสมบัติต่าง ๆ ทั้งหมด แต่ **ใบอนุญาต Aspose Slides ที่ถูกต้อง** จำเป็นสำหรับการใช้งานในสภาพแวดล้อมการผลิตเพื่อเอาลายน้ำการประเมินและรับประโยชน์ด้านประสิทธิภาพ ตัวเลือกการซื้อสามารถดูได้ที่ [หน้าการซื้อ](https://purchase.aspose.com/buy) หลังจากได้ไฟล์ใบอนุญาตแล้ว ให้โหลดไฟล์นั้นหนึ่งครั้งเมื่อแอปพลิเคชันเริ่มทำงาน:

`License` โหลดและใช้ใบอนุญาต Aspose.Slides ของคุณ  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## คู่มือการดำเนินการ

### สร้างและเพิ่มแผนภูมิวงกลมลงในงานนำเสนอ

#### ภาพรวม
ส่วนนี้อธิบายวิธีสร้างแผนภูมิวงกลม ตั้งค่าชุดข้อมูลของมัน และฝังแผนภูมิลงในสไลด์ คุณจะได้เห็นกระบวนการทั้งหมดตั้งแต่การเริ่มต้นอ็อบเจกต์ Presentation จนถึงการบันทึกไฟล์สุดท้าย

#### ขั้นตอนที่ 1: เริ่มต้น Presentation  
`Presentation` คืออ็อบเจกต์ระดับบนของ Aspose.Slides ที่แทนไฟล์ PowerPoint ในหน่วยความจำ การสร้างอินสแตนซ์จะให้สไลด์เด็คเปล่าที่พร้อมสำหรับการแก้ไข

```java
demo.Presentation pres = new demo.Presentation();
```  
บรรทัดนี้สร้าง Presentation ใหม่ที่การเปลี่ยนแปลงต่อไปทั้งหมดจะถูกนำไปใช้

#### ขั้นตอนที่ 2: เพิ่มแผนภูมิวงกลมลงในสไลด์  
`Chart` คือคลาสที่บรรจุอ็อบเจกต์แผนภูมิ รวมถึงแผนภูมิวงกลม การเพิ่มแผนภูมิลงในสไลด์ทำได้ด้วยการเรียกเมธอดเดียวที่ระบุตำแหน่งและขนาด

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` และ `yPosition` กำหนดมุมบนซ้ายของแผนภูมิ  
- `width` และ `height` กำหนดขนาดพื้นที่แสดงของแผนภูมิบนสไลด์  

#### ขั้นตอนที่ 3: ตั้งค่าข้อมูลแผนภูมิวงกลม  
`ChartData` เก็บชุดข้อมูลสำหรับแผนภูมิ  
**ฉันจะตั้งค่าข้อมูลแผนภูมิวงกลมอย่างไร?**  
ตอบสั้น ๆ ก่อน: ใช้คอลเลกชัน `ChartData` เพื่อเพิ่มซีรีส์ แล้วใส่ค่าในอ็อบเจกต์ `ChartDataPoint` ด้วยค่าตัวเลขและชื่อหมวดหมู่ วิธีนี้ทำให้คุณแสดงได้ถึง 10 000 ส่วนโดยคงรูปแบบป้ายกำกับ หลังจากตั้งค่าข้อมูลแล้ว คุณสามารถปรับสี, คำอธิบาย, และป้ายข้อมูลให้สอดคล้องกับแนวทางสไตล์ขององค์กร

ต่อไปนี้คือตัวอย่างโค้ดที่เพิ่มสองหมวดหมู่และแสดงป้ายกำกับของพวกมัน:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
สคริปต์นี้สร้างซีรีส์ข้อมูล แทรกสองจุด และเปิดใช้งานป้ายกำกับหมวดหมู่บนแผนภูมิ

#### ขั้นตอนที่ 4: บันทึก Presentation  
สุดท้าย ให้บันทึก Presentation เป็นรูปแบบไฟล์ที่คุณต้องการ (PPTX, PDF หรือ PNG) เมธอด `save` จะเคารพใบอนุญาตที่ใช้งานอยู่ ทำให้ไม่มีลายน้ำการทดลองปรากฏ

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### ปัญหาและวิธีแก้ไขทั่วไป
- **Missing License Error:** ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ใบอนุญาตถูกต้องและอ็อบเจกต์ `License` ถูกสร้างก่อนเรียกใช้ Aspose.Slides ใด ๆ
- **Empty Chart:** ยืนยันว่าซีรีส์ `ChartData` มีอย่างน้อยหนึ่ง `ChartDataPoint` มิฉะนั้นจะแสดงพื้นที่แผนภูมิว่างเปล่า
- **Performance Lag with Large Data Sets:** ใช้ `presentation.getSlides().removeAt(index)` เพื่อลบสไลด์ที่ไม่ได้ใช้และเรียก `System.gc()` หลังจากประมวลผลหนัก

## การประยุกต์ใช้เชิงปฏิบัติ
1. **รายงานธุรกิจ:** แสดงส่วนแบ่งตลาดหรือการกระจายรายได้ตามภูมิภาคด้วยแผนภูมิวงกลมเดียว
2. **การนำเสนอทางวิชาการ:** แสดงผลสำรวจหรือผลการทดลองในรูปแบบที่ชัดเจนและเข้าใจง่าย
3. **แดชบอร์ดโครงการ:** แสดงเปอร์เซ็นต์การทำงานเสร็จหรือการจัดสรรทรัพยากรบนสไลด์ได้ทันที

คุณยังสามารถรวม Aspose.Slides กับ JDBC เพื่อดึงข้อมูลสดจากฐานข้อมูล สร้างแผนภูมิอัปเดตอัตโนมัติสำหรับการสรุปผลผู้บริหารประจำสัปดาห์

## พิจารณาด้านประสิทธิภาพ
เมื่อทำงานกับงานนำเสนอที่มีภาพความละเอียดสูงหรือชุดข้อมูลขนาดใหญ่:
- ปล่อยอ็อบเจกต์โดยเร็วด้วย `try‑with‑resources` หรือการเรียก `dispose()` อย่างชัดเจน
- เปิดใช้งานการโหลดแบบ lazy ของทรัพยากรสไลด์เพื่อรักษาการใช้หน่วยความจำน้อยที่สุด
- สำหรับการประมวลผลเป็นชุด ให้ใช้ `Presentation` ตัวเดียวซ้ำเมื่อเป็นไปได้ เพื่อลดภาระ JVM

## สรุป
คุณมีเวิร์กโฟลว์ที่ครบถ้วนและพร้อมใช้งานในสภาพแวดล้อมการผลิตสำหรับการสร้างแผนภูมิวงกลมใน Java ด้วย **ใบอนุญาต Aspose Slides** ทดลองใช้แผนภูมิประเภทอื่น ๆ — แถบ, เส้น, หรือโดนัท — เพื่อเพิ่มความหลากหลายให้สไลด์ของคุณ ขั้นต่อไปคือสำรวจความสามารถในการส่งออกของ API เพื่อสร้างรายงาน PDF หรือภาพ PNG อัตโนมัติ

## คำถามที่พบบ่อย

**ถาม: ฉันจะเพิ่มหลายแผนภูมิในสไลด์เดียวได้อย่างไร?**  
ตอบ: เรียก `slide.getShapes().addChart()` สำหรับแต่ละแผนภูมิ โดยกำหนดพิกัดและขนาดที่ไม่ซ้ำกันสำหรับแต่ละอินสแตนซ์

**ถาม: มีทางเลือกอื่น ๆ สำหรับ Aspose.Slides for Java บ้างไหม?**  
ตอบ: Apache POI และ JFreeChart เป็นทางเลือกที่พบบ่อย แต่ไม่มีตัวเลือกการส่งออกที่ครบถ้วนและโมเดลการให้ลิขสิทธิ์ของ Aspose

**ถาม: ฉันสามารถแปลงงานนำเสนอเป็นรูปแบบอื่น ๆ ด้วย Aspose.Slides ได้หรือไม่?**  
ตอบ: ได้ — สามารถส่งออกเป็น PDF, XPS, HTML, PNG, JPEG, SVG และอื่น ๆ ด้วยการเรียก `save` เพียงครั้งเดียว

**ถาม: ฉันจะจัดการใบอนุญาตสำหรับทีมพัฒนาขนาดใหญ่ได้อย่างไร?**  
ตอบ: ซื้อใบอนุญาตระดับองค์กรที่ครอบคลุมหลายผู้พัฒนาและเซิร์ฟเวอร์; ติดต่อฝ่ายขายของ Aspose เพื่อขอส่วนลดตามปริมาณ

**ถาม: ถ้าข้อมูลแผนภูมิของฉันอัปเดตบ่อย ๆ จะทำอย่างไร?**  
ตอบ: ผสาน Aspose.Slides กับแหล่งข้อมูล (เช่น คำสั่ง SQL) แล้วสร้างแผนภูมิใหม่ในเวลารันไทม์; API รองรับการผูกข้อมูลแบบไดนามิก

## แหล่งข้อมูล
- **เอกสารอ้างอิง:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **ดาวน์โหลด:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **ซื้อ:** [Buy a License](https://purchase.aspose.com/buy)
- **ทดลองใช้ฟรี:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **ใบอนุญาตชั่วคราว:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **สนับสนุน:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**อัปเดตล่าสุด:** 2026-08-01  
**ทดสอบกับ:** Aspose.Slides for Java 25.4  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีเพิ่มและตั้งค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [สร้างและปรับแต่งแผนภูมิในงานนำเสนอ Java ด้วย Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [วิธีสร้างและตั้งค่างานนำเสนอด้วย Aspose.Slides Java: คู่มือขั้นตอนโดยละเอียด](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}