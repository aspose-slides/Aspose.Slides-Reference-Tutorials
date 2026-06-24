---
date: '2026-03-18'
description: เรียนรู้วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides วิธีเพิ่มแผนภูมิ
  ตั้งค่าสี และบันทึกงานนำเสนอเป็น PPTX คู่มือทีละขั้นตอนพร้อมตัวอย่างโค้ด
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides

## คำแนะนำ
การสร้างการแสดงผลข้อมูลที่น่าดึงดูดเป็นสิ่งสำคัญสำหรับการนำเสนอธุรกิจที่มีผลกระทบ, และการเรียนรู้ **วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่ม** ด้วยโปรแกรมสามารถช่วยคุณประหยัดเวลาหลายชั่วโมงจากการทำงานด้วยตนเอง ในบทเรียนนี้คุณจะได้เห็น **วิธีเพิ่มแผนภูมิ**, การตั้งค่าสีโดยอัตโนมัติ, และสุดท้าย **การบันทึกงานนำเสนอเป็น PPTX** ด้วย **Aspose.Slides for Java** เราจะอธิบายทุกขั้นตอนที่คุณต้องการ—ตั้งแต่การตั้งค่าไลบรารี, การเพิ่มแผนภูมิ, การปรับแต่งสีเติมของซีรีส์, จนถึงการบันทึกไฟล์

### สิ่งที่คุณจะได้เรียนรู้
- ติดตั้งและกำหนดค่า Aspose.Slides for Java  
- **สร้างแผนภูมิคอลัมน์แบบกลุ่ม** ในงานนำเสนอใหม่  
- ตั้งค่าสีเติมของซีรีส์โดยอัตโนมัติ (**how to set colors**)  
- **บันทึกงานนำเสนอเป็น PPTX** ลงดิสก์ (**how to save presentation**)  

มาดูข้อกำหนดเบื้องต้นก่อนที่เราจะเริ่มสร้างแผนภูมิ

## คำตอบอย่างรวดเร็ว
- **คลาสหลักคืออะไร?** `Presentation` จาก `com.aspose.slides`  
- **ฉันจะเพิ่มแผนภูมิอย่างไร?** ใช้ `addChart(ChartType.ClusteredColumn, …)` ในคอลเลกชันรูปร่างของสไลด์ (**how to add chart**)  
- **ฉันสามารถตั้งค่าสีโดยอัตโนมัติได้หรือไม่?** ได้, เรียก `setAutomaticSeriesColor(true)` ในแต่ละซีรีส์ (**how to set colors**)  
- **รูปแบบใดที่ใช้สำหรับการบันทึก?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้งานได้สำหรับการทดสอบ; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง  

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม, โปรดตรวจสอบว่าคุณมีเครื่องมือและความรู้ที่จำเป็น:

### ไลบรารีและการพึ่งพาที่จำเป็น
คุณจะต้องใช้ไลบรารี Aspose.Slides for Java. ตรวจสอบให้แน่ใจว่าคุณใช้เวอร์ชัน 25.4 ที่รองรับ JDK16

### ความต้องการการตั้งค่าสภาพแวดล้อม
สภาพแวดล้อมการพัฒนาของคุณควรสนับสนุน Java (แนะนำ JDK16) และสามารถสร้างโปรเจกต์ด้วย Maven หรือ Gradle

### ความรู้พื้นฐานที่ต้องมี
ความคุ้นเคยกับการเขียนโปรแกรม Java เบื้องต้น, การทำงานกับไลบรารีผ่าน Maven/Gradle, และความเข้าใจเกี่ยวกับงานนำเสนอ PowerPoint จะเป็นประโยชน์

## การตั้งค่า Aspose.Slides for Java
เพื่อรวม Aspose.Slides เข้ากับโปรเจกต์ของคุณ, ให้ทำตามคำแนะนำการตั้งค่าด้านล่าง:

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

**ดาวน์โหลดโดยตรง**  
สำหรับผู้ที่ต้องการดาวน์โหลดโดยตรง, เยี่ยมชม [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### ขั้นตอนการรับไลเซนส์
- **Free Trial**: เริ่มต้นด้วยการทดลองฟรีเพื่อสำรวจคุณลักษณะ.  
- **Temporary License**: รับไลเซนส์ชั่วคราวเพื่อทดสอบโดยไม่มีข้อจำกัด.  
- **Purchase**: สำหรับการใช้งานต่อเนื่อง, ซื้อไลเซนส์เต็ม.  

**การเริ่มต้นและการตั้งค่าเบื้องต้น**  
เริ่มต้น Aspose.Slides ดังนี้:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม
การเพิ่มแผนภูมิเป็นขั้นตอนการทำงานแรก. ส่วนนี้อธิบาย **วิธีเพิ่มแผนภูมิ** ด้วย API.

### คุณลักษณะ 1: สร้างแผนภูมิคอลัมน์แบบกลุ่ม
มาสร้างแผนภูมิคอลัมน์แบบกลุ่มด้วย Aspose.Slides for Java. คุณลักษณะนี้ช่วยให้คุณเพิ่มแผนภูมิที่ดูสวยงามลงในสไลด์ได้อย่างง่ายดาย.

#### ภาพรวม
ในส่วนนี้, เราจะเริ่มต้นงานนำเสนอใหม่และแทรกแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์แรก.

**ขั้นตอนที่ 1: เริ่มต้น Presentation**  
สร้างอ็อบเจ็กต์ `Presentation` เพื่อเริ่มทำงานกับไฟล์ PowerPoint:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**ขั้นตอนที่ 2: เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม**  
เพิ่มแผนภูมิที่พิกัดที่กำหนด (100, 50) และขนาด (600 × 400):
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**ขั้นตอนที่ 3: ทำความสะอาดทรัพยากร**  
ควรทำการปล่อยทรัพยากรเสมอเพื่อป้องกันการรั่วไหลของหน่วยความจำ:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## วิธีตั้งค่าสีสำหรับแผนภูมิ
เพิ่มความสวยงามของภาพโดยการตั้งค่าสีเติมของซีรีส์โดยอัตโนมัติ (**how to set colors**).

### คุณลักษณะ 2: ตั้งค่าสีเติมซีรีส์อัตโนมัติ
ตั้งค่าสีของซีรีส์แต่ละอันในแผนภูมิโดยอัตโนมัติเพื่อให้ได้ลุคที่สอดคล้องกัน.

#### ภาพรวม
ตั้งค่าสีของซีรีส์แต่ละอันในแผนภูมิโดยอัตโนมัติเพื่อให้ได้ลุคที่สอดคล้องกัน.

**ขั้นตอนที่ 1: เข้าถึงแผนภูมิและวนลูปซีรีส์**  
หลังจากสร้างแผนภูมิของคุณ, เข้าถึงและวนลูปผ่านซีรีส์ของมัน:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**ขั้นตอนที่ 2: การจัดการทรัพยากร**  
ปล่อยอ็อบเจ็กต์ Presentation เมื่อทำเสร็จแล้ว:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## วิธีบันทึกงานนำเสนอเป็น PPTX
เมื่อแผนภูมิดูดีแล้ว, คุณจะต้องบันทึกไฟล์ (**how to save presentation**).

### คุณลักษณะ 3: บันทึกงานนำเสนอลงดิสก์
สุดท้าย, บันทึกงานของคุณอย่างง่ายดายด้วย Aspose.Slides.

#### ภาพรวม
บันทึกงานนำเสนอที่แก้ไขแล้วในรูปแบบและตำแหน่งที่ต้องการ.

**ขั้นตอนที่ 1: กำหนดเส้นทางเอาต์พุต**  
ระบุที่ที่คุณต้องการบันทึกไฟล์:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**ขั้นตอนที่ 2: บันทึกงานนำเสนอ**  
ใช้เมธอด `save` ของอ็อบเจ็กต์ `Presentation`:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## การประยุกต์ใช้งานจริง
- **Financial Reports**: แสดงผลกำไรไตรมาสอย่างชัดเจน.  
- **Marketing Data Analysis**: นำเสนอผลลัพธ์ของแคมเปญด้วยภาพที่ดึงดูด.  
- **Project Management**: ติดตามไมล์สโตนและความคืบหน้าแบบภาพในประชุมทีม.

## การพิจารณาประสิทธิภาพ
เมื่อทำงานกับ Aspose.Slides, ควรพิจารณาปฏิบัติที่ดีที่สุดต่อไปนี้:
- จัดการหน่วยความจำอย่างมีประสิทธิภาพโดยปล่อยอ็อบเจ็กต์ `Presentation` ทันที.  
- เพิ่มประสิทธิภาพขนาดไฟล์เมื่อบันทึกงานนำเสนอเพื่อประหยัดพื้นที่ดิสก์.  
- ใช้โครงสร้างข้อมูลที่มีประสิทธิภาพสำหรับซีรีส์ของแผนภูมิเพื่อเพิ่มประสิทธิภาพ.

## สรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธี **สร้างแผนภูมิคอลัมน์แบบกลุ่ม**, ตั้งค่าสีโดยอัตโนมัติ, และ **บันทึกงานนำเสนอเป็น PPTX** ด้วย Aspose.Slides for Java ทักษะนี้ไม่เพียงช่วยยกระดับงานนำเสนอของคุณเท่านั้น แต่ยังทำให้กระบวนการแสดงผลข้อมูลเป็นภาพเป็นเรื่องง่ายขึ้น.

**ขั้นตอนต่อไป:**  
สำรวจคุณลักษณะเพิ่มเติมเช่นการปรับแต่งองค์ประกอบของแผนภูมิ, การเพิ่มป้ายข้อมูล, หรือการรวมกับแหล่งข้อมูลภายนอกเพื่อขยายความสามารถของโครงการของคุณ.

## ส่วนคำถามที่พบบ่อย
1. **ฉันจะติดตั้ง Aspose.Slides สำหรับเวอร์ชัน JDK เฉพาะได้อย่างไร?**  
   - ใช้การพึ่งพา Maven/Gradle โดยระบุ `classifier` ตามที่แสดงในส่วนการตั้งค่า.  
2. **ถ้างานนำเสนอของฉันไม่บันทึกอย่างถูกต้องจะทำอย่างไร?**  
   - ตรวจสอบว่าคุณมีสิทธิ์เขียนในไดเรกทอรีเอาต์พุตและเส้นทางไฟล์ถูกต้อง.  
3. **ฉันสามารถสร้างแผนภูมิประเภทอื่นด้วย Aspose.Slides for Java ได้หรือไม่?**  
   - แน่นอน! สำรวจตัวเลือก `ChartType` เช่น Pie, Bar, หรือ Line charts.  
4. **ฉันจะจัดการกับชุดข้อมูลขนาดใหญ่ในแผนภูมิของฉันอย่างไร?**  
   - ปรับโครงสร้างข้อมูลและพิจารณาการประมวลผลล่วงหน้าข้อมูลของคุณก่อนทำการแสดงผล.  
5. **ฉันจะหา ตัวอย่างเพิ่มเติมของการใช้ Aspose.Slides for Java ได้ที่ไหน?**  
   - เยี่ยมชม [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) เพื่อดูคู่มือและตัวอย่างโค้ดอย่างครบถ้วน.

## แหล่งข้อมูล
- **เอกสารอ้างอิง**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **ดาวน์โหลด**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **ซื้อไลเซนส์**: [Buy a License](https://purchase.aspose.com/buy)  
- **ทดลองใช้ฟรี**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **ไลเซนส์ชั่วคราว**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **สนับสนุน**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**อัปเดตล่าสุด:** 2026-03-18  
**ทดสอบด้วย:** Aspose.Slides 25.4 (JDK16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}