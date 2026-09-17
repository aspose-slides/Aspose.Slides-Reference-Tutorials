---
date: '2026-09-17'
description: เรียนรู้วิธีเพิ่ม clustered column chart ลงในงานนำเสนอ PowerPoint, ปรับแต่ง
  PowerPoint chart, และแทรก data series chart ด้วย Aspose.Slides for Java
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: เรียนรู้วิธีเพิ่ม clustered column chart ลงในงานนำเสนอ PowerPoint
  ด้วย Aspose.Slides for Java รวมถึงขั้นตอนการแทรก data series, ปรับแต่ง grouping,
  และบันทึกไฟล์เป็น PPTX
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: เพิ่ม clustered column chart ใน PowerPoint ด้วย Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: วิธีเพิ่ม clustered column chart ใน PowerPoint ด้วย Aspose.Slides for Java
url: /th/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่มใน PowerPoint ด้วย Aspose.Slides for Java

## บทนำ

เมื่อคุณต้องการ **เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม** ลงในชุดสไลด์ PowerPoint ภาพที่ชัดเจนสามารถเปลี่ยนตัวเลขดิบให้กลายเป็นเรื่องราวที่เข้าใจได้ทันที การทำเช่นนี้ด้วยตนเองใน PowerPoint ใช้เวลามาก โดยเฉพาะเมื่อคุณต้องสร้างสไลด์จำนวนมากโดยอัตโนมัติ **Aspose.Slides for Java** ขจัดความยุ่งยาก – มันทำให้คุณสร้าง ปรับแต่งแผนภูมิ PowerPoint และแทรกแผนภูมิดาต้าชุดได้ด้วยเพียงไม่กี่บรรทัดของโค้ด

ในบทเรียนนี้คุณจะได้เรียนรู้วิธีการ:
- สร้างการนำเสนอ PowerPoint ใหม่ด้วย Aspose.Slides for Java  
- **เพิ่มแผนภูมิลงในสไลด์** และกำหนดให้เป็นแผนภูมิคอลัมน์แบบกลุ่ม  
- **สร้างแผนภูมิคอลัมน์แบบกลุ่ม** โดยกำหนดระดับการจัดกลุ่มสำหรับหมวดหมู่  
- **แทรกแผนภูมิดาต้าชุด** เพื่อให้ข้อมูลของคุณแสดงอย่างถูกต้อง  
- บันทึกการนำเสนอที่เสร็จสมบูรณ์เป็นไฟล์ PPTX

## คำตอบด่วน
- **คลาสหลักคืออะไร?** `Presentation` จาก `com.aspose.slides`.  
- **ประเภทแผนภูมิที่ใช้คืออะไร?** `ChartType.ClusteredColumn`.  
- **ฉันต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** การทดลองใช้ฟรีทำงานได้ แต่ไลเซนส์จะลบข้อจำกัดการประเมินผล.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 16 หรือใหม่กว่า (ตัวอย่างใช้ JDK 16).  
- **วิธีรันตัวอย่าง?** เพิ่มการขึ้นต่อ Maven/Gradle, คอมไพล์, และเรียกใช้เมธอด `main`.

## “การเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม” คืออะไร?
แผนภูมิคอลัมน์แบบกลุ่มจะแสดงชุดข้อมูลหลายชุดเคียงข้างกันสำหรับแต่ละหมวดหมู่ ทำให้คุณเปรียบเทียบค่าต่าง ๆ ข้ามกลุ่มในภาพเดียวได้ เหมาะสำหรับยอดขายรายไตรมาส ผลสำรวจ หรือสถานการณ์ใด ๆ ที่คุณต้องการเปรียบเทียบชุดข้อมูลหลายชุดในหมวดหมู่เดียว

## ทำไมต้องใช้ Aspose.Slides เพื่อเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม?
คุณสามารถสร้างสไลด์หลายสิบสไลด์โดยอัตโนมัติ ปรับแต่งองค์ประกอบภาพทุกอย่าง และรันโค้ดบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java—ไม่ต้องติดตั้ง Microsoft Office Aspose.Slides รองรับ **แผนภูมิมากกว่า 50 ประเภท** และสามารถประมวลผลการนำเสนอที่มี **สูงสุด 500 สไลด์** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้เหมาะกับสายงานการรายงานขนาดใหญ่

## ข้อกำหนดเบื้องต้น
- **ไลบรารี Aspose.Slides for Java** (แนะนำให้ใช้เวอร์ชันล่าสุด).  
- JDK 16 หรือใหม่กว่า.  
- เครื่องมือสร้าง Maven หรือ Gradle (หรือคุณสามารถเพิ่มไฟล์ JAR ด้วยตนเอง).  
- IDE หรือโปรแกรมแก้ไขข้อความเพื่อรันโค้ด Java.

## การตั้งค่า Aspose.Slides for Java
เพิ่มไลบรารีลงในโครงการของคุณโดยใช้สคริปต์การสร้างต่อไปนี้

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

หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดโดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การรับไลเซนส์
ก่อนนำไปใช้ในผลิตภัณฑ์จริง ให้รับไลเซนส์:
- **ทดลองใช้ฟรี** – สำรวจคุณสมบัติทั้งหมดโดยไม่ต้องซื้อ.  
- **ไลเซนส์ชั่วคราว** – ประเมินความสามารถเพิ่มเติมในระยะสั้น.  
- **ไลเซนส์เต็ม** – ปลดล็อกการใช้งานไม่จำกัด. รับได้จาก [Aspose's purchase page](https://purchase.aspose.com/buy).

## วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่มใน PowerPoint ด้วย Aspose.Slides for Java?
โหลด `Presentation` ใหม่, เพิ่มสไลด์, แทรก `Chart` ประเภท `ChartType.ClusteredColumn`, เติมข้อมูลในเวิร์กบุ๊กภายในด้วยหมวดหมู่และชุดข้อมูล, จากนั้นบันทึกไฟล์เป็น PPTX. ลำดับนี้สร้างแผนภูมิคอลัมน์แบบกลุ่มที่ทำงานเต็มรูปแบบด้วยเพียงไม่กี่การเรียก API.

### เริ่มต้นการนำเสนอ
`Presentation` คือคลาสที่แทนไฟล์ PowerPoint ในหน่วยความจำ ทำให้คุณสามารถเพิ่มสไลด์, รูปร่าง, และแผนภูมิได้โดยโปรแกรม

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### เพิ่มแผนภูมิลงในสไลด์
`ChartType.ClusteredColumn` บอก Aspose.Slides ให้เรนเดอร์แผนภูมิคอลัมน์แบบกลุ่ม

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### เตรียมเวิร์กบุ๊กข้อมูลแผนภูมิ
แผนภูมิเก็บข้อมูลในเวิร์กบุ๊กภายใน การล้างข้อมูลจะให้พื้นที่ว่างสำหรับข้อมูลที่กำหนดเอง

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### เพิ่มหมวดหมู่พร้อมระดับการจัดกลุ่ม
การจัดกลุ่มหมวดหมู่สร้างเอฟเฟกต์แผนภูมิคอลัมน์แบบกลุ่ม แต่ละหมวดหมู่สามารถเป็นส่วนหนึ่งของกลุ่มตรรกะที่ปรากฏในป้ายแกน

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### เพิ่มชุดข้อมูลลงในแผนภูมิ
อ็อบเจ็กต์ `Series` แทนคอลัมน์แต่ละอันในแผนภูมิ การเพิ่มหลายชุดทำให้ได้คอลัมน์เคียงข้างกันสำหรับแต่ละหมวดหมู่

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### บันทึกการนำเสนอพร้อมแผนภูมิ
การบันทึก `Presentation` จะเขียนไฟล์ PPTX มาตรฐานที่สามารถเปิดได้ในโปรแกรมดู PowerPoint ใดก็ได้

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## การประยุกต์ใช้งานจริง
- **รายงานธุรกิจ** – เปรียบเทียบรายได้รายไตรมาสตามภูมิภาค.  
- **การวิจัยทางวิชาการ** – แสดงผลการทดลองที่จัดกลุ่มตามเงื่อนไขการทดสอบ.  
- **การจัดการโครงการ** – แสดงอัตราการทำงานเสร็จของหลายทีมในสไลด์เดียว.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ** – ปล่อยเวิร์กบุ๊กขนาดใหญ่หลังการใช้.  
- **การดำเนินการแบบแบตช์** – หลีกเลี่ยงการอัปเดตแผนภูมิภายในลูปที่แคบ; รวบรวมข้อมูลก่อนแล้วจึงนำไปใช้.  
- **การปรับแต่งในตัว** – Aspose.Slides มีเมธอดเช่น `Presentation.optimize()` สำหรับไฟล์ขนาดใหญ่ ลดการใช้หน่วยความจำได้ถึง **30 %**.

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ข้อผิดพลาด:** ลืมล้างชุดข้อมูล/หมวดหมู่ที่มีอยู่อาจทำให้ข้อมูลซ้ำซ้อน.  
  **เคล็ดลับ:** ควรเรียก `clear()` ก่อนเติมข้อมูลใหม่เสมอ.  
- **ข้อผิดพลาด:** ใช้ที่อยู่เซลล์ผิด (เช่น `"c2"` แทน `"C2"`).  
  **เคล็ดลับ:** การอ้างอิงเซลล์ไม่สนใจตัวพิมพ์ใหญ่/เล็ก แต่ควรรักษาความสอดคล้องเพื่อความอ่านง่าย.  
- **เคล็ดลับ:** ใช้ `setGroupingItem` เพื่อสร้างป้ายกลุ่มที่มีความหมาย; ป้ายเหล่านี้จะปรากฏในคำอธิบายแผนภูมิโดยอัตโนมัติ.

## คำถามที่พบบ่อย
**Q1: ฉันจะเพิ่มหลายชุดข้อมูลลงในแผนภูมิของฉันได้อย่างไร?**  
A1: เรียก `ch.getChartData().getSeries().add()` ซ้ำ ๆ โดยให้ชื่อที่ไม่ซ้ำและจุดข้อมูลสำหรับแต่ละชุด.

**Q2: ปัญหาทั่วไปที่พบกับแผนภูมิ Aspose.Slides มีอะไรบ้าง?**  
A2: ปัญหามักเกิดจากช่วงข้อมูลไม่ตรงกันหรือเซลล์เวิร์กบุ๊กหาย ตรวจสอบให้แน่ใจว่าทุกหมวดหมู่และจุดข้อมูลมีเซลล์ที่สอดคล้องกัน.

**Q3: ฉันสามารถใช้ Aspose.Slides กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A3: ได้, Aspose มีไลบรารีที่เทียบเท่าสำหรับ .NET, C++, Python และอื่น ๆ.

**Q4: ฉันจะอัปเดตแผนภูมิที่มีอยู่ในการนำเสนอได้อย่างไร?**  
A4: โหลดการนำเสนอ, ค้นหาแผนภูมิโดยใช้ `slide.getShapes().get_Item(index)`, จากนั้นแก้ไขชุดข้อมูลหรือการจัดรูปแบบตามต้องการ.

**Q5: มีข้อจำกัดใด ๆ เกี่ยวกับประเภทแผนภูมิใน Aspose.Slides หรือไม่?**  
A5: ไลบรารีรองรับมากกว่า **50 ประเภทแผนภูมิ** และเพิ่มประเภทใหม่อย่างต่อเนื่อง; ควรตรวจสอบเอกสารล่าสุดเพื่อดูรายการที่อัปเดตที่สุด.

## แหล่งข้อมูล
- **เอกสาร:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **ดาวน์โหลด:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **ซื้อ:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **ทดลองใช้ฟรี:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **ไลเซนส์ชั่วคราว:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **ฟอรั่มสนับสนุน:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**อัปเดตล่าสุด:** 2026-09-17  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง
- [สร้างคู่มือการสร้างแผนภูมิใน Java ด้วย Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนโดยละเอียด](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [เพิ่มแอนิเมชันให้แผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนโดยละเอียด](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}