---
date: '2026-02-06'
description: เรียนรู้บทแนะนำการสร้างแผนภูมิ Aspose Slides เพื่อเพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอ
  Java ทำให้กระบวนการทำงานของคุณเป็นระเบียบด้วยตัวอย่างโค้ดทีละขั้นตอน.
keywords:
- Aspose.Slides for Java
- adding charts to presentations with Java
- configuring data labels in Aspose.Slides
title: 'บทเรียนแผนภูมิ Aspose Slides: เพิ่มแผนภูมิด้วย Java'
url: /th/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# บทแนะนำ Aspose Slides Chart: การเพิ่มและกำหนดค่าชาร์ตในงานนำเสนอโดยใช้ Java

## บทนำ
การสร้างงานนำเสนอที่มีความเคลื่อนไหวเป็นสิ่งสำคัญในหลายสถานการณ์ระดับมืออาชีพ ไม่ว่าจะเป็นการนำเสนอธุรกิจหรือการบรรยายทางวิชาการ การแทรกชาร์ตด้วยมืออาจทำให้เสียเวลาและเกิดข้อผิดพลาดได้ **ในบทแนะนำ Aspose Slides chart นี้คุณจะได้เรียนรู้วิธีอัตโนมัติการเพิ่มและกำหนดค่าชาร์ต** ในไฟล์งานนำเสนอของคุณโดยใช้ Aspose.Slides for Java ซึ่งจะช่วยประหยัดเวลาและลดความผิดพลาด

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides for Java
- การโหลดและเตรียมงานนำเสนอสำหรับการแก้ไข
- การเพิ่ม Bubble Chart ลงในสไลด์ของคุณ
- การกำหนดค่าป้ายข้อมูลโดยอ้างอิงเซลล์
- การบันทึกงานนำเสนอที่แก้ไขแล้ว

มาดูกันว่าคุณจะทำให้กระบวนการนี้เป็นอัตโนมัติได้อย่างไรโดยการผสาน Aspose.Slides เข้ากับแอปพลิเคชัน Java ของคุณ

### คำตอบสั้น
- **บทแนะนำนี้ครอบคลุมอะไร?** การเพิ่มและกำหนดค่า Bubble Chart พร้อมป้ายข้อมูลในงานนำเสนอ Java  
- **ใช้เวอร์ชันไลบรารีใด?** Aspose.Slides for Java 25.4 (เข้ากันได้กับ JDK 16)  
- **ต้องใช้ไลเซนส์หรือไม่?** สามารถใช้รุ่นทดลองฟรีเพื่อทดสอบ; ต้องมีไลเซนส์ถาวรสำหรับการใช้งานจริง  
- **สามารถแก้ไขชาร์ตที่มีอยู่ได้หรือไม่?** ได้ – คุณสามารถโหลดไฟล์ PPTX ใดก็ได้และอัปเดตข้อมูลชาร์ตโดยโปรแกรม  
- **IDE ที่แนะนำ?** IDE Java ใดก็ได้ (IntelliJ IDEA, Eclipse, VS Code) ที่รองรับ Maven หรือ Gradle

## Aspose Slides chart tutorial คืออะไร?
บทแนะนำ Aspose Slides chart แสดงวิธีการสร้าง ปรับแต่ง และบันทึกอ็อบเจกต์ชาร์ตภายในไฟล์ PowerPoint ด้วยโค้ด โปรแกรมเมอร์จะได้ควบคุมประเภทชาร์ต แหล่งข้อมูล และสไตล์การแสดงผลโดยไม่ต้องเปิด PowerPoint ด้วยตนเอง

## ทำไมต้องใช้ Aspose Slides chart tutorial?
- **Automation:** สร้างชาร์ตแบบอัตโนมัติจากฐานข้อมูลหรือ API  
- **Consistency:** ทำให้ทุกงานนำเสนอเป็นไปตามแบรนด์และกฎการจัดรูปแบบเดียวกัน  
- **Cross‑platform:** ทำงานบน Windows, Linux, และ macOS ด้วยโค้ด Java เดียวกัน  
- **No Office dependency:** ไม่ต้องติดตั้ง Microsoft PowerPoint บนเซิร์ฟเวอร์

## ข้อกำหนดเบื้องต้น
- **ไลบรารีและ Dependencies:** Aspose.Slides for Java (เวอร์ชัน 25.4)  
- **เครื่องมือสร้าง:** Maven หรือ Gradle (ตามที่คุณถนัด)  
- **ความรู้พื้นฐาน:** ความคุ้นเคยกับไวยากรณ์ Java และโครงสร้างไฟล์ PPTX

## การตั้งค่า Aspose.Slides for Java

### คำแนะนำการติดตั้ง
เพื่อผสาน Aspose.Slides เข้ากับโปรเจกต์ของคุณ สามารถใช้ Maven หรือ Gradle ตามขั้นตอนต่อไปนี้:

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

หากต้องการดาวน์โหลดโดยตรง ให้เยี่ยมชมหน้า [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

### การรับไลเซนส์
- **Free Trial:** เริ่มต้นด้วยรุ่นทดลองฟรีเพื่อสำรวจฟีเจอร์  
- **Temporary License:** ขอรับไลเซนส์ชั่วคราวหากต้องการเวลามากขึ้นโดยไม่มีข้อจำกัด  
- **Purchase:** พิจารณาซื้อไลเซนส์เต็มรูปแบบสำหรับการใช้งานเชิงพาณิชย์  

เมื่อตั้งค่าเสร็จ การเริ่มต้นใช้งาน Aspose.Slides จะง่ายดาย คุณสามารถโหลดไฟล์งานนำเสนอและเตรียมพร้อมสำหรับการแก้ไขได้ทันที

## คู่มือการทำงาน

### ฟีเจอร์ 1: การตั้งค่างานนำเสนอ

#### ภาพรวม
ฟีเจอร์นี้เกี่ยวกับการโหลดไฟล์งานนำเสนอที่มีอยู่เพื่อเตรียมพร้อมสำหรับการแก้ไขต่อไปด้วย Aspose.Slides

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

- **ทำไม:** การโหลดไฟล์งานนำเสนอเป็นขั้นตอนสำคัญที่ทำให้คุณเข้าถึงและแก้ไขเนื้อหาได้

### ฟีเจอร์ 2: การเพิ่มชาร์ตลงสไลด์

#### ภาพรวม
ฟีเจอร์นี้สาธิตการเพิ่ม Bubble Chart ลงในสไลด์แรกของงานนำเสนอของคุณ ชาร์ตเป็นเครื่องมือสำคัญสำหรับการแสดงข้อมูลเชิงภาพ

**ขั้นตอนการทำงาน**

##### ขั้นตอนที่ 1: เริ่มต้น Presentation และเพิ่มชาร์ต
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

- **ทำไม:** การเพิ่มชาร์ตช่วยเพิ่มความน่าสนใจและการสื่อสารข้อมูลของงานนำเสนอ

### ฟีเจอร์ 3: การกำหนดค่าป้ายข้อมูลสำหรับ Series

#### ภาพรวม
ฟีเจอร์นี้ช่วยให้คุณตั้งค่าป้ายข้อมูลบนซีรีส์ของชาร์ตโดยอ้างอิงเซลล์ เพื่อเพิ่มความชัดเจนและรายละเอียดในการแสดงข้อมูล

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

- **ทำไม:** การกำหนดค่าป้ายข้อมูลเป็นสิ่งจำเป็นเพื่อให้ข้อมูลเชิงลึกปรากฏโดยตรงบนชาร์ตของคุณ

### ฟีเจอร์ 4: การบันทึกงานนำเสนอ

#### ภาพรวม
ฟีเจอร์นี้สาธิตวิธีบันทึกงานนำเสนอที่แก้ไขแล้วกลับไปยังไฟล์

**ขั้นตอนการทำงาน**

##### ขั้นตอนที่ 1: บันทึกงานของคุณ
```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

- **ทำไม:** การบันทึกงานนำเสนอทำให้การแก้ไขทั้งหมดของคุณถูกเก็บไว้สำหรับการใช้งานในอนาคต

## การประยุกต์ใช้งานจริง
1. **Business Reports:** สร้างและอัปเดตชาร์ตในรายงานไตรมาสโดยอัตโนมัติ  
2. **Academic Presentations:** เสริมการบรรยายด้วยการแสดงข้อมูลแบบเรียลไทม์  
3. **Sales Pitches:** สร้างงานนำเสนอไดนามิกที่แสดงแนวโน้มและการคาดการณ์การขาย  
4. **Project Management:** แสดงไทม์ไลน์โครงการและการจัดสรรทรัพยากรเป็นภาพ  
5. **Marketing Analytics:** ผสานชาร์ต Aspose.Slides เข้ากับแดชบอร์ดเพื่อการติดตามประสิทธิภาพแคมเปญ

## พิจารณาด้านประสิทธิภาพ
- ใช้โครงสร้างข้อมูลที่มีประสิทธิภาพเพื่อจัดการชุดข้อมูลขนาดใหญ่ในชาร์ต  
- จัดการหน่วยความจำโดยการทำลายอ็อบเจกต์อย่างถูกต้องด้วยบล็อก `try‑finally`  
- ปรับเทคนิคการจัดการหน่วยความจำของ Java เมื่อทำงานกับงานนำเสนอขนาดใหญ่

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Cause | Fix |
|-------|-------|-----|
| **OutOfMemoryError** | Very large PPTX or chart data | Process data in smaller batches; call `System.gc()` after disposing objects. |
| **Chart not displaying data** | Data labels not linked correctly | Verify cell references (`A10`, `A11`, `A12`) match actual workbook cells. |
| **License not applied** | Missing or incorrect license file | Load the license before creating `Presentation` objects (`License license = new License(); license.setLicense("Aspose.Slides.lic");`). |

## คำถามที่พบบ่อย

**Q: Aspose.Slides for Java คืออะไร?**  
A: ไลบรารีที่ทรงพลังสำหรับการสร้าง แก้ไข และแปลงไฟล์ PowerPoint ในแอปพลิเคชัน Java

**Q: สามารถใช้ Aspose.Slides ได้โดยไม่ซื้อไลเซนส์หรือไม่?**  
A: ใช่ คุณสามารถเริ่มต้นด้วยรุ่นทดลองฟรีเพื่อทดสอบความสามารถ

**Q: วิธีเพิ่มประเภทชาร์ตอื่น ๆ?**  
A: ใช้ enumeration `ChartType` (เช่น `ChartType.Pie`, `ChartType.Column`) เมื่อต้องการเรียก `addChart`

**Q: สามารถแก้ไขชาร์ตที่มีอยู่ในงานนำเสนอได้หรือไม่?**  
A: แน่นอน! โหลดไฟล์ PPTX, ดึงชาร์ตผ่าน `slide.getShapes().get_Item(index)` แล้วปรับคุณสมบัติต่าง ๆ

**Q: ปัญหาประสิทธิภาพที่พบบ่อยคืออะไร?**  
A: งานนำเสนอขนาดใหญ่ใช้หน่วยความจำมาก; ควรทำลายอ็อบเจกต์ `Presentation` และใช้ workbook ของชาร์ตซ้ำเมื่อเป็นไปได้

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

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose