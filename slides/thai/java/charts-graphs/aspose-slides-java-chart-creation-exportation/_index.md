---
date: '2026-06-03'
description: เรียนรู้วิธีส่งออกแผนภูมิไปยัง Excel และสร้างแผนภูมิด้วย Java โดยใช้
  Aspose.Slides for Java. เชี่ยวชาญการแสดงผลข้อมูล, สไลด์รายงานธุรกิจ, และการสร้างเวิร์กบุ๊ก.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: ส่งออกแผนภูมิไปยัง Excel และสร้างแผนภูมิด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ส่งออกแผนภูมิไปยัง Excel และสร้างแผนภูมิด้วย Aspose.Slides

**เชี่ยวชาญเทคนิคการแสดงผลข้อมูลด้วย Aspose.Slides for Java**

ในยุคที่ข้อมูลเป็นศูนย์กลางในปัจจุบัน การ *export chart to excel* ผ่านโปรแกรมเป็นทักษะที่สามารถเปลี่ยนตัวเลขดิบให้กลายเป็นเรื่องราวภาพที่น่าสนใจ ไม่ว่าคุณจะสร้างชุดสไลด์รายงานธุรกิจหรือแดชบอร์ดการวิเคราะห์แบบโต้ตอบ Aspose.Slides for Java จะมอบพลังให้คุณสร้าง ปรับแต่ง และส่งออกแผนภูมิโดยตรงจากโค้ดของคุณ ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีสร้างอ็อบเจกต์แผนภูมิ การส่งออกข้อมูลแผนภูมิไปยัง Excel และการเชื่อมแผนภูกิ์กับเวิร์กบุ๊กภายนอกเพื่อการจัดการข้อมูลที่ราบรื่น

## คำตอบสั้นๆ
- **ต้องการไลบรารีอะไร?** Aspose.Slides for Java (v25.4+).  
- **ฉันสามารถส่งออกข้อมูลแผนภูมิไปยัง Excel ได้หรือไม่?** ใช่ – ใช้ `readWorkbookStream()` และเขียนไบต์ไปยังไฟล์ *.xlsx*.  
- **ต้องการเวอร์ชัน Java ใด?** JDK 16 หรือสูงกว่า.  
- **ฉันต้องการไลเซนส์หรือไม่?** ไลเซนส์ทดลองฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์ถาวรสำหรับการใช้งานจริง.  
- **ประเภทแผนภูมิที่แสดงคืออะไร?** แผนภูมิวงกลม (Pie chart) แต่วิธีเดียวกันสามารถใช้กับแผนภูมิแท่ง, เส้น, และประเภทแผนภูมิอื่นๆ

## Aspose.Slides for Java คืออะไร?
Aspose.Slides for Java เป็น API แบบ pure‑Java ที่ทำให้นักพัฒนาสามารถสร้าง, แก้ไข, และแปลงงานนำเสนอ PowerPoint โดยไม่ต้องใช้ Microsoft Office มันให้ชุดคลาสที่ครบถ้วนสำหรับการจัดการสไลด์, การสร้างแผนภูมิ, และการแปลงรูปแบบ, ทำให้สามารถสร้างโซลูชันการรายงานอัตโนมัติได้ รองรับ **50+ chart types**, การผูกข้อมูลเต็มรูปแบบ, และการส่งออก Excel โดยตรง ทำให้เหมาะสำหรับโครงการ **data visualization java**

## ทำไมต้องใช้ Aspose.Slides เพื่อสร้างแผนภูมิและส่งออกแผนภูมิไปยัง Excel?
ส่งออกแผนภูมิไปยัง Excel อย่างรวดเร็วและเชื่อถือได้ Aspose.Slides ขจัดความจำเป็นในการติดตั้ง Office, มี **over 50‑built‑in chart styles**, และประมวลผลงานนำเสนอ **up to 300 MB in under 30 seconds** บนฮาร์ดแวร์เซิร์ฟเวอร์มาตรฐาน คุณยังได้รับการสร้างเวิร์กบุ๊ก Excel แบบเนทีฟ ซึ่งทำให้ผู้วิเคราะห์ต่อไปสามารถทำงานกับตัวเลขดิบโดยไม่ต้องคัดลอก‑วางด้วยตนเอง

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มลงลึก, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### ไลบรารีและเวอร์ชันที่จำเป็น
- **Aspose.Slides for Java** เวอร์ชัน 25.4 หรือใหม่กว่า (รองรับ JDK 16+)

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- Java Development Kit (JDK) 16 หรือสูงกว่า  
- IDE เช่น IntelliJ IDEA หรือ Eclipse (หรือโปรแกรมแก้ไขข้อความใดก็ได้ที่คุณชอบ)

### ความรู้เบื้องต้นที่จำเป็น
- ทักษะการเขียนโปรแกรม Java พื้นฐาน  
- ความคุ้นเคยกับเครื่องมือสร้าง Maven หรือ Gradle

## การตั้งค่า Aspose.Slides for Java
เพิ่มไลบรารีลงในโปรเจกต์ของคุณโดยใช้ระบบสร้างที่คุณชื่นชอบ.

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

### ขั้นตอนการรับไลเซนส์
Aspose.Slides มีไลเซนส์ทดลองฟรีเพื่อสำรวจความสามารถทั้งหมดของมัน คุณยังสามารถขอไลเซนส์ชั่วคราวหรือซื้อไลเซนส์สำหรับการใช้งานต่อเนื่อง ทำตามขั้นตอนต่อไปนี้:

1. เยี่ยมชม [หน้า Aspose Purchase](https://purchase.aspose.com/buy) เพื่อรับไลเซนส์ของคุณ.  
2. สำหรับการทดลองฟรี, ดาวน์โหลดจาก [Releases](https://releases.aspose.com/slides/java/).  
3. ขอไลเซนส์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/).

เมื่อคุณมีไฟล์ไลเซนส์แล้ว, ให้เริ่มต้นในแอปพลิเคชัน Java ของคุณ:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## คู่มือขั้นตอนโดยละเอียด

### วิธีสร้างแผนภูมิ – โหลดการนำเสนอ
โหลดไฟล์ PowerPoint ที่มีอยู่ก่อนที่คุณจะเพิ่มหรือแก้ไขแผนภูมิ.  
`Presentation` class แสดงไฟล์ PowerPoint ในหน่วยความจำ, เปิดเผยสไลด์, รูปร่าง, และอ็อบเจกต์แผนภูมิ.  
โหลดไฟล์ของคุณด้วย `new Presentation("input.pptx")`, จากนั้นทำงานกับสไลด์แรกโดยใช้ `presentation.getSlides().get_Item(0)`. ควรเรียก `presentation.dispose()` ในบล็อก `finally` เสมอเพื่อปล่อยทรัพยากรเนทีฟ.

### วิธีสร้างแผนภูมิ – เพิ่มแผนภูมวงกลมลงในสไลด์
แทรกแผนภูมวงกลม, เหมาะสำหรับแสดงข้อมูลเชิงสัดส่วน.  
`IChart` interface เป็นจุดเริ่มต้นหลักสำหรับการจัดการแผนภูมิ; `addChart` สร้างแผนภูมิใหม่บนสไลด์เป้าหมาย. ระบุประเภทแผนภูมิ (`ChartType.Pie`), พิกัด X/Y, และความกว้าง/ความสูง. หลังจากสร้าง, คุณสามารถปรับแต่งหัวเรื่อง, เลเจนด์, และชุดข้อมูลผ่านอ็อบเจกต์ `ChartData`.

### วิธีส่งออกแผนภูมิไปยัง Excel – ส่งออกข้อมูลแผนภูมิ
การส่งออกข้อมูลแผนภูมิทำให้ผู้วิเคราะห์สามารถทำงานกับตัวเลขใน Excel, เปิดโอกาสให้ได้ข้อมูลเชิงลึกที่ลึกซึ้งยิ่งขึ้น.  
`readWorkbookStream()` คืนค่าเวิร์กบุ๊ก Excel ที่อยู่ภายใต้แผนภูมิเป็นอาร์เรย์ของไบต์. เรียก `chart.getChartData().readWorkbookStream()` เพื่อดึงเวิร์กบุ๊กและเขียนอาร์เรย์นี้ไปยังไฟล์ชื่อ `externalWorkbook1.xlsx` ด้วย Java I/O มาตรฐาน. ไฟล์ Excel ที่ได้จะมีข้อมูลที่ใช้โดยแผนภูมิอย่างแม่นยำ, พร้อมสำหรับการวิเคราะห์ต่อไป.

### วิธีสร้างแผนภูมิ – ตั้งค่าเวิร์กบุ๊กภายนอกสำหรับข้อมูลแบบไดนามิก
เชื่อมแผนภูมิกับเวิร์กบุ๊กภายนอกเพื่อเปิดใช้งานการอัปเดตข้อมูลแบบเรียลไทม์โดยไม่ต้องสร้างสไลด์ใหม่.  
`setExternalWorkbook()` ผูกแผนภูกิ์กับไฟล์ Excel ภายนอกสำหรับการอัปเดตข้อมูลแบบไดนามิก. ใช้ `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` เพื่อผูกแผนภูกิ์กับไฟล์ภายนอก. เมื่อเวิร์กบุ๊ก Excel ถูกแก้ไข, แผนภูมิจะสะท้อนการเปลี่ยนแปลงโดยอัตโนมัติในครั้งต่อไปที่เปิดงานนำเสนอ, รองรับสถานการณ์การรายงานแบบไดนามิก.

## การประยุกต์ใช้งานจริง
Aspose.Slides มีโซลูชันที่หลากหลายสำหรับสถานการณ์จริงหลายประเภท:

1. **สไลด์รายงานธุรกิจ:** สร้างแผนภูมิบรรจุผลการดำเนินงานไตรมาสโดยอัตโนมัติจากสายข้อมูลของคุณ.  
2. **การนำเสนอทางวิชาการ:** แปลงข้อมูลการวิจัยเป็นภาพแสดงที่ชัดเจนโดยไม่ต้องสร้างแผนภูมิมือ.  
3. **การวิเคราะห์ทางการเงิน:** ส่งออกข้อมูลแผนภูมิไปยัง Excel เพื่อให้ผู้ตรวจสอบตรวจสอบตัวเลข, ลดข้อผิดพลาดจากการทำมือ.  
4. **การวิเคราะห์การตลาด:** แสดงเมตริกของแคมเปญและแชร์เวิร์กบุ๊กที่แก้ไขได้กับผู้มีส่วนได้ส่วนเสียเพื่อการตัดสินใจร่วมกัน.  
5. **การสร้างแดชบอร์ดอัตโนมัติ:** ผสาน API การสร้างแผนภูมิกับงานที่กำหนดเวลาเพื่อผลิตสไลด์เด็คที่อัปเดตทุกเช้า.

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **`FileNotFoundException`** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและเส้นทางเอาต์พุตสามารถเขียนได้.  
- **Memory leaks** – เรียก `presentation.dispose()` ในบล็อก `finally` เสมอเพื่อปล่อยทรัพยากรเนทีฟ.  
- **Chart not appearing** – ตรวจสอบว่าดัชนีสไลด์ (`get_Item(0)`) ตรงกับสไลด์ที่มีอยู่, และขนาดของแผนภูมิอยู่ภายในขอบเขตของสไลด์.  
- **Excel export produces empty file** – ยืนยันว่าแผนภูมิมีชุดข้อมูลจริงก่อนเรียก `readWorkbookStream()`.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ประเภทแผนภูมิอื่น (เช่น แท่ง, เส้น) กับโค้ดเดียวกันได้หรือไม่?**  
A: ใช่. แทนที่ `ChartType.Pie` ด้วยค่า enum `ChartType` ใดก็ได้ เช่น `ChartType.Bar` หรือ `ChartType.Line`.

**Q: สามารถอัปเดตเวิร์กบุ๊กภายนอกหลังจากสร้างแผนภูมิแล้วได้หรือไม่?**  
A: แน่นอน. แก้ไขไฟล์ Excel โดยตรง; แผนภูมิที่เชื่อมโยงจะสะท้อนการเปลี่ยนแปลงในครั้งต่อไปที่เปิดงานนำเสนอ.

**Q: ฉันต้องการไลเซนส์แยกสำหรับฟีเจอร์การส่งออก Excel หรือไม่?**  
A: ไม่. ความสามารถการส่งออก Excel รวมอยู่ในไลเซนส์มาตรฐานของ Aspose.Slides for Java.

**Q: รองรับเวอร์ชัน Java ใดบ้าง?**  
A: Aspose.Slides for Java รองรับ JDK 16 และใหม่กว่า; เวอร์ชันก่อนหน้าอาจทำงานได้แต่ไม่ได้รับการทดสอบอย่างเป็นทางการ.

**Q: ฉันจะฝังเวิร์กบุ๊ก Excel ที่สร้างขึ้นภายในไฟล์ PPTX ได้อย่างไร?**  
A: ใช้ `chart.getChartData().setExternalWorkbook(null)` เพื่อฝังเวิร์กบุ๊ก, หรือคงลิงก์ภายนอกสำหรับการอัปเดตแบบไดนามิก.

**อัปเดตล่าสุด:** 2026-06-03  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**ผู้เขียน:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้างแผนภูมิใน Java ด้วย Aspose.Slides – เพิ่มและตรวจสอบแผนภูมิ](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [กู้คืนข้อมูลเวิร์กบุ๊กจากแผนภูมิ PowerPoint ด้วย Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [วิธีอัปเดตช่วงข้อมูลแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}