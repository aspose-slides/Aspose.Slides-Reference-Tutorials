---
date: '2026-03-15'
description: เรียนรู้วิธีสร้างแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java, สร้างแผนภูมิคอลัมน์แบบกลุ่มแบบไดนามิก,
  และคำนวณสูตรแผนภูมิในงานนำเสนออัตโนมัติ
keywords:
- Aspose.Slides Java
- dynamic PowerPoint charts
- PowerPoint presentation automation
title: วิธีสร้างแผนภูมิ PowerPoint ด้วย Aspose.Slides สำหรับ Java
url: /th/java/charts-graphs/aspose-slides-java-add-charts-formulas/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เชี่ยวชาญ Aspose.Slides Java: เพิ่มแผนภูมิและสูตรในงานนำเสนอ PowerPoint

## บทนำ

การสร้างงานนำเสนอ PowerPoint ที่น่าสนใจเป็นสิ่งสำคัญเมื่อสื่อสารข้อมูลที่ซับซ้อนอย่างมีประสิทธิภาพ. ด้วย Aspose.Slides for Java คุณสามารถ **สร้าง PowerPoint chart** ด้วยโปรแกรมอัตโนมัติ, ทำให้การสร้างแผนภูมิ PowerPoint แบบไดนามิกเป็นอัตโนมัติ, และฝังสูตรแผนภูมิที่คำนวณแล้ว—ทั้งหมดโดยไม่ต้องเปิด UI ใด ๆ. บทเรียนนี้จะพาคุณผ่านการตั้งค่าไลบรารี, การแทรกแผนภูมิคอลัมน์แบบกลุ่ม, การใช้สูตร, และการบันทึกไฟล์ขั้นสุดท้าย.

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า Aspose.Slides for Java
- การสร้างงานนำเสนอ PowerPoint และแทรกแผนภูมิ
- การเข้าถึงและแก้ไขข้อมูลแผนภูมิด้วยสูตร
- การคำนวณสูตรแผนภูมิและบันทึกงานนำเสนอของคุณ

มาเริ่มต้นด้วยการตรวจสอบข้อกำหนดเบื้องต้นกัน!

## คำตอบอย่างรวดเร็ว
- **What is the primary goal?** สร้าง PowerPoint chart โดยอัตโนมัติด้วย Aspose.Slides for Java.  
- **Which chart type is demonstrated?** แผนภูมิคอลัมน์แบบกลุ่ม (clustered column chart).  
- **Can formulas be calculated?** ใช่—ใช้ `calculateFormulas()` เพื่อประเมินแผนภูมิ PowerPoint แบบไดนามิก.  
- **What build tool is recommended?** Maven (หรือ Gradle) สำหรับการรวม Aspose Slides.  
- **Do I need a license?** ทดลองใช้ฟรีสามารถใช้งานได้สำหรับการทดสอบ; ไลเซนส์เต็มจะลบข้อจำกัดการประเมิน.

## “add chart to PowerPoint” กับ Aspose.Slides คืออะไร?
Aspose.Slides for Java มี API ที่ครอบคลุมซึ่งทำให้นักพัฒนาสามารถสร้าง, แก้ไข, และบันทึกไฟล์ PowerPoint ด้วยโปรแกรมได้. ด้วยความสามารถ **add chart to PowerPoint** คุณสามารถสร้างการแสดงผลข้อมูลแบบภาพได้ทันที, เหมาะสำหรับรายงาน, แดชบอร์ด, หรือชุดสไลด์อัตโนมัติ.

## ทำไมต้องใช้แผนภูมิคอลัมน์แบบกลุ่ม?
แผนภูมิคอลัมน์แบบกลุ่มช่วยให้คุณเปรียบเทียบหลายชุดข้อมูลเคียงข้างกัน, ทำให้แนวโน้มและความแตกต่างปรากฏชัดเจนทันที. เป็นตัวเลือกทั่วไปสำหรับรายงานการเงิน, แดชบอร์ดการขาย, และเมตริกประสิทธิภาพ—สถานการณ์ที่แผนภูมิ PowerPoint แบบไดนามิกทำให้เด่นชัด.

## วิธีสร้าง PowerPoint chart ด้วย Aspose.Slides for Java

### ข้อกำหนดเบื้องต้น

ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- **Aspose.Slides for Java Library**: ต้องใช้เวอร์ชัน 25.4 หรือใหม่กว่า.  
- **Java Development Kit (JDK)**: ต้องติดตั้ง JDK 16 หรือสูงกว่าและกำหนดค่าในระบบของคุณ.  
- **Development Environment**: แนะนำให้ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse แต่ไม่จำเป็น.

ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรม Java เช่น คลาส, เมธอด, และการจัดการข้อยกเว้นเป็นสิ่งจำเป็น. หากคุณใหม่กับหัวข้อเหล่านี้, ควรศึกษา tutorial เบื้องต้นก่อน.

### การตั้งค่า Aspose.Slides for Java

#### การเพิ่ม Dependency ด้วย Maven (maven for aspose slides)
เพื่อรวม Aspose.Slides ในโปรเจกต์ของคุณโดยใช้ Maven, เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### การเพิ่ม Dependency ด้วย Gradle
หากคุณใช้ Gradle, ให้ใส่ส่วนนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลด Aspose.Slides for Java เวอร์ชันล่าสุดจาก [Aspose Releases](https://releases.aspose.com/slides/java/).

#### การรับไลเซนส์
- **Free Trial**: เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจความสามารถ.  
- **Temporary License**: รับไลเซนส์ชั่วคราวสำหรับการทดสอบต่อเนื่อง [here](https://purchase.aspose.com/temporary-license/).  
- **Purchase**: พิจารณาซื้อไลเซนส์เต็มหากคุณพบว่าเครื่องมือนี้มีคุณค่า.

### การเริ่มต้นพื้นฐาน

หลังจากตั้งค่าแล้ว, เริ่มต้นสภาพแวดล้อม Aspose.Slides ของคุณ:

```java
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## คู่มือการดำเนินการ

ส่วนนี้แบ่งเป็นขั้นตอนเพื่อช่วยให้คุณเข้าใจแต่ละส่วนอย่างชัดเจน.

### ขั้นตอนที่ 1: เริ่มต้น Presentation
เริ่มต้นด้วยการสร้างอ็อบเจ็กต์ `Presentation` ใหม่:

```java
Presentation presentation = new Presentation();
```

### ขั้นตอนที่ 2: เข้าถึงสไลด์แรก
ดึงสไลด์แรกที่คุณจะวางแผนภูมิของคุณ:

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

### ขั้นตอนที่ 3: เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม
เพิ่มแผนภูมิลงในสไลด์ที่ตำแหน่งและขนาดที่กำหนด:

```java
IChart chart = slide.getShapes().addChart(
    ChartType.ClusteredColumn, 
    150, 150, 
    500, 300
);
```
**อธิบายพารามิเตอร์:**
- `ChartType`: ระบุประเภทของแผนภูมิ (ในที่นี้คือแผนภูมิคอลัมน์แบบกลุ่ม).  
- พิกัด (x, y): ตำแหน่งบนสไลด์.  
- ความกว้างและความสูง: ขนาดของแผนภูมิ.

### ขั้นตอนที่ 4: เข้าถึง Workbook ของข้อมูลแผนภูมิ
ดึง workbook ที่เชื่อมโยงกับแผนภูมิของคุณ:

```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```

### ขั้นตอนที่ 5: ตั้งค่าสูตร (calculate chart formulas)

**สูตรในเซลล์ B2**  
```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

**สูตรแบบ R1C1 ในเซลล์ C2**  
```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```
สูตรเหล่านี้ทำให้แผนภูมิอัปเดตโดยอัตโนมัติเมื่อข้อมูลพื้นฐานมีการเปลี่ยนแปลง.

### ขั้นตอนที่ 6: คำนวณสูตรทั้งหมด
เรียกใช้เมธอดการคำนวณบน workbook ของคุณเพื่อให้แผนภูมิแสดงค่าล่าสุด:

```java
workbook.calculateFormulas();
```

### ขั้นตอนที่ 7: บันทึกงานนำเสนอของคุณ
บันทึกงานของคุณด้วยชื่อไฟล์และรูปแบบที่ระบุ:

```java
String outpptxFile = "YOUR_OUTPUT_DIRECTORY" + File.separator + "ChartDataCell_Formulas_out.pptx";
presentation.save(outpptxFile, SaveFormat.Pptx);
```
ตรวจสอบให้แน่ใจว่าได้แทนที่ `YOUR_OUTPUT_DIRECTORY` ด้วยเส้นทางจริงที่คุณต้องการเก็บไฟล์.

## การประยุกต์ใช้จริง

- **Financial Reporting**: อัตโนมัติการสร้างแผนภูมิสำหรับรายงานการเงินรายเดือนหรือไตรมาส.  
- **Data Visualization in Education**: สร้างสไลด์ที่ขับเคลื่อนด้วยข้อมูลอย่างรวดเร็วสำหรับการสอนแนวคิดที่ซับซ้อน.  
- **Business Analytics**: ปรับปรุงงานนำเสนอด้วยข้อมูลเชิงลึกแบบไดนามิกโดยใช้สูตรที่คำนวณ.

พิจารณานำ Aspose.Slides เข้ากับกระบวนการทำงานของคุณเพื่อปรับปรุงการเตรียมงานนำเสนอ, โดยเฉพาะอย่างยิ่งเมื่อจัดการกับชุดข้อมูลขนาดใหญ่ที่ต้องอัปเดตบ่อย.

## การพิจารณาประสิทธิภาพ

เพิ่มประสิทธิภาพโดย:

- จัดการทรัพยากรอย่างมีประสิทธิภาพ; ควรทำลายอ็อบเจ็กต์ `Presentation` เสมอ.  
- ลดจำนวนแผนภูมิและความซับซ้อนของมันบนสไลด์เดียวหากเวลาการประมวลผลเป็นสิ่งสำคัญ.  
- ใช้การดำเนินการแบบ batch สำหรับหลายแผนภูมิเพื่อลดภาระ.

การปฏิบัติตามแนวทางปฏิบัติที่ดีที่สุดเหล่านี้จะทำให้การทำงานเป็นไปอย่างราบรื่น, แม้ในสภาพแวดล้อมที่มีทรัพยากรจำกัด.

## สรุป

ตอนนี้คุณควรพร้อมอย่างดีที่จะ **create PowerPoint chart** ด้วย Aspose.Slides for Java, สร้างงานนำเสนอแบบไดนามิก, และใช้สูตรแผนภูมิที่คำนวณได้. ไลบรารีที่ทรงพลังนี้ช่วยประหยัดเวลาและยกระดับคุณภาพของการแสดงผลข้อมูลของคุณ. ค้นหาฟีเจอร์เพิ่มเติมโดยเข้าไปที่ [Aspose Documentation](https://reference.aspose.com/slides/java/) และพิจารณาขยายโปรเจกต์ของคุณด้วยความสามารถเพิ่มเติมของ Aspose.Slides.

### ขั้นตอนต่อไป

- ทดลองใช้ประเภทและรูปแบบแผนภูมิที่แตกต่าง.  
- ผสานฟังก์ชัน Aspose.Slides เข้ากับแอปพลิเคชัน Java ขนาดใหญ่.  
- สำรวจไลบรารีอื่นของ Aspose เพื่อเพิ่มประสิทธิภาพการประมวลผลเอกสารในหลายรูปแบบ.

## คำถามที่พบบ่อย

**Q: What is the minimum JDK version required for Aspose.Slides?**  
**A:** JDK 16 หรือสูงกว่าแนะนำเพื่อความเข้ากันได้และประสิทธิภาพ

**Q: Can I use Aspose.Slides without a license?**  
**A:** ใช่, แต่จะมีข้อจำกัดในฟังก์ชันการทำงาน. รับไลเซนส์ชั่วคราวหรือเต็มเพื่อใช้งานโดยไม่มีข้อจำกัด.

**Q: How do I handle exceptions when using Aspose.Slides?**  
**A:** ใช้บล็อก try‑finally เพื่อให้แน่ใจว่าทรัพยากรถูกปล่อย, ตามตัวอย่างในส่วนการเริ่มต้นพื้นฐาน.

**Q: Can I add multiple charts to the same slide?**  
**A:** แน่นอน—สร้างและวางตำแหน่งแต่ละแผนภูมิแยกกันภายในขอบเขตของสไลด์.

**Q: Is it possible to update chart data without regenerating the entire presentation?**  
**A:** ใช่—สามารถจัดการ workbook ของข้อมูลแผนภูมิโดยตรงและคำนวณสูตรใหม่ได้.

สำรวจแหล่งข้อมูลเพิ่มเติมผ่านลิงก์ด้านล่าง:
- [Aspose Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

**Last Updated:** 2026-03-15  
**Tested With:** Aspose.Slides 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}