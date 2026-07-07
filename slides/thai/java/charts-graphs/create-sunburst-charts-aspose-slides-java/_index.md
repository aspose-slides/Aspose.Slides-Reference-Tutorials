---
date: '2026-07-03'
description: เรียนรู้วิธีสร้าง Sunburst Charts ขั้นตอนต่อขั้นตอนด้วย Java โดยใช้ Aspose.Slides
  พร้อมตัวเลือกการปรับแต่งเต็มรูปแบบสำหรับการนำเสนอ PowerPoint
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: วิธีสร้าง Sunburst Charts ด้วย Java โดยใช้ Aspose.Slides
url: /th/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิ Sunburst ใน Java ด้วย Aspose.Slides

## บทนำ
ในงานนำเสนอที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน การสร้างภาพ **how to create sunburst** อย่างรวดเร็วสามารถทำให้สไลด์ของคุณโดดเด่นได้ คู่มือฉบับนี้จะพาคุณผ่านการสร้างแผนภูมิ Sunburst ด้วย Aspose.Slides for Java ตั้งแต่การตั้งค่าโครงการจนถึงการส่งออกขั้นสุดท้าย เพื่อให้คุณสามารถสร้างกราฟิกข้อมูลเชิงลำดับชั้นที่น่าสนใจโดยไม่ต้องออกจากระบบนิเวศของ Java

## คำตอบสั้น
- **คลาสหลักสำหรับไฟล์ PowerPoint คืออะไร?** `Presentation` – it represents the entire PPTX in memory.  
- **ต้องใช้บรรทัดโค้ดกี่บรรทัดสำหรับ Sunburst พื้นฐาน?** Typically 5–7 lines once the library is referenced.  
- **รูปแบบการส่งออกที่รองรับคืออะไร?** PPTX, PDF, PNG, SVG, and HTML.  
- **ฉันสามารถปรับแต่งส่วนย่อยแต่ละส่วนได้หรือไม่?** Yes – fill colors, borders, and data labels are fully customizable.  
- **ต้องใช้ใบอนุญาตสำหรับการผลิตหรือไม่?** A free evaluation works for testing; a commercial license is required for deployment.

## Sunburst Chart คืออะไร?
แผนภูมิ Sunburst แสดงข้อมูลเชิงลำดับชั้นเป็นวงแหวนศูนย์กลางที่ซ้อนกัน โดยแต่ละวงแสดงระดับของลำดับชั้น ช่วยให้ผู้ชมเข้าใจความสัมพันธ์แบบพ่อแม่‑ลูกได้ในทันที ทำให้เหมาะสำหรับแผนภูมิโครงสร้างองค์กร การแสดง taxonomy และเมตริกหลายระดับ มันมีประโยชน์อย่างยิ่งในการแสดงหมวดหมู่หลายระดับ เช่น สายผลิตภัณฑ์, ภูมิภาคทางภูมิศาสตร์, หรือโครงสร้างองค์กร ทำให้ผู้ชมเห็นการกระจายโดยรวมและการแยกรายละเอียดภายในแต่ละส่วน

## ทำไมต้องใช้ Aspose.Slides สำหรับ Sunburst Chart?
Aspose.Slides รองรับ **30+ chart types** ประมวลผลไฟล์ขนาดสูงสุด **500 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ และเรนเดอร์กราฟิกที่ **300 DPI** เพื่อให้ได้ผลลัพธ์คมชัด เหล่านี้ทำให้การสร้างเร็วและภาพคุณภาพสูงแม้กับงานนำเสนอขนาดใหญ่ นอกจากนี้ไลบรารียังให้การทำงานแบบ thread‑safe และผสานรวมอย่างราบรื่นกับเครื่องมือสร้าง Java ยอดนิยม ทำให้เหมาะสำหรับการสร้างงานนำเสนอทั้งบนเดสก์ท็อปและเซิร์ฟเวอร์ในระดับใหญ่

## ข้อกำหนดเบื้องต้น
- Java Development Kit (JDK) 8 หรือใหม่กว่า.  
- Maven หรือ Gradle สำหรับการจัดการ dependencies.  
- Aspose.Slides for Java (เวอร์ชันล่าสุด).  
- ความเข้าใจพื้นฐานเกี่ยวกับโครงสร้างข้อมูลเชิงลำดับชั้น.

## วิธีสร้าง Sunburst Chart ขั้นตอนต่อขั้นตอน?
โหลดสภาพแวดล้อมของคุณ, เพิ่มแผนภูมิ, ป้อนข้อมูลเชิงลำดับชั้น, ปรับสไตล์, และบันทึกไฟล์ – ทั้งหมดในไม่กี่ขั้นตอนที่ง่าย ด้านล่างเป็นขั้นตอนการทำงานที่คุณสามารถทำตามได้โดยไม่ต้องเขียนโค้ดโครงสร้างเพิ่มเติม กระบวนการนี้อัตโนมัติเต็มที่ ไม่ต้องมีการโต้ตอบ UI ด้วยตนเอง และสามารถนำไปใช้ในงานแบทช์หรือบริการเว็บเพื่อสร้างแผนภูมิเมื่อจำเป็น

### ขั้นตอนที่ 1: ตั้งค่าโครงการ
เพิ่ม dependency ของ Aspose.Slides สำหรับ Maven (หรือสคริปต์ Gradle ที่เทียบเท่า) ไปยังไฟล์ `pom.xml` ของคุณ ซึ่งจะดึงไบนารีและไลบรารีที่จำเป็นทั้งหมดเข้ามา

### ขั้นตอนที่ 2: โหลดหรือสร้าง Presentation
`Presentation` คืออ็อบเจกต์ระดับบนของ Aspose.Slides ที่แทนไฟล์ PowerPoint หนึ่งไฟล์ในหน่วยความจำ สร้างอินสแตนซ์ด้วย `new Presentation()` สำหรับงานนำเสนอใหม่ หรือส่งพาธไฟล์เพื่อเปิด PPTX ที่มีอยู่

### ขั้นตอนที่ 3: เพิ่ม Sunburst Chart
แทรกรูปแบบแผนภูมิใหม่ลงบนสไลด์โดยใช้ `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` ซึ่งจะสร้างตัวแทน Sunburst พร้อมรับข้อมูล `ChartType.Sunburst` ระบุประเภทแผนภูมิ Sunburst เมื่อเพิ่มแผนภูมิลงบนสไลด์

### ขั้นตอนที่ 4: เติมข้อมูลเชิงลำดับชั้น
`ChartData` เก็บชุดข้อมูลและหมวดหมู่สำหรับแผนภูมิ เข้าถึงคอลเลกชัน `ChartData` ของแผนภูมิและเพิ่ม series และ categories ที่สะท้อนลำดับชั้นของคุณ สำหรับแต่ละระดับ ให้ระบุความสัมพันธ์พ่อแม่‑ลูกผ่าน property `ParentSeries` เพื่อให้แผนภูมิสร้างวงแหวนศูนย์กลางโดยอัตโนมัติ

### ขั้นตอนที่ 5: ปรับแต่งลักษณะ
ปรับสีส่วน, สไตล์ขอบ, และป้ายข้อมูลอย่างละเอียดผ่านอ็อบเจกต์ `ChartSeries` และ `ChartDataPoint` `ChartSeries` แทนชุดข้อมูลของจุดในแผนภูมิ `ChartDataPoint` แทนจุดข้อมูลแต่ละจุดใน series คุณยังสามารถเปิดการหมุน 3‑D หรือกำหนด property `Explode` เพื่อเน้นส่วนเฉพาะได้

### ขั้นตอนที่ 6: บันทึก Presentation
`SaveFormat` enum กำหนดรูปแบบไฟล์ที่คุณสามารถบันทึก Presentation ได้ เรียก `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` เพื่อเขียนไฟล์ลงดิสก์ คุณยังสามารถส่งออกเป็น PDF หรือ PNG โดยเปลี่ยนค่า enum ของ `SaveFormat`

## วิธีปรับแต่งสีของ Sunburst Chart?
กำหนดสีเติมสำหรับแต่ละ `ChartDataPoint` ด้วย `point.getFillFormat().setFillType(FillType.Solid)` แล้วตามด้วย `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))` วิธีตรงนี้ช่วยให้คุณสอดคล้องกับแบรนด์ขององค์กรหรือเน้นจุดข้อมูลสำคัญ คุณยังสามารถใช้การเติมแบบไล่สี, ปรับความโปร่งแสง, หรือใช้สีธีมเพื่อให้สอดคล้องกับการออกแบบสไลด์ทั้งหมด

## ปัญหาทั่วไปและวิธีแก้
- **ปัญหา:** ลำดับชั้นปรากฏเป็นแบน.  
  **วิธีแก้:** Ensure each child series correctly references its `ParentSeries`. Missing links cause the chart to treat all data as a single level.
- **ปัญหา:** ไฟล์ PNG ที่ส่งออกดูเบลอ.  
  **วิธีแก้:** Increase the export DPI by setting `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **ปัญหา:** ไฟล์ PPTX ขนาดใหญ่ทำให้เกิด OutOfMemoryError.  
  **วิธีแก้:** Use `Presentation.setMemoryOptimization(true)` to stream data and keep memory usage low.

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้าง Sunburst chart จากไฟล์ CSV ได้หรือไม่?**  
A: ใช่. อ่านไฟล์ CSV, สร้างลำดับชั้นในหน่วยความจำ, แล้วป้อนให้กับคอลเลกชัน `ChartData` ของแผนภูมิ ก่อนบันทึก.

**Q: Aspose.Slides รองรับการเปลี่ยนภาพเคลื่อนไหวสำหรับ Sunburst chart หรือไม่?**  
A: มี. ใช้ `SlideShowTransition` กับสไลด์หรือใช้ `ChartFormat.setAnimationEnabled(true)` สำหรับการเคลื่อนไหวระดับแผนภูมิ.

**Q: สามารถส่งออกแผนภูมิเป็นกราฟิกเวกเตอร์ SVG ได้หรือไม่?**  
A: ได้แน่นอน. บันทึก Presentation ด้วย `SaveFormat.Svg` เพื่อรับเวอร์ชันเวกเตอร์ที่ขยายได้ของ Sunburst chart.

**Q: จำนวนจุดข้อมูลสูงสุดที่ Sunburst chart สามารถจัดการได้คือเท่าไหร่?**  
A: Aspose.Slides ประมวลผลได้อย่างเชื่อถือได้สูงสุด **10,000** จุดข้อมูลใน Sunburst chart เดียวโดยไม่มีการลดประสิทธิภาพ.

**Q: ฉันต้องมีใบอนุญาตแยกต่างหากสำหรับแต่ละสภาพแวดล้อมการปรับใช้หรือไม่?**  
A: ใบอนุญาตเชิงพาณิชย์เดียวครอบคลุมทุกสภาพแวดล้อม (การพัฒนา, การทดสอบ, การผลิต) ตราบใดที่ปฏิบัติตามเงื่อนไขใบอนุญาต.

## สรุป
คุณมีคู่มือครบถ้วนแบบขั้นตอนต่อขั้นตอนสำหรับ **how to create sunburst** ใน Java ด้วย Aspose.Slides แล้ว โดยการทำตามขั้นตอนข้างต้น คุณสามารถสร้างภาพเชิงลำดับชั้นคุณภาพสูงที่ปรับแต่งได้เต็มที่สำหรับการนำเสนอ PowerPoint ใด ๆ

---

**อัปเดตล่าสุด:** 2026-07-03  
**ทดสอบกับ:** Aspose.Slides for Java 24.12  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนต่อขั้นตอน](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [เชี่ยวชาญการปรับแต่งแผนภูมิ PowerPoint ด้วย Aspose.Slides Java สำหรับการนำเสนอแบบไดนามิก](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [ทำให้แผนภูมิ PowerPoint เคลื่อนไหวตามหมวดหมู่ด้วย Aspose.Slides for Java | คู่มือขั้นตอนต่อขั้นตอน](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}