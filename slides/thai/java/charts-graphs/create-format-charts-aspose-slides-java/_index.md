---
date: '2026-03-07'
description: เรียนรู้วิธีสร้างแผนภูมิเส้นใน Java ด้วย Aspose.Slides, เพิ่มชื่อแผนภูมิ,
  เพิ่มเส้นกริด, จัดรูปแบบป้ายชื่อแผนภูมิ และบันทึกงานนำเสนอระดับมืออาชีพ
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: วิธีสร้างแผนภูมิเส้นด้วย Aspose.Slides ใน Java – คู่มือฉบับสมบูรณ์
url: /th/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิเส้นด้วย Aspose.Slides ใน Java

## วิธีสร้างแผนภูมิเส้นใน Java ด้วย Aspose.Slides

### บทนำ
การสร้างงานนำเสนอที่ดูสวยงามเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ ไม่ว่าคุณจะเป็นผู้เชี่ยวชาญด้านธุรกิจหรือผู้สอน คุณมักต้อง **สร้างแผนภูมิเส้น** ที่ให้ข้อมูลครบถ้วนและสวยงาม ในบทแนะนำนี้เราจะพาคุณผ่านการใช้ **Aspose.Slides for Java** เพื่อสร้างแผนภูมิเส้น เพิ่มชื่อแผนภูมิ เพิ่มเส้นกริด ปรับรูปแบบป้ายแผนภูมิ และบันทึกผลลัพธ์เป็นไฟล์ PowerPoint

#### คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ดีที่สุดสำหรับสร้างแผนภูมิใน Java คืออะไร?** Aspose.Slides for Java  
- **ประเภทแผนภูมิที่คู่มือนี้เน้นคืออะไร?** แผนภูมิเส้นพร้อมเครื่องหมาย  
- **ต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** ลิขสิทธิ์ชั่วคราวฟรีใช้ได้สำหรับการประเมินผล  
- **ใช้ IDE ใดได้บ้าง?** IDE ใดก็ได้ที่รองรับ Java เช่น IntelliJ IDEA, Eclipse หรือ NetBeans  
- **องค์ประกอบของแผนภูมิถูกจัดรูปแบบอย่างไร?** ด้วยการเรียก API แบบ fluent สำหรับชื่อ, แกน, เส้นกริด, คำอธิบาย, และพื้นหลัง  

### แผนภูมิเส้นคืออะไรและทำไมต้องใช้ Aspose.Slides?
แผนภูมิเส้นแสดงจุดข้อมูลที่เชื่อมต่อด้วยเส้นตรง ทำให้เหมาะสำหรับการแสดงแนวโน้มตามเวลา Aspose.Slides ช่วยให้คุณสร้างและปรับแต่งแผนภูมิเหล่านี้โดยโปรแกรมเมติก ลดความจำเป็นในการแก้ไข PowerPoint ด้วยตนเอง  

### ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8+** ติดตั้งแล้ว  
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans ฯลฯ)  
- **Aspose.Slides for Java** ไลบรารี (เพิ่มผ่าน Maven หรือ Gradle)  

#### ไลบรารีและการพึ่งพาที่จำเป็น
**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หรือดาวน์โหลด JAR ล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)  

#### การรับลิขสิทธิ์
- รับ [ลิขสิทธิ์ทดลองฟรี](https://purchase.aspose.com/temporary-license/) เพื่อทดสอบ  
- ซื้อลิขสิทธิ์เต็มจาก [เว็บไซต์อย่างเป็นทางการของ Aspose](https://purchase.aspose.com/buy) สำหรับการใช้งานในผลิตภัณฑ์  

### การตั้งค่า Aspose.Slides for Java
1. **เพิ่มการพึ่งพา** ตามที่แสดงด้านบนในโปรเจกต์ของคุณ  
2. **ใช้ลิขสิทธิ์** (หากมี) ก่อนสร้างอ็อบเจ็กต์ Presentation ใด ๆ  

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## การดำเนินการแบบขั้นตอน

### ขั้นตอนที่ 1: สร้างโฟลเดอร์ผลลัพธ์ (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*ทำไมขั้นตอนนี้สำคัญ:* การตรวจสอบให้โฟลเดอร์มีอยู่จะป้องกัน `FileNotFoundException` เมื่อบันทึกงานนำเสนอภายหลัง  

### ขั้นตอนที่ 2: เพิ่มสไลด์และแทรกแผนภูมิเส้น
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*คำอธิบาย:* โค้ดนี้สร้างสไลด์ใหม่และวาง **แผนภูมิเส้นพร้อมเครื่องหมาย** ที่ตำแหน่งที่กำหนด  

### ขั้นตอนที่ 3: เพิ่มชื่อแผนภูมิ (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*เคล็ดลับ:* ใช้ชื่อที่หนาและสีเทาจะทำให้แผนภูมิดูชัดเจนทันที  

### ขั้นตอนที่ 4: ปรับรูปแบบแกนและเพิ่มเส้นกริด (add grid lines)
#### การจัดรูปแบบแกนแนวตั้ง
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### การจัดรูปแบบแกนแนวนอน
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*ทำไมขั้นตอนนี้สำคัญ:* เส้นกริดที่ชัดเจนและป้ายที่หมุนจะช่วยให้อ่านข้อมูลได้ง่ายขึ้น โดยเฉพาะเมื่อจุดข้อมูลหนาแน่น  

### ขั้นตอนที่ 5: ปรับแต่งคำอธิบาย (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### ขั้นตอนที่ 6: ตั้งค่าสีพื้นหลัง (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### ขั้นตอนที่ 7: บันทึกงานนำเสนอ
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*ผลลัพธ์:* ตอนนี้คุณมีไฟล์ PowerPoint (`FormattedChart_out.pptx`) ที่มีแผนภูมิเส้นที่จัดรูปแบบครบถ้วน  

## การนำไปใช้ในเชิงปฏิบัติ
- **รายงานธุรกิจ:** แสดงผลการดำเนินงานไตรมาสด้วยเส้นแนวโน้ม  
- **สไลด์การศึกษา:** ทำภาพข้อมูลวิทยาศาสตร์สำหรับการบรรยาย  
- **ข้อเสนอโปรเจกต์:** เน้นจุดสำคัญและการคาดการณ์  
- **การวิเคราะห์การตลาด:** นำเสนอแนวโน้ม ROI ของแคมเปญ  
- **การรวมกับแดชบอร์ด:** ส่งออกข้อมูลสดเป็น PowerPoint สำหรับการประชุมผู้มีส่วนได้ส่วนเสีย  

## พิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ:** ควรเรียก `dispose()` บนอ็อบเจ็กต์ `Presentation` เสมอเพื่อปล่อยทรัพยากรเนทีฟโดยเร็ว  

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **ลิขสิทธิ์ไม่ได้ใช้** | โหลดลิขสิทธิ์ทดลองหรือเต็มก่อนสร้างอ็อบเจ็กต์ `Presentation` ใด ๆ |
| **แผนภูมิเกิดเป็นค่าว่าง** | ตรวจสอบว่ามีชุดข้อมูลในสไลด์หรือไม่; เพิ่ม series หากจำเป็น |
| **ไฟล์ไม่ถูกบันทึก** | ยืนยันว่าโฟลเดอร์ผลลัพธ์มีอยู่ (ใช้ขั้นตอน “create directory java”) |
| **สีไม่ถูกนำไปใช้** | ใช้ค่าคงที่ `Color` จาก `java.awt.Color` หรือ `PresetColor` |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถสร้างประเภทแผนภูมิอื่น ๆ นอกจากแผนภูมิเส้นได้หรือไม่?**  
ตอบ: ได้, Aspose.Slides รองรับแผนภูมิแท่ง, พาย, กระจาย และหลายประเภทอื่น ๆ  

**ถาม: วิธีเพิ่มชุดข้อมูลหลายชุดในแผนภูมิเส้นคืออะไร?**  
ตอบ: ใช้ `chart.getChartData().getSeries().add(...)` เพื่อแทรก series เพิ่มเติมก่อนทำการจัดรูปแบบ  

**ถาม: สามารถส่งออกแผนภูมิเป็นรูปภาพได้หรือไม่?**  
ตอบ: แน่นอน. เรียก `chart.getChartData().getChartDataWorkbook().save(...)` หรือเรนเดอร์สไลด์เป็นรูปแบบภาพ  

**ถาม: ต้องมีลิขสิทธิ์แบบชำระเงินสำหรับการพัฒนาหรือไม่?**  
ตอบ: ลิขสิทธิ์ชั่วคราวฟรีใช้ได้สำหรับการประเมินผล; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  

**ถาม: รองรับเวอร์ชัน Java ใดบ้าง?**  
ตอบ: ไลบรารีทำงานกับ JDK 8 ถึง JDK 22 (ใช้ classifier ที่เหมาะสม, เช่น `jdk16`)  

---

**อัปเดตล่าสุด:** 2026-03-07  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (classifier jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}