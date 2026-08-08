---
date: '2026-08-06'
description: เรียนรู้วิธีเปลี่ยนสีฟอนต์ของ legend และแก้ไขข้อความ legend ของ chart
  โดยใช้ Aspose.Slides for Java. ปฏิบัติตามคำแนะนำ step‑by‑step เพื่อ customize chart
  legends อย่างรวดเร็ว.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: เรียนรู้วิธีเปลี่ยนสีฟอนต์ของ legend และแก้ไขข้อความ legend ของ chart
  ด้วย Aspose.Slides for Java. คู่มือนี้จะแสดงขั้นตอนที่แน่นอนและ best practices.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: วิธีเปลี่ยนสีฟอนต์ของ legend ใน Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: วิธีเปลี่ยนสีฟอนต์ของ legend ใน Aspose.Slides for Java
url: /th/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเปลี่ยนสีฟอนต์ของ legend ใน Aspose.Slides for Java

## บทนำ
หากคุณต้องการ **เปลี่ยนสีฟอนต์ของ legend** ในแผนภูมิ Aspose.Slides for Java จะให้คุณควบคุมทุกรายการ legend ได้อย่างเต็มที่ บทแนะนำนี้จะพาคุณผ่านการปรับสไตล์ข้อความ legend, การใช้ฟอนต์หนาหรือเอียง, และการตั้งค่าสีทึบ เพื่อให้แผนภูมิของคุณดูตรงตามที่คุณต้องการ เมื่อจบคู่มือคุณจะสามารถแก้ไขข้อความ legend ของแผนภูมิได้อย่างมั่นใจและผสานการเปลี่ยนแปลงเหล่านั้นเข้าไปในงานนำเสนอใด ๆ ที่มีอยู่

**สิ่งที่คุณจะได้เรียน**
- วิธี **เปลี่ยนสีฟอนต์ของ legend** ด้วยโปรแกรม
- วิธี **ปรับข้อความ legend ของแผนภูมิ** เช่น ทำให้เป็นตัวหนา, เอียง, และขนาดฟอนต์
- เคล็ดลับในการนำการเปลี่ยนแปลงไปใช้กับหลายแผนภูมิในงานนำเสนอเดียว
- วิธีผสานขั้นตอนเหล่านี้เข้ากับกระบวนการอัตโนมัติที่ใหญ่ขึ้น

## คำตอบอย่างรวดเร็ว
- **ฉันสามารถเปลี่ยนสีของรายการ legend เพียงรายการเดียวได้หรือไม่?** ได้ – เข้าถึงรายการโดยใช้ดัชนีและตั้งค่า fill format เป็นสีทึบ  
- **ต้องมีลิขสิทธิ์เพื่อใช้ API เหล่านี้หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือแบบชำระเงินสำหรับการใช้งานจริง; ลิขสิทธิ์ทดลองฟรีใช้ได้สำหรับการประเมินผล  
- **รองรับเวอร์ชัน Java ใด?** Aspose.Slides for Java 25.4+ ทำงานกับ JDK 16 ขึ้นไป  
- **การเปลี่ยนแปลงจะส่งผลต่อส่วนอื่นของแผนภูมิหรือไม่?** ไม่, การจัดรูปแบบ legend แยกจากการจัดสไตล์ของชุดข้อมูล  
- **สามารถทำการประมวลผลเป็นชุดได้หรือไม่?** แน่นอน – วนลูปผ่านสไลด์และแผนภูมิเพื่อใช้การตั้งค่า legend เดียวกันทั่วทั้งเด็ค

## การเปลี่ยนสีฟอนต์ของ legend คืออะไร?
`change legend font color` หมายถึงการดำเนินการโดยโปรแกรมเพื่อกำหนดสีข้อความของรายการ legend ในแผนภูมิด้วย Aspose.Slides API การดำเนินการนี้จะอัปเดตลักษณะการแสดงผลของ legend โดยไม่กระทบต่อข้อมูลพื้นฐาน

## ทำไมต้องปรับแต่ง legend ของแผนภูมิ?
Aspose.Slides รองรับ **รูปแบบเข้าและออกกว่า 50 แบบ** และสามารถจัดการงานนำเสนอที่มี **สไลด์กว่า 500 สไลด์** พร้อมการใช้หน่วยความจำต่ำกว่า 200 MB การปรับแต่ง legend ช่วยเพิ่มความอ่านง่าย, เสริมสีแบรนด์, และทำให้จุดข้อมูลสำคัญโดดเด่น—โดยเฉพาะในงานนำเสนอธุรกิจหรือการศึกษา ที่ความชัดเจนของภาพมีผลต่อการตัดสินใจ

## ข้อกำหนดเบื้องต้น
- ไลบรารี **Aspose.Slides for Java** (เวอร์ชัน 25.4 หรือใหม่กว่า)  
- Java Development Kit (JDK) 16 หรือสูงกว่า  
- IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans  
- Maven หรือ Gradle สำหรับการจัดการ dependencies  
- ความรู้พื้นฐานการเขียนโปรแกรม Java

## การตั้งค่า Aspose.Slides for Java
เพื่อเริ่มปรับแต่ง legend ของแผนภูมิ ให้เพิ่มไลบรารีลงในโปรเจกต์ของคุณด้วยวิธีใดวิธีหนึ่งต่อไปนี้

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
ใส่บรรทัดนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
คุณสามารถรับ JAR ล่าสุดได้จาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

#### ขั้นตอนการรับลิขสิทธิ์
- **ทดลองใช้ฟรี:** เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติของ Aspose.Slides  
- **ลิขสิทธิ์ชั่วคราว:** ขอรับลิขสิทธิ์ชั่วคราวสำหรับการประเมินผลระยะยาว  
- **ซื้อ:** หากต้องการเข้าถึงเต็มรูปแบบ ให้พิจารณาซื้อไลเซนส์จาก [Aspose Purchase](https://purchase.aspose.com/buy)

#### การเริ่มต้นและตั้งค่าพื้นฐาน
หลังจากเพิ่มไลบรารีลงในโปรเจกต์:
1. เริ่มต้น Aspose.Slides ในแอปพลิเคชัน Java ของคุณ  
2. โหลดงานนำเสนอที่มีอยู่หรือสร้างงานนำเสนอใหม่

## วิธีเปลี่ยนสีฟอนต์ของ legend?
เพื่อเปลี่ยนสีฟอนต์ของ legend ให้โหลดงานนำเสนอ, ดึงอ็อบเจกต์แผนภูมิ, รับ legend, แล้วแก้ไขรูปแบบข้อความของแต่ละรายการ legend โดยตั้งค่า fill type เป็น solid และกำหนดสีที่ต้องการ การดำเนินการเดียวนี้จะอัปเดตสีข้อความของ legend ทันทีโดยไม่ต้องวาดสไลด์ใหม่ ตัวอย่าง: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` วิธีนี้ทำงานกับแผนภูมิทุกประเภทและไม่ต้องเรนเดอร์สไลด์ทั้งหมดใหม่

### การเข้าถึงและแก้ไขคุณสมบัติข้อความ legend

#### คำอธิบายอ้างอิง
อินเทอร์เฟซ `IChart` แทนอ็อบเจกต์แผนภูมิบนสไลด์, และเมธอด `getLegend()` จะคืนค่าอ็อบเจกต์ `ILegend` ที่มีคอลเลกชันของรายการ `ILegendEntry`

#### การเพิ่มแผนภูมิลงในงานนำเสนอ
1. **โหลดงานนำเสนอ:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### การปรับคุณสมบัติฟอนต์
3. **เข้าถึงรูปแบบข้อความของรายการ legend:**  
   ที่นี่ `legendEntry` คืออ็อบเจกต์ `ILegendEntry` ที่แทนรายการเดียวใน legend ของแผนภูมิ  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **ตั้งค่าฟอนต์หนาและเอียงพร้อมความสูงที่กำหนด:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **เปลี่ยนประเภท fill เป็นสีทึบเพื่อความมองเห็นที่ดียิ่งขึ้น:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### การบันทึกงานนำเสนอ
6. **บันทึกการเปลี่ยนแปลงของคุณ:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- ตรวจสอบให้แน่ใจว่าดัชนีของรายการ legend ตรงกับลำดับของชุดข้อมูลในแผนภูมิของคุณ  
- ตรวจสอบว่าคุณใช้เวอร์ชันไลบรารีที่รองรับ `setSolidFillColor` (มีตั้งแต่เวอร์ชัน 20.9)

## การประยุกต์ใช้งานจริง
การปรับแต่งข้อความ legend มีประโยชน์ในหลายสถานการณ์จริง:

1. **งานนำเสนอธุรกิจ:** ปรับสี legend ให้สอดคล้องกับแบรนด์ของบริษัทเพื่อให้ดูเป็นมืออาชีพ  
2. **สื่อการศึกษา:** เน้นชุดข้อมูลสำคัญด้วยสี legend ที่ตัดกันชัดเจน  
3. **เด็คการตลาด:** เน้นเมตริกประสิทธิภาพด้วย legend ที่หนาและมีสีเพื่อดึงดูดความสนใจของผู้มีส่วนได้ส่วนเสีย  

คุณยังสามารถทำอัตโนมัติการอัปเดต legend โดยดึงค่าสีจากฐานข้อมูลหรือไฟล์กำหนดค่าได้อีกด้วย

## พิจารณาด้านประสิทธิภาพ
เมื่อประมวลผลเด็คขนาดใหญ่ ให้คำนึงถึงเคล็ดลับต่อไปนี้:

- **การจัดการหน่วยความจำอย่างมีประสิทธิภาพ:** เรียก `presentation.dispose()` หลังการบันทึกเพื่อปล่อยทรัพยากรเนทีฟ  
- **โหลดเฉพาะสไลด์ที่ต้องการ:** ใช้ `Presentation.load(String path, LoadOptions options)` พร้อม `LoadOptions.setLoadOnlySlideIds()` หากต้องการโหลดสไลด์ย่อยเท่านั้น  
- **การประมวลผลเป็นชุด:** จัดกลุ่มการอัปเดต legend ต่อสไลด์เพื่อลดจำนวนการเรียก API และเพิ่มอัตราการทำงาน

## สรุป
ตอนนี้คุณรู้วิธี **เปลี่ยนสีฟอนต์ของ legend** และ **ปรับข้อความ legend ของแผนภูมิ** ด้วย Aspose.Slides for Java การปรับแต่งเหล่านี้ช่วยเพิ่มความชัดเจนของภาพและทำให้คุณสื่อข้อมูลได้อย่างมีประสิทธิภาพ ทดลองใช้ฟอนต์, ขนาด, และสีต่าง ๆ เพื่อให้สอดคล้องกับแนวทางสไตล์ของงานนำเสนอของคุณ และสำรวจคุณสมบัติการจัดสไตล์แผนภูมิอื่น ๆ เพื่อสร้างเด็คที่เป็นมืออาชีพอย่างแท้จริง

**ขั้นตอนต่อไป**
- ลองนำสไตล์ legend เดียวกันไปใช้กับแผนภูมิวงกลมและเส้น  
- ผสานการปรับแต่ง legend กับการจัดรูปแบบป้ายข้อมูลเพื่อแผนภูมิที่มีแบรนด์ครบวงจร  

พร้อมที่จะยกระดับงานนำเสนอของคุณหรือยัง? นำขั้นตอนข้างต้นไปใช้และเห็นความแตกต่างทันที!

## ส่วนคำถามที่พบบ่อย
1. **ฉันจะเปลี่ยนสีข้อความของรายการ legend อย่างไร?**  
   ใช้ `getFillFormat().setFillType(FillType.Solid)` แล้วตามด้วย `setSolidFillColor(Color.YOUR_COLOR)` บนรูปแบบข้อความของรายการ legend  

2. **ฉันสามารถนำการเปลี่ยนแปลงนี้ไปใช้กับ legend ทั้งหมดในงานนำเสนอได้หรือไม่?**  
   ได้ – วนลูปผ่านแต่ละสไลด์, ค้นหาแผนภูมิแต่ละอัน, แล้วอัปเดตรายการ legend ภายในลูป  

3. **สามารถปรับขนาดฟอนต์โดยอัตโนมัติตามความยาวข้อความได้หรือไม่?**  
   คุณสามารถคำนวณขนาดที่ต้องการด้วย `TextFrame.getTextFrameFormat().getFontHeight()` แล้วตั้งค่าผ่าน `setFontHeight(double)`  

4. **ถ้าพบปัญหาเรื่องการจัดอันดับรายการ legend จะทำอย่างไร?**  
   ตรวจสอบให้แน่ใจว่าดัชนีที่ใช้ตรงกับลำดับของชุดข้อมูล; จำไว้ว่าดัชนีเริ่มจากศูนย์  

5. **จะหา ตัวอย่าง Aspose.Slides เพิ่มเติมได้จากที่ไหน?**  
   สำรวจ [Aspose Documentation](https://reference.aspose.com/slides/java/) เพื่อดูคู่มือและอ้างอิง API อย่างครบถ้วน  

**คำถามเพิ่มเติม**

**Q: การเปลี่ยนสีฟอนต์ของ legend มีผลต่อไฟล์ PDF ที่ส่งออกหรือไม่?**  
A: ไม่, การเปลี่ยนสีจะคงอยู่ในทุกรูปแบบการส่งออกที่ Aspose.Slides รองรับ รวมถึง PDF และ PPTX  

**Q: สามารถใช้ gradient แทนสีทึบได้หรือไม่?**  
A: ได้ – ตั้งค่า `FillType.Gradient` แล้วกำหนดจุดหยุดของ gradient ผ่าน `getGradientStyle()`  

**Q: แผนภูมิสามารถมีรายการ legend ได้กี่รายการ?**  
A: แผนภูมิสามารถมีรายการ legend ได้สูงสุด 256 รายการ ขึ้นอยู่กับจำนวนชุดข้อมูลที่คุณเพิ่ม

## แหล่งข้อมูล
- **เอกสาร:** คู่มือครบวงจรการใช้คุณสมบัติ Aspose.Slides ([Link](https://reference.aspose.com/slides/java/))  
- **ดาวน์โหลด:** รับเวอร์ชันล่าสุดของ Aspose.Slides for Java ([Link](https://releases.aspose.com/slides/java/))  
- **ซื้อ:** ซื้อไลเซนส์เพื่อเปิดใช้งานฟีเจอร์ทั้งหมด ([Link](https://purchase.aspose.com/buy))  
- **ทดลองใช้ฟรี & ลิขสิทธิ์ชั่วคราว:** เริ่มต้นด้วยการทดลองใช้ฟรีและขอรับลิขสิทธิ์ชั่วคราว ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/))  
- **สนับสนุน:** รับความช่วยเหลือจากชุมชนในฟอรั่มของ Aspose ([Link](https://forum.aspose.com/c/slides/11))

---

**อัปเดตล่าสุด:** 2026-08-06  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Enhancing PowerPoint Charts: Font & Axis Customization with Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: Dynamic Text Frames & Font Customization Guide](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}