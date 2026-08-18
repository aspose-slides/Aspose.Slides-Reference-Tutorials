---
date: '2026-06-03'
description: เรียนรู้วิธีเพิ่ม charts ด้วย aspose slides maven dependency, กำหนดค่า
  data labels, และสร้าง dynamic charts ใน Java presentations.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: เพิ่มและกำหนดค่า Charts ใน Presentations โดยใช้
  Aspose.Slides for Java'
url: /th/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: เพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java

## บทนำ
**aspose slides maven dependency** ช่วยให้นักพัฒนา Java สามารถสร้าง แก้ไข และเพิ่มคุณค่าให้ไฟล์ PowerPoint อย่างโปรแกรมมิ่งโดยไม่ต้องเปิด PowerPoint เอง ในหลายสถานการณ์ทางธุรกิจและการศึกษา การแทรกแผนภูมิด้วยตนเองใช้เวลานานและเสี่ยงต่อข้อผิดพลาด บทเรียนนี้จะแสดงขั้นตอนโดยละเอียดว่าต้องเพิ่ม Bubble Chart อย่างไร ผูกป้ายข้อมูลกับเซลล์ใน worksheet และบันทึกผลลัพธ์—ทั้งหมดโดยใช้ aspose slides maven dependency อย่างเป็นระบบและทำซ้ำได้

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีเพิ่มแผนภูมิด้วย aspose slides maven dependency
- การตั้งค่าโครงการ Java ด้วย Maven หรือ Gradle
- การโหลดงานนำเสนอที่มีอยู่และแทรก Bubble Chart
- การกำหนดค่าป้ายข้อมูลโดยใช้การอ้างอิงเซลล์ (เพิ่มแผนภูมิป้ายข้อมูล)
- บันทึกไฟล์ที่อัปเดตเพื่อการแจกจ่ายในภายหลัง
- กรณีการใช้งานจริง เช่น การสร้างแผนภูมิแบบไดนามิกและสร้างกระบวนการทำงานของแผนภูมิในงานนำเสนอ

## คำตอบสั้น
- **Maven artifact ใดที่เพิ่มความสามารถของแผนภูมิ?** `com.aspose:aspose-slides:25.4` (or latest)  
- **ฉันสามารถผูกป้ายข้อมูลกับเซลล์แบบ Excel‑style ได้หรือไม่?** Yes – use `ChartDataLabel` with `setDataLabelFormat` and cell references.  
- **จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** A full license removes the evaluation watermark and unlocks all features.  
- **จะทำงานบน Java 11+ หรือไม่?** Absolutely; the library is compatible with Java 8 through Java 21.  
- **มีประเภทแผนภูมิจำนวนเท่าไหร่ที่รองรับ?** Over 70 distinct chart types, including Bubble, Radar, and Stock charts.

## aspose slides maven dependency คืออะไร?
**aspose slides maven dependency** เป็นแพ็กเกจที่เข้ากันได้กับ Maven ซึ่งให้ API ครบชุดสำหรับสร้างและแก้ไขไฟล์ PowerPoint (PPTX, PPT, ODP) ใน Java โดยการเพิ่ม dependency นี้ลงใน `pom.xml` หรือ `build.gradle` คุณจะได้เข้าถึงแผนภูมิกว่า 70 ประเภท, เค้าโครงสไลด์กว่า 150 แบบ, และความสามารถในการจัดการรูปทรง, แอนิเมชัน, และเมตาดาต้าโดยไม่ต้องติดตั้ง Office

## ทำไมต้องใช้ aspose slides maven dependency สำหรับการอัตโนมัติของแผนภูมิ?
Aspose.Slides สามารถประมวลผลชุดสไลด์หลายพันสไลด์ภายในเวลาน้อยกว่าสักวินาทีบนฮาร์ดแวร์เซิร์ฟเวอร์มาตรฐาน รองรับ **70+ chart types** และสามารถเรนเดอร์งานนำเสนอได้ถึง **10,000 slides** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ความสามารถเชิงปริมาณเหล่านี้ทำให้เหมาะสำหรับการสร้างแผนภูมิแบบไดนามิกระดับองค์กร ที่ต้องการประสิทธิภาพและความสามารถในการขยายตัวที่ไม่อาจต่อรองได้

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** 8 หรือใหม่กว่า (แนะนำ Java 11+).  
- **Maven** 3.6+ **หรือ** **Gradle** 6+.  
- **Aspose.Slides for Java** library (aspose slides maven dependency, เวอร์ชัน 25.4 หรือใหม่กว่า).  
- ความคุ้นเคยพื้นฐานกับคอลเลกชันของ Java และการทำ I/O กับไฟล์.  
- ไฟล์ใบอนุญาตแบบประเมินหรือเต็ม (`license.json`) หากคุณวางแผนรันโค้ดหลังช่วงทดลอง.

## วิธีเพิ่มแผนภูมิลงในสไลด์โดยใช้ Aspose.Slides?
โหลดงานนำเสนอเป้าหมาย, สร้างรูปแผนภูมิใหม่บนสไลด์ที่ต้องการ, และระบุประเภทแผนภูมิ (Bubble ในตัวอย่างนี้) การดำเนินการทั้งหมดสามารถทำได้ใน **สามบรรทัดโค้ดสั้นกระชับ** หลังจากอ้างอิงไลบรารี ทำให้เหมาะสำหรับการสร้างต้นแบบอย่างรวดเร็วและสายงานการผลิต

### ขั้นตอนที่ 1: เพิ่ม aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
สแนปชอตเหล่านี้ดึง Aspose.Slides API เต็มรูปแบบ—รวมถึงการสนับสนุนแผนภูมิ—โดยตรงจาก Maven Central.

### ขั้นตอนที่ 2: โหลดงานนำเสนอและแทรก Bubble Chart
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### ขั้นตอนที่ 3: กำหนดค่าชุดข้อมูลและป้ายของแผนภูมิ
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### ขั้นตอนที่ 4: บันทึกงานนำเสนอที่แก้ไขแล้ว
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## วิธีกำหนดค่าป้ายข้อมูลโดยใช้การอ้างอิงเซลล์?
ป้ายข้อมูลสามารถผูกกับค่าของเซลล์ภายนอกได้ คล้ายกับฟีเจอร์ “Link to Cell” ของ Excel วิธีนี้ช่วยกำจัดค่าที่เขียนตายตัวและเปิดใช้งาน **dynamic chart generation** ที่เนื้อหาป้ายอัปเดตโดยอัตโนมัติเมื่อข้อมูลพื้นฐานเปลี่ยนแปลง โดยการเชื่อมโยงแต่ละป้ายกับเซลล์ใน workbook เฉพาะ คุณจะมั่นใจว่าการแก้ไขข้อมูลต้นทางจะแสดงผลทันทีในงานนำเสนอ ลดความพยายามในการบำรุงรักษาและลดความเสี่ยงของข้อมูลล้าสมัย

### คำตอบโดยตรง
เรียก `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` แล้วส่ง `DataLabelFormat` ที่อ้างอิงที่อยู่เซลล์ เช่น `"Sheet1!A2"` Aspose.Slides จะประมวลผลการอ้างอิงในขณะรันไทม์ และแทรกค่าปัจจุบันของเซลล์ลงในป้ายของแผนภูมิ

### ขั้นตอนโดยละเอียด
1. ระบุ series ที่ต้องการป้าย.  
2. ดึงอ็อบเจ็กต์ `IDataLabel` สำหรับแต่ละ data point.  
3. ใช้ `setDataLabelFormat` พร้อม `DataLabelFormat` ที่กำหนดค่าเป็น `CellReference`.  
4. ปรับแต่งฟอนต์, สี, และตัวเลือกการแสดงผลตามต้องการ.

## วิธีบันทึกงานนำเสนอที่แก้ไขแล้ว?
การบันทึกเป็นการเรียกเมธอดเดียวที่เขียนอ็อบเจ็กต์ `Presentation` ในหน่วยความจำไปยังเส้นทางไฟล์หรือสตรีมเอาต์พุต คุณยังสามารถเลือกรูปแบบเอาต์พุต (PPTX, PDF, ODP) โดยส่งค่า `SaveFormat` enum ที่เหมาะสม การดำเนินการนี้สตรีมผลลัพธ์โดยตรงไปยังดิสก์และปล่อยทรัพยากรเนทีฟทั้งหมดโดยอัตโนมัติเมื่ออินสแตนซ์ `Presentation` ถูกปิดหรือออกจากสโคป ซึ่งช่วยให้การใช้หน่วยความจำน้อยลงแม้กับเด็คขนาดใหญ่

### คำตอบโดยตรง
เรียก `presentation.save("output.pptx", SaveFormat.Pptx)`; ไลบรารีจะสตรีมผลลัพธ์โดยตรงไปยังดิสก์และปล่อยทรัพยากรเนทีฟทั้งหมดโดยอัตโนมัติเมื่ออินสแตนซ์ `Presentation` ถูกปิดหรือออกจากสโคป

## การประยุกต์ใช้งานจริง
1. **รายงานธุรกิจ:** สร้างแผนภูมิขายไตรมาสโดยอัตโนมัติจากการดัมพ์ฐานข้อมูล.  
2. **การบรรยายทางวิชาการ:** ดึงข้อมูลวิจัยสดเข้าสไลด์การบรรยายสำหรับแต่ละคลาส.  
3. **การนำเสนอขาย:** สร้างแดชบอร์ดประสิทธิภาพเฉพาะลูกค้าแบบทันที.  
4. **การจัดการโครงการ:** แสดงไทม์ไลน์แบบ Gantt พร้อมป้ายข้อมูลไดนามิก.  
5. **การวิเคราะห์การตลาด:** ฝัง KPI ของแคมเปญลงในงานนำเสนอที่อัปเดตเมื่อมีเมตริกใหม่เข้ามา.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ:** ใช้ try‑with‑resources หรือเรียก `presentation.dispose()` อย่างชัดเจนเพื่อปล่อยหน่วยความจำเนทีฟโดยเร็ว.  
- **ชุดข้อมูลขนาดใหญ่:** เมื่อจัดการกับข้อมูลมากกว่า 10,000 จุดข้อมูล ให้เติมข้อมูลแผนภูมิผ่าน `ChartDataWorkbook` เพื่อหลีกเลี่ยงการโหลดชุดข้อมูลทั้งหมดเข้าสู่วัตถุ Java.  
- **ความปลอดภัยของเธรด:** แต่ละเธรดควรทำงานกับอินสแตนซ์ `Presentation` ของตนเอง; API ไม่ปลอดภัยต่อการใช้ร่วมกันระหว่างอ็อบเจ็กต์.

## ปัญหาทั่วไปและวิธีแก้
- **ปัญหา:** “ไม่พบไฟล์ใบอนุญาต.”  
  **วิธีแก้:** วาง `license.json` ไว้ใน classpath และเรียก `License license = new License(); license.setLicense("license.json");` ก่อนใช้ API ใด ๆ  

- **ปัญหา:** แผนภูมิแสดงเป็นสีขาวหลังบันทึก.  
  **วิธีแก้:** ตรวจสอบให้แน่ใจว่า workbook ของข้อมูลแผนภูมิถูกบันทึกพร้อมกับงานนำเสนอ (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  

- **ปัญหา:** ป้ายข้อมูลแสดงข้อผิดพลาด “#REF!”.  
  **วิธีแก้:** ตรวจสอบให้แน่ใจว่าข้อความอ้างอิงเซลล์ตรงกับชื่อแผ่นและที่อยู่ที่แน่นอน และ workbook ที่อ้างอิงได้แนบกับแผนภูมิแล้ว.  

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถเพิ่มประเภทแผนภูมิอื่น ๆ นอกจาก Bubble ได้หรือไม่?**  
**ตอบ:** ได้, `ChartType` enumeration มีประเภท line, bar, pie, radar, stock, และมากกว่า 70 ประเภทเพิ่มเติม  

**ถาม: aspose slides maven dependency ทำงานกับ OpenJDK หรือไม่?**  
**ตอบ:** แน่นอน; รองรับ OpenJDK 8‑21 อย่างเต็มที่และทำงานบนระบบปฏิบัติการหลักทั้งหมด  

**ถาม: ฉันจะฝังแผนภูมิจากไฟล์ Excel ที่มีอยู่ได้อย่างไร?**  
**ตอบ:** โหลด workbook ของ Excel ด้วย `WorkbookFactory.create(new FileInputStream("data.xlsx"))` แล้วผูก `ChartDataWorkbook` ของแผนภูมิกับ workbook นั้นก่อนตั้งค่าการอ้างอิงเซลล์  

**ถาม: มีขีดจำกัดจำนวนแผนภูมิต่อสไลด์หรือไม่?**  
**ตอบ:** โดยปฏิบัติไม่มี—Aspose.Slides สามารถจัดการกับหลายสิบแผนภูมิต่อสไลด์ได้ ขึ้นอยู่กับหน่วยความจำที่มี  

**ถาม: ฉันสามารถส่งออกงานนำเสนอสุดท้ายเป็นรูปแบบใดได้บ้าง?**  
**ตอบ:** รองรับ PPTX, PPT, ODP, PDF, XPS, HTML, และแม้กระทั่งรูปแบบภาพเช่น PNG และ JPEG  

## แหล่งข้อมูล
- [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) – ดาวน์โหลดไบนารีของไลบรารีล่าสุด.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – เอกสารอ้างอิง API อย่างครอบคลุมและคู่มือ.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – หน้าดาวน์โหลดโดยตรงสำหรับแพ็กเกจ Maven/Gradle.  
- [Purchase a License](https://purchase.aspose.com/buy) – รับใบอนุญาตเชิงพาณิชย์เต็มรูปแบบ.  
- [Free Trial](https://releases.aspose.com/slides/java/) – เริ่มต้นด้วยการทดลองเพื่อประเมินคุณสมบัติ.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – ขอคีย์ชั่วคราวสำหรับการประเมินต่อเนื่อง.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – รับความช่วยเหลือจากชุมชนและวิศวกรของ Aspose.  

## สรุป
คุณได้มีคู่มือครบวงจรจากต้นจนจบสำหรับการใช้ **aspose slides maven dependency** เพื่อเพิ่ม, กำหนดค่า, และบันทึกแผนภูมิในงานนำเสนอ Java ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถอัตโนมัติการสร้างแผนภูมิ, ผูกป้ายข้อมูลกับค่าจากเซลล์แบบสด, และสร้างเด็คระดับมืออาชีพได้อย่างมีประสิทธิภาพ ทดลองใช้ประเภทแผนภูมิอื่น ๆ, สำรวจ API แอนิเมชัน, และผสานกระบวนการนี้เข้ากับสายงานการรายงานของคุณเพื่อเพิ่มผลกระทบสูงสุด.

---  
**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างและกำหนดค่าการนำเสนอด้วย Aspose.Slides Java: คู่มือขั้นตอนต่อขั้นตอน](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [สร้าง PPTX ด้วย Java และ Aspose.Slides Maven – คู่มือการอัตโนมัติ](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides: คู่มือเชิงลึก](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}