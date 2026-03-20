---
date: '2026-03-20'
description: เรียนรู้วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในงานนำเสนอ PowerPoint, ปรับแต่งแผนภูมิ
  PowerPoint, และแทรกแผนภูมิกลุ่มข้อมูลโดยใช้ Aspose.Slides for Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่มใน PowerPoint ด้วย Aspose.Slides สำหรับ Java
url: /th/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่มใน PowerPoint ด้วย Aspose.Slides for Java

## บทนำ

เมื่อคุณต้อง **เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม** ลงในชุดสไลด์ PowerPoint ภาพที่ชัดเจนสามารถเปลี่ยนตัวเลขดิบให้เป็นเรื่องราวที่เข้าใจได้ทันที การทำเช่นนี้ด้วยตนเองใน PowerPoint อาจใช้เวลามาก โดยเฉพาะเมื่อคุณต้องสร้างสไลด์จำนวนมากโดยอัตโนมัติ **Aspose.Slides for Java** ช่วยขจัดความยุ่งยาก – มันทำให้คุณสร้างและปรับแต่งแผนภูมิ PowerPoint และแทรกแผนภูมิกลุ่มข้อมูลได้ด้วยเพียงไม่กี่บรรทัดของโค้ด

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี:
- สร้างการนำเสนอ PowerPoint ใหม่ด้วย Aspose.Slides for Java
- **เพิ่มแผนภูมิลงในสไลด์** และกำหนดให้เป็นแผนภูมิคอลัมน์แบบกลุ่ม
- **สร้างแผนภูมิคอลัมน์แบบกลุ่ม** โดยกำหนดระดับการจัดกลุ่มสำหรับหมวดหมู่
- **แทรกแผนภูมิกลุ่มข้อมูล** เพื่อให้ข้อมูลของคุณแสดงอย่างถูกต้อง
- บันทึกการนำเสนอที่เสร็จสมบูรณ์เป็นไฟล์ PPTX

ให้แน่ใจว่าคุณมีทุกอย่างที่ต้องการก่อนที่เราจะลงลึกไปในโค้ด

## คำตอบอย่างรวดเร็ว
- **คลาสหลักคืออะไร?** `Presentation` จาก `com.aspose.slides`.
- **ประเภทแผนภูมิที่ใช้คืออะไร?** `ChartType.ClusteredColumn`.
- **ฉันต้องใช้ไลเซนส์สำหรับการทดสอบหรือไม่?** การทดลองใช้ฟรีทำงานได้ แต่ไลเซนส์จะลบข้อจำกัดการประเมิน.
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 16 หรือใหม่กว่า (ตัวอย่างใช้ JDK 16).
- **วิธีรันตัวอย่าง?** เพิ่ม dependency ของ Maven/Gradle, คอมไพล์, และเรียกใช้เมธอด `main`.

## “add clustered column chart” คืออะไร?

*แผนภูมิคอลัมน์แบบกลุ่ม* (หรือที่เรียกว่าแผนภูมิคอลัมน์แบบจัดกลุ่ม) แสดงชุดข้อมูลหลายชุดเคียงข้างกันสำหรับแต่ละหมวดหมู่ ทำให้เปรียบเทียบค่าต่าง ๆ ระหว่างกลุ่มได้ง่าย ใน PowerPoint ประเภทแผนภูมินี้เหมาะสำหรับยอดขายไตรมาส, ผลสำรวจ, หรือสถานการณ์ใด ๆ ที่คุณต้องการเปรียบเทียบชุดข้อมูลหลายชุดในหมวดหมู่เดียวกัน

## ทำไมต้องใช้ Aspose.Slides เพื่อเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม?

- **การทำงานอัตโนมัติเต็มรูปแบบ** – สร้างสไลด์หลายสิบสไลด์โดยไม่ต้องทำด้วยมือ
- **การปรับแต่งละเอียด** – ควบคุมสี, ป้ายกำกับ, ระดับการจัดกลุ่ม, และอื่น ๆ
- **ข้ามแพลตฟอร์ม** – ทำงานบน OS ใดก็ได้ที่รองรับ Java
- **ไม่ต้องติดตั้ง Office** – สร้างไฟล์ PPTX บนเซิร์ฟเวอร์หรือ pipeline CI

## ข้อกำหนดเบื้องต้น

- **ไลบรารี Aspose.Slides for Java** (แนะนำให้ใช้เวอร์ชันล่าสุด)
- JDK 16 หรือใหม่กว่า
- เครื่องมือสร้าง Maven หรือ Gradle (หรือคุณสามารถเพิ่ม JAR ด้วยตนเอง)
- IDE หรือโปรแกรมแก้ไขข้อความเพื่อรันโค้ด Java

## การตั้งค่า Aspose.Slides for Java

เพิ่มไลบรารีลงในโปรเจกต์ของคุณโดยใช้สคริปต์การสร้างต่อไปนี้

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
- **ทดลองใช้ฟรี** – สำรวจคุณสมบัติทั้งหมดโดยไม่ต้องซื้อ
- **ไลเซนส์ชั่วคราว** – ประเมินความสามารถเพิ่มเติมในช่วงสั้น
- **ไลเซนส์เต็ม** – เปิดใช้งานการใช้ไม่จำกัด. รับได้จาก [Aspose's purchase page](https://purchase.aspose.com/buy)

## คู่มือการดำเนินการ

เราจะเดินผ่านแต่ละขั้นตอน พร้อมอธิบาย **วิธีเพิ่มแผนภูมิ** และ **การปรับแต่งแผนภูมิ PowerPoint** ตลอดกระบวนการ

### เริ่มต้นการนำเสนอ

แรกสุด สร้างอ็อบเจ็กต์ `Presentation` ใหม่และดึงสไลด์เริ่มต้น

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### เพิ่มแผนภูมิลงในสไลด์

ตอนนี้เราจะ **เพิ่มแผนภูมิลงในสไลด์** โดยใช้ประเภท `ClusteredColumn` และล้างข้อมูลเริ่มต้นใด ๆ

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### เตรียมเวิร์กบุ๊กข้อมูลแผนภูมิ

แผนภูมิเก็บข้อมูลในเวิร์กบุ๊กภายใน เราจะล้างมันเพื่อเริ่มต้นใหม่

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### เพิ่มหมวดหมู่พร้อมระดับการจัดกลุ่ม

การจัดกลุ่มหมวดหมู่สร้างเอฟเฟกต์ **แผนภูมิคอลัมน์แบบจัดกลุ่ม** แต่ละหมวดหมู่สามารถเป็นส่วนหนึ่งของกลุ่มตรรกะได้

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### เพิ่มชุดข้อมูลลงในแผนภูมิ

ที่นี่เราจะ **แทรกรายการชุดข้อมูลแผนภูมิ** ที่จะแสดงเป็นคอลัมน์แยกกัน

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### บันทึกการนำเสนอพร้อมแผนภูมิ

สุดท้าย เขียนไฟล์ PPTX ลงดิสก์

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## การประยุกต์ใช้ในทางปฏิบัติ

- **รายงานธุรกิจ** – เปรียบเทียบรายได้ไตรมาสตามภูมิภาค
- **การวิจัยเชิงวิชาการ** – แสดงผลการทดลองที่จัดกลุ่มตามเงื่อนไขการทดสอบ
- **การจัดการโครงการ** – แสดงอัตราการทำงานเสร็จของหลายทีมในสไลด์เดียว

## ข้อควรพิจารณาด้านประสิทธิภาพ

- **การจัดการหน่วยความจำ** – ปล่อยเวิร์กบุ๊กขนาดใหญ่หลังการใช้
- **การดำเนินการแบบแบตช์** – หลีกเลี่ยงการอัปเดตแผนภูมิภายในลูปที่แน่น; รวบรวมข้อมูลก่อนแล้วจึงนำไปใช้
- **การปรับแต่งในตัว** – Aspose.Slides มีเมธอดเช่น `Presentation.optimize()` สำหรับไฟล์ขนาดใหญ่

## ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **ข้อผิดพลาด:** ลืมล้างชุดข้อมูล/หมวดหมู่ที่มีอยู่แล้วอาจทำให้ข้อมูลซ้ำ.  
  **เคล็ดลับ:** ควรเรียก `clear()` ก่อนใส่ข้อมูลใหม่เสมอ
- **ข้อผิดพลาด:** ใช้ที่อยู่เซลล์ผิด (เช่น `"c2"` แทน `"C2"`).  
  **เคล็ดลับ:** การอ้างอิงเซลล์ไม่สนใจตัวพิมพ์ใหญ่/เล็ก แต่ควรรักษาความสอดคล้องเพื่อความอ่านง่าย
- **เคล็ดลับ:** ใช้ `setGroupingItem` เพื่อสร้างป้ายกลุ่มที่มีความหมาย; ป้ายเหล่านี้จะแสดงในคำอธิบายแผนภูมิโดยอัตโนมัติ

## คำถามที่พบบ่อย

**Q1: ฉันจะเพิ่มหลายชุดข้อมูลในแผนภูมิของฉันได้อย่างไร?**  
A1: เรียก `ch.getChartData().getSeries().add()` ซ้ำ ๆ โดยให้ชื่อที่ไม่ซ้ำและจุดข้อมูลสำหรับแต่ละชุด

**Q2: ปัญหาที่พบบ่อยกับแผนภูมิ Aspose.Slides มีอะไรบ้าง?**  
A2: ปัญหามักเกิดจากช่วงข้อมูลไม่ตรงกันหรือเซลล์เวิร์กบุ๊กหาย ตรวจสอบว่าหมวดหมู่และจุดข้อมูลทุกอันมีเซลล์ที่สอดคล้องกัน

**Q3: ฉันสามารถใช้ Aspose.Slides กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A3: ได้, Aspose มีไลบรารีที่เทียบเท่าสำหรับ .NET, C++, Python และอื่น ๆ

**Q4: ฉันจะอัปเดตแผนภูมิที่มีอยู่ในการนำเสนอได้อย่างไร?**  
A4: โหลดการนำเสนอ, ค้นหาแผนภูมิผ่าน `slide.getShapes().get_Item(index)`, แล้วแก้ไขชุดข้อมูลหรือการจัดรูปแบบตามต้องการ

**Q5: มีข้อจำกัดของประเภทแผนภูมิกับ Aspose.Slides หรือไม่?**  
A5: ไลบรารีรองรับประเภทแผนภูมิมากมาย แต่ควรตรวจสอบเอกสารล่าสุดเสมอเพื่อดูประเภทที่เพิ่มใหม่หรือที่เลิกใช้แล้ว

## แหล่งข้อมูล

- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Free Trial**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Temporary License**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support Forum**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-20  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose