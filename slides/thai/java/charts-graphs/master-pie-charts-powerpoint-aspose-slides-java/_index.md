---
"date": "2025-04-17"
"description": "เรียนรู้วิธีการสร้าง แก้ไข และเพิ่มประสิทธิภาพแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยการแสดงข้อมูลแบบละเอียด"
"title": "สร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint ด้วย Aspose.Slides สำหรับ Java"
"url": "/th/java/charts-graphs/master-pie-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างและปรับแต่งแผนภูมิวงกลมใน PowerPoint ด้วย Aspose.Slides สำหรับ Java

## การแนะนำ

การสร้างแผนภูมิวงกลมที่ดึงดูดสายตาและให้ข้อมูลใน PowerPoint อาจเป็นเรื่องท้าทาย ด้วย **Aspose.Slides สำหรับ Java**กระบวนการนี้จะถูกปรับปรุงให้เหมาะสม ช่วยให้คุณปรับปรุงการแสดงภาพข้อมูลได้อย่างมีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการสร้างและกำหนดค่าแผนภูมิวงกลมพื้นฐาน การปรับเปลี่ยนข้อมูลแผนภูมิ และการเติมข้อมูลชุดโดยใช้ Aspose.Slides สำหรับ Java นอกจากนี้ คุณจะได้เรียนรู้วิธีเพิ่มประสิทธิภาพการนำเสนอและนำเทคนิคเหล่านี้ไปใช้ในสถานการณ์จริง

**สิ่งที่คุณจะได้เรียนรู้:**
- การสร้างและกำหนดค่าแผนภูมิวงกลมพื้นฐานใน PowerPoint
- การแก้ไขข้อมูลแผนภูมิที่มีอยู่ด้วยหมวดหมู่และชุดใหม่
- การเติมจุดข้อมูลชุดและการปรับการเปลี่ยนแปลงสี
- การเพิ่มประสิทธิภาพ Aspose.Slides สำหรับประสิทธิภาพของ Java

## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้น ให้แน่ใจว่าคุณมี:
1. **ห้องสมุดที่จำเป็น:**
   - Aspose.Slides สำหรับ Java เวอร์ชัน 25.4 ขึ้นไป
2. **การตั้งค่าสภาพแวดล้อม:**
   - JDK (Java Development Kit) ที่เข้ากันได้ โดยควรเป็น JDK16 ตามที่ใช้ในบทช่วยสอนนี้
3. **ข้อกำหนดความรู้เบื้องต้น:**
   - ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java และมีความคุ้นเคยกับการนำเสนอ PowerPoint

## การตั้งค่า Aspose.Slides สำหรับ Java
ในการใช้ Aspose.Slides สำหรับ Java ให้เพิ่มไลบรารีลงในโปรเจ็กต์ของคุณ:

**การติดตั้ง Maven:**
เพิ่มการอ้างอิงนี้ให้กับคุณ `pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**การติดตั้ง Gradle:**
รวมสิ่งนี้ไว้ในของคุณ `build.gradle` ไฟล์:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
อีกทางเลือกหนึ่งคือ [ดาวน์โหลดเวอร์ชั่นล่าสุด](https://releases.aspose.com/slides/java/) จาก Aspose.Slides สำหรับการเปิดตัว Java

**ขั้นตอนการรับใบอนุญาต:**
- **ทดลองใช้งานฟรี:** เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว:** สำหรับการประเมินแบบขยายเวลาโดยไม่มีข้อจำกัด ให้ขอใบอนุญาตชั่วคราว [ที่นี่](https://purchase-aspose.com/temporary-license/).
- **ซื้อ:** หากพอใจให้ซื้อลิขสิทธิ์จาก [หน้าจัดซื้อของ Aspose](https://purchase-aspose.com/buy).

**การเริ่มต้นและการตั้งค่าเบื้องต้น:**
การเริ่มต้น Aspose.Slides สำหรับ Java:
```java
import com.aspose.slides.Presentation;
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## คู่มือการใช้งาน

### การสร้างและกำหนดค่าแผนภูมิวงกลม
ทำตามขั้นตอนเหล่านี้เพื่อสร้างแผนภูมิวงกลมพื้นฐานใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java

**1. สร้างอินสแตนซ์ของคลาสการนำเสนอ**
สร้าง `Presentation` วัตถุที่แสดงไฟล์ PPTX ของคุณ:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

**2. เข้าถึงสไลด์แรก**
เข้าถึงสไลด์แรกจาก `presentation` วัตถุ:
```java
ISlide slides = presentation.getSlides().get_Item(0);
```

**3. เพิ่มแผนภูมิวงกลมลงในสไลด์**
เพิ่มและกำหนดค่าแผนภูมิวงกลมด้วยข้อมูลเริ่มต้นตามพิกัด (x, y) และขนาด (ความกว้าง ความสูง) ที่ระบุ:
```java
IChart chart = slides.getShapes().addChart(com.aspose.slides.ChartType.Pie, 100, 100, 400, 400);
```

**4. ตั้งชื่อแผนภูมิ**
ปรับแต่งแผนภูมิวงกลมของคุณด้วยชื่อ:
```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(true);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

**5. การกำจัดทรัพยากร**
ให้แน่ใจว่าทรัพยากรได้รับการปล่อยหลังการใช้งาน:
```java
try {
    // การดำเนินการแผนภูมิของคุณที่นี่
} finally {
    if (presentation != null) presentation.dispose();
}
```

### การแก้ไขข้อมูลแผนภูมิและชุดข้อมูล
แก้ไขข้อมูลแผนภูมิที่มีอยู่โดยการล้างชุดข้อมูลและหมวดหมู่เริ่มต้น แล้วเพิ่มรายการใหม่

**1. ล้างชุดและหมวดหมู่เริ่มต้น**
เข้าถึงสไลด์แรกและเริ่มต้นแผนภูมิวงกลมของคุณ:
```java
ISlide slides = presentation.getSlides().get_Item(0);
IChart chart = slides.getShapes().addChart(com.aspose.slides.ChartType.Pie, 100, 100, 400, 400);
// ล้างซีรีย์และหมวดหมู่เริ่มต้น
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

**2. เพิ่มหมวดหมู่ใหม่**
กำหนดหมวดหมู่ใหม่สำหรับข้อมูลของคุณ:
```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

**3. เพิ่มซีรีย์ใหม่**
แนะนำซีรีส์ใหม่ให้กับแผนภูมิ:
```java
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

### การเติมข้อมูลชุดข้อมูลและการบันทึกการนำเสนอ
เติมจุดข้อมูลชุดสำหรับแผนภูมิวงกลม ปรับรูปแบบสี และบันทึกการนำเสนอของคุณ

**1. เติมข้อมูลชุดข้อมูล**
เติมแผนภูมิด้วยจุดข้อมูลที่เฉพาะเจาะจง:
```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(0, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(0, 3, 1, 30));
// เปิดใช้งานสีที่หลากหลายสำหรับแต่ละชิ้น
series.getParentSeriesGroup().setColorVaried(true);
```

**2. บันทึกการนำเสนอ**
บันทึกการเปลี่ยนแปลงของคุณไปยังไดเร็กทอรีที่ระบุ:
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
presentation.save(dataDir + "Pie.pptx", com.aspose.slides.SaveFormat.Pptx);
```

## การประยุกต์ใช้งานจริง
การใช้แผนภูมิวงกลมอย่างเชี่ยวชาญบน PowerPoint จะช่วยเพิ่มประสิทธิภาพในการนำเสนอในโดเมนต่างๆ ได้:
1. **รายงานทางธุรกิจ:** แสดงภาพการกระจายการขายหรือส่วนแบ่งการตลาดอย่างมีประสิทธิภาพ
2. **สื่อการเรียนรู้:** ลดความซับซ้อนของข้อมูลสำหรับนักเรียนผ่านภาพที่น่าสนใจ
3. **การวิเคราะห์ทางการเงิน:** นำเสนอการจัดสรรงบประมาณหรือพอร์ตการลงทุนอย่างชัดเจน
4. **ข้อมูลการดูแลสุขภาพ:** แสดงสถิติคนไข้หรือผลการรักษา
5. **ข้อมูลเชิงลึกด้านการตลาด:** แสดงรูปแบบพฤติกรรมผู้บริโภคและประสิทธิภาพของแคมเปญ

## การพิจารณาประสิทธิภาพ
เมื่อทำงานกับ Aspose.Slides สำหรับ Java ควรพิจารณาเคล็ดลับเหล่านี้เพื่อเพิ่มประสิทธิภาพการทำงาน:
- **การจัดการทรัพยากรอย่างมีประสิทธิภาพ:** ทิ้งเสมอ `Presentation` วัตถุหลังการใช้งานเพื่อปลดปล่อยทรัพยากร
- **เพิ่มประสิทธิภาพการจัดการข้อมูล:** ลดการจัดการข้อมูลภายในแผนภูมิเพื่อลดเวลาในการประมวลผล
- **การจัดการหน่วยความจำ:** ระมัดระวังการใช้หน่วยความจำเมื่อต้องจัดการกับการนำเสนอขนาดใหญ่ ตรวจสอบและจัดการพื้นที่ฮีป Java อย่างเหมาะสม

## บทสรุป
ตอนนี้คุณมีความรู้ในการสร้าง กำหนดค่า และจัดการแผนภูมิวงกลมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แล้ว หากปฏิบัติตามคู่มือนี้ คุณจะสามารถพัฒนาทักษะการนำเสนอและถ่ายทอดข้อมูลเชิงลึกที่ขับเคลื่อนด้วยข้อมูลได้อย่างมีประสิทธิภาพ ลองพิจารณาดูคุณสมบัติเพิ่มเติมของ Aspose.Slides เพื่อขยายขีดความสามารถของคุณในการสร้างการนำเสนอแบบไดนามิก

## ส่วนคำถามที่พบบ่อย
**คำถามที่ 1: วิธีที่ดีที่สุดในการเรียนรู้ Aspose.Slides สำหรับ Java คืออะไร**
A1: เริ่มต้นด้วยบทช่วยสอนพื้นฐาน เช่นนี้ สำรวจเอกสาร และทดลองใช้โครงการตัวอย่างเพื่อให้ได้รับประสบการณ์จริง

**คำถามที่ 2: ฉันสามารถปรับแต่งสีของแผนภูมิวงกลมนอกเหนือจากการตั้งค่าที่หลากหลายได้หรือไม่**
A2: ใช่ คุณสามารถตั้งค่าสีแต่ละสีสำหรับแต่ละจุดข้อมูลได้โดยใช้ `IDataPoint` อินเทอร์เฟซใน Aspose.Slides

**คำถามที่ 3: ฉันจะจัดการชุดข้อมูลขนาดใหญ่ในแผนภูมิของฉันได้อย่างไร**
A3: เพิ่มประสิทธิภาพการจัดการข้อมูลและพิจารณาเทคนิคการจัดการหน่วยความจำเพื่อจัดการชุดข้อมูลขนาดใหญ่อย่างมีประสิทธิภาพ

**คำถามที่ 4: สามารถส่งออกแผนภูมิวงกลมไปยังรูปแบบอื่นได้หรือไม่**
A4: ใช่ Aspose.Slides รองรับการส่งออกแผนภูมิเป็นรูปแบบรูปภาพและเอกสารต่างๆ เพื่อความเข้ากันได้ที่กว้างขึ้น

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}