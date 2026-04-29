---
date: '2026-02-12'
description: เรียนรู้วิธีสร้างแผนภูมิและจัดการแผนภูมิด้วย Aspose.Slides for Java บทเรียนนี้แสดงวิธีสร้างแผนภูมิคอลัมน์แบบกลุ่ม,
  จัดการชุดข้อมูล, และปรับแต่งการแสดงผล.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides: คู่มือฉบับสมบูรณ์'
url: /th/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีสร้างแผนภูมิใน Java ด้วย Aspose.Slides

## วิธีสร้างแผนภูมิใน Java: บทนำ
การสร้างงานนำเสนอแบบไดนามิกมักต้องการการแสดงข้อมูลผ่านแผนภูมิ ด้วย **Aspose.Slides for Java** คุณสามารถสร้างวัตถุ **how to create chart** ได้อย่างง่ายดาย เพิ่มความชัดเจน และสร้างผลกระทบที่แข็งแรงต่อผู้ชม tutorial นี้จะพาคุณผ่านการตั้งค่าห้องสมุด การเพิ่ม **create clustered column chart** การจัดการ series และการกลับค่าติดลบแบบมีเงื่อนไข

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า Aspose.Slides for Java
- ขั้นตอนการ **create clustered column chart** ในงานนำเสนอของคุณ
- เทคนิคการจัดการ series และ data point ของแผนภูมิ
- วิธีการกลับค่าติดลบแบบมีเงื่อนไขเพื่อการแสดงผลที่ดียิ่งขึ้น
- วิธีบันทึกงานนำเสนออย่างปลอดภัย

### คำตอบสั้น ๆ
- **ห้องสมุดที่ใช้คืออะไร?** Aspose.Slides for Java
- **ประเภทแผนภูมิที่แสดงคืออะไร?** Clustered column chart
- **ฉันสามารถกลับค่าติดลบได้หรือไม่?** ได้ โดยใช้ `invertIfNegative`
- **ต้องการเวอร์ชัน Java ใด?** JDK 16 หรือใหม่กว่า
- **ต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** ต้อง มีไลเซนส์ Aspose ที่ถูกต้อง

## Clustered Column Chart คืออะไร?
Clustered column chart แสดงหลาย series ของข้อมูลเคียงข้างกันสำหรับแต่ละหมวดหมู่ ทำให้เปรียบเทียบค่าต่าง ๆ ระหว่างกลุ่มได้ง่าย เหมาะสำหรับรายงานการเงิน แดชบอร์ดการขาย และสถานการณ์ใด ๆ ที่ต้องการเปรียบเทียบเมตริกหลายตัว

## ทำไมต้องใช้ Aspose.Slides สำหรับการสร้างแผนภูมิ?
- **การควบคุมเต็มรูปแบบ** ของลักษณะแผนภูมิโดยไม่ต้องพึ่งพา UI ของ PowerPoint
- **การสร้างแบบโปรแกรม** ช่วยให้สามารถทำอัตโนมัติใน pipeline รายงาน
- **รองรับข้ามแพลตฟอร์ม** ทำให้โค้ดของคุณทำงานได้บนระบบที่รองรับ Java ทุกระบบ
- **API ที่ครอบคลุม** สำหรับการปรับแต่งละเอียด (สี, ป้ายข้อมูล, การกลับค่า, ฯลฯ)

## ข้อกำหนดเบื้องต้น
1. **ห้องสมุดที่ต้องการ**
   - Aspose.Slides for Java (เวอร์ชัน 25.4 หรือใหม่กว่า)

2. **สภาพแวดล้อม**
   - JDK 16 หรือใหม่กว่า
   - Maven หรือ Gradle สำหรับการจัดการ dependency

3. **ความรู้พื้นฐาน**
   - การเขียนโปรแกรม Java เบื้องต้น
   - ความคุ้นเคยกับเครื่องมือสร้าง (Maven/Gradle)

## การตั้งค่า Aspose.Slides for Java
### การติดตั้งด้วย Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การติดตั้งด้วย Gradle
เพิ่มบรรทัดต่อไปนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

### การรับไลเซนส์
- **Free Trial:** ทดลองใช้ฟีเจอร์โดยไม่ต้องมีไลเซนส์
- **Temporary License:** ใช้ระหว่างการประเมิน
- **Full License:** ซื้อสำหรับการใช้งานในผลิตภัณฑ์

### การเริ่มต้นพื้นฐาน
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: สร้าง Presentation และเพิ่ม Clustered Column Chart
ในขั้นตอนนี้เราจะ **how to create chart** วัตถุและวาง **create clustered column chart** บนสไลด์แรก

```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### ขั้นตอนที่ 2: จัดการ Series ของแผนภูมิ
ต่อไปเราจะลบ series เริ่มต้นทั้งหมด เพิ่ม series ใหม่ และใส่ค่าบวกและค่าลบลงไป

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### ขั้นตอนที่ 3: กลับค่าติดลบแบบมีเงื่อนไข
โดยค่าเริ่มต้น Aspose.Slides จะไม่กลับค่าติดลบ เราจะเปิดการกลับค่าเฉพาะจุดที่ต้องการเท่านั้น

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ลืมเรียก `dispose()` กับอ็อบเจ็กต์ `Presentation`?** ควรเรียก `dispose()` ในบล็อก `finally` เพื่อปล่อยทรัพยากรเนทีฟ
- **ค่าติดลบไม่แสดงเป็นการกลับค่า?** ตรวจสอบให้แน่ใจว่าได้เรียก `invertIfNegative(true)` **หลัง** จากการเพิ่ม data point
- **ปัญหาเรื่องขนาดแผนภูมิ:** พิกัด (X, Y) และขนาด (width, height) ใช้หน่วยเป็น points ปรับให้เหมาะกับเลย์เอาต์ของสไลด์ของคุณ

## คำถามที่พบบ่อย

**Q: ฉันสามารถสร้างแผนภูมิประเภทอื่นด้วยวิธีเดียวกันได้หรือไม่?**  
A: ได้ เพียงเปลี่ยน `ChartType.ClusteredColumn` เป็นค่า enum ของ `ChartType` อื่น ๆ (เช่น `Line`, `Pie`)

**Q: จำเป็นต้องมีไลเซนส์สำหรับการสร้าง build แบบพัฒนาไหม?**  
A: จำเป็นต้องมีไลเซนส์ชั่วคราวหรือไลเซนส์ประเมินเพื่อเข้าถึงฟีเจอร์เต็ม หากไม่มีจะทำงานในโหมดทดลองพร้อมข้อจำกัดของลายน้ำ

**Q: ฉันจะส่งออกงานนำเสนอเป็น PDF หลังจากเพิ่มแผนภูมิได้อย่างไร?**  
A: ใช้ `pres.save("output.pdf", SaveFormat.Pdf);` หลังจากทำการจัดการแผนภูมิเสร็จ

**Q: สามารถกำหนดสไตล์ให้คอลัมน์แต่ละคอลัมน์ (สี, เส้นขอบ) ได้หรือไม่?**  
A: ได้ แต่ละ `IChartDataPoint` มีตัวเลือกการฟอร์แมต เช่น `getFillFormat().setFillType(FillType.Solid)` และ `getLineFormat()`

**Q: ถ้าต้องการอัปเดตข้อมูลแผนภูมิหลังจากบันทึกงานนำเสนอแล้วทำอย่างไร?**  
A: โหลดงานนำเสนอใหม่ด้วย `new Presentation("file.pptx")` แก้ไขข้อมูลแผนภูมิ แล้วบันทึกใหม่

---

**Last Updated:** 2026-02-12  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}