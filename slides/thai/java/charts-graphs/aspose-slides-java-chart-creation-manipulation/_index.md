---
date: '2026-06-08'
description: เรียนรู้วิธี java สร้างแผนภูมิแบบพื้นที่ใน Java presentations, เชี่ยวชาญการแสดงผลข้อมูล,
  และบันทึกไฟล์ PPTX ด้วย Aspose.Slides for Java.
keywords:
- java create area chart
- Aspose.Slides Java
- Java chart generation
- data visualization Java
- PPTX export Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to java create area chart in Java presentations, master data
    visualization, and save PPTX files using Aspose.Slides for Java.
  headline: java create area chart in Presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to java create area chart in Java presentations, master data
    visualization, and save PPTX files using Aspose.Slides for Java.
  name: java create area chart in Presentations with Aspose.Slides
  steps:
  - name: Initialize Your Presentation
    text: '`Presentation` is the top‑level object that holds slides, layouts, and
      resources. First, create a new instance:'
  - name: Add an Area Chart
    text: '`IChart` is the object that encapsulates chart data, type, and formatting
      within a slide. Use the `addChart` method to insert an Area chart, specifying
      its position and dimensions: - **Parameters Explained**: - `ChartType.Area`:
      selects the Area chart type. - `(100, 100)`: X and Y coordinates for po'
  - name: Access Axes Properties
    text: '`getAxes()` returns the chart''s axis collection, allowing access to vertical
      and horizontal axes. `getVerticalAxis()` provides the vertical axis object of
      the chart. Retrieve values from the vertical axis, including the **maximum value**
      you might need for scaling or annotations: - `getActualMaxValu'
  - name: Save Your Presentation
    text: '`save(String path, SaveFormat format)` writes the presentation to the specified
      file in the given format. Finally, **how to save pptx** files with a single
      call: - `"YOUR_OUTPUT_DIRECTORY/ErrorBars_out.pptx"`: Destination path and filename.
      - `SaveFormat.Pptx`: Ensures the file is saved in the moder'
  type: HowTo
- questions:
  - answer: Absolutely. Aspose.Slides supports **50+ chart types**, including Column,
      Bar, Line, Pie, Radar, and Waterfall.
    question: Can I create other chart types besides Area charts?
  - answer: Yes. Retrieve data via JDBC or JPA, then populate the chart series programmatically
      using the `ChartData` API.
    question: Is it possible to bind chart data directly from a database?
  - answer: Aspose.Slides for Java works with **JDK 8** and newer; the examples target
      **JDK 16** for optimal performance.
    question: What Java versions are supported?
  - answer: Save using `SaveFormat.Ppt` for legacy compatibility, or stick with `SaveFormat.Pptx`
      for modern Office suites.
    question: How can I ensure the generated PPTX works on older PowerPoint versions?
  - answer: Yes. You can set the chart’s locale or manually provide translated strings
      for titles, axis labels, and data point legends.
    question: Does Aspose.Slides handle localization of chart labels?
  type: FAQPage
title: java สร้างแผนภูมิแบบพื้นที่ใน Presentations ด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างแผนภูมิพื้นที่ใน Java สำหรับการนำเสนอด้วย Aspose.Slides

## บทนำ

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **สร้างแผนภูมิพื้นที่ด้วย Java** ในการนำเสนอ Java โดยใช้ Aspose.Slides for Java ซึ่งเป็นไลบรารีที่เปลี่ยนตัวเลขดิบให้กลายเป็นเรื่องราวภาพที่สวยงาม เราจะเดินผ่านการติดตั้ง SDK, การสร้างแผนภูมิพื้นที่, การอ่านค่าตำแหน่งแกน, และสุดท้าย **วิธีการบันทึก pptx** ด้วยการเรียกเมธอดเดียว ไม่ว่าคุณจะสร้างเครื่องมือรายงานอัตโนมัติหรือเพิ่มคุณค่าให้กับสไลด์เด็คแบบเรียลไทม์ ขั้นตอนเหล่านี้จะพาคุณจากศูนย์สู่แผนภูมิที่เต็มรูปแบบในไม่กี่นาที

## คำตอบสั้น
- **คลาสหลักสำหรับสร้างการนำเสนอคืออะไร?** `Presentation` from Aspose.Slides.  
- **ตัวอย่างใช้ประเภทแผนภูมิใด?** An Area chart (`ChartType.Area`).  
- **คุณจะดึงค่ามากสุดบนแกนแนวตั้งได้อย่างไร?** `chart.getAxes().getVerticalAxis().getActualMaxValue()`.  
- **คุณควรใช้รูปแบบใดในการส่งออกไฟล์?** `SaveFormat.Pptx`.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** A free temporary license is available for evaluation.

## “วิธีการสร้างแผนภูมิ” ใน Java คืออะไร?
**คำตอบโดยตรง:** ใน Aspose.Slides, “วิธีการสร้างแผนภูมิ” หมายถึงการเรียก API ที่แทรกวัตถุแผนภูมิที่กำหนดค่าเต็มรูปแบบลงบนสไลด์, ให้คุณระบุประเภท, ข้อมูล, และการจัดรูปแบบในไม่กี่บรรทัดของโค้ด Java การเรียกเดียวนี้ทำให้ซ่อนการดำเนินการวาดระดับต่ำทั้งหมด, เพื่อให้คุณมุ่งเน้นที่ข้อมูลที่ต้องการแสดงผล

## ทำไมต้องใช้ Aspose.Slides สำหรับแผนภูมิ Java?
**คำตอบโดยตรง:** เลือกใช้ Aspose.Slides เพราะมันมอบ **50+ ชนิดแผนภูมิ**, รองรับ **ตัวเลือกการผูกข้อมูลมากกว่า 30 รายการ**, และสามารถสร้าง **ไฟล์ PPTX หลายร้อยหน้า** โดยไม่ต้องติดตั้ง Microsoft PowerPoint, พร้อมทั้งให้การควบคุมโปรแกรมระดับละเอียด นอกจากนี้ยังมีตัวเลือกการจัดรูปแบบที่หลากหลาย, ให้คุณปรับสี, ฟอนต์, และเครื่องหมาย, รวมถึง API สำหรับส่งออกเป็น PDF, SVG, และรูปภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะลงลึกในรายละเอียดของการสร้างแผนภูมิด้วย Aspose.Slides Java, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้ครบถ้วน:

### ไลบรารี, เวอร์ชัน, และการพึ่งพาที่จำเป็น
- **Aspose.Slides for Java**: Version **25.4** หรือใหม่กว่า (ไลบรารีนี้รองรับ **50+ ชนิดแผนภูมิ** และ **30+ รูปแบบการส่งออก**)  
- Java Development Kit (JDK) **16** หรือสูงกว่า

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- IDE ที่เข้ากันได้ เช่น **IntelliJ IDEA** หรือ **Eclipse**.  
- เครื่องมือสร้าง **Maven** หรือ **Gradle** ที่กำหนดค่าเพื่อการจัดการการพึ่งพา

### ความรู้เบื้องต้นที่จำเป็น
- แนวคิดการเขียนโปรแกรม Java พื้นฐาน.  
- การเพิ่มไลบรารีภายนอกลงในโครงการ Maven/Gradle

## การตั้งค่า Aspose.Slides สำหรับ Java

การรวม Aspose.Slides เข้าในโครงการ Java ของคุณทำได้ง่าย เลือกตัวจัดการแพ็กเกจที่เหมาะกับกระบวนการทำงานของคุณ

### การใช้ Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การใช้ Gradle
ใส่ส่วนนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
สำหรับผู้ที่ต้องการดาวน์โหลดโดยตรง, เยี่ยมชมหน้า [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)  

#### ขั้นตอนการรับไลเซนส์
- **Free Trial**: ทดสอบ Aspose.Slides ด้วยไลเซนส์ชั่วคราวเพื่อประเมินคุณสมบัติ  
- **Temporary License**: ขอไลเซนส์ชั่วคราวฟรีสำหรับการประเมินผลต่อเนื่อง  
- **Purchase**: ซื้อการสมัครสมาชิกสำหรับการใช้งานในผลิตภัณฑ์และเปิดใช้งานความสามารถขั้นสูงทั้งหมด  

#### การเริ่มต้นและตั้งค่าเบื้องต้น
`Presentation` เป็นคลาสหลักของ Aspose.Slides ที่แทนไฟล์ PowerPoint ทั้งหมดในหน่วยความจำ เริ่มต้นด้วยการสร้างอ็อบเจกต์ `Presentation`, ซึ่งทำหน้าที่เป็นคอนเทนเนอร์สำหรับการกระทำทั้งหมดที่เกี่ยวกับสไลด์:

```java
import com.aspose.slides.Presentation;

public class AsposeInit {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        // Your code to manipulate presentations goes here.
        pres.dispose();  // Always dispose of resources when done.
    }
}
```

## คู่มือการทำงาน

### วิธีการสร้างแผนภูมิพื้นที่ด้วย Java ทีละขั้นตอน
**คำตอบโดยตรง:** เพื่อสร้างแผนภูมิพื้นที่ด้วย Java, สร้างอ็อบเจกต์ `Presentation`, เพิ่มแผนภูมิพื้นที่ด้วย `addChart(ChartType.Area, …)`, ปรับแกนตามต้องการ, แล้วเรียก `save("output.pptx", SaveFormat.Pptx)` ทั้งหมดใช้เพียงสี่โค้ดสั้นและทำงานภายในไม่กี่วินาทีสำหรับชุดข้อมูลทั่วไป

#### ภาพรวม
ส่วนนี้จะแสดงวิธี **add chart**, โดยเฉพาะแผนภูมิพื้นที่, ลงในการนำเสนอของคุณและกำหนดคุณสมบัติพื้นฐาน

##### ขั้นตอนที่ 1: เริ่มต้นการนำเสนอของคุณ
`Presentation` เป็นอ็อบเจกต์ระดับบนสุดที่เก็บสไลด์, เลเอาต์, และทรัพยากรต่าง ๆ ก่อนอื่นให้สร้างอินสแตนซ์ใหม่:

```java
import com.aspose.slides.Presentation;

public class ChartCreation {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        
        try {
            // Proceed with chart creation in the next steps.
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

##### ขั้นตอนที่ 2: เพิ่มแผนภูมิพื้นที่
`IChart` เป็นอ็อบเจกต์ที่บรรจุข้อมูลแผนภูมิ, ประเภท, และการจัดรูปแบบภายในสไลด์ ใช้เมธอด `addChart` เพื่อแทรกแผนภูมิพื้นที่, ระบุตำแหน่งและขนาด:

```java
import com.aspose.slides.Chart;
import com.aspose.slides.ChartType;

// Inside the try block of your main method
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Area, 100, 100, 500, 350);
```

- **อธิบายพารามิเตอร์**:  
  - `ChartType.Area`: เลือกประเภทแผนภูมิ Area.  
  - `(100, 100)`: พิกัด X และ Y สำหรับตำแหน่งบนสไลด์.  
  - `(500, 350)`: ความกว้างและความสูงของแผนภูมิในหน่วย points.

##### ขั้นตอนที่ 3: เข้าถึงคุณสมบัติของแกน
`getAxes()` คืนค่าคอลเลกชันของแกนแผนภูมิ, ให้เข้าถึงแกนแนวตั้งและแนวนอน `getVerticalAxis()` ให้วัตถุแกนแนวตั้งของแผนภูมิ ดึงค่าจากแกนแนวตั้ง, รวมถึง **maximum value** ที่อาจต้องใช้สำหรับการสเกลหรือคำอธิบาย:

```java
double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
```

- `getActualMaxValue()` และ `getActualMinValue()` คืนค่ามากสุดและน้อยสุดปัจจุบันที่ตั้งบนแกน.

ดึงหน่วยหลักและหน่วยรองจากแกนแนวนอนเพื่อเข้าใจการเว้นระยะห่างของช่วง `getHorizontalAxis()` คืนค่าอ็อบเจกต์แกนแนวนอน, และเมธอดของมันเปิดเผยช่วงหน่วย:

```java
double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
```

- `getActualMajorUnit()` และ `getActualMinorUnit()` ให้ช่วงหน่วยสำหรับการสเกลแกน.

##### ขั้นตอนที่ 4: บันทึกการนำเสนอของคุณ
`save(String path, SaveFormat format)` เขียนการนำเสนอไปยังไฟล์ที่ระบุในรูปแบบที่กำหนด สุดท้าย, **วิธีการบันทึก pptx** ด้วยการเรียกเดียว:

```java
import com.aspose.slides.SaveFormat;

// At the end of your try block
pres.save("YOUR_OUTPUT_DIRECTORY/ErrorBars_out.pptx", SaveFormat.Pptx);
```

- `"YOUR_OUTPUT_DIRECTORY/ErrorBars_out.pptx"`: เส้นทางและชื่อไฟล์ปลายทาง.  
- `SaveFormat.Pptx`: ทำให้ไฟล์บันทึกในรูปแบบ PowerPoint สมัยใหม่ที่เข้ากันได้กับ Office 2016‑2021.

## เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบว่า Aspose.Slides ถูกเพิ่มเข้าไปในการพึ่งพาของโครงการอย่างถูกต้อง.  
- ตรวจสอบให้แน่ใจว่ามีคำสั่ง `import` ที่จำเป็นทั้งหมดอยู่ที่ส่วนบนของคลาส Java ของคุณ.  
- ตรวจสอบสิทธิ์ของระบบไฟล์สำหรับไดเรกทอรีผลลัพธ์; ใช้เส้นทางแบบเต็มหากจำเป็น.

## การประยุกต์ใช้งานจริง
Aspose.Slides มีการใช้งานที่หลากหลายเกินกว่าการสร้างแผนภูมิพื้นฐาน นี่คือตัวอย่างสถานการณ์จริงที่ **java data visualization** โดดเด่น:

1. **Business Reporting** – อัตโนมัติแดชบอร์ดไตรมาสด้วยแผนภูมิที่ดึงข้อมูลโดยตรงจากฐานข้อมูล SQL, ลดการคัดลอก‑วางด้วยมือ.  
2. **Educational Presentations** – สร้างสไลด์การบรรยายที่แสดงแนวคิดสถิติแบบเรียลไทม์, ทำให้เนื้อหาเป็นปัจจุบันด้วยข้อมูลการวิจัยล่าสุด.  
3. **Marketing Campaigns** – แสดงเมตริกการทำงานของแคมเปญในไฟล์ PPTX แบบไดนามิกที่สามารถส่งอีเมลไปยังผู้มีส่วนได้ส่วนเสียได้ทันที.

โดยการผสาน Aspose.Slides กับ JDBC หรือ REST API, คุณสามารถป้อนข้อมูลสดเข้าสู่แผนภูมิ, ทำให้การวิเคราะห์ภาพแบบเรียลไทม์ในงานนำเสนอของคุณเป็นไปได้

## ข้อควรพิจารณาด้านประสิทธิภาพ
เมื่อประมวลผลชุดข้อมูลขนาดใหญ่หรือฝังแผนภูมิหลายรายการ:

- **Minimize series**: รักษาจำนวนซีรีส์และจุดข้อมูลให้เหมาะสม (เช่น < 1,000 จุด) เพื่อลดเวลาเรนเดอร์.  
- **Dispose resources**: เรียก `pres.dispose()` หลังการบันทึกเพื่อปล่อยหน่วยความจำเนทีฟ.  
- **Streaming mode**: ใช้ `Presentation`'s `setSlideSize` และ `setMemoryOptimization` เพื่อจัดการเด็คหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่ RAM.

แนวทางเหล่านี้ช่วยให้การสร้างแผนภูมิใช้เวลาไม่ถึงวินาทีแม้ไฟล์จะเกิน **200 pages**.

## ปัญหาทั่วไปและวิธีแก้

| Issue | Reason | Solution |
|-------|--------|----------|
| แผนภูมิแสดงเป็นสีขาว | ไม่มีซีรีส์ข้อมูลที่เพิ่ม | เพิ่มซีรีส์โดยใช้ `chart.getChartData().getSeries().add(...)` (อยู่นอกขอบเขตของบทเรียนนี้). |
| ค่าของแกนไม่ถูกต้อง | การปรับสเกลแกนไม่ได้รีเฟรช | เรียก `chart.getAxes().getVerticalAxis().resetValueRange()` ก่อนอ่านค่า. |
| การบันทึกล้มเหลวด้วยข้อผิดพลาดสิทธิ์ | โฟลเดอร์ผลลัพธ์ไม่สามารถเขียนได้ | ตรวจสอบให้แอปพลิเคชันมีสิทธิ์เขียนหรือเลือกไดเรกทอรีอื่น. |

## ส่วนคำถามที่พบบ่อย

**1. Aspose.Slides Java ใช้ทำอะไร?**  
Aspose.Slides Java เป็นไลบรารีที่ทรงพลัง ช่วยให้นักพัฒนาสร้าง, แก้ไข, และแปลงการนำเสนอ PowerPoint อย่างโปรแกรมเมติกโดยไม่ต้องใช้ Microsoft Office.

**2. ฉันจะจัดการไลเซนส์กับ Aspose.Slides อย่างไร?**  
เริ่มต้นด้วยไลเซนส์ทดลองฟรีสำหรับการประเมิน; สำหรับการผลิต, ซื้อการสมัครสมาชิกที่ลบลายน้ำการประเมินและเปิดใช้งาน API ทั้งหมด.

**3. ฉันสามารถรวมแผนภูมิ Aspose.Slides เข้าในเว็บแอปพลิเคชันได้หรือไม่?**  
ได้. ใช้ Java ฝั่งเซิร์ฟเวอร์เพื่อสร้างไฟล์ PPTX ตามความต้องการและสตรีมไปยังเบราว์เซอร์หรือเก็บไว้ในคลาวด์สำหรับดาวน์โหลดภายหลัง.

**4. ฉันจะปรับแต่งสไตล์ของแผนภูมิด้วย Aspose.Slides อย่างไร?**  
คุณสามารถแก้ไขสี, ฟอนต์, สไตล์เส้น, และรูปแบบเครื่องหมายโดยตรงผ่านคุณสมบัติ `ChartData` และ `ChartFormat` ของอ็อบเจกต์ `IChart`.

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างประเภทแผนภูมิอื่น ๆ นอกจากแผนภูมิพื้นที่ได้หรือไม่?**  
A: แน่นอน. Aspose.Slides รองรับ **50+ ชนิดแผนภูมิ**, รวมถึง Column, Bar, Line, Pie, Radar, และ Waterfall.

**Q: สามารถผูกข้อมูลแผนภูมิกับฐานข้อมูลโดยตรงได้หรือไม่?**  
A: ได้. ดึงข้อมูลผ่าน JDBC หรือ JPA, แล้วเติมซีรีส์แผนภูมิโดยใช้ API `ChartData`.

**Q: รองรับเวอร์ชัน Java ใดบ้าง?**  
A: Aspose.Slides for Java ทำงานกับ **JDK 8** ขึ้นไป; ตัวอย่างนี้ใช้ **JDK 16** เพื่อประสิทธิภาพสูงสุด.

**Q: ฉันจะทำให้แน่ใจว่า PPTX ที่สร้างขึ้นทำงานบนเวอร์ชัน PowerPoint เก่าได้อย่างไร?**  
A: บันทึกโดยใช้ `SaveFormat.Ppt` สำหรับความเข้ากันได้กับรุ่นเก่า, หรือใช้ `SaveFormat.Pptx` สำหรับชุด Office สมัยใหม่.

**Q: Aspose.Slides จัดการการแปลภาษาของป้ายแผนภูมิหรือไม่?**  
A: ใช่. คุณสามารถตั้งค่า locale ของแผนภูมิหรือให้สตริงแปลด้วยตนเองสำหรับหัวเรื่อง, ป้ายแกน, และคำอธิบายจุดข้อมูล.

## สรุป

ในคู่มือนี้คุณได้เรียนรู้วิธี **สร้างแผนภูมิพื้นที่ด้วย Java** อ่านค่ามาตรฐานแกน, และ **วิธีการบันทึก pptx** ด้วย Aspose.Slides for Java โดยใช้ไลบรารีที่มีแผนภูมิหลากหลาย—มากกว่า **50 ชนิดแผนภูมิ** และ **30+ รูปแบบการส่งออก**—คุณสามารถอัตโนมัติการสร้างภาพข้อมูลที่ซับซ้อน, ผสานแหล่งข้อมูลสด, และมอบการนำเสนอที่สวยงามโดยไม่ต้องใช้ Microsoft PowerPoint. สำรวจสไตล์แผนภูมิเพิ่มเติม, ทดลองธีมแบบกำหนดเอง, และผสาน Aspose.Slides กับผลิตภัณฑ์ Aspose อื่น ๆ เพื่อโซลูชันการรายงานแบบครบวงจร

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides – การสร้างและตรวจสอบแผนภูมิขั้นสูง](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [บันทึกการนำเสนอพร้อมแผนภูมิด้วย Aspose.Slides for Java: คู่มือฉบับสมบูรณ์](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [สร้างแผนภูมิดินามิกในการนำเสนอ Java: เชื่อมโยงกับเวิร์กบุ๊กภายนอกด้วย Aspose.Slides](/slides/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}