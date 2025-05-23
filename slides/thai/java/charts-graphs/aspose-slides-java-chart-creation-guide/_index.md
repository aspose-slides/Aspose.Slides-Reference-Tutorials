---
"date": "2025-04-17"
"description": "เรียนรู้วิธีการสร้างและจัดการแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java คู่มือนี้ครอบคลุมถึงแผนภูมิคอลัมน์แบบคลัสเตอร์ การจัดการชุดข้อมูล และอื่นๆ อีกมากมาย"
"title": "เรียนรู้การสร้างแผนภูมิใน Java ด้วย Aspose.Slides และคู่มือฉบับสมบูรณ์"
"url": "/th/java/charts-graphs/aspose-slides-java-chart-creation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เรียนรู้การสร้างแผนภูมิใน Java ด้วย Aspose.Slides

## วิธีการสร้างและจัดการแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java

### การแนะนำ
การสร้างงานนำเสนอแบบไดนามิกมักเกี่ยวข้องกับการแสดงข้อมูลผ่านแผนภูมิ **Aspose.Slides สำหรับ Java**คุณสามารถสร้างและจัดการแผนภูมิประเภทต่างๆ ได้อย่างง่ายดาย ซึ่งช่วยเพิ่มความชัดเจนและผลกระทบ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการสร้างการนำเสนอแบบว่างเปล่า การเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ การจัดการชุดข้อมูล และการปรับแต่งการผกผันจุดข้อมูล ทั้งหมดนี้โดยใช้ Aspose.Slides สำหรับ Java

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่า Aspose.Slides สำหรับ Java
- ขั้นตอนในการสร้างแผนภูมิคอลัมน์แบบกลุ่มในงานนำเสนอของคุณ
- เทคนิคการจัดการชุดแผนภูมิและจุดข้อมูลอย่างมีประสิทธิภาพ
- วิธีการกลับจุดข้อมูลเชิงลบตามเงื่อนไขเพื่อการแสดงภาพที่ดีขึ้น
- วิธีการบันทึกการนำเสนออย่างปลอดภัย

มาเจาะลึกข้อกำหนดเบื้องต้นกันก่อนที่จะเริ่มต้น

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. **ห้องสมุดที่จำเป็น:**
   - Aspose.Slides สำหรับ Java (เวอร์ชัน 25.4 หรือใหม่กว่า)

2. **ข้อกำหนดการตั้งค่าสภาพแวดล้อม:**
   - เวอร์ชัน JDK ที่เข้ากันได้ (เช่น JDK 16)
   - ติดตั้ง Maven หรือ Gradle หากคุณต้องการการจัดการการอ้างอิง

3. **ข้อกำหนดความรู้เบื้องต้น:**
   - ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
   - ความคุ้นเคยกับการจัดการการอ้างอิงในสภาพแวดล้อมการพัฒนาของคุณ

## การตั้งค่า Aspose.Slides สำหรับ Java
หากต้องการเริ่มใช้ Aspose.Slides ให้ทำตามขั้นตอนเหล่านี้:

**การติดตั้ง Maven:**
เพิ่มการอ้างอิงต่อไปนี้ให้กับของคุณ `pom.xml` ไฟล์:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**การติดตั้ง Gradle:**
เพิ่มบรรทัดต่อไปนี้ลงในของคุณ `build.gradle`-

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**ดาวน์โหลดโดยตรง:**
หรือดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

### การขอใบอนุญาต
- **ทดลองใช้งานฟรี:** คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ต่างๆ
- **ใบอนุญาตชั่วคราว:** รับใบอนุญาตชั่วคราวเพื่อการเข้าถึงแบบเต็มรูปแบบในช่วงระยะเวลาประเมินผลของคุณ
- **ซื้อ:** พิจารณาซื้อหากคุณพบว่ามันเหมาะกับความต้องการในระยะยาวของคุณ

### การเริ่มต้นขั้นพื้นฐาน
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// รหัสของคุณที่นี่...
pres.dispose(); // กำจัดวัตถุที่นำเสนอทุกครั้งเมื่อใช้งานเสร็จ
```

## คู่มือการใช้งาน
ตอนนี้ มาแบ่งคุณลักษณะแต่ละอย่างออกเป็นขั้นตอนที่สามารถจัดการได้

### การสร้างงานนำเสนอด้วยแผนภูมิคอลัมน์แบบคลัสเตอร์
#### ภาพรวม
หัวข้อนี้จะกล่าวถึงวิธีการสร้างงานนำเสนอเปล่าและการเพิ่มแผนภูมิคอลัมน์แบบกลุ่มตามพิกัดที่เจาะจงบนสไลด์ของคุณ

**ขั้นตอน:**
1. **เริ่มต้นวัตถุการนำเสนอ:**
   - สร้างอินสแตนซ์ใหม่ของ `Presentation`-
2. **เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์:**
   - ใช้ `getSlides().get_Item(0).getShapes().addChart()` เพื่อเพิ่มแผนภูมิ
   - ระบุตำแหน่ง ขนาด และประเภท

**ตัวอย่างโค้ด:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ (50, 50) โดยมีความกว้าง 600 และความสูง 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### การจัดการแผนภูมิชุด
#### ภาพรวม
เรียนรู้วิธีการล้างซีรีย์ที่มีอยู่และเพิ่มซีรีย์ใหม่ด้วยจุดข้อมูลที่กำหนดเอง

**ขั้นตอน:**
1. **ล้างซีรีย์ที่มีอยู่:**
   - ใช้ `series.clear()` เพื่อลบข้อมูลที่มีอยู่ก่อนหน้านี้ออก
2. **เพิ่มซีรีย์ใหม่:**
   - เพิ่มซีรีย์ใหม่โดยใช้ `series-add()`.
3. **แทรกจุดข้อมูล:**
   - ใช้ประโยชน์ `getDataPoints().addDataPointForBarSeries()` เพื่อเพิ่มค่าต่างๆ รวมถึงค่าลบด้วย

**ตัวอย่างโค้ด:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // ล้างซีรีย์ที่มีอยู่และเพิ่มซีรีย์ใหม่
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // เพิ่มจุดข้อมูลที่มีค่าแตกต่างกัน (บวกและลบ)
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

### การกลับจุดข้อมูลของอนุกรมตามเงื่อนไข
#### ภาพรวม
ปรับแต่งการแสดงภาพจุดข้อมูลเชิงลบโดยการกลับค่าแบบมีเงื่อนไข

**ขั้นตอน:**
1. **ตั้งค่าพฤติกรรมการกลับด้านเริ่มต้น:**
   - ใช้ `setInvertIfNegative(false)` เพื่อกำหนดพฤติกรรมการกลับด้านโดยรวม
2. **การกลับจุดข้อมูลเฉพาะตามเงื่อนไข:**
   - นำมาใช้ `setInvertIfNegative(true)` บนจุดข้อมูลเฉพาะถ้าเป็นค่าลบ

**ตัวอย่างโค้ด:**
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
    
    // เพิ่มจุดข้อมูลที่มีค่าแตกต่างกัน (บวกและลบ)
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
    
    // ตั้งค่าพฤติกรรมการกลับด้านเริ่มต้น
    series.get_Item(0).invertIfNegative(false);
    
    // การกลับจุดข้อมูลเฉพาะตามเงื่อนไข
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### บทสรุป
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการตั้งค่า Aspose.Slides สำหรับ Java และสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ นอกจากนี้ คุณยังได้เรียนรู้การจัดการชุดข้อมูลและปรับแต่งการแสดงภาพจุดข้อมูลเชิงลบ ด้วยทักษะเหล่านี้ คุณสามารถสร้างแผนภูมิแบบไดนามิกในแอปพลิเคชัน Java ของคุณได้อย่างมั่นใจ

**ขั้นตอนต่อไป:**
- ทดลองใช้ประเภทแผนภูมิต่างๆ ที่มีอยู่ใน Aspose.Slides สำหรับ Java
- สำรวจตัวเลือกการปรับแต่งเพิ่มเติมเพื่อเพิ่มประสิทธิภาพการนำเสนอของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}