---
"date": "2025-04-17"
"description": "เรียนรู้การสร้างและส่งออกแผนภูมิโดยใช้ Aspose.Slides ใน Java เรียนรู้เทคนิคการสร้างภาพข้อมูลด้วยคำแนะนำทีละขั้นตอนและตัวอย่างโค้ด"
"title": "Aspose.Slides Java&#58; การสร้างและการส่งออกแผนภูมิสำหรับการแสดงข้อมูล"
"url": "/th/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างและการส่งออกแผนภูมิโดยใช้ Aspose.Slides Java

**เรียนรู้เทคนิคการสร้างภาพข้อมูลอย่างเชี่ยวชาญด้วย Aspose.Slides สำหรับ Java**

ในภูมิทัศน์ที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน การแสดงข้อมูลอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับการตัดสินใจอย่างรอบรู้ การรวมฟังก์ชันแผนภูมิเข้ากับแอปพลิเคชัน Java ของคุณสามารถแปลงข้อมูลดิบให้กลายเป็นเรื่องราวภาพที่น่าสนใจได้ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างและส่งออกแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java เพื่อให้แน่ใจว่าการนำเสนอของคุณทั้งให้ข้อมูลและดึงดูดสายตา

**สิ่งที่คุณจะได้เรียนรู้:**
- โหลดและจัดการไฟล์การนำเสนอได้อย่างง่ายดาย
- เพิ่มแผนภูมิประเภทต่างๆ ลงในสไลด์ของคุณ
- ส่งออกข้อมูลแผนภูมิไปยังสมุดงานภายนอกได้อย่างราบรื่น
- กำหนดเส้นทางเวิร์กบุ๊กภายนอกเพื่อการจัดการข้อมูลที่มีประสิทธิภาพ

มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีการตั้งค่าต่อไปนี้พร้อมแล้ว:

### ไลบรารีและเวอร์ชันที่จำเป็น
- **Aspose.Slides สำหรับ Java** เวอร์ชัน 25.4 ขึ้นไป

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- Java Development Kit (JDK) 16 หรือสูงกว่า
- โปรแกรมแก้ไขโค้ดหรือ IDE เช่น IntelliJ IDEA หรือ Eclipse

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- ความคุ้นเคยกับระบบสร้าง Maven หรือ Gradle

## การตั้งค่า Aspose.Slides สำหรับ Java
หากต้องการเริ่มใช้ Aspose.Slides คุณต้องรวม Aspose.Slides ไว้ในโปรเจ็กต์ของคุณ ดังต่อไปนี้:

**เมเวน**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**แกรเดิล**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

อีกทางเลือกหนึ่งคุณสามารถทำได้ [ดาวน์โหลดเวอร์ชันล่าสุดได้โดยตรง](https://releases-aspose.com/slides/java/).

### ขั้นตอนการรับใบอนุญาต
Aspose.Slides เสนอใบอนุญาตทดลองใช้งานฟรีเพื่อสำรวจความสามารถทั้งหมด คุณสามารถสมัครใบอนุญาตชั่วคราวหรือซื้อใบอนุญาตสำหรับการใช้งานต่อเนื่องได้ ทำตามขั้นตอนเหล่านี้:
1. เยี่ยมชม [หน้าสั่งซื้อ Aspose](https://purchase.aspose.com/buy) เพื่อรับใบอนุญาตของคุณ
2. สำหรับการทดลองใช้ฟรี โปรดดาวน์โหลดจาก [การเปิดตัว](https://releases-aspose.com/slides/java/).
3. การขอใบอนุญาตชั่วคราว [ที่นี่](https://purchase-aspose.com/temporary-license/).

เมื่อคุณมีไฟล์ลิขสิทธิ์แล้ว ให้เริ่มต้นใช้งานในแอปพลิเคชัน Java ของคุณ:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## คู่มือการใช้งาน
### คุณสมบัติ 1: การนำเสนอโหลด
การโหลดงานนำเสนอเป็นขั้นตอนแรกของงานการจัดการใดๆ

#### ภาพรวม
ฟีเจอร์นี้สาธิตวิธีโหลดไฟล์ PowerPoint ที่มีอยู่โดยใช้ Aspose.Slides สำหรับ Java

#### การดำเนินการแบบทีละขั้นตอน
**เพิ่มแผนภูมิลงในสไลด์**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // โหลดการนำเสนอที่มีอยู่
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // ทำความสะอาดทรัพยากร
        if (pres != null) pres.dispose();
    }
}
```
**คำอธิบาย:**
- `Presentation` จะถูกเริ่มต้นด้วยเส้นทางไปยังของคุณ `.pptx` ไฟล์.
- กำจัดทิ้งเสมอ `Presentation` คัดค้านการใช้ทรัพยากรฟรี

### คุณลักษณะที่ 2: เพิ่มแผนภูมิลงในสไลด์
การเพิ่มแผนภูมิสามารถเพิ่มประสิทธิภาพการนำเสนอข้อมูลได้อย่างมาก

#### ภาพรวม
คุณลักษณะนี้จะแสดงวิธีการเพิ่มแผนภูมิวงกลมลงในสไลด์แรกของการนำเสนอ

#### การดำเนินการแบบทีละขั้นตอน
**เพิ่มแผนภูมิลงในสไลด์**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // เพิ่มแผนภูมิวงกลมที่ตำแหน่ง (50, 50) โดยมีความกว้าง 400 และความสูง 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**คำอธิบาย:**
- `addChart` วิธีนี้ใช้ในการแทรกแผนภูมิวงกลม
- พารามิเตอร์ได้แก่ ประเภทของแผนภูมิและตำแหน่ง/ขนาดบนสไลด์

### คุณสมบัติที่ 3: ส่งออกข้อมูลแผนภูมิไปยังสมุดงานภายนอก
การส่งออกข้อมูลช่วยให้สามารถวิเคราะห์เพิ่มเติมนอก PowerPoint ได้

#### ภาพรวม
คุณลักษณะนี้สาธิตการส่งออกข้อมูลแผนภูมิจากการนำเสนอไปยังเวิร์กบุ๊ก Excel ภายนอก

#### การดำเนินการแบบทีละขั้นตอน
**การส่งออกข้อมูล**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // ตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารและไดเร็กทอรีเอาท์พุตของคุณ
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // เข้าถึงแผนภูมิสไลด์แรก
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // กำหนดเส้นทางสำหรับสมุดงานภายนอก
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // ส่งออกข้อมูลแผนภูมิไปยังสตรีม Excel
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
- `readWorkbookStream` ดึงข้อมูลแผนภูมิ
- ข้อมูลจะถูกเขียนลงในไฟล์ Excel โดยใช้ `FileOutputStream`-

### คุณสมบัติที่ 4: ตั้งค่าเวิร์กบุ๊กภายนอกสำหรับข้อมูลแผนภูมิ
การเชื่อมโยงแผนภูมิกับสมุดงานภายนอกสามารถทำให้การจัดการข้อมูลมีประสิทธิภาพมากขึ้น

#### ภาพรวม
คุณลักษณะนี้สาธิตการตั้งค่าเส้นทางเวิร์กบุ๊กภายนอกเพื่อจัดเก็บข้อมูลแผนภูมิ

#### การดำเนินการแบบทีละขั้นตอน
**ตั้งค่าเส้นทางเวิร์กบุ๊กภายนอก**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // เข้าถึงแผนภูมิสไลด์แรก
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // กำหนดและตั้งค่าเส้นทางสำหรับสมุดงานภายนอก
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**คำอธิบาย:**
- `setExternalWorkbook` เชื่อมโยงแผนภูมิกับไฟล์ Excel ช่วยให้สามารถอัปเดตข้อมูลแบบไดนามิกได้

## การประยุกต์ใช้งานจริง
Aspose.Slides นำเสนอโซลูชันที่หลากหลายสำหรับสถานการณ์ต่างๆ:

1. **รายงานทางธุรกิจ:** สร้างรายงานโดยละเอียดพร้อมแผนภูมิโดยตรงจากแอปพลิเคชัน Java
2. **การนำเสนอผลงานทางวิชาการ:** ปรับปรุงเนื้อหาการศึกษาด้วยแผนภูมิเชิงโต้ตอบ
3. **การวิเคราะห์ทางการเงิน:** ส่งออกข้อมูลทางการเงินไปยัง Excel เพื่อการวิเคราะห์เชิงลึก
4. **การวิเคราะห์การตลาด:** แสดงภาพประสิทธิภาพของแคมเปญโดยใช้แผนภูมิแบบไดนามิก

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}