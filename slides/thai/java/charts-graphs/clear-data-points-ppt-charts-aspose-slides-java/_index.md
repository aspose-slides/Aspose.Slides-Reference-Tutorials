---
date: '2026-08-27'
description: เรียนรู้วิธีลบ chart data points ใน PowerPoint ด้วย Aspose.Slides for
  Java. คู่มือ step‑by‑step นี้แสดงวิธีลบ chart values อย่าง programmatically, best
  practices, และ efficient series handling.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: เรียนรู้วิธีลบ chart data points ใน PowerPoint ด้วย Aspose.Slides
  for Java. ปฏิบัติตามคำแนะนำ step‑by‑step เพื่อรีเซ็ต charts อย่าง programmatically
  อย่างมีประสิทธิภาพ.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: วิธีลบ chart data points ใน PowerPoint ด้วย Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'วิธีลบ data points ในแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java: คู่มือฉบับสมบูรณ์'
url: /th/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีลบจุดข้อมูลในแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java

## บทนำ

ในหลาย ๆ กระบวนการรายงานคุณอาจต้อง **รีเซ็ตแผนภูมิ** โดยไม่ต้องสร้างเลย์เอาต์ใหม่ ไม่ว่าคุณจะรีเฟรชแดชบอร์ด, แจกจ่ายเทมเพลต, หรือทำอัตโนมัติรายงานประจำคืน การรู้ **วิธีลบจุดข้อมูลของแผนภูมิ** จะช่วยประหยัดเวลาและลดข้อผิดพลาดได้อย่างมาก บทแนะนำนี้จะแสดงวิธีใช้ **Aspose.Slides for Java** เพื่อลบจุดข้อมูลเฉพาะหรือทั้งซีรีส์โดยอัตโนมัติ พร้อมคงสไตล์การแสดงผลไว้เหมือนเดิม

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีที่ Aspose.Slides ช่วยให้คุณจัดการแผนภูมิ PowerPoint จาก Java  
- คำแนะนำขั้นตอนต่อขั้นตอนสำหรับการลบจุดข้อมูลในซีรีส์ของแผนภูมิ  
- เคล็ดลับปฏิบัติที่ดีที่สุดสำหรับประสิทธิภาพและการใช้ไลเซนส์

## คำตอบสั้น ๆ
- **ต้องใช้ไลบรารีอะไร?** Aspose.Slides for Java (v25.4+)  
- **เมธอดใดที่ลบจุดข้อมูลจริง ๆ?** การตั้งค่าเซลล์ X และ Y ให้เป็น `null`  
- **ต้องมีไลเซนส์สำหรับการใช้งานในโปรดักชันหรือไม่?** ใช่ – ไลเซนส์เชิงพาณิชย์จะลบข้อจำกัดของรุ่นทดลองออก  
- **รองรับ Java 16 หรือไม่?** รองรับอย่างเต็มที่; ไลบรารีทำงานกับ JDK 16 และใหม่กว่า  
- **สามารถลบเฉพาะซีรีส์เดียวได้หรือไม่?** ได้ – เพียงวนลูปซีรีส์ที่ต้องการลบ

## Aspose.Slides for Java คืออะไร?

Aspose.Slides for Java เป็น API ครบวงจรที่ช่วยสร้าง, แก้ไข, และแปลงไฟล์ PowerPoint โดยไม่ต้องใช้ Microsoft Office รองรับประเภทแผนภูมิมากกว่า 70 แบบ, ฟอร์แมตไฟล์กว่า 150+, และสามารถประมวลผลงานนำเสนอขนาดสูงสุด 500 MB โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ

## ทำไมต้องลบจุดข้อมูลของแผนภูมิ?

การลบจุดข้อมูลของแผนภูมิช่วยให้คุณคงเลย์เอาต์เดิมของแผนภูมิ—เช่น สี, คำอธิบาย, การตั้งค่าแกน, และมาร์คเกอร์—ในขณะที่เปลี่ยนค่าตัวเลขพื้นฐาน วิธีนี้เป็นประโยชน์เมื่อคุณต้องรีเฟรชแผนภูมิด้วยข้อมูลใหม่, ให้เทมเพลตที่มีช่องว่างสำหรับผู้ใช้กรอก, หรือสร้างแดชบอร์ดแบบไดนามิกที่เปลี่ยนบ่อยโดยไม่ต้องสร้างการออกแบบใหม่

- รีเฟรชแผนภูมิด้วยชุดข้อมูลใหม่โดยคงสี, คำอธิบาย, และการตั้งค่าแกนไว้  
- แจกจ่ายเทมเพลตที่มีแผนภูมิเปล่าสำหรับผู้ใช้กรอกข้อมูล  
- สร้างแดชบอร์ดไดนามิกที่ข้อมูลเปลี่ยนบ่อย

## วิธีลบจุดข้อมูลของแผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java

โหลดงานนำเสนอ, ค้นหาแผนภูมิ, แล้วตั้งค่าเซลล์ X และ Y ของแต่ละจุดข้อมูลเป็น `null` การดำเนินการนี้จะลบค่าตัวเลขแต่คงซีรีส์, มาร์คเกอร์, และการจัดรูปแบบไว้ ไม่ต้องแก้ไขโครงสร้างแผนภูมิทั้งหมด กระบวนการทั้งหมดมักใช้เวลาน้อยกว่าสองวินาทีสำหรับไฟล์ PPTX ขนาดมาตรฐาน 10 สไลด์

### คำตอบโดยตรง
เพื่อทำการลบจุดข้อมูลของแผนภูมิ ให้เปิดไฟล์ PPTX ด้วย `new Presentation("input.pptx")`, ดึงอ็อบเจกต์ `IChart` ที่ต้องการ, วนลูปผ่าน `IChartSeries` ที่ต้องการ, แล้วเรียก `dataPoint.getXValue().setValue(null)` และ `dataPoint.getYValue().setValue(null)` สำหรับแต่ละจุด สุดท้ายบันทึกงานนำเสนอด้วย `pres.save("output.pptx", SaveFormat.Pptx)` วิธีนี้จะลบข้อมูลโดยอัตโนมัติพร้อมคงการออกแบบของแผนภูมิไว้

### คำอธิบายสั้น ๆ
- `Presentation` คืออ็อบเจกต์ระดับบนของ Aspose.Slides ที่แทนไฟล์ PowerPoint ในหน่วยความจำ  
- `IChart` เป็นอินเทอร์เฟซที่ให้เข้าถึงซีรีส์, แกน, และการจัดรูปแบบของแผนภูมิ  
- `IChartSeries` แทนซีรีส์เดียวในแผนภูมิและมีคอลเลกชันของอ็อบเจกต์ `IDataPoint`  
- `IDataPoint` เก็บค่าตัวเลข X และ Y ของจุดบนแผนภูมิแต่ละจุด

### การดำเนินการแบบขั้นตอน

1. **โหลดงานนำเสนอ** – สร้างอินสแตนซ์ `Presentation` ชี้ไปยังไฟล์ต้นทางของคุณ  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **เข้าถึงสไลด์และแผนภูมิ** – ดึงสไลด์ (โดยทั่วไปที่ตำแหน่ง index 0) แล้วแคสต์รูปร่างแรกเป็น `IChart`  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **วนลูปผ่านซีรีส์เป้าหมาย** – เลือกซีรีส์ที่ต้องการลบ (เช่น `chart.getChartData().getSeries().get_Item(0)`) แล้ววนลูปจุดข้อมูลของมัน เพื่อตั้งค่าเซลล์ X และ Y ให้เป็น `null`  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **บันทึกงานนำเสนอที่แก้ไข** – เขียนการเปลี่ยนแปลงลงไฟล์ใหม่หรือทับไฟล์เดิม  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## การตั้งค่า Aspose.Slides for Java

### การติดตั้งผ่าน Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### การติดตั้งผ่าน Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### ดาวน์โหลดโดยตรง

หรือดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

### การขอรับไลเซนส์

เพื่อใช้ Aspose.Slides นอกขอบเขตการทดลอง:
- รับไลเซนส์ **ทดลองฟรี**  
- ขอไลเซนส์ **ชั่วคราว** สำหรับการประเมินผล  
- ซื้อไลเซนส์ **เชิงพาณิชย์** สำหรับการใช้งานในโปรดักชัน

#### การเริ่มต้นพื้นฐานและการตั้งค่า

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## การประยุกต์ใช้งานจริง

การลบจุดข้อมูลของแผนภูมิมีประโยชน์ในหลายสถานการณ์จริง:

1. **กระบวนการรีเฟรชข้อมูล** – แทนที่ตัวเลขเก่าโดยข้อมูลใหม่โดยไม่ต้องสร้างเลย์เอาต์แผนภูมิใหม่  
2. **การแจกจ่ายเทมเพลต** – ให้เทมเพลต PowerPoint ที่มีแผนภูมิเปล่าสำหรับผู้ใช้กรอกข้อมูล  
3. **แดชบอร์ดไดนามิก** – สร้างงานนำเสนอประจำคืนที่ดึงข้อมูลจาก API และลบค่าที่เก่าออกก่อน  
4. **งานอัตโนมัติการรายงาน** – ผสานตรรกะการลบเข้ากับ pipeline CI/CD เพื่อสร้างรายงานอัตโนมัติ

## ข้อควรพิจารณาด้านประสิทธิภาพ

- **ปล่อยอ็อบเจกต์**: เรียก `pres.dispose()` หลังบันทึกเพื่อปลดปล่อยทรัพยากรเนทีฟ  
- **การประมวลผลเป็นชุด**: ใช้ `License` ตัวเดียวหลายไฟล์เพื่อลดภาระการโหลดซ้ำ  
- **การปรับจูน JVM**: เพิ่มขนาด heap (`-Xmx2g` หรือมากกว่า) เมื่อจัดการงานนำเสนอใหญ่กว่า 200 MB  
- **โหมดประหยัดหน่วยความจำ**: Aspose.Slides สามารถสตรีมไฟล์ PPTX ขนาดใหญ่ ทำให้ประมวลผลได้ถึง 10 000 สไลด์โดยไม่ต้องโหลดทั้งหมดเข้าสู่หน่วยความจำ

## คำถามที่พบบ่อย

**ถาม: ต้องใช้ไลเซนส์สำหรับการสร้างในขั้นพัฒนาไหม?**  
ตอบ: ไลเซนส์ทดลองฟรีเพียงพอสำหรับการพัฒนาและทดสอบ ส่วนไลเซนส์เชิงพาณิชย์จำเป็นสำหรับการใช้งานในโปรดักชัน

**ถาม: Aspose.Slides for Java รองรับฟีเจอร์ของ PowerPoint 2016/2019 หรือไม่?**  
ตอบ: รองรับเต็มที่; ไลบรารีสนับสนุนฟีเจอร์ PPTX สมัยใหม่ รวมถึงแผนภูมิขั้นสูงและ SmartArt

**ถาม: สามารถลบจุดข้อมูลในแผนภูมิที่ใช้แกนรองได้หรือไม่?**  
ตอบ: ได้ – เพียงอ้างอิงซีรีส์ที่อยู่บนแกนรองแล้วตั้งค่าจุดข้อมูลเป็น `null` ตามที่อธิบายข้างต้น

**ถาม: สามารถลบเฉพาะค่า Y ได้โดยคงค่า X ไว้หรือไม่?**  
ตอบ: ทำได้โดยเรียก `dataPoint.getYValue().setValue(null)` และไม่ต้องแก้ไขเซลล์ X

**ถาม: จะทำอัตโนมัติสำหรับหลายไฟล์ PPTX อย่างไร?**  
ตอบ: ห่อโค้ดลบไว้ในลูปที่วนผ่านไดเรกทอรีของไฟล์ PPTX แล้วใช้ตรรกะเดียวกันกับแต่ละไฟล์

## แหล่งข้อมูล

- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/slides/java/)
- [Temporary License Application](https://purchase.aspose.com/temporary-license/)
- [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

ด้วยแหล่งข้อมูลเหล่านี้คุณพร้อมที่จะเริ่มลบจุดข้อมูลของแผนภูมิในแอปพลิเคชัน Java ของคุณแล้ว ขอให้เขียนโค้ดอย่างสนุกสนาน!

---

**อัปเดตล่าสุด:** 2026-08-27  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Clear Specific Chart Series Data Points Data in Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}