---
date: '2026-02-22'
description: เรียนรู้วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides, เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม,
  และตรวจสอบการจัดวางแผนภูมิ—ทั้งหมดในคู่มือสั้นกระชับหนึ่งเดียว.
keywords:
- Aspose.Slides Java
- create charts in Java
- validate chart layout
title: สร้างแผนภูมิใน Java ด้วย Aspose.Slides – เพิ่มและตรวจสอบแผนภูมิ
url: /th/java/charts-graphs/aspose-slides-java-create-validate-charts/
weight: 1
---

0}}.

Also preserve markdown formatting.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides

ในโลกที่ขับเคลื่อนด้วยข้อมูลในทุกวันนี้ การทำภาพข้อมูลผ่านแผนภูมิเป็นสิ่งสำคัญเพื่อทำความเข้าใจชุดข้อมูลที่ซับซ้อน **หากคุณต้องการสร้างแผนภูมิใน Java** Aspose.Slides จะมอบวิธีที่สะอาดและเป็นโปรแกรมเมติกให้คุณเพิ่ม กำหนดค่า และตรวจสอบแผนภูมิโดยตรงภายในงานนำเสนอ PowerPoint ไม่ว่าคุณจะสร้างเครื่องมือรายงาน แอปการศึกษา หรือแดชบอร์ดแบบเรียลไทม์ คู่มือนี้จะพาคุณผ่านกระบวนการทั้งหมด—from การตั้งค่าไลบรารีจนถึงการบันทึกไฟล์ขั้นสุดท้าย

## คำตอบอย่างรวดเร็ว
- **ไลบรารีอะไรที่ให้คุณสร้างแผนภูมิใน Java?** Aspose.Slides for Java.  
- **ประเภทแผนภูมิที่แสดงคืออะไร?** A clustered column chart.  
- **คุณตรวจสอบการจัดวางแผนภูมิอย่างไร?** Call `validateChartLayout()` on the chart object.  
- **คุณสามารถดึงขนาดพื้นที่พล็อตได้หรือไม่?** Yes, via `chart.getPlotArea().getActualX()` and related methods.  
- **ขั้นตอนสุดท้ายคืออะไร?** Save the presentation with `pres.save(...)`.  

## สิ่งที่คุณจะได้เรียนรู้
- วิธีตั้งค่า Aspose.Slides for Java ในโครงการของคุณ  
- **วิธีสร้างแผนภูมิ** – โดยเฉพาะแผนภูมิคอลัมน์แบบกลุ่ม – และเพิ่มลงในสไลด์  
- **วิธีตรวจสอบการจัดวางแผนภูมิ** อย่างโปรแกรม  
- การดึงและตีความมิติของพื้นที่พล็อต  
- การบันทึกงานนำเสนอพร้อมแผนภูมิที่อัปเดต  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)** – JDK 16 หรือใหม่กว่า.  
- **Aspose.Slides for Java** – ไลบรารี (เราจะใช้เวอร์ชัน 25.4 ในตัวอย่าง).  
- **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขที่รองรับ Java ใด ๆ.  

## การตั้งค่า Aspose.Slides for Java
คุณสามารถนำ Aspose.Slides เข้าสู่โครงการของคุณด้วย Maven, Gradle หรือการดาวน์โหลดโดยตรง

### Maven
เพิ่ม dependency นี้ในไฟล์ `pom.xml` ของคุณ:
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
หรือคุณสามารถดาวน์โหลดไลบรารีโดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### การรับใบอนุญาต
- **Free Trial** – ฟีเจอร์จำกัดสำหรับการประเมินอย่างรวดเร็ว.  
- **Temporary License** – ขอคีย์ระยะสั้นสำหรับการทดสอบเต็มรูปแบบ.  
- **Purchase** – ซื้อการสมัครใช้งานสำหรับการใช้งานในผลิตภัณฑ์.

#### การเริ่มต้นและตั้งค่าเบื้องต้น
ด้านล่างเป็นโค้ดขั้นต่ำที่คุณต้องการเพื่อเริ่มทำงานกับงานนำเสนอ:
```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your chart creation logic will go here
        presentation.dispose();  // Clean up resources
    }
}
```

## วิธีเพิ่มแผนภูมิลงในสไลด์และสร้างแผนภูมิคอลัมน์แบบกลุ่ม
การสร้างแผนภูมิในงานนำเสนอเป็นเรื่องง่ายด้วย Aspose.Slides ส่วนต่อไปนี้จะแบ่งขั้นตอนแต่ละขั้นตอนออกมา

### ขั้นตอนที่ 1: ตั้งค่างานนำเสนอของคุณ
โหลดไฟล์ที่มีอยู่หรือเริ่มไฟล์ใหม่:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.Pptx");
```

### ขั้นตอนที่ 2: เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม
ที่นี่เราจะ **add clustered column chart** ไปยังสไลด์แรกในตำแหน่งที่กำหนด:
```java
import com.aspose.slides.ShapeType;

Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 350
);
```

### ขั้นตอนที่ 3: ตรวจสอบการจัดวางแผนภูมิ
หลังจากวางแผนภูมิแล้ว ให้ตรวจสอบให้แน่ใจว่าทุกอย่างจัดเรียงอย่างถูกต้อง:
```java
chart.validateChartLayout();
```

#### ทำไมการตรวจสอบจึงสำคัญ
`validateChartLayout()` ตรวจสอบการทับซ้อนขององค์ประกอบ แกนที่หายไป และความไม่สอดคล้องด้านภาพอื่น ๆ เพื่อให้ผู้ชมของคุณเห็นแผนภูมิที่เรียบหรู

## วิธีดึงขนาดพื้นที่พล็อตจากแผนภูมิ
การเข้าใจพื้นที่ที่แผนภูมิใช้จริงช่วยให้คุณปรับแต่งการจัดวางหรือวางกราฟิกเพิ่มเติมได้อย่างแม่นยำ

### ขั้นตอนที่ 4: เข้าถึงอ็อบเจกต์แผนภูมิ
```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

### ขั้นตอนที่ 5: ดึงเมตริกซ์ของพื้นที่พล็อต
```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();

System.out.println("Plot Area: X=" + x + ", Y=" + y + ", Width=" + w + ", Height=" + h);
```

ค่าต่าง ๆ เหล่านี้มีประโยชน์เมื่อคุณต้องจัดตำแหน่งรูปร่างอื่นหรือคำนวณระยะขอบแบบกำหนดเอง

## วิธีบันทึกงานนำเสนอพร้อมแผนภูมิใหม่
เมื่อแผนภูมิของคุณสร้างและตรวจสอบแล้ว ให้บันทึกการเปลี่ยนแปลง:
 
### ขั้นตอนที่ 6: บันทึกไฟล์
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
```

## การประยุกต์ใช้งานจริง
- **Business Reporting** – อัตโนมัติการสร้างสไลด์ไตรมาสด้วยแผนภูมิที่อัปเดตล่าสุด.  
- **Educational Tools** – สร้างสไลด์การบรรยายที่แสดงแนวโน้มข้อมูลแบบเรียลไทม์.  
- **Dashboard Integration** – ส่งออกการวิเคราะห์แบบเรียลไทม์ไปยัง PowerPoint สำหรับการบรรยายต่อผู้บริหาร.  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ทำลายอ็อบเจกต์ `Presentation` (`pres.dispose()`) เพื่อปล่อยทรัพยากรเนทีฟ.  
- เมื่อประมวลผลเด็คขนาดใหญ่ ให้ใช้แผนภูมิซ้ำเมื่อเป็นไปได้เพื่อลดการใช้หน่วยความจำ.  
- แนะนำให้ใช้ Streaming API สำหรับชุดข้อมูลขนาดใหญ่เพื่อหลีกเลี่ยงการโหลดทั้งหมดเข้าสู่หน่วยความจำพร้อมกัน.  

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| แผนภูมิแสดงเป็นสีขาวเปล่า | ยังไม่ได้เพิ่มชุดข้อมูล | ใช้ `chart.getChartData().getSeries().add(...)` ก่อนทำการตรวจสอบ. |
| การตรวจสอบการจัดวางเกิดข้อผิดพลาด | รูปร่างทับซ้อนบนสไลด์ | ปรับพิกัด X/Y หรือเพิ่มขนาดของแผนภูมิ. |
| `OutOfMemoryError` บนไฟล์ขนาดใหญ่ | ไม่ได้ทำลายอ็อบเจกต์ | เรียก `presentation.dispose()` ในบล็อก `finally`. |

## คำถามที่พบบ่อย

**Q: Aspose.Slides คืออะไร?**  
A: เป็นไลบรารี Java ที่ทรงพลังสำหรับสร้าง แก้ไข และแปลงไฟล์ PowerPoint โดยไม่ต้องใช้ Microsoft Office.

**Q: ฉันจะขอใบอนุญาตชั่วคราวได้อย่างไร?**  
A: เยี่ยมชม [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) และทำตามขั้นตอนการขอ.

**Q: ฉันสามารถสร้างประเภทแผนภูมิอื่น ๆ นอกจากคอลัมน์แบบกลุ่มได้หรือไม่?**  
A: ได้, Aspose.Slides รองรับแผนภูมิแบบแท่ง, เส้น, พาย, พื้นที่ และประเภทอื่น ๆ อีกมากมาย.

**Q: มีวิธีใดบ้างที่จะเพิ่มข้อมูลลงในแผนภูมิโดยโปรแกรมเมติก?**  
A: แน่นอน. ใช้ `chart.getChartData().getSeries().add(...)` และ `chart.getChartData().getCategories().add(...)`.

**Q: ไลบรารีนี้ทำงานบนระบบปฏิบัติการทั้งหมดหรือไม่?**  
A: เวอร์ชัน Java เป็นแบบข้ามแพลตฟอร์มและทำงานบน Windows, Linux, และ macOS.

## แหล่งข้อมูล
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase Subscription](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}