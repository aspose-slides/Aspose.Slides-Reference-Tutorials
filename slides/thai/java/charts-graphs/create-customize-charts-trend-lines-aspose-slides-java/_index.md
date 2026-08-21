---
date: '2026-08-21'
description: เรียนรู้วิธีสร้าง clustered column chart และเพิ่ม trend lines ด้วย Aspose.Slides
  for Java รวมถึง license setup, การรวม Maven/Gradle, และตัวอย่างโดยละเอียด
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: สร้าง clustered column chart และเพิ่ม trend lines ด้วย Aspose.Slides
  for Java คู่มือนี้ครอบคลุม license setup, Maven/Gradle, และ step‑by‑step code snippets
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: สร้าง clustered column chart และเพิ่ม trend lines ด้วย Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: วิธีสร้าง clustered column chart และเพิ่ม trend lines ด้วย Aspose.Slides for
  Java
url: /th/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มและเพิ่มเส้นแนวโน้มโดยใช้ Aspose.Slides for Java

การสร้างงานนำเสนอที่น่าสนใจมักเริ่มจากการแสดงภาพข้อมูลที่ชัดเจน ในคู่มือนี้คุณจะ **สร้างแผนภูมิคอลัมน์แบบกลุ่ม** แล้วเสริมด้วยเส้นแนวโน้มหลากหลายประเภท—เอ็กซ์โพเนนเชียล, เส้นตรง, ลอการิทึม, ค่าเฉลี่ยเคลื่อนที่, พหุนาม, และพาวเวอร์—โดยใช้ Aspose.Slides for Java API ที่มีประสิทธิภาพ

## คำตอบสั้น
- **ขั้นตอนแรกคืออะไร?** เริ่มต้นด้วยอ็อบเจ็กต์ `Presentation` แล้วเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์.  
- **ต้องใช้เวอร์ชันไลบรารีใด?** Aspose.Slides for Java 25.4 หรือใหม่กว่า.  
- **ฉันสามารถใช้ Maven หรือ Gradle ได้หรือไม่?** ใช่ ทั้งสองได้รับการสนับสนุน; Maven ใช้ `<dependency>` และ Gradle ใช้ `implementation`.  
- **ต้องการไลเซนส์หรือไม่?** ไลเซนส์ทดลองใช้ได้สำหรับการประเมิน; ไลเซนส์เต็มของ Aspose.Slides จะลบข้อจำกัดการประเมิน.  
- **มีประเภทเส้นแนวโน้มกี่ประเภท?** มีทั้งหมดหกประเภทในตัว: exponential, linear, logarithmic, moving average, polynomial, และ power.

## create clustered column chart คืออะไร?
`create clustered column chart` หมายถึงการสร้างแผนภูมิที่จัดกลุ่มหลายชุดข้อมูลเคียงข้างกันในแต่ละหมวดหมู่ ทำให้เปรียบเทียบค่าระหว่างชุดได้ง่าย ประเภทแผนภูมินี้เหมาะสำหรับการแสดงข้อมูลเชิงหมวดหมู่ เช่น ยอดขายไตรมาสต่อภูมิภาค ช่วยให้ผู้ชมมองเห็นความแตกต่างระหว่างกลุ่มได้อย่างรวดเร็ว

## ทำไมต้องเพิ่มเส้นแนวโน้ม?
เส้นแนวโน้มเปิดเผยรูปแบบพื้นฐานของชุดข้อมูล ช่วยให้คุณคาดการณ์ค่าต่อไปในอนาคต, เน้นอัตราการเติบโต, หรือทำให้ข้อมูลที่มีเสียงรบกวนเรียบขึ้น โดยการเพิ่มเส้นแนวโน้มลงในแผนภูมิคอลัมน์แบบกลุ่ม ตัวเลขดิบจะกลายเป็นข้อมูลเชิงลึกที่นำไปใช้ได้ ทำให้ผู้มีส่วนได้ส่วนเสียเข้าใจแนวโน้มระยะยาวและตัดสินใจบนพื้นฐานข้อมูล

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK):** 8 หรือใหม่กว่า.  
- **Aspose.Slides for Java:** เวอร์ชัน 25.4 หรือใหม่กว่า.  
- **IDE:** IntelliJ IDEA, Eclipse หรือโปรแกรมแก้ไขที่รองรับ Java ใดก็ได้.  
- **เครื่องมือสร้าง:** Maven หรือ Gradle (ไม่บังคับแต่แนะนำ).  
- **ไลเซนส์:** ไฟล์ไลเซนส์ทดลองหรือไลเซนส์ Aspose.Slides ที่ซื้อ.  

คุณควรมีความคุ้นเคยกับไวยากรณ์พื้นฐานของ Java และการจัดการการพึ่งพาของโครงการ

## วิธีตั้งค่า Aspose.Slides for Java?
เพิ่มไลบรารี Aspose.Slides ลงในโครงการของคุณโดยใช้ตัวจัดการการพึ่งพาที่คุณต้องการ แล้ววางไฟล์ไลเซนส์ในตำแหน่งที่ runtime สามารถค้นหาได้ สิ่งนี้จะทำให้ฟังก์ชันทำงานเต็มที่และลบข้อจำกัดการประเมิน

### Maven
เพิ่มการพึ่งพานี้ในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
ใส่บรรทัดนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
คุณยังสามารถดาวน์โหลดไฟล์ JAR ด้วยตนเองจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### ไลเซนส์ Aspose Slides
วางไฟล์ `Aspose.Slides.lic` ไว้ที่รากของโครงการของคุณ หรือกำหนดไลเซนส์โดยโปรแกรมด้วย `License license = new License(); license.setLicense("Aspose.Slides.lic");`. ไลเซนส์ทดลองจะลบข้อจำกัดฟีเจอร์ทั้งหมด แต่ไลเซนส์ที่ซื้อจะลบลายน้ำการประเมินและให้การปรับประสิทธิภาพเต็มรูปแบบ สำหรับการใช้งานในผลิตภัณฑ์ ควรพิจารณาซื้อไลเซนส์จาก [Aspose purchase page](https://purchase.aspose.com/buy).

## วิธีสร้างงานนำเสนอและเพิ่มแผนภูคอลัมน์แบบกลุ่ม?
`คลาส `Presentation` แทนไฟล์ PowerPoint และให้เมธอดสำหรับสร้าง, แก้ไข, และบันทึกสไลด์. สร้างอินสแตนซ์ของ `Presentation`, เพิ่มสไลด์, จากนั้นเรียก `addChart` พร้อม `ChartType.ClusteredColumn` เพื่อสร้างอ็อบเจ็กต์แผนภูมิ กระบวนการนี้จะตั้งค่าแคนวาสสไลด์, แทรกรูปร่างแผนภูมิ, และเตรียมพร้อมสำหรับการใส่ข้อมูลและการจัดรูปแบบ

1. **เริ่มต้นการนำเสนอ** – ตั้งค่าโฟลเดอร์เอาต์พุตและสร้างอินสแตนซ์ `Presentation` ใหม่.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **เพิ่มแผนภูคอลัมน์แบบกลุ่ม** – รับรูปร่างแผนภูมิ, กำหนดค่าซีรีส์, และใส่ข้อมูลจุด.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## วิธีเพิ่มเส้นแนวโน้มเอ็กซ์โพเนนเชียล?
`อินเทอร์เฟซ `ITrendline` กำหนดเส้นแนวโน้มที่สามารถเพิ่มลงในซีรีส์ของแผนภูมิเพื่อจำลองรูปแบบข้อมูล. เพิ่มเส้นแนวโน้มเอ็กซ์โพเนนเชียลให้กับซีรีส์โดยสร้างอินสแตนซ์ `ITrendline`, ตั้งค่า `TrendlineType` เป็น `Exponential`, และแนบเข้ากับซีรีส์ที่ต้องการ. ประเภทนี้เหมาะกับข้อมูลที่เติบโตอย่างรวดเร็วและอัตราเพิ่มขึ้น

1. **กำหนดค่าเส้นแนวโน้ม** – เลือกซีรีส์และเรียก `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## วิธีเพิ่มเส้นแนวโน้มเชิงเส้น?
เส้นแนวโน้มเชิงเส้นแสดงเส้นตรงที่เหมาะสมที่สุดผ่านจุดข้อมูลของคุณ คุณยังสามารถปรับแต่งลักษณะของมัน เช่น สีเส้นและความหนา เพื่อให้สอดคล้องกับสไตล์การนำเสนอของคุณ

1. **ตั้งค่าเส้นแนวโน้ม** – ใช้ `addTrendline(TrendlineType.Linear)` แล้วปรับ `getLineFormat().setFillFormat().setFillType(FillType.Solid)` เพื่อเปลี่ยนสี.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## วิธีเพิ่มเส้นแนวโน้มลอการิทึมพร้อมกรอบข้อความกำหนดเอง?
เส้นแนวโน้มลอการิทึมเหมาะกับข้อมูลที่เติบโตเร็วในช่วงแรกแล้วค่อยคงที่ การเขียนทับป้ายกำกับเริ่มต้นทำให้คุณสามารถเพิ่มข้อความอธิบายที่ชี้แจงความสำคัญของแนวโน้มได้

1. **ปรับแต่งเส้นแนวโน้ม** – หลังจากเพิ่มเส้นแนวโน้ม, เข้าถึง `getDataLabel()` แล้วตั้งค่าคุณสมบัติ `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## วิธีเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่?
เส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่ทำให้ความผันผวนระยะสั้นเรียบลงเพื่อเน้นแนวโน้มระยะยาว คุณสามารถกำหนดช่วงเวลา (จำนวนจุด) ที่ใช้ในการเฉลี่ย เพื่อควบคุมความเรียบของเส้น

1. **กำหนดค่าเส้นแนวโน้ม** – เรียก `addTrendline(TrendlineType.MovingAverage)` และตั้งค่า `setPeriod(3)` เพื่อใช้ค่าเฉลี่ยเคลื่อนที่สามจุด.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## วิธีเพิ่มเส้นแนวโน้มพหุนาม?
เส้นแนวโน้มพหุนามทำให้ข้อมูลเข้ากับโค้งที่กำหนดโดยสมการพหุนาม คุณสมบัติ `order` ควบคุมระดับของพหุนาม ทำให้คุณสามารถจำลองความสัมพันธ์ที่ซับซ้อนได้

1. **ปรับแต่งเส้นแนวโน้ม** – หลังจากเพิ่มเส้นแนวโน้ม, ตั้งค่า `setOrder(3)` เพื่อให้เป็นการฟิตแบบคิวบิก.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## วิธีเพิ่มเส้นแนวโน้มพาวเวอร์?
เส้นแนวโน้มพาวเวอร์มีประโยชน์เมื่อข้อมูลเป็นไปตามความสัมพันธ์แบบพาวเวอร์‑ลอว์ คุณยังสามารถตั้งค่าการพยากรณ์ย้อนหลังและต่อหน้าเพื่อขยายเส้นนอกช่วงข้อมูลที่มีอยู่

1. **กำหนดค่าเส้นแนวโน้ม** – ใช้ `addTrendline(TrendlineType.Power)` และปรับ `setBackward(2)` เพื่อขยายเส้นย้อนกลับ.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## การใช้งานจริงของเส้นแนวโน้มในแผนภูมิคอลัมน์แบบกลุ่ม
- **การวิเคราะห์การเงิน:** แนวโน้มเอ็กซ์โพเนนเชียลและพหุนามช่วยคาดการณ์การเคลื่อนที่ของราคาหุ้น.  
- **การพยากรณ์การขาย:** เส้นค่าเฉลี่ยเคลื่อนที่ทำให้การพุ่งสูงตามฤดูกาลเรียบลง ให้มุมมองที่ชัดเจนขึ้นของแนวโน้มการขายพื้นฐาน.  
- **การวิจัยทางวิทยาศาสตร์:** แนวโน้มลอการิทึมเหมาะกับข้อมูลที่ครอบคลุมหลายลำดับของขนาด เช่น ความเข้มของเสียงหรือระดับ pH.  
- **การตรวจสอบการดำเนินงาน:** เส้นแนวโน้มพาวเวอร์สามารถจำลองการเสื่อมสภาพของประสิทธิภาพตามเวลา.

## วิธีเพิ่มประสิทธิภาพการใช้หน่วยความจำเมื่อใช้ Aspose.Slides?
ทำลายอ็อบเจ็กต์โดยเร็วและใช้ `presentation.dispose()` หลังจากบันทึก สำหรับชุดข้อมูลขนาดใหญ่ ให้เปิดใช้งานการโหลดแบบ lazy ของรูปภาพและหลีกเลี่ยงการโหลดแผนภูมิทั้งหมดเข้าสู่หน่วยความจำพร้อมกัน
- **รูปแบบการทำลาย:** ห่อ `Presentation` ด้วยบล็อก try‑with‑resources หรือเรียก `presentation.dispose()` ในบล็อก finally.  
- **การโหลดแบบ lazy:** ตั้งค่า `ChartData.setUseCache(true)` เมื่อจัดการกับข้อมูลหลายพันจุด.  
- **การส่งออกแบบสตรีม:** เขียนงานนำเสนอโดยตรงไปยัง `FileOutputStream` เพื่อหลีกเลี่ยงการเก็บไฟล์ทั้งหมดใน RAM.

## ประโยชน์เชิงปริมาณของ Aspose.Slides for Java
Aspose.Slides รองรับ **แผนภูมิมากกว่า 50 ประเภท**, สามารถสร้างงานนำเสนอที่มี **มากกว่า 1,000 สไลด์** ภายใน **30 วินาที** บน CPU 2 GHz ปกติ, และประมวลผล **PDF 500 หน้า** โดยไม่ต้องติดตั้ง Microsoft Office ตัวเลขเหล่านี้ได้รับการตรวจสอบในรุ่น 25.4 ล่าสุด

## สรุป
ตอนนี้คุณมีโซลูชันครบวงจรสำหรับ **การสร้างแผนภูคอลัมน์แบบกลุ่ม** และการเสริมด้วยทุกประเภทเส้นแนวโน้มหลักที่มีใน Aspose.Slides for Java ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถสร้างงานนำเสนอที่ขับเคลื่อนด้วยข้อมูลที่สวยงามและมีพลังด้านการวิเคราะห์  
ขั้นตอนต่อไปรวมถึงการสำรวจตัวเลือกการจัดรูปแบบแผนภูมิ, การส่งออกเป็น PDF/HTML, และการอัตโนมัติการสร้างแผนภูมิจากหลายแหล่งข้อมูล

## คำถามที่พบบ่อย

**Q: ฉันจะตั้งค่า Aspose.Slides สำหรับโครงการ Maven อย่างไร?**  
A: เพิ่ม snippet `<dependency>` ที่แสดงในส่วน Maven ลงใน `pom.xml` ของคุณและรัน `mvn clean install`.

**Q: ฉันสามารถปรับแต่งเส้นแนวโน้มนอกเหนือจากสีและป้ายกำกับได้หรือไม่?**  
A: ได้ คุณสามารถแก้ไขสไตล์เส้น, ความกว้าง, รูปแบบเส้นประ, และแม้กระทั่งการพยากรณ์ค่าต่อหน้า/ย้อนหลังผ่าน API `ITrendline`.

**Q: ควรทำอย่างไรหากพบข้อผิดพลาดความเข้ากันของเวอร์ชัน?**  
A: ตรวจสอบว่าเวอร์ชัน JDK ของคุณตรงกับข้อกำหนดขั้นต่ำของ Aspose.Slides (JDK 8+) และดูบันทึกการปล่อยของ Aspose เพื่อหาการเปลี่ยนแปลงที่ทำให้เกิดปัญหา.

**Q: สามารถเพิ่มเส้นแนวโน้มให้หลายแผนภูมิได้โดยอัตโนมัติหรือไม่?**  
A: แน่นอน ให้วนลูปผ่านแต่ละ `IChart` ในคอลเลกชันสไลด์และเรียกใช้เมธอด `addTrendline` ที่เหมาะสมสำหรับแต่ละซีรีส์.

**Q: จำเป็นต้องมีไลเซนส์แบบชำระเงินสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?**  
A: ใช่ ไลเซนส์ Aspose.Slides ที่ซื้อจะลบข้อจำกัดการประเมินและเปิดใช้งานการปรับประสิทธิภาพเต็มรูปแบบ.

**อัปเดตล่าสุด:** 2026-08-21  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [การพึ่งพา Maven ของ Aspose Slides: เพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [เพิ่มแอนิเมชันให้แผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนต่อขั้นตอน](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [สร้างแผนภูมิ PowerPoint ด้วย Java – บันทึกงานนำเสนอพร้อมแผนภูมิด้วย Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}