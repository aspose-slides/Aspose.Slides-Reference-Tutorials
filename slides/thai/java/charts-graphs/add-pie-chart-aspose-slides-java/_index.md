---
date: '2026-01-09'
description: ค้นพบวิธีใช้ Aspose Slides Maven เพื่อเพิ่มแผนภูมิลงในสไลด์และปรับแต่งแผนภูมิวงกลมในงานนำเสนอ
  Java ขั้นตอนการตั้งค่าแบบทีละขั้นตอน โค้ด และตัวอย่างจากโลกจริง
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - เพิ่มแผนภูมิวงกลมลงในงานนำเสนอ'
url: /th/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเพิ่มแผนภูมิวงกลมลงในงานนำเสนอโดยใช้ Aspose.Slides Java

## บทนำ
การสร้างงานนำเสนอที่ดูสวยงามเป็นสิ่งสำคัญสำหรับการสื่อสารข้อมูลอย่างมีประสิทธิภาพ โดยเฉพาะเมื่อการแสดงผลข้อมูลเป็นบทบาทหลัก หากคุณกำลังมองหาวิธีอัตโนมัติกระบวนการนี้ด้วย **aspose slides maven** คุณมาถูกที่แล้ว ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **add chart to slide** — โดยเฉพาะแผนภูมิวงกลม — ด้วย Aspose.Slides for Java และดูวิธีปรับแต่งให้เหมาะกับสถานการณ์จริง

### สิ่งที่คุณจะได้เรียนรู้
- วิธีการเริ่มต้นอ็อบเจ็กต์ Presentation ใน Java  
- ขั้นตอนการ **add a pie chart java** บนสไลด์แรกของงานนำเสนอ  
- การเข้าถึง workbook ข้อมูลแผนภูมิและการแสดงรายการ worksheet ภายใน  

มาดูกันว่าคุณจะใช้ Aspose.Slides Java เพื่อเสริมงานนำเสนอของคุณด้วยแผนภูมิดินามิกอย่างไร!

## คำตอบสั้น
- **What library adds charts via Maven?** aspose slides maven  
- **Which chart type is demonstrated?** Pie chart (add chart to slide)  
- **Minimum Java version required?** JDK 16 or later  
- **Do I need a license for testing?** A free trial works; production needs a license  
- **Where can I find the Maven dependency?** In the setup section below  

## Aspose Slides Maven คืออะไร?
Aspose.Slides for Java เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสร้าง แก้ไข และแปลงไฟล์ PowerPoint อย่างโปรแกรมเมติก แพคเกจ Maven (`aspose-slides`) ทำให้การจัดการ dependencies ง่ายขึ้น ทำให้คุณสามารถมุ่งเน้นการสร้างและปรับแต่งสไลด์—เช่นการเพิ่มแผนภูมิวงกลม—โดยไม่ต้องจัดการไฟล์ระดับล่าง

## ทำไมต้องใช้ Aspose.Slides Maven เพื่อเพิ่มแผนภูมิลงในสไลด์?
- **Automation:** สร้างรายงานและแดชบอร์ดโดยอัตโนมัติ  
- **Precision:** ควบคุมประเภทแผนภูมิ ข้อมูล และสไตล์ได้เต็มที่  
- **Cross‑Platform:** ทำงานได้บนสภาพแวดล้อมที่รองรับ Java ใดก็ได้  

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** เวอร์ชัน 25.4 หรือใหม่กว่า (Maven/Gradle)  
- JDK 16+ ติดตั้งแล้ว  
- IDE (IntelliJ IDEA, Eclipse ฯลฯ)  
- ความรู้พื้นฐาน Java และความคุ้นเคยกับ Maven หรือ Gradle  

## การตั้งค่า Aspose.Slides สำหรับ Java
ก่อนอื่น ให้เพิ่ม Aspose.Slides ลงในโปรเจกต์ของคุณผ่าน Maven หรือ Gradle

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

หรือคุณสามารถ [ดาวน์โหลดเวอร์ชันล่าสุด](https://releases.aspose.com/slides/java/) โดยตรงจากเว็บไซต์ของ Aspose

### การรับใบอนุญาต
Aspose.Slides for Java มีรุ่นทดลองฟรีพร้อมใบอนุญาตชั่วคราวสำหรับการทดสอบ หากต้องการใช้งานในผลิตภัณฑ์จริงอย่างไม่มีข้อจำกัด ให้ซื้อใบอนุญาตผ่าน [หน้าการซื้อ](https://purchase.aspose.com/buy)

## คู่มือการดำเนินการ
ต่อไปนี้เราจะแบ่งวิธีแก้เป็นสองฟีเจอร์: การเพิ่มแผนภูมิวงกลมและการเข้าถึง workbook ข้อมูลของแผนภูมิ

### ฟีเจอร์ 1: การสร้างงานนำเสนอและเพิ่มแผนภูมิ
#### ภาพรวม
ส่วนนี้แสดงวิธีสร้างงานนำเสนอใหม่และ **add a pie chart** ลงบนสไลด์แรก

#### ขั้นตอนทีละขั้นตอน

**Step 1: Initialize a New Presentation Object**  
```java
Presentation pres = new Presentation();
```
*สร้างอินสแตนซ์ `Presentation` ที่จะเก็บสไลด์ทั้งหมด*

**Step 2: Add a Pie Chart**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*วางแผนภูมิวงกลมที่ตำแหน่ง (50, 50) ด้วยความกว้าง 400 และความสูง 500 ตัวแปร `ChartType.Pie` บอก Aspose ให้เรนเดอร์เป็นแผนภูมิวงกลม*

**Step 3: Dispose of Resources**  
```java
if (pres != null) pres.dispose();
```
*ปล่อยทรัพยากรเนทีฟ; ควรเรียก `dispose()` เสมอเมื่อทำงานเสร็จ*

### ฟีเจอร์ 2: การเข้าถึง Workbook ข้อมูลแผนภูมิและ Worksheet
#### ภาพรวม
เรียนรู้วิธีเข้าถึง workbook ที่เก็บข้อมูลแผนภูมิและวนลูปผ่าน worksheet ต่าง ๆ

#### ขั้นตอนทีละขั้นตอน

**Step 1: (Reuse) Initialize a New Presentation Object**  
*เหมือนกับ Feature 1, Step 1*

**Step 2: (Reuse) Add a Pie Chart**  
*เหมือนกับ Feature 1, Step 2*

**Step 3: Get the Chart Data Workbook**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*ดึง `IChartDataWorkbook` ที่เชื่อมโยงกับแผนภูมิ*

**Step 4: Iterate Through Worksheets**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*พิมพ์ชื่อของแต่ละ worksheet เพื่อให้คุณตรวจสอบโครงสร้างข้อมูล*

**Step 5: Dispose of Resources**  
*เหมือนกับ Feature 1, Step 3*

## การประยุกต์ใช้ในทางปฏิบัติ
- **Data Reporting:** สร้างชุดสไลด์อัตโนมัติพร้อมเมตริกที่อัปเดตสำหรับ Business Intelligence  
- **Academic Presentations:** แสดงผลการวิจัยโดยไม่ต้องสร้างแผนภูมิด้วยมือ  
- **Marketing Material:** นำเสนอประสิทธิภาพผลิตภัณฑ์หรือผลสำรวจได้ทันที  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ควรจำกัดจำนวนสไลด์และแผนภูมิให้เหมาะสม; แต่ละอันใช้หน่วยความจำ  
- เรียก `dispose()` เสมอเพื่อคืนทรัพยากรเนทีฟ  
- ปรับการจัดการข้อมูล workbook ให้เหมาะสม—หลีกเลี่ยงการโหลดชุดข้อมูลขนาดใหญ่ลงในแผนภูมิเดียว  

## สรุป
เราได้อธิบายวิธีที่ **aspose slides maven** ช่วยให้คุณ **add chart to slide** ได้โดยโปรแกรมเมติกและวิธีทำงานกับ workbook ของแผนภูมิ ด้วยบล็อกพื้นฐานเหล่านี้คุณสามารถอัตโนมัติขั้นตอนการรายงานใด ๆ ที่ต้องการผลลัพธ์ PowerPoint ที่ดูเป็นมืออาชีพ

### ขั้นตอนต่อไป
- สำรวจตัวเลือกการจัดรูปแบบแผนภูมิ (สี, legend, data label)  
- เชื่อมต่อแหล่งข้อมูลภายนอก (CSV, ฐานข้อมูล) เพื่อเติมข้อมูลแผนภูมิแบบไดนามิก  
- รวมหลายประเภทแผนภูมิในงานนำเสนอเดียวเพื่อการเล่าเรื่องที่หลากหลายยิ่งขึ้น  

## คำถามที่พบบ่อย

**Q: ฉันจะติดตั้ง Aspose.Slides for Java อย่างไร?**  
A: ใช้ dependency ของ Maven หรือ Gradle ที่แสดงด้านบน หรือดาวน์โหลดไลบรารีจากหน้าปล่อยเวอร์ชัน

**Q: ระบบต้องการอะไรบ้างสำหรับ Aspose.Slides?**  
A: JDK 16 หรือใหม่กว่า; ไลบรารีเป็นแบบ platform‑independent

**Q: ฉันสามารถเพิ่มประเภทแผนภูมิอื่น ๆ นอกจากแผนภูมิวงกลมได้หรือไม่?**  
A: ได้, Aspose.Slides รองรับแผนภูมิแบบ bar, line, scatter และอื่น ๆ อีกมากมาย

**Q: ควรจัดการงานนำเสนอขนาดใหญ่อย่างมีประสิทธิภาพอย่างไร?**  
A: ปล่อยอ็อบเจ็กต์โดยเร็ว, จำกัดจำนวนภาพความละเอียดสูง, และใช้เทมเพลตแผนภูมิซ้ำเมื่อเป็นไปได้

**Q: ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับคุณสมบัติของ Aspose.Slides ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose documentation](https://reference.aspose.com/slides/java/) เพื่อดูเอกสาร API อย่างครบถ้วน

**Q: จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่?**  
A: ต้องมีใบอนุญาตที่ถูกต้องสำหรับการผลิต; มีรุ่นทดลองฟรีสำหรับการประเมิน

**Q: แพคเกจ Maven มีความสามารถของแผนภูมิทั้งหมดหรือไม่?**  
A: มี, artifact `aspose-slides` ของ Maven มีเครื่องมือสร้างแผนภูมิครบชุด

## แหล่งข้อมูล
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-01-09  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## แหล่งข้อมูล
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)
