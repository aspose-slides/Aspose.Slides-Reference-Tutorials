---
date: '2026-01-06'
description: เรียนรู้วิธีอัตโนมัติการสร้างแผนภูมิ, เพิ่มแผนภูมิบับเบิลและป้ายข้อมูลในงานนำเสนอด้วย
  Aspose.Slides for Java. ปรับกระบวนการทำงานของคุณให้เป็นระบบด้วยคู่มือขั้นตอนต่อขั้นตอนนี้.
keywords:
- Aspose.Slides for Java
- adding charts to presentations with Java
- configuring data labels in Aspose.Slides
title: วิธีอัตโนมัติการสร้างแผนภูมิและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides
  สำหรับ Java
url: /th/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการทำอัตโนมัติการสร้างแผนภูมิและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java

## บทนำ
การสร้างงานนำเสนอแบบไดนามิกเป็นสิ่งสำคัญในหลายสภาพแวดล้อมมืออาชีพ ตั้งแต่การพรีเซนต์ธุรกิจจนถึงการบรรยายทางวิชาการ เมื่อคุณ **ทำอัตโนมัติการสร้างแผนภูมิ** คุณจะขจัดขั้นตอนที่ทำซ้ำด้วยมือ ลดข้อผิดพลาด และทำให้การแสดงผลข้อมูลของคุณเป็นปัจจุบันอยู่เสมอ บทแนะนำนี้จะพาคุณผ่านการใช้ Aspose.Slides for Java เพื่อเพิ่มแผนภูมิบับเบิล กำหนดค่าป้ายข้อมูล และบันทึกผลลัพธ์ — ทั้งหมดโดยโปรแกรม

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides for Java
- การโหลดและเตรียมงานนำเสนอสำหรับการแก้ไข
- **วิธีการเพิ่มแผนภูมิ** – โดยเฉพาะแผนภูมิบับเบิล – ลงในสไลด์
- **เพิ่มป้ายข้อมูล** ด้วยการอ้างอิงเซลล์
- การบันทึกงานนำเสนอที่แก้ไขแล้ว

มาเริ่มกันและดูว่าคุณสามารถ **ทำอัตโนมัติการสร้างแผนภูมิ** ในแอปพลิเคชัน Java ของคุณได้อย่างไร

## คำตอบสั้น
- **ไลบรารีใดที่ทำให้การทำอัตโนมัติแผนภูมิใน Java เป็นไปได้?** Aspose.Slides for Java  
- **ประเภทแผนภูมิที่แสดงตัวอย่างคืออะไร?** Bubble Chart  
- **ป้ายข้อมูลตั้งค่าอย่างไร?** โดยเชื่อมโยงกับเซลล์ใน worksheet  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ใช่ ต้องมีลิขสิทธิ์เต็มรูปแบบ  
- **สามารถเพิ่มแผนภูมิลงในสไลด์ใดก็ได้หรือไม่?** ใช่ ใช้ `addChart` บนสไลด์เป้าหมาย  

## การทำอัตโนมัติการสร้างแผนภูมิคืออะไร?
การทำอัตโนมัติการสร้างแผนภูมิหมายถึงการสร้างและปรับแต่งแผนภูมิผ่านโค้ดแทนการวาดด้วยมือใน PowerPoint วิธีนี้รับประกันความสอดคล้อง เร่งความเร็วในการสร้างรายงาน และทำให้การรวมแหล่งข้อมูลสดเป็นเรื่องง่าย

## ทำไมต้องใช้ Aspose.Slides for Java?
- **การควบคุมเต็มรูปแบบ** ทุกองค์ประกอบของแผนภูมิ (ประเภท, ขนาด, แหล่งข้อมูล)  
- **ไม่ต้องพึ่งพา Microsoft Office** – ทำงานบนเซิร์ฟเวอร์หรือสภาพแวดล้อม CI ใดก็ได้  
- **API ที่ครอบคลุม** สำหรับการเพิ่มแผนภูมิบับเบิล, ป้ายข้อมูล, และอื่น ๆ  
- **ประสิทธิภาพสูง** สำหรับงานนำเสนอขนาดใหญ่เมื่อจัดการหน่วยความจำอย่างเหมาะสม  

## ข้อกำหนดเบื้องต้น
- **ไลบรารีและการพึ่งพา:** Aspose.Slides for Java (เวอร์ชัน 25.4)  
- **เครื่องมือสร้าง:** Maven หรือ Gradle (ตัวอย่างด้านล่าง)  
- **ความรู้ Java:** ความคุ้นเคยกับไวยากรณ์พื้นฐานของ Java และการจัดการอ็อบเจกต์  

## การตั้งค่า Aspose.Slides for Java

### คำแนะนำการติดตั้ง
เพื่อรวม Aspose.Slides เข้าในโปรเจกต์ของคุณ คุณสามารถใช้ Maven หรือ Gradle ดังนี้:

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

หากคุณต้องการดาวน์โหลดโดยตรง ให้เยี่ยมชมหน้า [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

### การขอรับลิขสิทธิ์
- **ทดลองใช้ฟรี:** เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์  
- **ลิขสิทธิ์ชั่วคราว:** ขอรับลิขสิทธิ์ชั่วคราวหากต้องการเวลามากขึ้นโดยไม่มีข้อจำกัด  
- **ซื้อ:** พิจารณาซื้อลิขสิทธิ์เต็มรูปแบบสำหรับการใช้งานเชิงพาณิชย์  

เมื่อตั้งค่าเสร็จ การเริ่มต้น Aspose.Slides จะง่ายดาย คุณสามารถเริ่มโดยการโหลดไฟล์งานนำเสนอและเตรียมพร้อมสำหรับการแก้ไข

## วิธีการเพิ่มแผนภูมิลงในสไลด์

### ฟีเจอร์ 1: การตั้งค่างานนำเสนอ

#### ภาพรวม
โหลดไฟล์งานนำเสนอที่มีอยู่เพื่อให้คุณสามารถแก้ไขเนื้อหาได้

**ขั้นตอนการทำงาน**

##### ขั้นตอนที่ 1: โหลดงานนำเสนอ
```java
import com.aspose.slides.Presentation;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```

- **ทำไม:** การโหลดไฟล์งานนำเสนอเป็นขั้นตอนสำคัญ เนื่องจากทำให้คุณเข้าถึงและแก้ไขเนื้อหาได้

### ฟีเจอร์ 2: การเพิ่มแผนภูมิบับเบิล

#### ภาพรวม
เพิ่มแผนภูมิบับเบิลลงในสไลด์แรก – วิธีที่นิยมในการแสดงข้อมูลสามมิติ

**ขั้นตอนการทำงาน**

##### ขั้นตอนที่ 1: เริ่มต้น Presentation และเพิ่มแผนภูมิ
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

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

- **ทำไม:** การเพิ่มแผนภูมิช่วยเพิ่มความน่าสนใจและการสื่อสารข้อมูลของงานนำเสนอของคุณ

### ฟีเจอร์ 3: การกำหนดค่าป้ายข้อมูลสำหรับ Series

#### ภาพรวม
ตั้งค่าป้ายข้อมูลบนซีรีส์ของแผนภูมิโดยใช้การอ้างอิงเซลล์ ซึ่งทำให้ป้ายข้อมูลเป็นแบบไดนามิกและอัปเดตง่าย

**ขั้นตอนการทำงาน**

##### ขั้นตอนที่ 1: กำหนดค่าป้ายข้อมูล
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

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

- **ทำไม:** การกำหนดค่าป้ายข้อมูลเป็นสิ่งจำเป็นสำหรับการให้ข้อมูลเชิงลึกโดยตรงบนแผนภูมิของคุณ

### ฟีเจอร์ 4: การบันทึกงานนำเสนอ

#### ภาพรวม
บันทึกงานนำเสนอที่แก้ไขแล้วลงไฟล์ เพื่อให้คุณสามารถแชร์หรือประมวลผลต่อได้

**ขั้นตอนการทำงาน**

##### ขั้นตอนที่ 1: บันทึกงานของคุณ
```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

- **ทำไม:** การบันทึกงานนำเสนอทำให้การแก้ไขทั้งหมดของคุณถูกเก็บรักษาไว้สำหรับการใช้งานในอนาคต

## การประยุกต์ใช้ในเชิงปฏิบัติ
1. **รายงานธุรกิจ:** สร้างและอัปเดตแผนภูมิอัตโนมัติในรายงานไตรมาส  
2. **การนำเสนอทางวิชาการ:** เพิ่มการแสดงผลข้อมูลแบบเรียลไทม์ในบทเรียน  
3. **การพรีเซนต์ขาย:** สร้างงานนำเสนอไดนามิกที่แสดงแนวโน้มและการคาดการณ์การขาย  
4. **การจัดการโครงการ:** แสดงไทม์ไลน์โครงการและการจัดสรรทรัพยากร  
5. **การวิเคราะห์การตลาด:** ผสานแผนภูมิ Aspose.Slides ลงในแดชบอร์ดเพื่อการติดตามประสิทธิภาพแคมเปญ  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ใช้โครงสร้างข้อมูลที่มีประสิทธิภาพเพื่อจัดการชุดข้อมูลขนาดใหญ่ในแผนภูมิ  
- จัดการหน่วยความจำโดยการทำลายอ็อบเจกต์อย่างเหมาะสมด้วยบล็อก `try‑finally`  
- ปรับเทคนิคการจัดการหน่วยความจำของ Java เมื่อต้องทำงานกับงานนำเสนอขนาดใหญ่  

## คำถามที่พบบ่อย

**ถาม: Aspose.Slides for Java คืออะไร?**  
ตอบ: ไลบรารีที่ทรงพลังสำหรับการสร้าง, แก้ไข, และแปลงไฟล์งานนำเสนอในแอปพลิเคชัน Java  

**ถาม: สามารถใช้ Aspose.Slides ได้โดยไม่ซื้อไหม?**  
ตอบ: ใช่ คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อทดสอบความสามารถ  

**ถาม: จะเพิ่มประเภทแผนภูมิอื่น ๆ อย่างไร?**  
ตอบ: ใช้ enumeration `ChartType` เพื่อระบุสไตล์แผนภูมิต่าง ๆ เช่น `ChartType.Pie`, `ChartType.Column` เป็นต้น  

**ถาม: สามารถแก้ไขแผนภูมิที่มีอยู่ในงานนำเสนอได้หรือไม่?**  
ตอบ: แน่นอน! โหลดงานนำเสนอ, ค้นหา shape ของแผนภูมิ, แล้วแก้ไขคุณสมบัติใด ๆ ผ่านโปรแกรม  

**ถาม: จุดอ่อนด้านประสิทธิภาพที่พบบ่อยคืออะไร?**  
ตอบ: งานนำเสนอขนาดใหญ่อาจใช้หน่วยความจำมาก; ควรทำลายอ็อบเจกต์ `Presentation` และใช้ worksheet ร่วมกันเมื่อเป็นไปได้  

## แหล่งข้อมูล
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose