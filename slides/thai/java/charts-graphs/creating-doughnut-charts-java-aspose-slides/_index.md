---
date: '2026-07-27'
description: เรียนรู้วิธีสร้าง Doughnut Chart Java ด้วย Aspose.Slides – คู่มือสั้นเพื่อกำหนดค่าไลบรารี,
  เพิ่มแผนภูมิ Doughnut ที่ปรับแต่งได้, ปรับขนาดรู, และบันทึกการนำเสนอ
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: เรียนรู้วิธีสร้าง Doughnut Chart Java ด้วย Aspose.Slides – คู่มือสั้นเพื่อกำหนดค่าไลบรารี,
  เพิ่มแผนภูมิ Doughnut ที่ปรับแต่งได้, ปรับขนาดรู, และบันทึกการนำเสนอ
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: สร้าง Doughnut Chart Java – ขั้นตอนโดยละเอียดกับ Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: สร้าง Doughnut Chart Java – ขั้นตอนโดยละเอียดกับ Aspose.Slides
url: /th/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูดิดอนัทใน Java ด้วย Aspose.Slides สำหรับการนำเสนอ

## บทนำ
การสร้างการนำเสนอที่ดูสวยงามเป็นสิ่งสำคัญสำหรับการสื่อสารข้อมูลอย่างมีประสิทธิภาพ. **Create doughnut chart java** เป็นความต้องการทั่วไปเมื่อคุณต้องการแสดงข้อมูลเชิงสัดส่วนด้วยรูปลักษณ์ที่ทันสมัย. ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีตั้งค่า Aspose.Slides for Java, สร้างแผนภูดิดอนัท, ปรับขนาดรูและสี, และสุดท้ายบันทึกไฟล์การนำเสนอ. เมื่อเสร็จคุณจะมีรูปแบบที่นำกลับมาใช้ใหม่ได้ซึ่งสามารถใส่ลงในโครงการ Java ใด ๆ ที่สร้างสไลด์ PowerPoint อัตโนมัติ.

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides for Java
- การสร้างและกำหนดค่าแผนภูดิดอนัทในงานนำเสนอ
- การปรับแต่งลักษณะของแผนภูมิ เช่น ขนาดรู
- การบันทึกการนำเสนอพร้อมแผนภูมิใหม่ของคุณ

มาเริ่มต้นโดยการตั้งค่าสภาพแวดล้อมของเรากันเถอะ!

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดที่สร้าง doughnut chart java?** Aspose.Slides for Java.  
- **ต้องใช้บรรทัดโค้ดเท่าไหร่สำหรับแผนภูดิดอนัทพื้นฐาน?** ประมาณ 8–10 บรรทัดหลังจากสร้างอ็อบเจ็กต์ Presentation.  
- **ฉันสามารถเปลี่ยนขนาดรูได้หรือไม่?** ใช่, เมธอด `setHoleSize(double)` รับค่าตั้งแต่ 0 % ถึง 100 %.  
- **รูปแบบผลลัพธ์ที่รองรับคืออะไร?** PPTX, PDF, XPS, PNG, JPEG และอื่น ๆ อีกหลายรูปแบบ (รวมกว่า 50 รูปแบบ).  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานไม่จำกัด; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน.

## Aspose.Slides for Java คืออะไร?
**Aspose.Slides for Java** เป็น API ที่จัดการเต็มรูปแบบที่ช่วยให้นักพัฒนาสามารถสร้าง, แก้ไข, แปลง, และแสดงไฟล์ PowerPoint โดยไม่ต้องใช้ Microsoft Office. รองรับไฟล์รูปแบบมากกว่า 50 แบบและสามารถจัดการการนำเสนอที่มีสไลด์หลายพันสไลด์โดยคงการใช้หน่วยความจำน้อย.

## ทำไมต้องใช้แผนภูดิดอนัทในงานนำเสนอ?
แผนภูดิดอนัทแสดงความสัมพันธ์ส่วนต่อส่วนรวมโดยปล่อยพื้นที่ตรงกลางสำหรับป้ายกำกับหรือรูปภาพ. Aspose.Slides สามารถเรนเดอร์แผนภูดิดอนัทได้ถึง **500 สไลด์ต่อหนึ่งนาที** บนเซิร์ฟเวอร์ที่มีความเร็วประมาณ 2.5 GHz, และสามารถประมวลผล **การนำเสนอหลายร้อยหน้า** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ทำให้เหมาะสำหรับโซลูชันการรายงานในระดับใหญ่.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณได้ทำตามข้อกำหนดเบื้องต้นเหล่านี้แล้ว:

### ไลบรารีและเวอร์ชันที่ต้องการ
เพื่อทำงานกับ Aspose.Slides for Java, ให้รวมไลบรารีนี้ในโครงการของคุณผ่าน Maven หรือ Gradle, หรือดาวน์โหลดโดยตรง.

#### ความต้องการในการตั้งค่าสภาพแวดล้อม
- JDK (Java Development Kit) ที่ทำงานได้, แนะนำเวอร์ชัน 8 หรือสูงกว่า.
- IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse.

### ความรู้เบื้องต้นที่จำเป็น
ความคุ้นเคยกับ Java และแนวคิดการเขียนโปรแกรมพื้นฐานเป็นประโยชน์. ความรู้พื้นฐานของ Maven หรือ Gradle จะช่วยให้การตั้งค่าง่ายขึ้น.

## การตั้งค่า Aspose.Slides for Java
การนำ Aspose.Slides เข้าไปในโครงการของคุณสามารถทำได้หลายวิธี:

**Maven:**  
เพิ่ม dependency นี้ในไฟล์ `pom.xml` ของคุณ:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
ใส่ส่วนนี้ในไฟล์ `build.gradle` ของคุณ:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การรับใบอนุญาต
- **Free Trial:** เริ่มต้นด้วยการดาวน์โหลดเวอร์ชันทดลองเพื่อสำรวจคุณสมบัติของ Aspose.Slides.  
- **Temporary License:** รับใบอนุญาตชั่วคราวเพื่อใช้งานฟังก์ชันเพิ่มเติมโดยไม่มีข้อจำกัด.  
- **Purchase:** สำหรับการใช้งานต่อเนื่องจำเป็นต้องซื้อใบอนุญาต.

เมื่อคุณตั้งค่าห้องสมุดและสภาพแวดล้อมเรียบร้อยแล้ว, เรามาไปยังขั้นตอนการสร้างแผนภูดิดอนัทของเรา.

## วิธีสร้างแผนภูดิดอนัทใน Java?
โหลดอ็อบเจ็กต์ `Presentation` ใหม่, เพิ่มแผนภูดิดอนัทลงในสไลด์, ตั้งค่าขนาดรู, และบันทึกไฟล์ – ทั้งหมดนี้ทำได้ด้วยการเรียก API ไม่กี่ครั้ง. วิธีนี้ให้คุณควบคุมข้อมูลแผนภูมิ, รูปลักษณ์, และรูปแบบการส่งออกได้เต็มที่, และทำงานโดยไม่ต้องติดตั้ง Microsoft PowerPoint บนเซิร์ฟเวอร์.

### เริ่มต้นอ็อบเจ็กต์ Presentation
คลาส `Presentation` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Slides ที่แทนไฟล์ PowerPoint ในหน่วยความจำ.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
ขั้นตอนนี้สร้างการนำเสนอเปล่าที่คุณสามารถเพิ่มสไลด์, รูปร่าง, และแผนภูมิได้.

### เพิ่มแผนภูดิดอนัทลงในสไลด์
`ISlide` เป็นอินเทอร์เฟซของสไลด์เดียว; คุณสามารถดึงสไลด์แรกหรือเพิ่มสไลด์ใหม่ได้.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
เมธอด `addChart` สร้างแผนภูดิดอนัท; พารามิเตอร์กำหนดตำแหน่ง (X, Y) และขนาด (ความกว้าง, ความสูง) บนสไลด์.

### กำหนดขนาดรูของแผนภูดิดอนัท
`Chart` มีเมธอด `setHoleSize(double)` เพื่อควบคุมรัศมีภายในเป็นเปอร์เซ็นต์ของรัศมีแผนภูมิ.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
การตั้งค่าขนาดรูเป็น 90 % ทำให้แผนภูดิดูเหมือนวงกลมเต็ม, ซึ่งเป็นประโยชน์เมื่อคุณต้องการเน้นส่วนภายนอก.

### บันทึกการนำเสนอ
`presentation.save(String, SaveFormat)` เขียนไฟล์ลงดิสก์ในรูปแบบที่เลือก.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
ตัวอย่างบันทึกผลลัพธ์เป็น `DoughnutHoleSize_out.pptx`, แต่คุณก็สามารถเลือกเป็น PDF, PNG หรือรูปแบบที่รองรับกว่า 50 แบบอื่นได้.

### ทำความสะอาดทรัพยากร
การเรียก `presentation.dispose()` จะปล่อยทรัพยากรเนทีฟและป้องกันการรั่วไหลของหน่วยความจำ, ซึ่งสำคัญโดยเฉพาะในแอปพลิเคชันเซิร์ฟเวอร์ที่ทำงานต่อเนื่อง.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```

## การประยุกต์ใช้งานจริง
แผนภูดิดอนัทมีความหลากหลาย นี่คือตัวอย่างสถานการณ์ที่มันโดดเด่น:
1. **การจัดสรรงบประมาณ:** แสดงวิธีการกระจายงบประมาณไปยังแต่ละแผนก.  
2. **ผลสำรวจ:** แสดงผลการตอบคำถามที่มีตัวเลือกหลายตัว.  
3. **แหล่งที่มาของการเข้าชมเว็บไซต์:** แสดงเปอร์เซ็นต์ของการเข้าชมที่มาจากช่องทางต่าง ๆ (ออร์แกนิก, ชำระเงิน, การอ้างอิง, ฯลฯ).

## ข้อควรพิจารณาด้านประสิทธิภาพ
เมื่อทำงานกับ Aspose.Slides, พิจารณาคำแนะนำต่อไปนี้เพื่อประสิทธิภาพที่ดีที่สุด:
- ปล่อยอ็อบเจ็กต์ `Presentation` ทันทีที่เสร็จสิ้นเพื่อคืนหน่วยความจำเนทีฟ.  
- ใช้สตรีม (`FileInputStream`, `ByteArrayOutputStream`) สำหรับชุดข้อมูลขนาดใหญ่เพื่อหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่ RAM.  
- ใช้แผนภูมิซ้ำเมื่อสร้างสไลด์หลาย ๆ สไลด์ในลูป เพื่อลดภาระการสร้างอ็อบเจ็กต์.

## ปัญหาและวิธีแก้ไขทั่วไป
- **ข้อผิดพลาดขณะบันทึก:** ตรวจสอบว่าไดเรกทอรีปลายทางมีอยู่และแอปพลิเคชันมีสิทธิ์เขียน.  
- **ข้อมูลแผนภูมิหาย:** ตรวจสอบว่าคุณได้เติมข้อมูลในคอลเลกชัน `ChartData` ของแผนภูมิก่อนเรียก `setHoleSize`.  
- **การเพิ่มขึ้นของหน่วยความจำ:** สำหรับการนำเสนอที่มีสไลด์หลายพันสไลด์, เปิดใช้งาน `Presentation.setSlideSize` ให้เป็นขนาดเล็กลงและปล่อยสไลด์กลางโดยเร็ว.

## คำถามที่พบบ่อย

**Q: ฉันสามารถปรับสีของส่วนต่าง ๆ ของแผนภูดิดอนัทได้หรือไม่?**  
A: ใช่. ใช้ `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` แล้วกำหนดสี RGB ที่ต้องการ.

**Q: ฉันจะเพิ่มป้ายกำกับข้อมูลให้กับแผนภูมิได้อย่างไร?**  
A: เรียก `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` เพื่อแสดงค่าภายในแต่ละส่วน.

**Q: สามารถบันทึกแผนภูมิในรูปแบบอื่นนอกจาก PPTX ได้หรือไม่?**  
A: แน่นอน. Aspose.Slides รองรับ PDF, XPS, PNG, JPEG, TIFF, และรูปแบบอื่น ๆ อีกมาก—รวมกว่า 50 รูปแบบ.

**Q: ควรทำอย่างไรหากพบข้อยกเว้นขณะโหลดการนำเสนอขนาดใหญ่?**  
A: ใช้คอนสตรัคเตอร์ `Presentation` ที่รับสตรีมและเปิดใช้งาน `loadOptions.setLoadFormat(LoadFormat.Pptx)` เพื่อสตรีมไฟล์และลดการใช้หน่วยความจำ.

**Q: ฉันสามารถทำให้แผนภูมิตัวอัปเดตอัตโนมัติด้วยแหล่งข้อมูลสดได้หรือไม่?**  
A: ใช่. ดึงข้อมูลจากฐานข้อมูลหรือ REST API, อัปเดตคอลเลกชัน `ChartData`, แล้วเรียก `chart.refresh()` ก่อนบันทึกการนำเสนอ.

## แหล่งข้อมูล
- **Documentation:** สำรวจเอกสารอ้างอิง API รายละเอียดที่ [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Download:** ดาวน์โหลดเวอร์ชันล่าสุดของไลบรารีจาก [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Purchase:** สำหรับการเข้าถึงเต็มรูปแบบ, ซื้อใบอนุญาตที่ [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Free Trial:** ทดลองใช้ Aspose.Slides ด้วยเวอร์ชันทดลองฟรีที่หน้าดาวน์โหลด.  
- **Temporary License:** รับใบอนุญาตชั่วคราวเพื่อการทดสอบต่อเนื่องโดยไม่มีข้อจำกัด.  
- **Support:** มีคำถาม? เยี่ยมชม [Aspose Forum](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือ.

---

**อัปเดตล่าสุด:** 2026-07-27  
**ทดสอบด้วย:** Aspose.Slides for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนโดยละเอียด](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides: คู่มือฉบับสมบูรณ์](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}