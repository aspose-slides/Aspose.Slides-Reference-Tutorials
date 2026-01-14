---
date: '2026-01-14'
description: เรียนรู้วิธีส่งออกแผนภูมิไปยัง Excel ด้วย Aspose.Slides for Java และเพิ่มสไลด์แผนภูมิวงกลมลงในงานนำเสนอ
  คู่มือขั้นตอนโดยละเอียดพร้อมโค้ด
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: ส่งออกแผนภูมิไปยัง Excel ด้วย Aspose.Slides Java
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ส่งออกแผนภูมิไปยัง Excel ด้วย Aspose.Slides for Java

**เชี่ยวชาญเทคนิคการแสดงผลข้อมูลด้วย Aspose.Slides for Java**

ในสภาพแวดล้อมที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน การที่คุณสามารถ **export chart to excel** โดยตรงจากแอปพลิเคชัน Java ของคุณ จะทำให้ภาพ PowerPoint ที่คงที่กลายเป็นชุดข้อมูลที่นำกลับมาใช้ใหม่และวิเคราะห์ได้ ไม่ว่าคุณจะต้องการสร้างรายงาน, ป้อนข้อมูลเข้าสู่สายงานวิเคราะห์, หรือเพียงแค่ให้ผู้ใช้ธุรกิจแก้ไขข้อมูลแผนภูมิใน Excel, Aspose.Slides ทำให้ทุกอย่างเป็นเรื่องง่าย บทเรียนนี้จะพาคุณผ่านการสร้างแผนภูมิ, การเพิ่มสไลด์แผนภูมิวงกลม, และการส่งออกข้อมูลแผนภูมินั้นไปยังไฟล์ Excel workbook.

**สิ่งที่คุณจะได้เรียนรู้:**
- โหลดและจัดการไฟล์พรีเซนเทชันได้อย่างง่ายดาย
- **Add pie chart slide** และประเภทแผนภูมิอื่น ๆ ไปยังสไลด์ของคุณ
- **Export chart to excel** (สร้าง excel จากแผนภูมิ) สำหรับการวิเคราะห์ต่อเนื่อง
- ตั้งค่าเส้นทาง workbook ภายนอกเพื่อ **embed chart in presentation** และรักษาการซิงโครไนซ์ของข้อมูล

มาลงมือทำกันเลย!

## คำตอบอย่างรวดเร็ว
- **What is the primary purpose?** ส่งออกข้อมูลแผนภูมิจากสไลด์ PowerPoint ไปยังไฟล์ Excel.  
- **Which library version is required?** Aspose.Slides for Java 25.4 หรือใหม่กว่า.  
- **Do I need a license?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Can I add a pie chart slide?** ได้ – บทเรียนแสดงวิธีการเพิ่มแผนภูมิวงกลม.  
- **Is Java 16 minimum?** ใช่, แนะนำให้ใช้ JDK 16 หรือสูงกว่า.

## วิธีส่งออกแผนภูมิไปยัง excel ด้วย Aspose.Slides?
การส่งออกข้อมูลแผนภูมิไปยัง Excel ง่ายเพียงการโหลดพรีเซนเทชัน, สร้างแผนภูมิ, แล้วเขียนสตรีม workbook ของแผนภูมิไปยังไฟล์ ขั้นตอนต่อไปนี้จะพาคุณผ่านกระบวนการทั้งหมด ตั้งแต่การตั้งค่าโปรเจกต์จนถึงการตรวจสอบขั้นสุดท้าย.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:

### ไลบรารีและเวอร์ชันที่ต้องการ
- **Aspose.Slides for Java** เวอร์ชัน 25.4 หรือใหม่กว่า

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- Java Development Kit (JDK) 16 หรือสูงกว่า
- เครื่องมือแก้ไขโค้ดหรือ IDE เช่น IntelliJ IDEA หรือ Eclipse

### ความรู้เบื้องต้นที่ต้องมี
- ทักษะการเขียนโปรแกรม Java เบื้องต้น
- ความคุ้นเคยกับระบบการสร้าง Maven หรือ Gradle

## การตั้งค่า Aspose.Slides for Java
เพื่อเริ่มใช้ Aspose.Slides, ให้เพิ่มเข้าไปในโปรเจกต์ของคุณโดยใช้ Maven หรือ Gradle.

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

หรือคุณสามารถ [ดาวน์โหลดเวอร์ชันล่าสุดโดยตรง](https://releases.aspose.com/slides/java/).

### ขั้นตอนการรับลิขสิทธิ์
Aspose.Slides มีลิขสิทธิ์ทดลองฟรีเพื่อสำรวจความสามารถทั้งหมดของมัน คุณยังสามารถขอรับลิขสิทธิ์ชั่วคราวหรือซื้อเพื่อใช้งานต่อเนื่อง ทำตามขั้นตอนเหล่านี้:
1. เยี่ยมชม [หน้า Aspose Purchase](https://purchase.aspose.com/buy) เพื่อรับลิขสิทธิ์ของคุณ.  
2. สำหรับการทดลองใช้ฟรี, ดาวน์โหลดจาก [Releases](https://releases.aspose.com/slides/java/).  
3. ขอรับลิขสิทธิ์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/).

เมื่อคุณมีไฟล์ลิขสิทธิ์แล้ว, ให้ทำการเริ่มต้นในแอปพลิเคชัน Java ของคุณ:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## คู่มือการใช้งาน

### ฟีเจอร์ 1: โหลดพรีเซนเทชัน
การโหลดพรีเซนเทชันเป็นขั้นตอนแรกของงานจัดการใด ๆ

#### ภาพรวม
ฟีเจอร์นี้แสดงวิธีการโหลดไฟล์ PowerPoint ที่มีอยู่โดยใช้ Aspose.Slides for Java.

#### การดำเนินการแบบขั้นตอนต่อขั้นตอน
**โหลดพรีเซนเทชัน**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```
**คำอธิบาย:**  
- `Presentation` ถูกกำหนดค่าเริ่มต้นด้วยเส้นทางไปยังไฟล์ `.pptx` ของคุณ.  
- ควรทำการ dispose วัตถุ `Presentation` เสมอเพื่อปล่อยทรัพยากรพื้นฐาน.

### ฟีเจอร์ 2: เพิ่มสไลด์แผนภูมิวงกลม
การเพิ่มแผนภูมิสามารถเสริมการนำเสนอข้อมูลได้อย่างมาก, และนักพัฒนาหลายคนถาม **how to add chart slide** ใน Java.

#### ภาพรวม
ฟีเจอร์นี้แสดงวิธีการเพิ่ม **pie chart slide** (สถานการณ์คลาสสิก “add pie chart slide”) ไปยังสไลด์แรกของพรีเซนเทชัน.

#### การดำเนินการแบบขั้นตอนต่อขั้นตอน
**เพิ่มแผนภูมิวงกลม**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**คำอธิบาย:**  
- `addChart` แทรกแผนภูมิวงกลม.  
- พารามิเตอร์กำหนดประเภทของแผนภูมิและตำแหน่ง/ขนาดบนสไลด์.

### ฟีเจอร์ 3: สร้าง Excel จากแผนภูมิ
การส่งออกข้อมูลแผนภูมิทำให้คุณสามารถ **generate excel from chart** เพื่อการวิเคราะห์ที่ลึกซึ้งยิ่งขึ้น.

#### ภาพรวม
ฟีเจอร์นี้แสดงการส่งออกข้อมูลแผนภูมิจากพรีเซนเทชันไปยัง workbook Excel ภายนอก.

#### การดำเนินการแบบขั้นตอนต่อขั้นตอน
**ส่งออกข้อมูล**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**คำอธิบาย:**  
- `readWorkbookStream` ดึงข้อมูล workbook ของแผนภูมิ.  
- อาเรย์ไบต์จะถูกเขียนลงไฟล์ `.xlsx` ด้วย `FileOutputStream`.

### ฟีเจอร์ 4: ฝังแผนภูมิในพรีเซนเทชันพร้อม Workbook ภายนอก
การเชื่อมโยงแผนภูมิกับ workbook ภายนอกช่วยให้คุณ **embed chart in presentation** และรักษาการซิงโครไนซ์ของข้อมูล.

#### ภาพรวม
ฟีเจอร์นี้แสดงการตั้งค่าเส้นทาง workbook ภายนอกเพื่อให้แผนภูมิสามารถอ่าน/เขียนข้อมูลโดยตรงจาก Excel.

#### การดำเนินการแบบขั้นตอนต่อขั้นตอน
**ตั้งค่าเส้นทาง Workbook ภายนอก**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**คำอธิบาย:**  
- `setExternalWorkbook` เชื่อมแผนภูมิกับไฟล์ Excel, ทำให้สามารถอัปเดตแบบไดนามิกโดยไม่ต้องสร้างสไลด์ใหม่.

## การประยุกต์ใช้งานจริง
Aspose.Slides มีโซลูชันที่หลากหลายสำหรับสถานการณ์ต่าง ๆ:

1. **Business Reports:** สร้างรายงานละเอียดพร้อมแผนภูมิโดยตรงจากแอปพลิเคชัน Java.  
2. **Academic Presentations:** ปรับปรุงการบรรยายด้วยสไลด์แผนภูมิวงกลมแบบโต้ตอบ.  
3. **Financial Analysis:** **Export chart to excel** สำหรับการสร้างโมเดลการเงินเชิงลึก.  
4. **Marketing Analytics:** แสดงผลการทำแคมเปญและ **generate excel from chart** สำหรับทีมวิเคราะห์.

## คำถามที่พบบ่อย

**Q: Can I use this approach with other chart types (e.g., Bar, Line)?**  
A: แน่นอน. แทนที่ `ChartType.Pie` ด้วยค่า enum `ChartType` ใด ๆ ที่ต้องการ.

**Q: Do I need a separate Excel library to read the exported file?**  
A: ไม่จำเป็น. ไฟล์ `.xlsx` ที่ส่งออกเป็น workbook Excel มาตรฐานที่สามารถเปิดด้วยแอปสเปรดชีตใดก็ได้.

**Q: How does the external workbook affect slide size?**  
A: การเชื่อมโยงกับ workbook ภายนอกไม่ได้เพิ่มขนาดไฟล์ PPTX อย่างมีนัยสำคัญ; แผนภูมิอ้างอิง workbook ในขณะรันไทม์.

**Q: Is it possible to update the Excel data and have the slide reflect changes automatically?**  
A: ใช่. หลังจากเรียก `setExternalWorkbook`, การเปลี่ยนแปลงใด ๆ ที่บันทึกลงใน workbook จะปรากฏในสไลด์เมื่อเปิดพรีเซนเทชันครั้งต่อไป.

**Q: What if I need to export multiple charts from the same presentation?**  
A: ทำการวนลูปผ่านคอลเลกชันแผนภูมิของแต่ละสไลด์, เรียก `readWorkbookStream()` สำหรับแต่ละอัน, แล้วเขียนเป็นไฟล์ workbook แยกกัน.

---

**อัปเดตล่าสุด:** 2026-01-14  
**ทดสอบกับ:** Aspose.Slides 25.4 for Java  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}