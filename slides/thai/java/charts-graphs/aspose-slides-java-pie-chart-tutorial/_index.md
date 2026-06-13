---
date: '2026-06-13'
description: เรียนรู้วิธีเพิ่ม Excel ไปยัง PowerPoint และสร้าง PowerPoint จาก Excel
  โดยการสร้างแผนภูมิวงกลมแบบไดนามิกด้วย Aspose.Slides for Java.
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'เพิ่ม Excel ไปยัง PowerPoint: การนำเสนอแบบไดนามิกด้วยแผนภูมิวงกลมโดยใช้ Aspose.Slides
  for Java'
url: /th/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เพิ่ม Excel ไปยัง PowerPoint: การนำเสนอแบบไดนามิกด้วยแผนภูมิวงกลมโดยใช้ Aspose.Slides for Java

ในสภาพแวดล้อมที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน, **add Excel to PowerPoint** อย่างรวดเร็วและเชื่อถือได้เพื่อให้ผู้ชมของคุณเห็นตัวเลขในรูปแบบภาพ. บทแนะนำนี้จะพาคุณผ่านการสร้าง PowerPoint จาก Excel, การสร้างแผนภูมิวงกลมด้วย Java, และการกำหนดช่วงข้อมูลของแผนภูมิ—ทั้งหมดด้วย Aspose.Slides for Java. เมื่อเสร็จสิ้นคุณจะมีงานนำเสนอที่พร้อมใช้งานซึ่งดึงข้อมูลสดจากเวิร์กบุ๊ก Excel โดยตรง.

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่สร้างแผนภูมิใน Java คืออะไร?** Aspose.Slides for Java.  
- **ฉันสามารถดึงข้อมูล Excel ไปยังแผนภูมิ PowerPoint ได้โดยตรงหรือไม่?** ใช่ – ใช้ Aspose.Cells เพื่ออ่านเวิร์กบุ๊กและส่งให้แผนภูมิ.  
- **ประเภทแผนภูมิที่แสดงคืออะไร?** แผนภูมิวงกลม.  
- **ฉันตั้งค่าช่วงข้อมูลสำหรับแผนภูมิอย่างไร?** โดยเรียก `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.  
- **ประโยชน์หลักของวิธีนี้คืออะไร?** ทำให้กระบวนการ “เพิ่ม Excel ไปยัง PowerPoint” เป็นอัตโนมัติ ลดการคัดลอก‑วางด้วยมือ.

## **add Excel to PowerPoint** คืออะไร?
การเพิ่ม Excel ไปยัง PowerPoint หมายถึงการนำเข้าข้อมูลสเปรดชีตโดยโปรแกรมและแสดงผลภายในชุดสไลด์ ซึ่งทำให้คุณสามารถเก็บข้อมูลต้นฉบับในรูปแบบ Excel ได้ในขณะที่นำเสนอเป็นแผนภูมิที่ดูเป็นมืออาชีพ และการอัปเดตใด ๆ ในเวิร์กบุ๊กจะสะท้อนในงานนำเสนอโดยทันที.

## ทำไมต้องสร้าง PowerPoint จาก Excel ด้วย Aspose.Slides for Java?
การสร้าง PowerPoint จาก Excel ด้วย Aspose.Slides for Java ทำให้คุณสร้างชุดสไลด์ได้ในไม่กี่วินาทีโดยดึงข้อมูลตรงจากเวิร์กบุ๊กโดยไม่ต้องคัดลอก‑วางด้วยมือ. ไลบรารีนี้รองรับรูปแบบเข้าและออกกว่า 50 รูปแบบ, ประมวลผลเวิร์กบุ๊กหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, และให้การควบคุมโปรแกรมเต็มรูปแบบต่อการจัดรูปแบบแผนภูมิ, สี, และช่วงข้อมูล.

## วิธีสร้าง PowerPoint จาก Excel ด้วย Aspose.Slides for Java?
โหลดเวิร์กบุ๊ก Excel ด้วย Aspose.Cells, สร้าง `Presentation` ใหม่, เพิ่มรูปแผนภูมิวงกลมลงในสไลด์, แล้วผูกแผนภูมิกับช่วงข้อมูลของเวิร์กบุ๊ก. ด้วยเพียงไม่กี่บรรทัดของโค้ด Java คุณสามารถสร้างไฟล์ `.pptx` ที่สะท้อนค่าตารางล่าสุดได้.

## วิธีนำเข้า Excel ไปยัง PowerPoint ด้วย Aspose.Slides?
การนำเข้า Excel ไปยัง PowerPoint ทำได้โดยอ่านไฟล์ Excel เข้าเป็นอ็อบเจ็กต์ `Workbook`, แปลงเวิร์กบุ๊กเป็นอาร์เรย์ไบต์, แล้วส่งอาร์เรย์ไบต์นั้นไปยังแหล่งข้อมูลของแผนภูมิ. แผนภูมิจะอ่านช่วงที่ระบุโดยอัตโนมัติ ทำให้ภาพแสดงผลสอดคล้องกับสเปรดชีตเสมอ.

## วิธีตั้งค่าช่วงข้อมูลของแผนภูมิใน Aspose.Slides for Java?
ใช้เมธอด `chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` เพื่อชี้แผนภูมิไปยังเซลล์ที่มีหมวดหมู่และค่า. การเรียกครั้งเดียวนี้กำหนดทั้งแหล่งข้อมูลและการจัดวาง, ลดความจำเป็นในการสร้างซีรีส์ด้วยมือ.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK) 1.8+** ติดตั้งแล้ว.
- **Aspose.Slides for Java** และ **Aspose.Cells for Java** (Maven, Gradle, หรือดาวน์โหลด JAR โดยตรง).
- เวิร์กบุ๊ก Excel (`book1.xlsx`) ที่มีข้อมูลที่คุณต้องการแสดงผล.
- ลิขสิทธิ์ Aspose ที่ถูกต้อง (รุ่นทดลองฟรีใช้ได้สำหรับการประเมิน).

### ไลบรารีที่จำเป็น
คุณจะต้องใช้ Aspose.Slides และ Aspose.Cells. ใช้เครื่องมือจัดการ dependency ใดต่อไปนี้:

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

หรือดาวน์โหลด JAR โดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การรับลิขสิทธิ์
- **รุ่นทดลองฟรี:** มีให้ดาวน์โหลดที่ [Aspose download page](https://releases.aspose.com/slides/java/).  
- **ลิขสิทธิ์ชั่วคราว:** สำหรับการทดสอบโดยไม่มีข้อจำกัดการประเมิน สามารถขอได้ที่ [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).  
- **ลิขสิทธิ์แบบซื้อ:** เพื่อใช้ผลิตภัณฑ์ Aspose ในการผลิต ให้ซื้อลิขสิทธิ์เต็มรูปแบบ.

## การตั้งค่า Aspose.Slides for Java

เพิ่ม dependency ของ Aspose.Slides ไปยังโปรเจกต์ของคุณ (ดู snippet ของ Maven/Gradle ด้านบน) และวางไฟล์ JAR บน classpath หากไม่ได้ใช้เครื่องมือ build.

### การเริ่มต้นและตั้งค่าเบื้องต้น
นำเข้าคลาสหลักที่แทนไฟล์ PowerPoint:  
```java
import com.aspose.slides.Presentation;
```  

## คู่มือการดำเนินการ

ด้านล่างเป็นขั้นตอนแบบละเอียดที่ครอบคลุม **create pie chart java**, **set chart data range**, และ **add Excel to PowerPoint** ในกระบวนการเดียว.

### สร้างและเพิ่มแผนภูมิไปยังงานนำเสนอ

**ภาพรวม:** เริ่มต้นงานนำเสนอใหม่, ดึงสไลด์แรก, และแทรกแผนภูมิวงกลม.

#### ขั้นตอนที่ 1: เริ่มต้น Presentation  
```java
Presentation pres = new Presentation();
```  
- **วัตถุประสงค์:** สร้างไฟล์ PowerPoint ว่างในหน่วยความจำ.

#### ขั้นตอนที่ 2: เข้าถึงสไลด์แรก  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **คำอธิบาย:** ดึงสไลด์แรกที่สร้างโดยอัตโนมัติ.

#### ขั้นตอนที่ 3: เพิ่มแผนภูมิวงกลมไปยังสไลด์  
`IChart` object แทนรูปแผนภูมิบนสไลด์.  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **พารามิเตอร์:** ตำแหน่ง (`x`, `y`) และขนาด (`width`, `height`).  
- **วัตถุประสงค์:** วางรูปแผนภูมิวงกลมบนสไลด์.

### โหลดเวิร์กบุ๊กจากไฟล์

**ภาพรวม:** โหลดเวิร์กบุ๊ก Excel ที่มีข้อมูลสำหรับแผนภูมิ.

#### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- ตั้งค่านี้เป็นโฟลเดอร์ที่มี `book1.xlsx`.

#### ขั้นตอนที่ 2: เปิดเวิร์กบุ๊ก  
`Workbook` class จาก Aspose.Cells โหลดไฟล์ Excel เข้าไปในหน่วยความจำ.  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **วัตถุประสงค์:** อ่านไฟล์ Excel เข้าไปในหน่วยความจำ.

### บันทึกเวิร์กบุ๊กเป็น ByteArrayOutputStream

**ภาพรวม:** แปลงเวิร์กบุ๊กเป็นอาร์เรย์ไบต์เพื่อให้ Aspose.Slides ใช้งานได้.

#### ขั้นตอนที่ 1: สร้าง ByteArrayOutputStream  
`ByteArrayOutputStream` ให้บัฟเฟอร์ในหน่วยความจำสำหรับข้อมูลไบนารี.  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **วัตถุประสงค์:** ให้สตรีมในหน่วยความจำสำหรับการจัดเก็บชั่วคราว.

#### ขั้นตอนที่ 2: บันทึกเวิร์กบุ๊กลงสตรีม  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **คำอธิบาย:** เขียนเวิร์กบุ๊กเป็นสตรีมไบต์ XLSX.

### เขียนข้อมูลเวิร์กบุ๊กลงในแผนภูมิ

**ภาพรวม:** ส่งอาร์เรย์ไบต์ของ Excel ไปยังแผนภูมิเป็นแหล่งข้อมูล.

#### ขั้นตอนที่ 1: ป้อนข้อมูลลงในแผนภูมิ  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **วัตถุประสงค์:** เชื่อมแผนภูมิกับข้อมูล Excel.

### ตั้งค่าช่วงข้อมูลของแผนภูมิและกำหนดซีรีส์

**ภาพรวม:** กำหนดเซลล์ที่แผนภูมิจะอ่านและปรับแต่งสไตล์การแสดงผล.

#### ขั้นตอนที่ 1: กำหนดช่วงข้อมูล  
`setRange` method กำหนดเซลล์ Excel ที่ใช้เป็นแหล่งข้อมูลของแผนภูมิ.  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **คำอธิบาย:** ชี้แผนภูมิไปยังช่วงที่แน่นอนบน *Sheet2*.

#### ขั้นตอนที่ 2: กำหนดคุณสมบัติของซีรีส์  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **วัตถุประสงค์:** เปิดใช้งานสีที่แตกต่างสำหรับแต่ละชิ้นของแผนภูมิวงกลม.

### บันทึกงานนำเสนอเป็นไฟล์

**ภาพรวม:** บันทึกงานนำเสนอที่เสร็จสมบูรณ์ลงดิสก์.

#### ขั้นตอนที่ 1: กำหนดเส้นทางเอาต์พุต  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- เลือกโฟลเดอร์ที่ต้องการบันทึกไฟล์ PowerPoint สุดท้าย.

#### ขั้นตอนที่ 2: บันทึกงานนำเสนอ  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **คำอธิบาย:** เขียนงานนำเสนอเป็นไฟล์ `.pptx`.

## การประยุกต์ใช้งานจริง

- **การรายงานทางธุรกิจ:** แปลงสเปรดชีตยอดขายรายเดือนเป็นชุดสไลด์ที่ดูเป็นมืออาชีพด้วยคำสั่งเดียว.  
- **เครื่องมือการศึกษา:** แสดงการแยกสถิติสำหรับการนำเสนอในห้องเรียนโดยไม่ต้องสร้างแผนภูมิด้วยมือ.  
- **การรวมกับแดชบอร์ด:** ทำให้การสร้างแดชบอร์ดแบบสไลด์เป็นอัตโนมัติโดยดึงข้อมูลสดจากเวิร์กบุ๊ก Excel.

## ข้อควรพิจารณาด้านประสิทธิภาพ

- **การจัดการหน่วยความจำ:** ห่อสตรีมด้วย try‑with‑resources หรือปิดในบล็อก `finally` เพื่อหลีกเลี่ยงการรั่วไหล.  
- **ชุดข้อมูลขนาดใหญ่:** ประมวลผลข้อมูลเป็นชิ้นส่วนหรือใช้ `Workbook.getWorksheets().clear()` หลังจากดึงค่าที่ต้องการ.  
- **การโหลดแบบ Lazy:** โหลดเวิร์กบุ๊กเฉพาะเมื่อจำเป็นต้องเติมข้อมูลในแผนภูมิ ไม่ใช่เมื่อเริ่มแอปพลิเคชัน.

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **Chart shows no data** | ตรวจสอบว่าข้อความช่วงตรงกับชื่อแผ่นและที่อยู่เซลล์อย่างแม่นยำ (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | ใช้ `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` เพื่อให้สตรีมถูกปล่อยโดยเร็ว. |
| **License not applied** | โหลดลิขสิทธิ์ก่อนที่คลาส Aspose ใด ๆ จะถูกสร้างอินสแตนซ์: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Slides ได้โดยไม่ต้องมีลิขสิทธิ์หรือไม่?**  
**ตอบ:** ใช่, แต่โหมดประเมินผลจะเพิ่มลายน้ำและจำกัดบางฟีเจอร์ สำหรับการใช้งานจริง ควรขอรับลิขสิทธิ์ชั่วคราวหรือเต็มรูปแบบ.

**ถาม: ฉันจะจัดการกับงานนำเสนอขนาดใหญ่ใน Aspose.Slides อย่างไร?**  
**ตอบ:** ใช้การจัดการทรัพยากรอย่างมีประสิทธิภาพ, แบ่งงานนำเสนอเป็นส่วนย่อย ๆ, และทำลายอ็อบเจ็กต์ที่ไม่ได้ใช้โดยเร็ว.

**ถาม: Aspose.Slides สามารถส่งออกเป็นรูปแบบไฟล์อะไรได้บ้าง?**  
**ตอบ:** PPTX, PDF, XPS, ODP, HTML, และรูปแบบภาพเช่น PNG, JPEG, BMP.

**ถาม: สามารถอัปเดตไฟล์ PowerPoint ที่มีอยู่แทนการสร้างไฟล์ใหม่ได้หรือไม่?**  
**ตอบ:** แน่นอน. โหลดไฟล์ที่มีอยู่ด้วย `new Presentation("existing.pptx")`, แก้ไขสไลด์/แผนภูมิ, แล้วบันทึก.

**ถาม: ไลบรารีสนับสนุนการตั้งค่าสีที่กำหนดเองสำหรับแต่ละชิ้นของแผนภูมิวงกลมหรือไม่?**  
**ตอบ:** ใช่ – หลังจากดึงซีรีส์, คุณสามารถตั้งค่า `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` แล้วกำหนด `Color`.

## แหล่งข้อมูล
- **เอกสารอ้างอิง:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **ดาวน์โหลด:** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)
- **ซื้อไลเซนส์:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **รุ่นทดลองฟรี:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **ลิขสิทธิ์ชั่วคราว:** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2026-06-13  
**ทดสอบกับ:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [How to add pie chart PowerPoint with Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}