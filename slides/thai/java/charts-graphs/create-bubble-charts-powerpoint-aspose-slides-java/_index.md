---
date: '2026-09-17'
description: เรียนรู้วิธีสร้าง bubble chart powerpoint ด้วย Aspose.Slides for Java.
  คู่มือนี้แสดงวิธีเพิ่ม chart ไปยัง slide, กำหนดค่า bubble size, และบันทึก PPTX อย่างมีประสิทธิภาพ.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: เรียนรู้วิธีสร้าง bubble chart powerpoint ด้วย Aspose.Slides for Java.
  บทเรียนนี้อธิบายวิธีเพิ่ม chart ไปยัง slide, ปรับขนาด bubble, และบันทึก presentation
  อย่างมีประสิทธิภาพ.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: สร้าง bubble chart powerpoint ด้วย Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: สร้าง bubble chart powerpoint ด้วย Aspose.Slides for Java
url: /th/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างแผนภูมิบับเบิลใน PowerPoint ด้วย Aspose.Slides สำหรับ Java

## บทนำ
หากคุณต้องการ **create bubble chart powerpoint** การนำเสนอโดยโปรแกรม, Aspose.Slides for Java จะมอบ API แบบเซิร์ฟเวอร์‑ไซด์ที่สะอาดและทำงานได้โดยไม่ต้องใช้ Microsoft Office ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีเพิ่มแผนภูมิลงในสไลด์, ควบคุมขนาดของบับเบิล, และบันทึกไฟล์ PPTX สุดท้ายพร้อมการจัดการทรัพยากรอย่างมีประสิทธิภาพ ขั้นตอนต่าง ๆ ถูกแบ่งเป็นส่วนย่อยเพื่อให้คุณสามารถคัดลอก‑วางโค้ดลงในโครงการ Java ใดก็ได้และเห็นผลทันที

## คำตอบด่วน
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Slides for Java
- **เวอร์ชัน Java ที่ต้องการคืออะไร?** JDK 16 or higher
- **จะเพิ่มแผนภูมิบับเบิลอย่างไร?** Call `addChart(ChartType.Bubble, …)` on a slide
- **ฉันสามารถเปลี่ยนขนาดบับเบิลได้หรือไม่?** Yes, via `setBubbleSizeScale()`
- **จะบันทึกไฟล์อย่างไร?** Use `pres.save("Result.pptx", SaveFormat.Pptx)`

## สร้างแผนภูมิบับเบิลใน PowerPoint คืออะไร?
การสร้างแผนภูมิบับเบิลใน PowerPoint หมายถึงการสร้างแผนภูมิโดยโปรแกรม ซึ่งแต่ละจุดข้อมูลจะแสดงเป็นบับเบิลที่ตำแหน่ง X‑position, Y‑position และขนาดบ่งบอกมิติข้อมูลสามมิติ Aspose.Slides for Java จะจัดการการเรนเดอร์ให้คุณจึงไม่จำเป็นต้องติดตั้ง PowerPoint

## ทำไมต้องใช้ Aspose.Slides สำหรับ Java?
Aspose.Slides รองรับ **50+ chart types** สามารถประมวลผลการนำเสนอได้ถึง **2 GB** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ และทำงานบนแพลตฟอร์มใด ๆ ที่รองรับ Java 16+ ความสามารถที่ระบุเป็นตัวเลขเหล่านี้ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับการรายงานระดับองค์กร

## ข้อกำหนดเบื้องต้น
- **Java Development Kit** 16 หรือใหม่กว่า ติดตั้งแล้ว.
- **Aspose.Slides for Java** ไลบรารี (เพิ่มผ่าน Maven, Gradle, หรือดาวน์โหลด JAR โดยตรง).
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และการเขียนโปรแกรมเชิงวัตถุ

## การตั้งค่า Aspose.Slides สำหรับ Java
เพื่อเริ่มใช้ Aspose.Slides ให้รวมไลบรารีในระบบการสร้างของคุณ

### Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
ใส่ส่วนนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
คุณยังสามารถรับ JAR ล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### การรับใบอนุญาต
- **Free trial** – สำรวจคุณสมบัติทั้งหมดโดยไม่มีค่าใช้จ่าย.  
- **Temporary license** – การประเมินต่อเนื่องสำหรับโครงการขนาดใหญ่.  
- **Full license** – จำเป็นสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  

### การเริ่มต้นและตั้งค่าเบื้องต้น
คลาส `Presentation` เป็นจุดเริ่มต้นสำหรับการสร้างหรือโหลดไฟล์ PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## คู่มือการทำงาน
ต่อไปนี้เป็นขั้นตอนแบบละเอียดสำหรับการสร้างแผนภูมิบับเบิลและการจัดการทรัพยากร

## วิธีสร้างแผนภูมิบับเบิลใน PowerPoint
ในส่วนนี้คุณจะได้เรียนรู้ลำดับการเรียก API ที่จำเป็นเพื่อสร้างแผนภูมิบับเบิล, ตั้งค่าลักษณะการแสดงผล, และบันทึกผลลัพธ์เป็นไฟล์ PPTX วิธีนี้ทำงานกับโครงการ Java ใด ๆ ที่รวม Aspose.Slides และปฏิบัติตามแนวทางการจัดการทรัพยากรที่ดีที่สุด

โหลดการนำเสนอ, เพิ่มแผนภูมิบับเบิล, ตั้งค่าลักษณะการแสดงผล, และบันทึกไฟล์

### คำตอบโดยตรง
สร้าง `Presentation` ใหม่, เรียก `addChart(ChartType.Bubble, …)` บนสไลด์ที่ต้องการ, ปรับสเกลขนาดบับเบิลด้วย `setBubbleSizeScale(150)`, แล้วบันทึกโดยใช้ `pres.save("Result.pptx", SaveFormat.Pptx)` ลำดับนี้จะเพิ่มแผนภูมิบับเบิลที่ทำงานเต็มรูปแบบในไม่กี่บรรทัดของ Java

- **`ChartType.Bubble`** แสดงประเภทแผนภูมิบับเบิล.  
- **`addChart`** แทรกแผนภูมิใหม่ของประเภทที่ระบุลงบนสไลด์.  
- **`setBubbleSizeScale`** ปรับขนาดโดยรวมของบับเบิลในแผนภูมิ.  
- **`SaveFormat.Pptx`** ระบุรูปแบบไฟล์ PPTX สำหรับการบันทึก.  

#### การดำเนินการแบบขั้นตอน
**1. เริ่มต้นการนำเสนอ** – สร้างอ็อบเจกต์ `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. เพิ่มแผนภูมิบับเบิล** – แทรกแผนภูมิที่พิกัดที่เลือก.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` บอก Aspose.Slides ให้สร้างแผนภูมิบับเบิล.  
- พารามิเตอร์ตัวเลขกำหนดตำแหน่ง X/Y และความกว้าง/ความสูงเป็นหน่วยจุด.

**3. ตั้งค่าสเกลขนาดบับเบิล** – ขยายบับเบิลเพื่อให้เห็นผลภาพที่ดีขึ้น.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- การตั้งค่าสเกลเป็น **150 %** ทำให้บับเบิลแต่ละอันใหญ่ขึ้น 1.5 × เท่าของค่าเริ่มต้น.

**4. บันทึกการนำเสนอ** – เขียนไฟล์ PPTX ลงดิสก์.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบสิทธิ์การเขียนสำหรับโฟลเดอร์ผลลัพธ์.  
- ยืนยันว่า JAR ของ Aspose.Slides ตรงกับเวอร์ชัน JDK ที่คุณใช้งาน.

## วิธีจัดการทรัพยากร PowerPoint อย่างมีประสิทธิภาพ
การจัดการทรัพยากรอย่างมีประสิทธิภาพช่วยป้องกันการรั่วไหลของหน่วยความจำและทำให้ขนาด JVM ต่ำลง โดยเฉพาะเมื่อประมวลผลเด็คขนาดใหญ่หรือทำงานในสภาพแวดล้อมเซิร์ฟเวอร์ ให้ทำตามรูปแบบด้านล่างเพื่อรับประกันว่าทรัพยากรพื้นฐานจะถูกปล่อยแม้เกิดข้อยกเว้น

### คำตอบโดยตรง
หลังจากทำงานกับ `Presentation` เสร็จสิ้น ให้เรียก `pres.dispose()` ภายในบล็อก `try‑finally` เสมอ; การทำเช่นนี้จะปล่อยทรัพยากรพื้นฐานและทำให้ JVM สามารถคืนหน่วยความจำได้อย่างรวดเร็ว

- **`pres.dispose()`** ปล่อยทรัพยากรพื้นฐานที่ใช้โดยการนำเสนอ.

**1. สร้างและแก้ไข** – ทำงานกับการนำเสนอตามต้องการ.  
```java
Presentation pres = new Presentation();
```

**2. ปล่อยทรัพยากร** – ปลดปล่อยหน่วยความจำเมื่อการประมวลผลเสร็จสิ้น.  
```java
if (pres != null) pres.dispose();
```

## การประยุกต์ใช้ในทางปฏิบัติ
แผนภูมิบับเบิลโดดเด่นในสถานการณ์ที่ต้องการแสดงมิติข้อมูลสามมิติพร้อมกัน:

1. **Market analysis** – ขนาดบับเบิลแสดงรายได้ในขณะที่แกน X/Y แสดงการเติบโตและส่วนแบ่งตลาด.  
2. **Performance metrics** – เปรียบเทียบประสิทธิภาพพนักงาน (X), ความพึงพอใจ (Y), และผลกระทบ (ขนาด).  
3. **Geographical data** – แสดงเมืองโดยเข้ารหัสประชากรเป็นขนาดบับเบิล.  
4. **Project management** – แสดงไทม์ไลน์ (X), ค่าใช้จ่าย (Y), และความเสี่ยง (ขนาด) บนสไลด์เดียว.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Resource usage** – ปล่อยการนำเสนอโดยเร็วเพื่อให้การใช้ heap ต่ำ.  
- **Java memory management** – ห่อหุ้มการทำงานของการนำเสนอใน `try‑finally` เพื่อรับประกันการปล่อยทรัพยากรแม้เกิดข้อยกเว้น.  
- **Stay current** – อัปเกรดเป็นเวอร์ชันล่าสุดของ Aspose.Slides เพื่อรับประโยชน์จากการปรับปรุงประสิทธิภาพและการแก้ไขบั๊ก.

## คำถามที่พบบ่อย

**Q: Aspose.Slides for Java คืออะไร?**  
A: Aspose.Slides for Java เป็นไลบรารีสแตนด์อโลนที่ให้คุณสร้าง, แก้ไข, และแปลงไฟล์ PowerPoint โดยไม่ต้องใช้ Microsoft Office.

**Q: ฉันจะรวม Aspose.Slides กับโครงการ Java ที่มีอยู่ของฉันอย่างไร?**  
A: เพิ่ม dependency ของ Maven หรือ Gradle ตามที่แสดงไว้ก่อนหน้า, หรือวาง JAR ลงใน classpath ของคุณ, จากนั้น import `com.aspose.slides.*`.

**Q: ฉันสามารถใช้ Aspose.Slides กับการนำเสนอขนาดใหญ่ได้หรือไม่?**  
A: ได้, ไลบรารีจัดการการนำเสนอได้อย่างมีประสิทธิภาพถึง **2 GB** และรองรับการสตรีมเพื่อหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.

**Q: มีประเภทแผนภูมิอะไรบ้างนอกจากแผนภูมิบับเบิล?**  
A: รองรับ **50 chart types** ขึ้นไป, รวมถึงแผนภูมิแท่ง, เส้น, พาย, เรดาร์, และวอเตอร์ฟอล.

**Q: มีการสนับสนุนในตัวสำหรับการจัดรูปแบบองค์ประกอบของแผนภูมิหรือไม่?**  
A: แน่นอน. คุณสามารถปรับแต่งสี, ฟอนต์, เส้นขอบ, และป้ายข้อมูลผ่านอ็อบเจกต์ `ChartSeries` และ `ChartTitle` ของแผนภูมิ.

## แหล่งข้อมูล
- **เอกสาร**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **ดาวน์โหลด**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **ซื้อ**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **ทดลองใช้ฟรี**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **ใบอนุญาตชั่วคราว**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **สนับสนุน**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**อัปเดตล่าสุด:** 2026-09-17  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนโดยละเอียด](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java สร้างแผนภูมิ PowerPoint ด้วย Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [สร้างแผนภูมิ PowerPoint ด้วย Java – บันทึกการนำเสนอพร้อมแผนภูมิด้วย Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}