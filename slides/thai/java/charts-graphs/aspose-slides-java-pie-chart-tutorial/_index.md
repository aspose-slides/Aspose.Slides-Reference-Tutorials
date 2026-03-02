---
date: '2026-03-02'
description: เรียนรู้วิธีเพิ่ม Excel ลงใน PowerPoint และสร้าง PowerPoint จาก Excel
  โดยการสร้างแผนภูมิวงกลมแบบไดนามิกด้วย Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 'เพิ่ม Excel ลงใน PowerPoint: การนำเสนอแบบไดนามิกด้วยแผนภูมิวงกลมโดยใช้ Aspose.Slides
  สำหรับ Java'
url: /th/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เพิ่ม Excel ไปยัง PowerPoint: การนำเสนอแบบไดนามิกด้วยแผนภูมิวงกลมโดยใช้ Aspose.Slides for Java

ในสภาพแวดล้อมที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน, **add Excel to PowerPoint** อย่างรวดเร็วและเชื่อถือได้เพื่อให้ผู้ชมของคุณเห็นตัวเลขในรูปแบบภาพ. บทแนะนำนี้จะพาคุณผ่านการสร้าง PowerPoint จาก Excel, การสร้างแผนภูมิวงกลมด้วย Java, และการกำหนดช่วงข้อมูลของแผนภูมิ—ทั้งหมดด้วย Aspose.Slides for Java. เมื่อเสร็จคุณจะมีการนำเสนอที่พร้อมใช้งานซึ่งดึงข้อมูลสดโดยตรงจากเวิร์กบุ๊ก Excel.

## คำตอบด่วน
- **ไลบรารีใดสร้างแผนภูมิใน Java?** Aspose.Slides for Java.
- **ฉันสามารถดึงข้อมูล Excel ไปยังแผนภูมิ PowerPoint ได้โดยตรงหรือไม่?** Yes – use Aspose.Cells to read the workbook and feed it to the chart.
- **ประเภทแผนภูมิที่แสดงคืออะไร?** A pie chart.
- **ฉันตั้งค่าช่วงข้อมูลสำหรับแผนภูมิอย่างไร?** By calling `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.
- **ประโยชน์หลักของวิธีการนี้คืออะไร?** Automates the “add Excel to PowerPoint” workflow, eliminating manual copy‑paste.

## อะไรคือ **add Excel to PowerPoint**?
การเพิ่ม Excel ไปยัง PowerPoint หมายถึงการนำเข้าข้อมูลสเปรดชีตโดยโปรแกรมและแสดงผลภายในชุดสไลด์. ด้วย Aspose.Slides และ Aspose.Cells, คุณสามารถอ่านไฟล์ Excel ใดก็ได้, แมปเซลล์ไปยังซีรีส์ของแผนภูมิ, และสร้างการนำเสนอที่ดูดีโดยไม่ต้องเปิด PowerPoint ด้วยตนเอง.

## ทำไมต้องสร้าง PowerPoint จาก Excel ด้วย Aspose.Slides for Java?
- **Speed:** สร้างรายงานในไม่กี่วินาที ไม่ใช่หลายนาที.
- **Accuracy:** ข้อมูลถูกอ่านโดยตรงจากเวิร์กบุ๊กต้นทาง, ลดข้อผิดพลาดจากการคัดลอก.
- **Flexibility:** ปรับแต่งสีของแผนภูมิ, สไตล์, และช่วงข้อมูลได้ตามต้องการ.
- **Scalability:** ผสานรวมกับงานแบบแบตช์, เว็บเซอร์วิส, หรือไพป์ไลน์การรายงานที่กำหนดเวลา.

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่ม, ตรวจสอบให้แน่ใจว่าคุณมี:

- **Java Development Kit (JDK) 1.8+** ติดตั้งแล้ว.
- **Aspose.Slides for Java** และ **Aspose.Cells for Java** ไลบรารี (Maven, Gradle, หรือดาวน์โหลด JAR โดยตรง).
- เวิร์กบุ๊ก Excel (`book1.xlsx`) ที่มีข้อมูลที่คุณต้องการแสดงผล.
- ใบอนุญาต Aspose ที่ถูกต้อง (รุ่นทดลองฟรีใช้ได้สำหรับการประเมิน).

### ไลบรารีที่จำเป็น
คุณจะต้องใช้ Aspose.Slides และ Aspose.Cells. ใช้เครื่องมือจัดการ dependencies ใดต่อไปนี้:

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

### การรับใบอนุญาต
- **Free Trial:** มีให้ดาวน์โหลดบน [Aspose download page](https://releases.aspose.com/slides/java/).  
- **Temporary License:** สำหรับการทดสอบโดยไม่มีข้อจำกัดการประเมิน, ขอรับได้ที่ [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).  
- **Purchase License:** เพื่อใช้ผลิตภัณฑ์ Aspose ในการผลิต, ซื้อใบอนุญาตเต็มรูปแบบ.

## การตั้งค่า Aspose.Slides for Java

เพิ่ม dependency ของ Aspose.Slides ลงในโปรเจกต์ของคุณ (ดูตัวอย่าง Maven/Gradle ด้านบน) และวางไฟล์ JAR ลงใน classpath หากคุณไม่ได้ใช้เครื่องมือสร้าง.

### การเริ่มต้นและตั้งค่าเบื้องต้น
Import the core class that represents a PowerPoint file:

```java
import com.aspose.slides.Presentation;
```

## คู่มือการดำเนินการ

ด้านล่างเป็นขั้นตอนแบบละเอียดที่ครอบคลุม **create pie chart java**, **set chart data range**, และ **add Excel to PowerPoint** ในขั้นตอนเดียว.

### สร้างและเพิ่มแผนภูมิลงในงานนำเสนอ

**Overview:** เริ่มต้นงานนำเสนอใหม่, ดึงสไลด์แรก, และแทรกแผนภูมิวงกลม.

#### ขั้นตอนที่ 1: เริ่มต้น Presentation
```java
Presentation pres = new Presentation();
```
- **Purpose:** สร้างไฟล์ PowerPoint ว่างเปล่าในหน่วยความจำ.

#### ขั้นตอนที่ 2: เข้าถึงสไลด์แรก
```java
ISlide slide = pres.getSlides().get_Item(0);
```
- **Explanation:** ดึงสไลด์แรกที่สร้างโดยอัตโนมัติ.

#### ขั้นตอนที่ 3: เพิ่มแผนภูมิวงกลมลงในสไลด์
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **Parameters:** ตำแหน่ง (`x`, `y`) และขนาด (`width`, `height`).  
- **Purpose:** วางรูปร่างแผนภูมิวงกลมบนสไลด์.

### โหลดเวิร์กบุ๊กจากไฟล์

**Overview:** โหลดเวิร์กบุ๊ก Excel ที่มีข้อมูลสำหรับแผนภูมิ.

#### ขั้นตอนที่ 1: กำหนดไดเรกทอรีของเอกสาร
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- ตั้งค่านี้เป็นโฟลเดอร์ที่มี `book1.xlsx`.

#### ขั้นตอนที่ 2: เปิดเวิร์กบุ๊ก
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **Purpose:** อ่านไฟล์ Excel เข้าสู่หน่วยความจำ.

### บันทึกเวิร์กบุ๊กเป็น ByteArrayOutputStream

**Overview:** แปลงเวิร์กบุ๊กเป็นอาร์เรย์ไบต์เพื่อให้ Aspose.Slides ใช้งานได้.

#### ขั้นตอนที่ 1: สร้าง ByteArrayOutputStream
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```
- **Purpose:** ให้สตรีมในหน่วยความจำสำหรับการจัดเก็บชั่วคราว.

#### ขั้นตอนที่ 2: บันทึกเวิร์กบุ๊กลงสตรีม
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```
- **Explanation:** เขียนเวิร์กบุ๊กเป็นสตรีมไบต์รูปแบบ XLSX.

### เขียนข้อมูลเวิร์กบุ๊กลงในแผนภูมิ

**Overview:** ส่งอาร์เรย์ไบต์ของ Excel ไปยังแผนภูมิเป็นแหล่งข้อมูล.

#### ขั้นตอนที่ 1: ป้อนข้อมูลลงในแผนภูมิ
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **Purpose:** เชื่อมแผนภูมิกับข้อมูล Excel.

### ตั้งค่าช่วงข้อมูลของแผนภูมิและกำหนดค่าซีรีส์

**Overview:** กำหนดเซลล์ที่แผนภูมิจะอ่านและปรับปรุงสไตล์การแสดงผล.

#### ขั้นตอนที่ 1: กำหนดช่วงข้อมูล
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```
- **Explanation:** ชี้แผนภูมิไปยังช่วงที่แน่นอนบน *Sheet2*.

#### ขั้นตอนที่ 2: กำหนดค่าคุณสมบัติของซีรีส์
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```
- **Purpose:** เปิดใช้งานสีที่แตกต่างสำหรับแต่ละชิ้นของแผนภูมิวงกลม.

### บันทึกงานนำเสนอเป็นไฟล์

**Overview:** บันทึกงานนำเสนอที่เสร็จสมบูรณ์ลงดิสก์.

#### ขั้นตอนที่ 1: กำหนดเส้นทางเอาต์พุต
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```
- เลือกโฟลเดอร์ที่คุณต้องการบันทึกไฟล์ PowerPoint สุดท้าย.

#### ขั้นตอนที่ 2: บันทึกงานนำเสนอ
```java
pres.save(outPath, SaveFormat.Pptx);
```
- **Explanation:** เขียนงานนำเสนอเป็นไฟล์ `.pptx`.

## การประยุกต์ใช้งานจริง

1. **Business Reporting:** แปลงสเปรดชีตยอดขายรายเดือนเป็นชุดสไลด์ที่ดูดีด้วยคำสั่งเดียว.  
2. **Educational Tools:** แสดงการแยกสถิติสำหรับการนำเสนอในห้องเรียนโดยไม่ต้องสร้างแผนภูมิด้วยมือ.  
3. **Dashboard Integration:** ทำให้การสร้างแดชบอร์ดแบบสไลด์อัตโนมัติที่ดึงข้อมูลสดจากเวิร์กบุ๊ก Excel.

## ข้อควรพิจารณาด้านประสิทธิภาพ

- **Memory Management:** ห่อสตรีมด้วย try‑with‑resources หรือปิดในบล็อก `finally` เพื่อหลีกเลี่ยงการรั่วไหล.  
- **Large Datasets:** ประมวลผลข้อมูลเป็นชิ้นส่วนหรือใช้ `Workbook.getWorksheets().clear()` หลังจากดึงค่าที่ต้องการ.  
- **Lazy Loading:** โหลดเวิร์กบุ๊กเฉพาะเมื่อคุณต้องการเติมข้อมูลลงในแผนภูมิ, ไม่ใช่ตอนเริ่มแอปพลิเคชัน.

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Solution |
|-------|----------|
| **Chart shows no data** | ตรวจสอบว่า string ช่วงตรงกับชื่อแผ่นและที่อยู่เซลล์อย่างแม่นยำ (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | ใช้ `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` เพื่อให้สตรีมถูกปล่อยอย่างรวดเร็ว. |
| **License not applied** | โหลดใบอนุญาตก่อนที่คลาส Aspose ใดจะถูกสร้าง: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## คำถามที่พบบ่อย

**Q: Can I use Aspose.Slides without a license?**  
A: ใช่, แต่โหมดประเมินจะใส่ลายน้ำและจำกัดบางฟีเจอร์. สำหรับการผลิต, ควรได้รับใบอนุญาตชั่วคราวหรือเต็มรูปแบบ.

**Q: How do I handle large presentations in Aspose.Slides?**  
A: ใช้การจัดการทรัพยากรอย่างมีประสิทธิภาพ, แบ่งงานนำเสนอเป็นส่วนย่อย, และทำลายอ็อบเจกต์ที่ไม่ได้ใช้โดยเร็ว.

**Q: What file formats can Aspose.Slides export to?**  
A: PPTX, PDF, XPS, ODP, HTML, และรูปภาพเช่น PNG, JPEG, และ BMP.

**Q: Is it possible to update an existing PowerPoint file instead of creating a new one?**  
A: แน่นอน. โหลดไฟล์ที่มีอยู่ด้วย `new Presentation("existing.pptx")`, แก้ไขสไลด์/แผนภูมิ, แล้วบันทึก.

**Q: Does the library support setting custom colors for individual pie slices?**  
A: ใช่ – หลังจากดึงซีรีส์, คุณสามารถตั้งค่า `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` และกำหนด `Color`.

## แหล่งข้อมูล
- **Documentation:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)
- **Purchase License:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Free Trial:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Temporary License:** [Get a Temporary License](https://purchase.aspose.com/temporary-license)

---
**อัปเดตล่าสุด:** 2026-03-02  
**ทดสอบด้วย:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}