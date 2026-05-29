---
date: '2026-05-29'
description: เรียนรู้วิธีสร้าง pie chart ด้วย Aspose.Slides Maven, เพิ่ม pie chart
  java ไปยังสไลด์, และปรับแต่งข้อมูล chart. คู่มือขั้นตอนโดยละเอียดพร้อมการตั้งค่า
  Maven และตัวอย่างจากโลกจริง.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: สร้าง Pie Chart Aspose – เพิ่ม Chart ไปยัง Presentation ด้วย Maven
url: /th/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเพิ่มแผนภูมิวงกลมลงในงานนำเสนอโดยใช้ Aspose.Slides Java

## บทนำ
ในคู่มือนี้คุณจะ **create pie chart aspose** ด้วย Aspose.Slides Maven และดูวิธีฝังลงในสไลด์ PowerPoint การสร้างงานนำเสนอที่ดูสวยงามเป็นสิ่งสำคัญสำหรับการสื่อสารข้อมูลอย่างมีประสิทธิภาพ โดยเฉพาะเมื่อการแสดงผลข้อมูลมีบทบาทสำคัญ หากคุณกำลังมองหาวิธีอัตโนมัติกระบวนการนี้ด้วย **aspose slides maven** คุณมาถูกที่แล้ว เราจะพาคุณผ่านขั้นตอนการเพิ่มแผนภูมิลงในสไลด์ — โดยเฉพาะแผนภูมิวงกลม — และปรับแต่งให้เหมาะกับสถานการณ์จริง

### สิ่งที่คุณจะได้เรียนรู้
- วิธีการเริ่มต้นอ็อบเจกต์ presentation ใน Java.  
- ขั้นตอนการ **add a pie chart java** บนสไลด์แรกของงานนำเสนอ.  
- การเข้าถึง workbook ข้อมูลแผนภูมิและการแสดงรายการ worksheets ภายใน  

มาดำดิ่งเข้าไปดูวิธีที่คุณสามารถใช้ Aspose.Slides Java เพื่อเพิ่มประสิทธิภาพงานนำเสนอของคุณด้วยแผนภูมิแบบไดนามิก!

## คำตอบสั้น
- **ไลบรารีใดที่เพิ่มแผนภูมิผ่าน Maven?** aspose slides maven  
- **ประเภทแผนภูมิที่แสดงคืออะไร?** Pie chart (add chart to slide)  
- **เวอร์ชัน Java ขั้นต่ำที่ต้องการคืออะไร?** JDK 16 or later  
- **ต้องการใบอนุญาตสำหรับการทดสอบหรือไม่?** A free trial works; production needs a license  
- **จะหา Maven dependency ได้จากที่ไหน?** In the setup section below  

## Aspose Slides Maven คืออะไร?
Aspose.Slides for Java เป็น API ที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง, แก้ไข, และเรนเดอร์ไฟล์ PowerPoint ด้วยโปรแกรมได้ แพคเกจ Maven (`aspose-slides`) ทำให้การจัดการ dependencies ง่ายขึ้น ช่วยให้คุณมุ่งเน้นการสร้างและปรับแต่งสไลด์—เช่นการเพิ่มแผนภูมิวงกลม—โดยไม่ต้องจัดการกับการจัดการไฟล์ระดับต่ำ

## ทำไมต้องใช้ Aspose.Slides Maven เพื่อเพิ่มแผนภูมิลงในสไลด์?
การใช้ Aspose.Slides Maven ช่วยให้คุณสร้างแผนภูมิโดยตรงจากโค้ด Java โดยไม่ต้องแก้ไข PowerPoint ด้วยตนเอง มันให้การควบคุมโปรแกรมเต็มรูปแบบต่อประเภทแผนภูมิ, แหล่งข้อมูล, และการจัดรูปแบบ, เพื่อให้แบรนด์และความแม่นยำสอดคล้องกัน แพคเกจ Maven ยังจัดการ dependencies ที่จำเป็นทั้งหมด ทำให้การสร้างโปรเจกต์ง่ายขึ้นและสามารถรวมเข้ากับ pipeline CI/CD ได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** เวอร์ชัน 25.4 หรือใหม่กว่า (Maven/Gradle).  
- ติดตั้ง JDK 16+.  
- IDE (IntelliJ IDEA, Eclipse, ฯลฯ).  
- ความรู้พื้นฐาน Java และความคุ้นเคยกับ Maven หรือ Gradle.

## การตั้งค่า Aspose.Slides สำหรับ Java
ขั้นแรก ให้เพิ่ม Aspose.Slides ในโปรเจกต์ของคุณผ่าน Maven หรือ Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หรือคุณสามารถ [download the latest release](https://releases.aspose.com/slides/java/) โดยตรงจากเว็บไซต์ของ Aspose

### การรับใบอนุญาต
Aspose.Slides for Java มีการทดลองใช้งานฟรีพร้อมใบอนุญาตชั่วคราวสำหรับการทดสอบ สำหรับการใช้งานในผลิตภัณฑ์โดยไม่มีข้อจำกัด ให้ซื้อใบอนุญาตผ่าน [purchase page](https://purchase.aspose.com/buy).

## คู่มือการใช้งาน
ด้านล่างเราจะแบ่งโซลูชันออกเป็นสองฟีเจอร์: การเพิ่มแผนภูมิวงกลมและการเข้าถึง workbook ข้อมูลของแผนภูมิ

### ฟีเจอร์ 1: การสร้างงานนำเสนอและเพิ่มแผนภูมิ
#### ภาพรวม
ส่วนนี้แสดงวิธีสร้างงานนำเสนอใหม่และ **add a pie chart** ลงในสไลด์แรก

#### วิธีสร้าง pie chart aspose?
โหลดคลาส `Presentation` เพิ่มแผนภูมิประเภท `ChartType.Pie` แล้วบันทึกไฟล์ การดำเนินการทั้งหมดต้องใช้เพียงสามการเรียก API และทำงานภายในเวลาน้อยกว่าวินาทีสำหรับเด็คสไลด์ประมาณ 10 สไลด์ ทำให้เหมาะสำหรับการสร้างรายงานอัตโนมัติ

#### ขั้นตอนทีละขั้นตอน

**Step 1: Initialize a New Presentation Object**  
คลาส `Presentation` เป็นอ็อบเจกต์ระดับบนสุดของ Aspose.Slides ที่แสดงไฟล์ PowerPoint ในหน่วยความจำ  
```java
Presentation pres = new Presentation();
```
*สร้างอินสแตนซ์ `Presentation` ที่จะเก็บสไลด์ทั้งหมด.*

**Step 2: Add a Pie Chart**  
`ChartType.Pie` บอก Aspose ให้เรนเดอร์แผนภูมิวงกลม.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*วางแผนภูมิวงกลมที่พิกัด (50, 50) ด้วยความกว้าง 400 และความสูง 500.*

**Step 3: Dispose of Resources**  
การเรียก `dispose()` จะปล่อยทรัพยากร native และป้องกันการรั่วไหลของหน่วยความจำ.  
```java
if (pres != null) pres.dispose();
```
*ปล่อยทรัพยากร native; ควรเรียก `dispose()` เสมอเมื่อทำงานเสร็จ.*

### ฟีเจอร์ 2: การเข้าถึง Chart Data Workbook และ Worksheets
#### ภาพรวม
เรียนรู้วิธีเข้าถึง workbook พื้นฐานที่เก็บข้อมูลแผนภูมิและวนลูปผ่าน worksheets ของมัน

#### วิธีเข้าถึง chart data workbook?
ดึง `IChartDataWorkbook` จากแผนภูมิ แล้ววนลูปผ่านคอลเลกชัน `Worksheets` ของมัน Workbook นี้จำลองไฟล์ Excel ทำให้คุณสามารถอ่าน, แก้ไข, หรือเพิ่ม series ของข้อมูลโดยโปรแกรม ซึ่งแผนภูมิจะอัปเดตทันทีเมื่อรีเฟรชในระหว่างการทำงานโดยไม่ต้องรีสตาร์ท

#### ขั้นตอนทีละขั้นตอน

**Step 1: (Reuse) Initialize a New Presentation Object**  
*เช่นเดียวกับฟีเจอร์ 1, ขั้นตอน 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*เช่นเดียวกับฟีเจอร์ 1, ขั้นตอน 2.*

**Step 3: Get the Chart Data Workbook**  
`IChartDataWorkbook` คืออินเทอร์เฟซที่ให้การเข้าถึงแบบอ่าน/เขียนต่อ workbook ภายในของแผนภูมิที่คล้าย Excel.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*ดึง `IChartDataWorkbook` ที่เชื่อมโยงกับแผนภูมิ.*

**Step 4: Iterate Through Worksheets**  
อ็อบเจกต์ `Worksheet` แทนชีตแต่ละชีตภายใน workbook.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*พิมพ์ชื่อของแต่ละ worksheet เพื่อให้คุณตรวจสอบโครงสร้างข้อมูล.*

**Step 5: Dispose of Resources**  
*เช่นเดียวกับฟีเจอร์ 1, ขั้นตอน 3.*

## การประยุกต์ใช้งานจริง
- **Data Reporting:** สร้างสไลด์เด็คอัตโนมัติด้วยเมตริกที่อัปเดตล่าสุดสำหรับ Business Intelligence.  
- **Academic Presentations:** แสดงผลการวิจัยโดยไม่ต้องสร้างแผนภูมิด้วยตนเอง.  
- **Marketing Material:** แสดงประสิทธิภาพของผลิตภัณฑ์หรือผลสำรวจทันที.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- Aspose.Slides สามารถจัดการ **50+ รูปแบบการนำเข้าและส่งออก** และประมวลผลงานนำเสนอหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- ควรจำกัดจำนวนสไลด์และแผนภูมิให้อยู่ในระดับที่สมเหตุสมผล; แต่ละแผนภูมิใช้หน่วยความจำ native.  
- ควรเรียก `dispose()` เสมอเพื่อปล่อยทรัพยากรโดยเร็ว.  
- ปรับการจัดการข้อมูล workbook ให้เหมาะสม—หลีกเลี่ยงการโหลดชุดข้อมูลขนาดใหญ่เข้าสู่แผนภูมิเดียว.

## สรุป
เราได้อธิบายวิธีที่ **aspose slides maven** ช่วยให้คุณ **add chart to slide** ด้วยโปรแกรมและวิธีทำงานกับ workbook ข้อมูลของแผนภูมิ ด้วยบล็อกการสร้างเหล่านี้คุณสามารถอัตโนมัติ workflow การรายงานใด ๆ ที่ต้องการผลลัพธ์ PowerPoint ที่ดูเป็นมืออาชีพ

### ขั้นตอนต่อไป
- สำรวจตัวเลือกการจัดรูปแบบแผนภูมิ (สี, คำอธิบาย, ป้ายข้อมูล).  
- เชื่อมต่อกับแหล่งข้อมูลภายนอก (CSV, ฐานข้อมูล) เพื่อเติมข้อมูลแผนภูมิแบบไดนามิก.  
- รวมหลายประเภทแผนภูมิในงานนำเสนอเดียวเพื่อการเล่าเรื่องที่หลากหลายยิ่งขึ้น

## คำถามที่พบบ่อย

**Q: ฉันจะติดตั้ง Aspose.Slides for Java อย่างไร?**  
A: ใช้ dependency ของ Maven หรือ Gradle ที่แสดงด้านบน หรือดาวน์โหลดไลบรารีจากหน้าริลีส.

**Q: ข้อกำหนดระบบสำหรับ Aspose.Slides คืออะไร?**  
A: JDK 16 หรือใหม่กว่า; ไลบรารีทำงานบนแพลตฟอร์มใดก็ได้ที่รองรับ Java.

**Q: ฉันสามารถเพิ่มประเภทแผนภูมิอื่น ๆ นอกจากแผนภูมิวงกลมได้หรือไม่?**  
A: ได้, Aspose.Slides รองรับแผนภูมิแท่ง, เส้น, กระจาย, เรดาร์, และมากกว่า 20 ประเภทแผนภูมิ.

**Q: ฉันควรจัดการกับงานนำเสนอขนาดใหญ่อย่างมีประสิทธิภาพอย่างไร?**  
A: ปล่อยอ็อบเจกต์โดยเร็ว, จำกัดภาพความละเอียดสูง, และใช้เทมเพลตแผนภูมิซ้ำเพื่อรักษาการใช้หน่วยความจำให้ต่ำ.

**Q: ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติของ Aspose.Slides ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose documentation](https://reference.aspose.com/slides/java/) เพื่อดูเอกสารอ้างอิง API อย่างครบถ้วน.

**Q: จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่?**  
A: จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการผลิต; มีการทดลองใช้งานฟรีสำหรับการประเมินผล.

**Q: แพคเกจ Maven มีความสามารถของแผนภูมิทั้งหมดหรือไม่?**  
A: มี, artifact `aspose-slides` ของ Maven มีเครื่องมือสร้างแผนภูมิครบชุด.

## แหล่งข้อมูล
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)  
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)  
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)  
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)  
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**อัปเดตล่าสุด:** 2026-05-29  
**ทดสอบด้วย:** Aspose.Slides 25.4 for Java (jdk16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีปรับแต่งสีแผนภูมิวงกลมใน Java ด้วย Aspose.Slides – คู่มือครบถ้วน](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [สร้างแผนภูมิ Pie of Pie ใน Java ด้วย Aspose.Slides: คู่มือเชิงลึก](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [ทำแอนิเมชันแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนต่อขั้นตอน](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}