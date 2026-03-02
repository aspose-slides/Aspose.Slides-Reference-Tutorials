---
date: '2026-03-02'
description: เรียนรู้วิธีสร้างกราฟกล่องใน Java, เพิ่มแผนภูมิลงในสไลด์, และสร้างแผนภูมิกล่อง
  (box‑whisker) ใน PowerPoint ด้วย Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: สร้างแผนภูมิกล่องใน Java ด้วย Aspose.Slides สำหรับ PowerPoint
url: /th/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิ Box-and-Whisker ใน PowerPoint ด้วย Aspose.Slides for Java

ในคู่มือนี้คุณจะ **สร้าง box plot java** ด้วย Aspose.Slides แล้วฝังแผนภูมิลงในสไลด์ PowerPoint โดยตรง การสร้างการนำเสนอข้อมูลที่ดูน่าสนใจเป็นสิ่งสำคัญในโลกที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน และแผนภูมิเป็นเครื่องมือที่จำเป็น หากคุณต้องการสร้างแผนภูมิ box-and-whisker ใน PowerPoint ด้วย Java ไลบรารี Aspose.Slides มีโซลูชันที่แข็งแกร่ง คู่มือนี้จะพาคุณผ่านขั้นตอนการสร้างและกำหนดค่าแผนภูมิเหล่านี้อย่างราบรื่นด้วย Aspose.Slides for Java.

## สิ่งที่คุณจะได้เรียนรู้

- ตั้งค่าสภาพแวดล้อมของคุณสำหรับ Aspose.Slides for Java
- ขั้นตอนในการ **add chart to slide** และสร้างแผนภูมิ box‑whisker ใน PowerPoint ด้วย Java
- แนวทางปฏิบัติที่ดีที่สุดสำหรับการเพิ่มประสิทธิภาพเมื่อทำงานกับ Aspose.Slides
- การใช้งานจริงของแผนภูมิ box‑and‑whisker

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดสร้าง box plot ใน Java?** Aspose.Slides for Java.
- **ประเภทแผนภูมิใดที่ใช้?** `ChartType.BoxAndWhisker`.
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการผลิต.
- **ฉันสามารถเพิ่มหลายซีรีส์ได้หรือไม่?** ใช่ – ทำซ้ำบล็อกการสร้างซีรีส์สำหรับแต่ละชุดข้อมูล.
- **รูปแบบไฟล์สุดท้ายคืออะไร?** PowerPoint PPTX (`SaveFormat.Pptx`).

## ข้อกำหนดเบื้องต้น

เพื่อทำตามบทเรียนนี้ โปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)**: ควรติดตั้ง JDK 8 หรือสูงกว่า
- **Aspose.Slides for Java Library**: จำเป็นสำหรับการจัดการงานนำเสนอ PowerPoint ใน Java
- **IDE**: สภาพแวดล้อมการพัฒนาแบบบูรณาการ เช่น IntelliJ IDEA หรือ Eclipse เพื่อเขียนและรันโค้ดของคุณ

## การตั้งค่า Aspose.Slides for Java

เพื่อใช้ Aspose.Slides ให้เพิ่มเป็น dependency คุณสามารถจัดการได้ผ่าน Maven, Gradle หรือการดาวน์โหลดโดยตรง

### Maven

เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

ในไฟล์ `build.gradle` ของคุณ ให้รวม:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download

หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition

- **Free Trial**: เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณลักษณะต่าง ๆ.  
- **Temporary License**: รับไลเซนส์ชั่วคราวสำหรับการประเมิน.  
- **Purchase**: สำหรับการทำงานเต็มรูปแบบ พิจารณาซื้อไลเซนส์.

เพื่อเริ่มต้น Aspose.Slides ให้แน่ใจว่าคุณมีไลบรารีใน classpath และตั้งค่าข้อกำหนดไลเซนส์ตามที่จำเป็น

## คู่มือการใช้งาน

ตอนนี้เราจะลงลึกในโค้ดแบบขั้นตอนต่อขั้นตอน แต่ละบล็อกจะอธิบายก่อนโค้ดสแนปเพื่อตรวจสอบว่ามันทำอะไร

### กล่องแผนภูมิคืออะไรและทำไมต้องใช้ใน Java?

แผนภูมิ box‑and‑whisker (ที่มักเรียกว่า *box plot*) แสดงการกระจายของข้อมูล—ค่ากลาง, ควอร์ไทล์, และค่าผิดปกติ—in รูปแบบที่กระชับ ใน Java การสร้างแผนภูมินี้โดยโปรแกรมทำให้คุณสามารถฝังข้อมูลสถิติลงในสไลด์ PowerPoint ได้โดยตรง ลดการสร้างแผนภูมิด้วยมือ

### ทำไมต้องเพิ่มแผนภูมิลงในสไลด์ด้วย Aspose.Slides?

Aspose.Slides ทำให้ซ่อนรายละเอียดระดับต่ำของ OpenXML ให้คุณมี API ที่ไหลลื่นในการสร้าง, ปรับสไตล์, และส่งออกแผนภูมิ ซึ่งหมายความว่าคุณสามารถอัตโนมัติการสร้างรายงาน, ผลิตแบรนด์ที่สม่ำเสมอ, และรวมแผนภูมิเข้าไปในกระบวนการทำงานของ Java ที่ใหญ่ขึ้น

### ขั้นตอนที่ 1: สร้างหรือเปิดงานนำเสนอ

แรกสุด เปิดไฟล์ PPTX ที่มีอยู่หรือเริ่มไฟล์ใหม่:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **เคล็ดลับ:** หากไฟล์ไม่มีอยู่ Aspose.Slides จะสร้างงานนำเสนอเปล่าใหม่ให้คุณ

### ขั้นตอนที่ 2: เพิ่มแผนภูมิ Box‑and‑Whisker ลงในสไลด์

วางแผนภูมิในตำแหน่งที่ต้องการโดยระบุตำแหน่งและขนาด (เป็นจุด):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### ขั้นตอนที่ 3: ล้างข้อมูลที่มีอยู่

ก่อนใส่ข้อมูลใหม่ ให้ลบหมวดหมู่หรือซีรีส์ที่เป็นตัวแทนไว้ล่วงหน้า:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### ขั้นตอนที่ 4: ตั้งค่าหมวดหมู่

เพิ่มหมวดหมู่ (ป้ายแกน X) ที่จะแสดงใต้แต่ละกล่อง:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **หมายเหตุ:** ปรับข้อความป้ายให้ตรงกับโดเมนข้อมูลของคุณ (เช่น “Q1”, “Product A”).

### ขั้นตอนที่ 5: สร้างและปรับแต่งซีรีส์

ตอนนี้สร้างซีรีส์ ตั้งค่าตัวเลือกการแสดงผล และใส่ค่าตัวเลข:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

คุณสามารถแทนที่อาร์เรย์ `int[] data` ด้วยค่าที่อ่านจากฐานข้อมูล, ไฟล์ CSV, หรือแหล่งอื่นใดก็ได้

### ขั้นตอนที่ 6: บันทึกงานนำเสนอ

บันทึกการเปลี่ยนแปลงลงในไฟล์ PPTX ใหม่:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### ขั้นตอนที่ 7: ทำความสะอาดทรัพยากร

ควรทำการ dispose วัตถุ `Presentation` เสมอเพื่อปล่อยทรัพยากรเนทีฟ:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## การประยุกต์ใช้ในทางปฏิบัติ

แผนภูมิ Box‑and‑whisker มีคุณค่าอย่างยิ่งในการวิเคราะห์สถิติและการนำเสนอข้อมูล ต่อไปนี้คือบางสถานการณ์ที่มันโดดเด่น:

- **Financial Analysis** – แสดงการกระจายของรายได้ตามภูมิภาค.  
- **Quality Control** – ตรวจจับค่าผิดปกติในการวัดการผลิต.  
- **Academic Research** – แสดงความแปรปรวนของผลการทดลอง.  
- **Market Research** – เปรียบเทียบประสิทธิภาพผลิตภัณฑ์ตามกลุ่มประชากร.

การรวมแผนภูมิเหล่านี้ลงในสไลด์ PowerPoint ทำให้ผู้มีส่วนได้ส่วนเสียเข้าใจข้อมูลซับซ้อนได้อย่างรวดเร็ว

## ข้อควรพิจารณาด้านประสิทธิภาพ

เมื่อทำงานกับ Aspose.Slides ใน Java ให้คำนึงถึงเคล็ดลับต่อไปนี้:

- **Memory Management** – ทำการ dispose วัตถุ `Presentation` อย่างทันท่วงที.  
- **Data Handling** – โหลดเฉพาะข้อมูลที่ต้องการ; หลีกเลี่ยงการใส่ชุดข้อมูลขนาดใหญ่โดยตรงลงใน workbook ของแผนภูมิ.  
- **Lazy Loading** – หากคุณสร้างสไลด์จำนวนมาก ควรสร้างแผนภูมิเฉพาะสำหรับสไลด์ที่จะแสดงเท่านั้น.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| **แผนภูมิแสดงเป็นค่าว่าง** | เซลล์ข้อมูลไม่ได้เติมค่าอย่างถูกต้อง | ตรวจสอบว่า `wb.getCell` อ้างอิงแถว/คอลัมน์ที่ถูกต้องและค่าที่ได้ไม่เป็น `null`. |
| **ค่าผิดปกติไม่แสดง** | `setShowOutlierPoints` ถูกตั้งค่าเป็น `false` | ตรวจสอบว่าได้เรียก `series.setShowOutlierPoints(true)` |
| **การรั่วของหน่วยความจำ** | ไม่ได้ทำการ dispose งานนำเสนอ | ควรห่อการใช้งานด้วย try/finally และเรียก `dispose()` เสมอ |
| **ควอร์ไทล์ไม่ถูกต้อง** | ใช้วิธี `Inclusive` เริ่มต้น | เปลี่ยนเป็น `Exclusive` ผ่าน `setQuartileMethod(QuartileMethodType.Exclusive)` |

## คำถามที่พบบ่อย

**Q1: แผนภูมิ box-and-whisker คืออะไร?**  
แผนภูมิ box-and-whisker หรือที่เรียกว่า box plot แสดงการกระจายของข้อมูลโดยอิงจากสถิติสรุปห้าประการ: ค่าต่ำสุด, ควอร์ไทล์แรก, ค่ากลาง, ควอร์ไทล์ที่สาม, และค่าสูงสุด พร้อมค่าผิดปกติที่อาจมี

**Q2: ฉันสามารถปรับแต่งลักษณะของแผนภูมิ box-and-whisker ได้หรือไม่?**  
ได้. Aspose.Slides ให้คุณเปลี่ยนสี, รูปแบบเส้น, รูปร่างของมาร์คเกอร์, และแม้กระทั่งเพิ่มป้ายข้อมูลผ่าน API การจัดรูปแบบของแผนภูมิ

**Q3: สามารถจัดการหลายซีรีส์ในแผนภูมิเดียวได้หรือไม่?**  
แน่นอน. ทำซ้ำบล็อกการสร้างซีรีส์สำหรับแต่ละชุดข้อมูลที่ต้องการแสดง

**Q4: จะแก้ปัญหาข้อมูลไม่แสดงอย่างถูกต้องอย่างไร?**  
ตรวจสอบให้แน่ใจว่าข้อมูลถูกเขียนลงในเซลล์ของ workbook อย่างถูกต้องและคุณสมบัติการมองเห็นเช่น `setShowMeanLine` ถูกเปิดใช้งาน

**Q5: จะหาแหล่งสนับสนุนเมื่อเจอปัญหาได้จากที่ไหน?**  
เยี่ยมชม [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) เพื่อรับความช่วยเหลือจากชุมชน หรือดูเอกสารอย่างเป็นทางการ

**Q6: Aspose.Slides รองรับประเภทแผนภูมิอื่น ๆ หรือไม่?**  
ใช่, รองรับแผนภูมิประเภท line, bar, pie, scatter, radar และอื่น ๆ อีกมาก

**Q7: สามารถสร้างแผนภูมิในสภาพแวดล้อมเซิร์ฟเวอร์แบบ headless ได้หรือไม่?**  
ไลบรารีทำงานเต็มรูปแบบในสภาพแวดล้อมเซิร์ฟเวอร์; ไม่จำเป็นต้องมี UI

## แหล่งข้อมูล

- **Documentation**: สำรวจอ้างอิง API รายละเอียดที่ [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: เข้าถึงการปล่อย Aspose.Slides [ที่นี่](https://releases.aspose.com/slides/java/)  
- **Purchase**: ซื้อไลเซนส์เพื่อเปิดฟีเจอร์เต็มที่ที่ [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: เริ่มต้นด้วยการทดลองใช้ฟรีหรือขอไลเซนส์ชั่วคราว [ที่นี่](https://releases.aspose.com/slides/java/)

โดยทำตามคู่มือนี้ คุณจะพร้อมสร้างแผนภูมิ box‑and‑whisker อย่างมีประสิทธิภาพในแอปพลิเคชัน Java ของคุณและฝังลงในงานนำเสนอ PowerPoint โดยตรง ขอให้สนุกกับการเขียนโค้ด!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-02  
**ทดสอบด้วย:** Aspose.Slides 25.4 (JDK 16 classifier)  
**ผู้เขียน:** Aspose