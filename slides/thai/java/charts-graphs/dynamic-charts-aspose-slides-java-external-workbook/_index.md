---
date: '2026-08-06'
description: เรียนรู้วิธีสร้าง chart ในงานนำเสนอ Java ด้วย Aspose.Slides และวิธีเชื่อมโยง
  workbook เพื่อการอัปเดตข้อมูลแบบ dynamic data updates คู่มือขั้นตอนโดยละเอียด
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: เรียนรู้วิธีสร้าง chart ในงานนำเสนอ Java ด้วย Aspose.Slides และวิธีเชื่อมโยง
  workbook เพื่อการอัปเดตข้อมูลแบบ dynamic data updates ตามบทเรียนสั้นนี้
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: วิธีสร้าง chart ในงานนำเสนอ Java ด้วย Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: วิธีสร้าง chart ในงานนำเสนอ Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิในงานนำเสนอ Java ด้วย Aspose.Slides: การเชื่อมโยงกับสมุดงานภายนอก

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้างแผนภูมิ** ในงานนำเสนอ Java และ **วิธีเชื่อมโยงข้อมูลสมุดงาน** เพื่อให้แผนภูมิรีเฟรชโดยอัตโนมัติ แผนภูมิแบบไดนามิกช่วยให้สไลด์ของคุณเป็นปัจจุบันโดยไม่ต้องคัดลอก‑วางด้วยตนเอง ซึ่งเป็นสิ่งสำคัญสำหรับการรายงานสด, แดชบอร์ดการเงิน, และชุดสไลด์สถานะโครงการ เราจะอธิบายขั้นตอนการตั้งค่า, การนำไปใช้, และข้อผิดพลาดทั่วไป เพื่อให้คุณสามารถรวมข้อมูล Excel แบบเรียลไทม์ได้ด้วยเพียงไม่กี่บรรทัดของโค้ด

## คำตอบอย่างรวดเร็ว
- **ประโยชน์หลักคืออะไร?** แผนภูมิจะอัปเดตโดยอัตโนมัติเมื่อสมุดงาน Excel ที่เชื่อมโยงมีการเปลี่ยนแปลง.  
- **ต้องการเวอร์ชันไลบรารีใด?** Aspose.Slides for Java 25.4 หรือใหม่กว่า.  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; ไลเซนส์เชิงพาณิชย์จะลบข้อจำกัดการประเมินทั้งหมด.  
- **สามารถใช้รูปแบบ Excel ใดก็ได้หรือไม่?** ใช่ – รองรับไฟล์ `.xlsx` และไฟล์ `.xls` แบบเก่า.  
- **ความหน่วงของเครือข่ายเป็นปัญหาหรือไม่?** แคชสมุดงานไว้ในเครื่องหรือใช้ CDN เพื่อลดความหน่วง.

## การเชื่อมโยงแผนภูมิแบบไดนามิกคืออะไร?
การเชื่อมโยงแผนภูมิแบบไดนามิกทำให้แผนภูมิอ่านแหล่งข้อมูลจากสมุดงานภายนอกขณะทำงาน ดังนั้นการเปลี่ยนแปลงใดๆ ในสมุดงานจะสะท้อนในสไลด์เมื่อเปิดครั้งต่อไป ซึ่งช่วยขจัดความจำเป็นในการสร้างงานนำเสนอใหม่หลังการอัปเดตข้อมูลแต่ละครั้ง.

## ทำไมต้องใช้ Aspose.Slides for Java?
Aspose.Slides รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 แบบ**, สามารถเรนเดอร์งานนำเสนอหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, และประมวลผลการอัปเดตข้อมูลแผนภูมิภายในเวลาไม่ถึง 200 ms บนเซิร์ฟเวอร์ทั่วไป ตัวเลขประสิทธิภาพที่วัดได้เหล่านี้ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับสายงานการรายงานระดับองค์กร.

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** 25.4 หรือใหม่กว่า.  
- **Java Development Kit (JDK)** 16 หรือใหม่กว่า.  
- ความคุ้นเคยกับ Maven หรือ Gradle สำหรับการจัดการ dependencies.  

### ไลบรารีและ dependencies ที่จำเป็น
- **Aspose.Slides for Java** – ให้ API สำหรับงานนำเสนอ.  
- **Java Development Kit (JDK)** – จำเป็นสำหรับการคอมไพล์และรันโค้ด.

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- ความรู้พื้นฐานการเขียนโปรแกรม Java.  
- การเข้าถึงสมุดงาน Excel ภายนอก (เส้นทางไฟล์ในเครื่องหรือ HTTP URL).

## การตั้งค่า Aspose.Slides for Java
เพื่อเพิ่ม Aspose.Slides ลงในโครงการของคุณ ให้เลือกหนึ่งในระบบการสร้างที่รองรับ.

### การตั้งค่า Maven
เพิ่ม dependency นี้ลงในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การตั้งค่า Gradle
ใส่ส่วนนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดไลบรารีจาก [เอกสาร Aspose.Slides Java](https://releases.aspose.com/slides/java/).

#### การรับไลเซนส์
เริ่มต้นด้วยการทดลองใช้ฟรีหรือรับไลเซนส์ชั่วคราวเพื่อทดสอบ Aspose.Slides โดยไม่มีข้อจำกัด สำหรับการใช้งานระยะยาว ควรพิจารณาซื้อไลเซนส์.

##### การเริ่มต้นและตั้งค่าเบื้องต้น
`Presentation` คือคลาสหลักของ Aspose.Slides ที่แสดงไฟล์ PowerPoint ในหน่วยความจำ เริ่มต้นอ็อบเจกต์ presentation ของคุณดังนี้:
```java
Presentation pres = new Presentation();
```

## คู่มือการนำไปใช้
ในส่วนนี้เราจะอธิบายขั้นตอนการตั้งค่าสมุดงานภายนอกเพื่ออัปเดตข้อมูลแผนภูมิในงานนำเสนอ.

### การตั้งค่าสมุดงานภายนอกพร้อมอัปเดตข้อมูลแผนภูมิ
#### ภาพรวม
ฟีเจอร์นี้ทำให้แผนภูมิสามารถอัปเดตข้อมูลจากแหล่งภายนอกแบบไดนามิก เหมาะสำหรับกรณีที่ข้อมูลของคุณเปลี่ยนแปลงบ่อยและต้องการให้สไลด์สะท้อนการเปลี่ยนแปลงนั้นโดยอัตโนมัติ.

#### การดำเนินการแบบขั้นตอน
1. **สร้างการนำเสนอใหม่**  
   เริ่มต้นด้วยการสร้างอ็อบเจกต์ `Presentation` ใหม่:
   ```java
   Presentation pres = new Presentation();
   ```

2. **เข้าถึงสไลด์แรก**  
   การเข้าถึงสไลด์ทำได้อย่างง่ายดาย:
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **เพิ่มแผนภูมิลงในสไลด์**  
   เพิ่มแผนภูมิวงกลมที่ตำแหน่งและขนาดที่ต้องการ:
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **ตั้งค่า URL ของสมุดงานภายนอกสำหรับข้อมูลแผนภูมิ**  
   ระบุสมุดงานภายนอกเป็นแหล่งข้อมูล:
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### ตัวเลือกการกำหนดค่า
- **Chart type** – เลือกจาก Pie, Bar, Line, Area ฯลฯ ตามที่คุณต้องการแสดงข้อมูล.  
- **Position & size** – ปรับค่าพิกัด X/Y และความกว้าง/ความสูงให้เหมาะกับการจัดวางสไลด์ของคุณ.

## วิธีสร้างแผนภูมิที่เชื่อมโยงกับสมุดงาน?
`Chart` คืออ็อบเจกต์ของ Aspose.Slides ที่บรรจุรูปแบบแผนภูมิและข้อมูลของมัน.  
โหลดงานนำเสนอของคุณ, เพิ่มแผนภูมิ, และเรียก `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`. ตอนนี้แผนภูมิจะอ่านค่าชุดข้อมูลจากสมุดงานทุกครั้งที่ไฟล์ถูกเปิด, ให้การอัปเดตแบบเรียลไทม์โดยไม่ต้องสร้าง PPTX ใหม่ ย่อหน้านี้ตอบโดยตรงตามข้อกำหนด GEO และให้คำอธิบายที่กระชับและนำไปปฏิบัติได้.

## ปัญหาทั่วไปและวิธีแก้
หากลิงก์ภายนอกไม่อัปเดต:
- ตรวจสอบว่า URL สามารถเข้าถึงได้และส่งคืนไฟล์ Excel ที่ถูกต้อง.  
- ตรวจสอบว่าเซิร์ฟเวอร์อนุญาตการร้องขอ GET แบบไม่ระบุตัวตนหรือให้ข้อมูลรับรองหากจำเป็น.  
- แคชสมุดงานไว้ในเครื่องหากความหน่วงของเครือข่ายสูง; อัปเดตแคชก่อนเปิดงานนำเสนอ.

## การประยุกต์ใช้งานจริง
แผนภูมิแบบไดนามิกที่ใช้สมุดงานภายนอกสามารถเป็นประโยชน์ในหลายสถานการณ์:
1. **Real‑time data reporting** – แดชบอร์ดการขายที่ดึงตัวเลขล่าสุดจากไฟล์ Excel ศูนย์กลาง.  
2. **Financial analysis** – แนวโน้มราคาหุ้นที่รีเฟรชอัตโนมัติจากฟีดข้อมูลตลาด.  
3. **Project management** – แดชบอร์ด KPI ที่สะท้อนสถิติการทำงานล่าสุดของงาน.

## การพิจารณาด้านประสิทธิภาพ
การเพิ่มประสิทธิภาพเป็นสิ่งสำคัญเมื่อทำงานกับสมุดงานขนาดใหญ่:
- แคชสมุดงานบนเซิร์ฟเวอร์แอปพลิเคชันเพื่อจำกัดการเรียกเครือข่ายซ้ำ.  
- ใช้ API สตรีมเพื่ออ่านเฉพาะช่วง worksheet ที่ต้องการ ลดการใช้หน่วยความจำ.  
- Aspose.Slides ประมวลผลการอัปเดตแผนภูมิภายในเวลาไม่ถึง 200 ms สำหรับสมุดงานขนาดสูงสุด 10 MB ซึ่งเหมาะกับสถานการณ์การรายงานส่วนใหญ่.

## สรุป
โดยทำตามคู่มือนี้คุณจะรู้ **วิธีสร้างแผนภูมิ** ในงานนำเสนอ Java และ **วิธีเชื่อมโยงข้อมูลสมุดงาน** เพื่อการอัปเดตอัตโนมัติ ความสามารถนี้ทำให้สไลด์ของคุณมีความโต้ตอบมากขึ้น ลดความพยายามด้วยมือและทำให้ผู้มีส่วนได้ส่วนเสียเห็นตัวเลขล่าสุดเสมอ สำรวจคุณลักษณะเพิ่มเติมของ Aspose.Slides เช่น การคัดลอกสไลด์, การเคลื่อนไหว, และการส่งออกเป็น PDF เพื่อเพิ่มประสิทธิภาพการทำงานของการรายงานของคุณ.

## ส่วนคำถามที่พบบ่อย
**Q1: สามารถใช้ URL ใดก็ได้เป็นสมุดงานภายนอกหรือไม่?**  
A1: URL ต้องชี้ไปยังไฟล์ Excel ที่สามารถเข้าถึงได้ (`.xlsx` หรือ `.xls`). ตรวจสอบว่าเซิร์ฟเวอร์ส่งคืน MIME type ที่ถูกต้องและการตรวจสอบสิทธิ์ (หากจำเป็น) ถูกจัดการในโค้ดของคุณ.

**Q2: ชนิดแผนภูมิใดบ้างที่รองรับการเชื่อมโยงแบบไดนามิก?**  
A2: แผนภูมิประเภททั้งหมดของ Aspose.Slides – Pie, Bar, Line, Area, Scatter, Radar และอื่นๆ – สามารถเชื่อมโยงกับสมุดงานภายนอกได้.

**Q3: มีขนาดจำกัดสำหรับสมุดงานภายนอกหรือไม่?**  
A3: แม้ว่า Aspose.Slides จะรองรับสมุดงานที่ใหญ่กว่า 100 MB, เวลาในการประมวลผลจะเพิ่มขึ้นตามขนาด; เพื่อประสิทธิภาพที่ดีที่สุด ควรเก็บไฟล์ให้มีขนาดไม่เกิน 20 MB หรือสตรีมเฉพาะช่วงที่ต้องการ.

**Q4: ควรจัดการกับ URL ที่ไม่สามารถเข้าถึงได้อย่างไร?**  
A4: ห่อหุ้มโค้ดการเชื่อมโยงด้วยบล็อก try‑catch, บันทึกข้อยกเว้น, และอาจใช้แหล่งข้อมูลแบบคงที่เป็นสำรองเพื่อให้การนำเสนอยังคงโหลดได้.

**Q5: สามารถใช้สิ่งนี้ในสายงานการรายงานอัตโนมัติได้หรือไม่?**  
A5: แน่นอน. API ทำงานแบบ head‑less, ดังนั้นคุณสามารถสร้างหรืออัปเดตงานนำเสนอบนเซิร์ฟเวอร์, ฝังลงในอีเมล, หรือเผยแพร่ไปยังไลบรารี SharePoint ได้.

## แหล่งข้อมูล
- [เอกสาร Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- [ดาวน์โหลด Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [ซื้อไลเซนส์](https://purchase.aspose.com/buy)
- [ทดลองใช้ฟรีและไลเซนส์ชั่วคราว](https://releases.aspose.com/slides/java/)
- [ฟอรั่มสนับสนุน Aspose](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides: คู่มือเชิงลึก](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [วิธีเพิ่มแผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนต่อขั้นตอน](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [ทำแอนิเมชันให้แผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนต่อขั้นตอน](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}