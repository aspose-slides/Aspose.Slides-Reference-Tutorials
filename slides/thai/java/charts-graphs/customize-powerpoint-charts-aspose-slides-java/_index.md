---
date: '2026-09-07'
description: เรียนรู้วิธีเพิ่ม custom lines ไปยัง chart ของ Aspose Slides ด้วย Java.
  คู่มือ step‑by‑step ช่วยปรับปรุง chart ของ PowerPoint ให้การแสดงผลข้อมูลชัดเจนยิ่งขึ้น.
keywords:
- aspose slides chart
- customize PowerPoint charts
- add custom lines to charts Java
lastmod: '2026-09-07'
og_description: เรียนรู้วิธีเพิ่ม custom lines ไปยัง chart ของ Aspose Slides ด้วย
  Java. คู่มือ step‑by‑step ช่วยปรับปรุง chart ของ PowerPoint ให้การแสดงผลข้อมูลชัดเจนยิ่งขึ้น.
og_image_alt: Developer guide showing custom line addition to an Aspose Slides chart
  in Java
og_title: วิธีเพิ่ม custom lines ไปยัง chart ของ Aspose Slides ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  headline: How to add custom lines to an Aspose Slides chart in Java
  type: TechArticle
- description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  name: How to add custom lines to an Aspose Slides chart in Java
  steps:
  - name: create a presentation object
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a single PowerPoint file in memory.
  - name: add a clustered column chart
    text: Insert a clustered column chart on the first slide at coordinates (100,
      100) with a width of 500 px and a height of 400 px.
  - name: add an auto‑shape line to the chart
    text: Add a line shape to the chart’s `userShapes` collection, which stores custom
      drawing objects. `userShapes` is a collection that holds custom shapes drawn
      directly on a chart, allowing you to overlay lines, arrows, or other annotations.
  - name: customize line properties
    text: Set the line’s fill type to solid, change its color to red, and optionally
      adjust thickness or dash style.
  - name: save the presentation
    text: Persist the modified presentation to disk.
  type: HowTo
- questions:
  - answer: '`Presentation` represents a PowerPoint file in memory.'
    question: What is the main class for creating a presentation?
  - answer: '`slide.getShapes().addChart(...)` creates a chart object.'
    question: Which method adds a chart to a slide?
  - answer: Use `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.
    question: How do you draw a line on a chart?
  - answer: Yes—set the line’s fill to a solid red `Color.RED`.
    question: Can I set the line color to red?
  - answer: A full license removes evaluation limits; a trial works for testing.
    question: Do I need a license for production use?
  type: FAQPage
tags:
- aspose slides
- chart customization
- java presentation
title: วิธีเพิ่ม custom lines ไปยัง chart ของ Aspose Slides ด้วย Java
url: /th/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มเส้นกำหนดเองลงในแผนภูมิ Aspose Slides ด้วย Java

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีเพิ่มเส้นกำหนดเองลงใน **aspose slides chart** ด้วย Java. เส้นกำหนดเองช่วยให้คุณเน้นค่าขีดจำกัด, แนวโน้ม, หรือจุดข้อมูลสำคัญ, ทำให้แผนภูมิธรรมดากลายเป็นเรื่องราวภาพที่ทรงพลัง. เมื่อจบคู่มือคุณจะสามารถรวม Aspose.Slides เข้าในโครงการของคุณ, วาดเส้นบนแผนภูมิ, และปรับแต่งลักษณะของเส้นเพื่อให้ได้ผลกระทบสูงสุด.

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีการติดตั้งและรับใบอนุญาต Aspose.Slides for Java
- ขั้นตอนที่แน่นอนในการวาดเส้นกำหนดเองบนแผนภูมิ
- วิธีการจัดรูปแบบเส้น (สี, ความหนา, รูปแบบเส้นประ)
- สถานการณ์จริงที่เส้นกำหนดเองช่วยปรับปรุงการสื่อสารข้อมูล

## คำตอบอย่างรวดเร็ว
- **คลาสหลักสำหรับสร้างการนำเสนอคืออะไร?** `Presentation` represents a PowerPoint file in memory.  
- **เมธอดใดที่เพิ่มแผนภูมิลงในสไลด์?** `slide.getShapes().addChart(...)` creates a chart object.  
- **คุณวาดเส้นบนแผนภูมิอย่างไร?** Use `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.  
- **ฉันสามารถตั้งค่าสีเส้นเป็นสีแดงได้หรือไม่?** Yes—set the line’s fill to a solid red `Color.RED`.  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** A full license removes evaluation limits; a trial works for testing.  

`ShapeType.Line` เป็นค่า enum ที่บอก Aspose.Slides ให้สร้าง auto‑shape รูปเส้น.

## Aspose Slides chart คืออะไร?

**Aspose Slides chart** คืออ็อบเจ็กต์แผนภูมิที่โปรแกรมได้ซึ่งอยู่ภายในสไลด์ PowerPoint, ทำให้คุณสามารถสร้าง, แก้ไข, และจัดรูปแบบแผนภูมิทั้งหมดจากโค้ด Java. มันรองรับหลายประเภทของแผนภูมิ (คอลัมน์, แถบ, เส้น, พาย ฯลฯ), ให้การควบคุมเต็มรูปแบบต่อซีรีส์, แกน, คำอธิบาย, และสามารถผสานกับองค์ประกอบสไลด์อื่น ๆ เช่นรูปภาพและรูปร่างกำหนดเอง, ทำให้เหมาะสำหรับการรายงานอัตโนมัติและการนำเสนอแบบไดนามิก.

## ทำไมต้องเพิ่มเส้นกำหนดเองลงใน Aspose Slides chart?

เส้นกำหนดเองช่วยให้คุณทำหมายเหตุบนแผนภูมิด้วยสัญญาณภาพที่แม่นยำ. Aspose.Slides รองรับ **50+ input and output formats** และสามารถประมวลผลการนำเสนอที่มี **hundreds of slides** ในขณะที่ใช้หน่วยความจำต่ำกว่า **150 MB of RAM** บนเครื่องพัฒนาแบบทั่วไป, ทำให้เหมาะสำหรับการรายงานในระดับใหญ่.

## ข้อกำหนดเบื้องต้น

- **Aspose.Slides for Java** – เวอร์ชัน 25.4 (หรือใหม่กว่า)  
- **JDK 16+** – runtime Java ล่าสุดใดก็ได้  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  
- ความรู้พื้นฐาน Java และความคุ้นเคยกับแนวคิด PowerPoint  

### ไลบรารีที่ต้องการ
- Aspose.Slides for Java (Version 25.4)

### การตั้งค่าสภาพแวดล้อม
- ติดตั้ง JDK 16 หรือใหม่กว่า  
- ใช้ Maven หรือ Gradle เพื่อจัดการ dependencies (ตัวอย่างด้านล่าง)  

## การตั้งค่า Aspose.Slides สำหรับ Java

เพิ่มไลบรารีลงในโครงการของคุณด้วยเครื่องมือสร้างต่อไปนี้.

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

สำหรับการดาวน์โหลดด้วยตนเอง, เยี่ยมชม [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) เพื่อรับแพคเกจล่าสุด.

### การรับใบอนุญาต
- **Free trial:** เริ่มทดสอบโดยไม่ต้องซื้อ.  
- **Temporary license:** ใช้สำหรับการประเมินระยะยาวโดยไม่มีลายน้ำ.  
- **Full license:** ปลดล็อกคุณสมบัติทั้งหมดสำหรับงานผลิต.  

เริ่มต้นใบอนุญาตในโค้ดของคุณตามที่แสดงด้านล่าง:
```java
License license = new License();
license.setLicense("path_to_license.lic");
```  

`License` คือคลาสที่ใช้โหลดและใช้ไฟล์ใบอนุญาต Aspose.Slides ของคุณกับแอปพลิเคชัน.

## คุณจะเพิ่มเส้นกำหนดเองลงใน Aspose Slides chart อย่างไร?

โหลดหรือสร้างการนำเสนอ, แทรกแผนภูมิ, แล้วเพิ่มรูปร่างเส้นลงในคอลเลกชัน user‑shapes ของแผนภูมิ. เส้นสามารถกำหนดตำแหน่ง, ขนาด, และสไตล์ให้ตรงกับความต้องการรายงานของคุณ. วิธีนี้ทำงานได้กับแผนภูมิคอลัมน์แบบกลุ่ม, แถบ, เส้น, และพื้นที่เช่นกัน.

## คู่มือการใช้งาน

### การเพิ่มเส้นกำหนดเองลงในแผนภูมิ

#### ภาพรวม
เส้นกำหนดเองดึงความสนใจไปยังค่าที่เฉพาะเจาะจง—เช่นขีดจำกัดงบประมาณหรือเส้นเป้าหมาย—ทำให้แผนภูมิของคุณให้ข้อมูลเชิงลึกมากขึ้น.

#### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ presentation
คลาส `Presentation` เป็นอ็อบเจ็กต์ระดับบนสุดของ Aspose.Slides ที่แทนไฟล์ PowerPoint หนึ่งไฟล์ในหน่วยความจำ.  
```java
Presentation pres = new Presentation();
```  

#### ขั้นตอนที่ 2: เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม
แทรกแผนภูมิคอลัมน์แบบกลุ่มบนสไลด์แรกที่พิกัด (100, 100) ด้วยความกว้าง 500 px และความสูง 400 px.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 400);
```  

#### ขั้นตอนที่ 3: เพิ่มเส้น auto‑shape ลงในแผนภูมิ
เพิ่มรูปร่างเส้นลงในคอลเลกชัน `userShapes` ของแผนภูมิ, ซึ่งเก็บอ็อบเจ็กต์การวาดแบบกำหนดเอง.  
```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(
    ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```  

`userShapes` คือคอลเลกชันที่เก็บรูปร่างกำหนดเองที่วาดโดยตรงบนแผนภูมิ, ช่วยให้คุณสามารถวางเส้น, ลูกศร, หรือหมายเหตุอื่น ๆ ทับบนแผนภูมิได้.

#### ขั้นตอนที่ 4: ปรับแต่งคุณสมบัติของเส้น
ตั้งค่าชนิดการเติมของเส้นเป็นแบบทึบ, เปลี่ยนสีเป็นสีแดง, และสามารถปรับความหนาหรือรูปแบบเส้นประได้ตามต้องการ.  
```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```  

#### ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขแล้วลงดิสก์.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/" + "AddCustomLines.pptx", SaveFormat.Pptx);
```  

### การทำงานกับคลาส Presentation
คลาส `Presentation` มีเมธอดสำหรับโหลด, สร้าง, และบันทึกไฟล์ PowerPoint, รวมถึงการเข้าถึงสไลด์และรูปร่างแต่ละรายการ.

### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบว่าเส้นทางไฟล์ที่ใช้ใน `save` สามารถเขียนได้; ใช้เส้นทางแบบเต็มเพื่อความน่าเชื่อถือ.  
- หากแผนภูมิไม่ปรากฏ, ตรวจสอบพิกัด X/Y อีกครั้งและให้แน่ใจว่าดัชนีสไลด์ถูกต้อง.  

## การประยุกต์ใช้งานจริง

เส้นกำหนดเองมีประโยชน์เป็นพิเศษใน:
1. **Financial reports** – เน้นขีดจำกัดงบประมาณหรือเป้าหมายกำไร.  
2. **Sales dashboards** – วาดเส้นสำหรับเป้าหมายการขายรายไตรมาส.  
3. **Healthcare analytics** – ทำเครื่องหมายค่าขีดจำกัดสำคัญในแนวโน้มสัญญาณชีพของผู้ป่วย.  

คุณยังสามารถทำให้การวางตำแหน่งเส้นเป็นอัตโนมัติโดยดึงค่าขีดจำกัดจากฐานข้อมูลหรือ API, ทำให้การรายงานเป็นแบบเรียลไทม์.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ปล่อยอ็อบเจ็กต์ `Presentation` ด้วย `presentation.dispose()` เมื่อเสร็จสิ้นเพื่อคืนหน่วยความจำเนทีฟ.  
- ใช้ความละเอียดของรูปภาพและแผนภูมิในระดับปานกลาง (เช่น 150 dpi) เพื่อควบคุมขนาดไฟล์.  
- ในระหว่างการพัฒนา, ใบอนุญาตชั่วคราวช่วยหลีกเลี่ยงลายน้ำการประเมินขณะยังคงให้การเข้าถึง API อย่างเต็มที่.

## สรุป

ตอนนี้คุณรู้วิธีเพิ่มเส้นกำหนดเองลงใน **aspose slides chart** ด้วย Java, ให้คุณควบคุมการทำหมายเหตุและการเน้นภาพบนแผนภูมิได้อย่างเต็มที่. ทดลองใช้สไตล์เส้น, ตำแหน่ง, และประเภทแผนภูมิที่ต่างกันเพื่อสร้างรายงานที่สื่อข้อมูลได้ทันที.

## ส่วนคำถามที่พบบ่อย

**Q1: ฉันสามารถเปลี่ยนสีของเส้นกำหนดเองได้หรือไม่?**  
A1: ใช่, ปรับสีเส้นโดยตั้งค่า property `SolidFillColor` ให้เป็น `java.awt.Color` ที่ต้องการใดก็ได้.

**Q2: Aspose.Slides รองรับกับ IDE Java ทั้งหมดหรือไม่?**  
A2: ใช่, ตราบใดที่ IDE ของคุณสนับสนุน Maven หรือ Gradle, คุณสามารถรวม Aspose.Slides ได้โดยไม่มีปัญหา.

**Q3: ชนิดของแผนภูมิใดบ้างที่รองรับการเพิ่มเส้นกำหนดเอง?**  
A3: สามารถเพิ่มเส้นกำหนดเองลงในแผนภูมิคอลัมน์แบบกลุ่ม, แถบ, เส้น, พื้นที่, และพาย รวมถึงอื่น ๆ.

**Q4: ฉันจะแก้ไขปัญหาในการบันทึกการนำเสนออย่างไร?**  
A4: ตรวจสอบให้แน่ใจว่าไดเรกทอรีปลายทางมีอยู่, เส้นทางไฟล์ถูกต้อง, และแอปพลิเคชันมีสิทธิ์เขียน.

**Q5: มีข้อจำกัดใดบ้างเมื่อใช้ใบอนุญาตทดลอง?**  
A5: รุ่นทดลองอาจเพิ่มลายน้ำและจำกัดคุณสมบัติพรีเมี่ยมบางอย่าง; ใบอนุญาตชั่วคราวหรือเต็มจะลบข้อจำกัดเหล่านี้ออก.

## แหล่งข้อมูล
- **Documentation**: [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license**: [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

**Last Updated:** 2026-09-07  
**Tested with:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างแผนภูมิที่กำหนดเองและเส้นแนวโน้ม Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)
- [วิธีแก้ไขข้อมูลแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java: คู่มือฉบับสมบูรณ์](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [วิธีหมุนชื่อแกนแผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนโดยละเอียด](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}