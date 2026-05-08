---
date: '2026-02-17'
description: เรียนรู้วิธีเพิ่มแผนภูมิวงกลมในงานนำเสนอ PowerPoint ด้วย Aspose.Slides
  for Java. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อสร้างและปรับแต่งแผนภูมิวงกลมระดับมืออาชีพ.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: วิธีเพิ่มแผนภูมิวงกลมใน PowerPoint ด้วย Aspose.Slides สำหรับ Java
url: /th/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint ด้วย Aspose.Slides for Java

## Introduction

คุณกำลังประสบปัญหาในการทำให้ข้อมูลเป็นภาพที่เข้าใจง่ายในงานนำเสนอ PowerPoint ของคุณหรือไม่? **การเพิ่มแผนภูมิวงกลม PowerPoint** สามารถเปลี่ยนตัวเลขดิบให้กลายเป็นเรื่องราวภาพที่ชัดเจนได้ทันที ด้วย Aspose.Slides for Java คุณสามารถ **เพิ่มแผนภูมิวงกลม PowerPoint** ผ่านโค้ดได้อย่างอัตโนมัติ ให้คุณควบคุมการออกแบบและข้อมูลได้เต็มที่โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง ในบทเรียนนี้เราจะพาคุณผ่านกระบวนการทั้งหมด—from การตั้งค่าห้องสมุดไปจนถึงการปรับแต่งจุดข้อมูลแต่ละจุด—เพื่อให้คุณสามารถสร้างสไลด์ที่ดูเป็นมืออาชีพและขับเคลื่อนด้วยข้อมูลได้ในเวลาไม่กี่นาที

### Quick Answers
- **ต้องใช้ห้องสมุดอะไร?** Aspose.Slides for Java (เวอร์ชันล่าสุด)  
- **สามารถสร้างแผนภูมิได้โดยไม่ต้องติดตั้ง PowerPoint หรือไม่?** ได้, API ทำงานแบบออฟไลน์ทั้งหมด  
- **ต้องใช้ Java เวอร์ชันใด?** แนะนำให้ใช้ JDK 16 หรือใหม่กว่า  
- **จะเปลี่ยนสีของชิ้นส่วนได้อย่างไร?** ใช้เมธอด `setFillType` และ `setSolidFillColor` บนจุดข้อมูล  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองสำหรับการพัฒนา; ลิขสิทธิ์ถาวรจะลบข้อจำกัดการประเมินผลออก

### What You’ll Learn
- วิธี **เพิ่มแผนภูมิวงกลม PowerPoint** ผ่านโค้ด Java  
- วิธีปรับแต่งการระเบิดชิ้นส่วน, สี, และคุณสมบัติดูอื่น ๆ  
- แนวทางปฏิบัติที่ดีที่สุดสำหรับการจัดการทรัพยากรและประสิทธิภาพเมื่อทำงานกับงานนำเสนอขนาดใหญ่

## Why add pie chart PowerPoint using Aspose.Slides for Java?
การฝังแผนภูมิวงกลมโดยตรงจากโค้ดทำให้คุณสามารถสร้างรายงานที่อัปเดตอยู่เสมอ, ทำให้แดชบอร์ดรายเดือนอัตโนมัติ, หรือสร้างชุดสไลด์ส่วนบุคคลได้อย่างรวดเร็ว มันช่วยขจัดข้อผิดพลาดจากการคัดลอก‑วางด้วยมือ, ทำให้การออกแบบสอดคล้องกันในทุกงานนำเสนอ, และรวมเข้ากับแบ็กเอนด์ Java ที่มีอยู่ได้อย่างราบรื่น

## Prerequisites

ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- **Aspose.Slides for Java library** – บทเรียนนี้อ้างอิงเวอร์ชัน 25.4 (รุ่นล่าสุด ณ เวลาที่เขียน)  
- **Java Development Kit (JDK)** ที่เข้ากันได้ – แนะนำให้ใช้ JDK 16+  
- ความคุ้นเคยพื้นฐานกับ **Maven** หรือ **Gradle** สำหรับการจัดการ dependencies  

## Setting Up Aspose.Slides for Java

เพื่อเริ่มต้น, ให้เพิ่มห้องสมุด Aspose.Slides ลงในโปรเจกต์ของคุณ

### Maven
เพิ่ม dependency นี้ลงในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
ใส่ส่วนต่อไปนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดโดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

### Licensing
เพื่อใช้ Aspose.Slides โดยไม่มีข้อจำกัด:

- เริ่มต้นด้วย **free trial** เพื่อประเมิน API  
- ขอ **temporary license** สำหรับการทดสอบระยะยาวที่หน้า [Temporary License](https://purchase.aspose.com/temporary-license/)  
- ซื้อการสมัครสมาชิกเต็มรูปแบบผ่าน [Purchase page](https://purchase.aspose.com/buy)

## How to add pie chart PowerPoint using Aspose.Slides for Java

ด้านล่างเป็นคำแนะนำแบบขั้นตอนที่แสดงวิธีสร้างและปรับแต่งแผนภูมิวงกลมอย่างละเอียด

### Step 1: Initialize the Presentation
แรกเริ่ม, สร้างอ็อบเจ็กต์ `Presentation` ใหม่ ซึ่งเป็นไฟล์ PowerPoint ว่างเปล่า
```java
Presentation pres = new Presentation();
```

### Step 2: Add the Pie Chart
แทรกแผนภูมิวงกลมลงบนสไลด์แรก พิกัด (50, 50) และขนาด (600 × 400) ทำงานได้ดีสำหรับสไลด์ขนาดมาตรฐาน 16:9
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Step 3: Save the Presentation
บันทึกงานนำเสนอลงดิสก์ แทนที่ `YOUR_OUTPUT_DIRECTORY` ด้วยโฟลเดอร์ที่คุณต้องการบันทึกไฟล์
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Step 4: Clean Up Resources
ทำลายอ็อบเจ็กต์ `Presentation` เพื่อคืนทรัพยากรเนทีฟ
```java
if (pres != null) pres.dispose();
```

## Customizing Data Point Explosion and Color

การปรับแต่งชิ้นส่วนแต่ละชิ้นทำให้แผนภูมิของคุณอ่านง่ายขึ้น, โดยเฉพาะเมื่อคุณต้องการเน้นค่าที่สำคัญ

### Step 1: Load an Existing Presentation (or reuse the one you just created)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Step 2: Access the Chart and Target Data Point
ที่นี่เราจะดึงจุดข้อมูลที่สอง (index 1) จากซีรีส์แรก
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Step 3: Apply Explosion and Color
แยกชิ้นส่วนออกจากกันโดยภาพและเปลี่ยนสีเติมเป็นสีฟ้า
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Step 4: Save and Dispose
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Practical Applications
- **Sales Reports:** เน้นผลิตภัณฑ์ขายดีด้วยชิ้นส่วนที่ระเบิดออกมา  
- **Budget Analysis:** กำหนดสีที่แตกต่างให้แต่ละแผนกเพื่อเปรียบเทียบอย่างรวดเร็ว  
- **Educational Slides:** แบ่งแนวคิดซับซ้อนเป็นส่วนของแผนภูมิที่เข้าใจง่าย

## Performance Considerations
- **Dispose objects** ทันทีเพื่อหลีกเลี่ยง memory leak, โดยเฉพาะเมื่อสร้างสไลด์หลาย ๆ สไลด์ในลูป  
- **Monitor heap usage** สำหรับงานนำเสนอขนาดใหญ่; พิจารณาใช้การสตรีมผลลัพธ์ด้วย overload ของ `Save` ที่รับ `OutputStream`  
- ใช้ **JDK 16+** เพื่อรับประโยชน์จากการปรับปรุง garbage‑collection ล่าสุด

## Conclusion
ตอนนี้คุณมีเวิร์กโฟลว์ที่พร้อมใช้งานในระดับ production เพื่อ **add pie chart PowerPoint** ด้วย Aspose.Slides for Java แล้ว ลองปรับระยะการระเบิด, สี, และชุดข้อมูลต่าง ๆ เพื่อให้สอดคล้องกับแบรนด์ของคุณ เมื่อพร้อมแล้ว, สำรวจประเภทแผนภูมิอื่น ๆ — แถบ, เส้น, หรือกระจาย — เพื่อสร้างแดชบอร์ดวิเคราะห์ข้อมูลเต็มรูปแบบภายใน PowerPoint

## FAQ Section
1. **What is the primary advantage of using Aspose.Slides for Java?**  
   - It simplifies the creation and manipulation of PowerPoint files programmatically, offering a wide array of features.  
2. **Can I customize other chart types with Aspose.Slides?**  
   - Absolutely! Aspose.Slides supports various chart types such as bar, line, and scatter charts.  
3. **How do I handle multiple slides when creating charts?**  
   - Access each slide by index using `get_Item()` method to apply changes across different slides.  
4. **What if my pie chart doesn't display correctly after customization?**  
   - Verify the coordinates and dimensions used in `addChart()`, ensuring they fit within your slide layout.  
5. **Where can I find more advanced features for Aspose.Slides?**  
   - Explore the [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) to learn about additional functionalities and options.

## Resources
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}