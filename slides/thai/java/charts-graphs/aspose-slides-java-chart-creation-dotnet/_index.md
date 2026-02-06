---
date: '2026-02-06'
description: เรียนรู้วิธีเริ่มต้นงานนำเสนอด้วย Aspose Slides และปรับแต่งแผนภูมิคอลัมน์แบบกลุ่มใน
  .NET ด้วย Aspose.Slides for Java ทำตามคำแนะนำขั้นตอนต่อขั้นตอนนี้เพื่อเพิ่มการแสดงผลข้อมูล
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'เริ่มต้นการนำเสนอด้วย Aspose Slides: แผนภูมิ .NET'
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างแผนภูมิในงานนำเสนอ .NET ด้วย Aspose.Slides for Java

## บทนำ
ในบทเรียนนี้คุณจะ **initialize presentation Aspose Slides** และเรียนรู้วิธีฝังแผนภูมิที่ปรับเปลี่ยนได้และกำหนดค่าได้ลงในสไลด์ .NET ของคุณ ข้อมูลภาพ—เช่นแผนภูมิคอลัมน์แบบกลุ่ม—ช่วยให้ผู้ชมของคุณเข้าใจแนวโน้มได้ทันที และ Aspose.Slides for Java ให้การควบคุมแบบโปรแกรมเต็มรูปแบบแม้คุณจะกำหนดเป้าหมายเป็นสภาพแวดล้อม .NET เราจะอธิบายขั้นตอนการตั้งค่าห้องสมุด การสร้างงานนำเสนอใหม่ การเพิ่มแผนภูมิ การใส่ข้อมูล และการใช้เทคนิคการจัดรูปแบบ เช่น การทำสีค่าติดลบ

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า Aspose.Slides for Java ในโครงการ .NET  
- วิธี **initialize presentation Aspose Slides** และเพิ่มแผนภูมิ  
- วิธี **customize clustered column chart** ซีรีส์และหมวดหมู่  
- การจัดการ data workbook ของแผนภูมิและการใช้ conditional formatting  

### คำตอบเร็ว
- **ขั้นตอนแรกคืออะไร?** Initialize a `Presentation` object.  
- **ประเภทแผนภูมิที่ใช้ในตัวอย่างคืออะไร?** `ClusteredColumn`.  
- **ฉันสามารถจัดรูปแบบค่าติดลบให้แตกต่างได้หรือไม่?** ใช่, โดยใช้ conditional fill colors.  
- **ฉันต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** ไลเซนส์ทดลองฟรีใช้ได้สำหรับการพัฒนา.  
- **Maven artifact ที่ต้องการคืออะไร?** `com.aspose:aspose-slides:25.4` พร้อม classifier `jdk16`.  

## “initialize presentation Aspose Slides” คืออะไร?
การเริ่มต้นงานนำเสนอจะสร้างไฟล์ PPTX ในหน่วยความจำที่คุณสามารถจัดการได้ก่อนบันทึก Aspose.Slides ทำให้คุณไม่ต้องจัดการกับโครงสร้าง OPC ระดับต่ำโดยตรง สามารถเพิ่มสไลด์ รูปร่าง และแผนภูมิได้

## ทำไมต้องปรับแต่งแผนภูมิคอลัมน์แบบกลุ่ม?
แผนภูมิคอลัมน์แบบกลุ่มเหมาะสำหรับการเปรียบเทียบหลายซีรีส์ข้อมูลในแต่ละหมวดหมู่ การปรับแต่งสี จุดข้อมูล และป้ายกำกับช่วยให้คุณเน้นข้อมูลสำคัญ—เช่นทำให้ค่าติดลบเป็นสีแดงและค่าบวกเป็นสีเขียว—ทำให้สไลด์ของคุณน่าสนใจยิ่งขึ้น

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** ≥ 25.4  
- สภาพแวดล้อมการพัฒนา .NET (Visual Studio, แนะนำ .NET 6+)  
- ความรู้พื้นฐาน Java (คุณจะเขียนโค้ด Java ที่ทำงานบน JVM และเรียกจาก .NET ผ่าน JNI หรือชั้นเชื่อมต่อ)  

### ไลบรารีและเวอร์ชันที่ต้องการ
- **Aspose.Slides for Java**: เวอร์ชัน 25.4 หรือใหม่กว่า.  

### ความต้องการการตั้งค่าสภาพแวดล้อม
- Java runtime ที่เข้ากันได้กับ .NET (เช่น AdoptOpenJDK 16).  
- Maven หรือ Gradle สำหรับการจัดการ dependencies.  

### ความรู้พื้นฐานที่ต้องมี
- ความคุ้นเคยกับการสร้างงานนำเสนอในบริบท .NET.  
- ความเข้าใจในการกำหนดค่าโครงการ Java (Maven/Gradle).  

## การตั้งค่า Aspose.Slides for Java
เพิ่มไลบรารีลงในโครงการของคุณโดยใช้เครื่องมือสร้างที่คุณชื่นชอบ

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
คุณยังสามารถดาวน์โหลด JAR ล่าสุดจากหน้าปล่อยอย่างเป็นทางการ: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### ขั้นตอนการรับไลเซนส์
- **Free Trial** – สร้างไฟล์ไลเซนส์ชั่วคราวสำหรับการพัฒนา.  
- **Purchase** – รับไลเซนส์เต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  

#### การเริ่มต้นและตั้งค่าเบื้องต้น
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
บล็อก `try/finally` รับประกันว่าทรัพยากรเนทีฟจะถูกปล่อยออก, ป้องกันการรั่วของหน่วยความจำ.

## วิธีการ initialize presentation Aspose Slides
ต่อไปนี้เป็นขั้นตอนที่ชัดเจนสำหรับการสร้างงานนำเสนอใหม่และเตรียมพร้อมสำหรับการแทรกแผนภูมิ

### การเริ่มต้น Presentation
**ภาพรวม:**  
การสร้างอินสแตนซ์ของงานนำเสนอเป็นการตั้งค่าพื้นฐานสำหรับการดำเนินการต่อไปทั้งหมด.

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
```

#### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์ Presentation ใหม่
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*สิ่งนี้ทำให้แน่ใจว่าอ็อบเจ็กต์ presentation จะถูกทำลายอย่างเหมาะสมหลังการใช้งาน, ป้องกันการรั่วของหน่วยความจำ.*

## วิธีการ customize clustered column chart
เมื่อการนำเสนอพร้อมแล้ว, เรามาเพิ่มและปรับแต่งแผนภูมิคอลัมน์แบบกลุ่มกัน

### การเพิ่มแผนภูมิลงสไลด์
**ภาพรวม:**  
การเพิ่มแผนภูมิทำให้ข้อมูลมีชีวิตบนสไลด์.

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### ขั้นตอนที่ 2: เริ่มต้น Presentation และเพิ่มแผนภูมิ
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*ที่นี่, เราเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์แรกที่พิกัดและขนาดที่กำหนด.*

### การจัดการ Chart Data Workbook
**ภาพรวม:**  
การจัดการ data workbook ของแผนภูมิอย่างมีประสิทธิภาพทำให้คุณสามารถจัดการซีรีส์และหมวดหมู่ได้อย่างราบรื่น.

#### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### ขั้นตอนที่ 2: เข้าถึงและล้าง Data Workbook
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*การล้าง workbook มีความสำคัญเพื่อเริ่มต้นด้วยแผ่นงานว่างเมื่อเพิ่มซีรีส์และหมวดหมู่ใหม่.*

### การเพิ่ม Series และ Categories ลงในแผนภูมิ
**ภาพรวม:**  
ขั้นตอนนี้แสดงวิธีการเพิ่มจุดข้อมูลที่มีความหมายโดยการจัดการซีรีส์และหมวดหมู่.

#### ขั้นตอนที่ 1: เพิ่ม Series และ Categories
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*การเพิ่ม series และ categories ทำให้การนำเสนอข้อมูลเป็นระเบียบมากขึ้น.*

### การใส่ข้อมูล Series และการจัดรูปแบบ
**ภาพรวม:**  
ใส่ข้อมูลจุดลงในแผนภูมิและจัดรูปแบบเพื่อเพิ่มความอ่านง่าย, โดยเฉพาะเมื่อจัดการค่าติดลบ.

#### ขั้นตอนที่ 1: ใส่ข้อมูล Series
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*ส่วนนี้แสดงวิธีการใส่ข้อมูลและใช้การจัดรูปแบบสีเพื่อการมองเห็นที่ดียิ่งขึ้น.*

## ปัญหาที่พบบ่อยและวิธีแก้
- **Memory leaks** – ควรห่ออ็อบเจ็กต์ `Presentation` ด้วยบล็อก `try/finally` ตามที่แสดงเพื่อรับประกันการทำลาย.  
- **Incorrect cell coordinates** – จำว่ารายการแถวและคอลัมน์เริ่มจากศูนย์; ดัชนีที่ไม่ตรงกันทำให้เกิด `NullPointerException`.  
- **License not found** – วางไฟล์ไลเซนส์ในไดเรกทอรีทำงานของแอปพลิเคชันหรือกำหนดเส้นทางโดยตรงผ่าน `License.setLicense("Aspose.Slides.Java.lic")`.  

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้วิธีนี้กับ .NET Core ได้หรือไม่?**  
**ตอบ:** ใช่. Aspose.Slides for Java ทำงานบน JVM ใดก็ได้และคุณสามารถเรียกโค้ด Java จาก .NET Core ผ่านบริดจ์เช่น IKVM หรือ JNI.

**ถาม: ฉันต้องการไลเซนส์แบบชำระเงินสำหรับการพัฒนาหรือไม่?**  
**ตอบ:** ไลเซนส์ทดลองฟรีเพียงพอสำหรับการพัฒนาและทดสอบ การใช้งานในสภาพแวดล้อมการผลิตต้องมีไลเซนส์ที่ซื้อไว้.

**ถาม: ฉันจะเปลี่ยนประเภทแผนภูมิหลังจากสร้างได้อย่างไร?**  
**ตอบ:** คุณสามารถเรียก `chart.getChartData().setChartType(ChartType.Pie)` เพื่อสลับเป็นประเภทแผนภูมิอื่น.

**ถาม: สามารถเพิ่มป้ายข้อมูลโดยโปรแกรมได้หรือไม่?**  
**ตอบ:** ได้. ใช้ `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` เพื่อแสดงค่าบนแผนภูมิ.

**ถาม: ฉันสามารถบันทึกงานนำเสนอในรูปแบบใดได้บ้าง?**  
**ตอบ:** Aspose.Slides รองรับ PPTX, PPT, PDF, XPS, และหลายรูปแบบภาพเช่น PNG และ JPEG.

---

**อัปเดตล่าสุด:** 2026-02-06  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}