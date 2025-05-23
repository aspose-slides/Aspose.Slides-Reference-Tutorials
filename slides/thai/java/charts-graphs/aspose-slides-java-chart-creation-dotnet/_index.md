---
"date": "2025-04-17"
"description": "เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิในงานนำเสนอ .NET โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อปรับปรุงการแสดงภาพข้อมูลในงานนำเสนอของคุณ"
"title": "Aspose.Slides สำหรับ Java และการสร้างแผนภูมิในงานนำเสนอ .NET"
"url": "/th/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างแผนภูมิในงานนำเสนอ .NET โดยใช้ Aspose.Slides สำหรับ Java
## การแนะนำ
การสร้างงานนำเสนอที่น่าสนใจมักเกี่ยวข้องกับการผสานการแสดงข้อมูลภาพ เช่น แผนภูมิ เพื่อเพิ่มความเข้าใจและการมีส่วนร่วมของผู้ฟัง หากคุณเป็นนักพัฒนาที่ต้องการเพิ่มแผนภูมิแบบไดนามิกที่ปรับแต่งได้ให้กับงานนำเสนอ .NET ของคุณโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้เหมาะสำหรับคุณโดยเฉพาะ เราจะเจาะลึกถึงวิธีการเริ่มต้นงานนำเสนอ เพิ่มแผนภูมิประเภทต่างๆ จัดการข้อมูลแผนภูมิ และจัดรูปแบบข้อมูลชุดอย่างมีประสิทธิภาพ
**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่าและใช้งาน Aspose.Slides สำหรับ Java ในสภาพแวดล้อม .NET ของคุณ
- การเริ่มต้นการนำเสนอใหม่โดยใช้ Aspose.Slides
- การเพิ่มและปรับแต่งแผนภูมิในสไลด์
- การจัดการสมุดงานข้อมูลแผนภูมิ
- การจัดรูปแบบข้อมูลชุดโดยเฉพาะการจัดการค่าลบ
การเปลี่ยนไปสู่ส่วนข้อกำหนดเบื้องต้นจะช่วยให้คุณมั่นใจว่าทุกอย่างพร้อมที่จะปฏิบัติตามได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มสร้างแผนภูมิด้วย Aspose.Slides สำหรับ Java เรามาสรุปสิ่งที่คุณต้องการกันก่อน:
### ไลบรารีและเวอร์ชันที่จำเป็น
ตรวจสอบให้แน่ใจว่าคุณมีสิ่งที่ต้องพึ่งพาต่อไปนี้:
- **Aspose.Slides สำหรับ Java**: เวอร์ชัน 25.4 ขึ้นไป.
### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่สนับสนุนแอปพลิเคชัน .NET
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรมภาษา Java
### ข้อกำหนดเบื้องต้นของความรู้
- ความคุ้นเคยกับการสร้างงานนำเสนอในบริบทแอปพลิเคชัน .NET
- ทำความเข้าใจเกี่ยวกับการอ้างอิง Java และการจัดการ (Maven/Gradle)
## การตั้งค่า Aspose.Slides สำหรับ Java
หากต้องการเริ่มใช้ Aspose.Slides คุณต้องรวม Aspose.Slides เป็นส่วนที่ต้องพึ่งพาในโปรเจ็กต์ของคุณ โดยคุณสามารถทำได้ดังนี้:
### เมเวน
เพิ่มการอ้างอิงต่อไปนี้ให้กับของคุณ `pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### แกรเดิล
รวมสิ่งนี้ไว้ในของคุณ `build.gradle` ไฟล์:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).
#### ขั้นตอนการรับใบอนุญาต
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยใบอนุญาตชั่วคราวเพื่อสำรวจคุณสมบัติต่างๆ
- **ซื้อ**:ควรพิจารณาซื้อใบอนุญาตเพื่อใช้งานอย่างกว้างขวาง
#### การเริ่มต้นและการตั้งค่าเบื้องต้น
นี่คือวิธีการเริ่มต้น Aspose.Slides ในโค้ดของคุณ:
```java
import com.aspose.slides.Presentation;
// เริ่มต้นวัตถุการนำเสนอใหม่
Presentation pres = new Presentation();
try {
    // ตรรกะของคุณที่นี่...
} finally {
    if (pres != null) pres.dispose();
}
```
การตั้งค่านี้ช่วยให้มั่นใจว่าการจัดการทรัพยากรได้รับการจัดการอย่างมีประสิทธิภาพ
## คู่มือการใช้งาน
เราจะพาคุณแนะนำวิธีนำคุณลักษณะต่างๆ ไปใช้ทีละขั้นตอน
### การเริ่มต้นการนำเสนอ
**ภาพรวม:**
การสร้างอินสแตนซ์ของการนำเสนอจะเป็นการกำหนดขั้นตอนสำหรับการดำเนินการทั้งหมดที่ตามมา คุณลักษณะนี้จะแสดงวิธีการเริ่มต้นตั้งแต่ต้นโดยใช้ Aspose.Slides
#### ขั้นตอนที่ 1: นำเข้าแพ็คเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
```
#### ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอใหม่
นี่คือวิธีการทำ:
```java
Presentation pres = new Presentation();
try {
    // ลอจิกโค้ดของคุณอยู่ที่นี่...
} finally {
    if (pres != null) pres.dispose(); // รับรองว่าทรัพยากรได้รับการปลดปล่อย
}
```
*วิธีนี้จะช่วยให้แน่ใจว่าวัตถุการนำเสนอจะถูกกำจัดอย่างถูกต้องหลังการใช้งาน และป้องกันการรั่วไหลของหน่วยความจำ*
### การเพิ่มแผนภูมิลงในสไลด์
**ภาพรวม:**
การเพิ่มแผนภูมิลงในสไลด์สามารถทำให้การแสดงข้อมูลมีประสิทธิภาพและน่าสนใจมากขึ้น
#### ขั้นตอนที่ 1: นำเข้าแพ็คเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```
#### ขั้นตอนที่ 2: เริ่มต้นการนำเสนอและเพิ่มแผนภูมิ
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // ตรรกะเพิ่มเติมสำหรับการปรับแต่งแผนภูมิ...
} finally {
    if (pres != null) pres.dispose();
}
```
*ที่นี่ เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์แรกตามพิกัดและมิติที่ระบุ*
### การจัดการสมุดงานข้อมูลแผนภูมิ
**ภาพรวม:**
การจัดการเวิร์กบุ๊กข้อมูลแผนภูมิของคุณอย่างมีประสิทธิภาพช่วยให้คุณสามารถจัดการชุดข้อมูลและหมวดหมู่ได้อย่างราบรื่น
#### ขั้นตอนที่ 1: นำเข้าแพ็คเกจที่จำเป็น
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### ขั้นตอนที่ 2: เข้าถึงและล้างสมุดงานข้อมูล
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // ล้างข้อมูลที่มีอยู่
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // ตรรกะการปรับแต่งของคุณที่นี่...
} finally {
    if (pres != null) pres.dispose();
}
```
*การล้างเวิร์กบุ๊กเป็นสิ่งสำคัญสำหรับการเริ่มต้นด้วยการเริ่มต้นใหม่เมื่อเพิ่มชุดและหมวดหมู่ใหม่*
### การเพิ่มซีรีส์และหมวดหมู่ลงในแผนภูมิ
**ภาพรวม:**
ฟีเจอร์นี้แสดงให้เห็นว่าคุณสามารถเพิ่มจุดข้อมูลที่มีความหมายได้อย่างไรโดยการจัดการชุดข้อมูลและหมวดหมู่
#### ขั้นตอนที่ 1: เพิ่มซีรี่ส์และหมวดหมู่
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // ล้างซีรีย์และหมวดหมู่ที่มีอยู่
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // เพิ่มซีรีย์และหมวดหมู่ใหม่
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // ตรรกะการปรับแต่งเพิ่มเติม...
} finally {
    if (pres != null) pres.dispose();
}
```
*การเพิ่มชุดข้อมูลและหมวดหมู่ทำให้การนำเสนอข้อมูลมีความเป็นระเบียบมากขึ้น*
### การเติมข้อมูลและการจัดรูปแบบชุดข้อมูล
**ภาพรวม:**
เติมจุดข้อมูลลงในแผนภูมิของคุณและจัดรูปแบบลักษณะที่ปรากฏเพื่อให้อ่านง่ายขึ้น โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับค่าลบ
#### ขั้นตอนที่ 1: เติมข้อมูลชุดข้อมูล
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

    // เพิ่มซีรีย์และหมวดหมู่ (ใช้ตรรกะเดิมซ้ำ)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // รูปแบบซีรีย์สำหรับค่าลบ
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

    // บันทึกการนำเสนอ
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*หัวข้อนี้สาธิตวิธีเติมข้อมูลและจัดรูปแบบสีเพื่อให้มองเห็นได้ชัดเจนยิ่งขึ้น*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}