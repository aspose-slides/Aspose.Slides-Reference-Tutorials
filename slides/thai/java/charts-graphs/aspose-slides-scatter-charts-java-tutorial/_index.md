---
date: '2026-02-24'
description: เรียนรู้วิธีปรับแต่งแผนภูมิกระจายด้วย Aspose.Slides for Java คำแนะนำนี้จะพาคุณผ่านขั้นตอนการสร้าง
  การจัดสไตล์ และการบันทึกแผนภูมิกระจายแบบไดนามิกในงานนำเสนอของคุณ
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: ปรับแต่งแผนภูมิกระจาย Aspose ใน Java
url: /th/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# ปรับแต่ง Scatter Chart Aspose ใน Java

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **customize scatter chart aspose** ด้วยไลบรารี Aspose.Slides for Java ที่ทรงพลัง เราจะพาคุณผ่านการตั้งค่าโปรเจกต์ การสร้าง scatter chart การปรับประเภทซีรีส์และมาร์คเกอร์ต่าง ๆ และสุดท้ายการบันทึกพรีเซนเทชัน เมื่อจบแล้วคุณจะสามารถสร้าง scatter chart ที่ดูเป็นมืออาชีพโดยอัตโนมัติและปรับแต่งรายละเอียดภาพทุกอย่างให้ตรงกับแบรนด์หรือความต้องการรายงานของคุณได้

## คำตอบอย่างรวดเร็ว
- **ต้องใช้ไลบรารีอะไร?** Aspose.Slides for Java (v25.4 ขึ้นไป)  
- **รองรับเวอร์ชัน Java ใด?** JDK 8 หรือสูงกว่า  
- **สามารถเปลี่ยนรูปแบบมาร์คเกอร์ได้หรือไม่?** ได้ – ใช้ `MarkerStyleType` เพื่อเลือกดาว, วงกลม ฯลฯ  
- **บันทึกไฟล์อย่างไร?** เรียก `pres.save("output.pptx", SaveFormat.Pptx)`  
- **ต้องมีลิขสิทธิ์หรือไม่?** ทดลองใช้ฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง

## “customize scatter chart aspose” คืออะไร?
การปรับแต่ง scatter chart ด้วย Aspose หมายถึงการกำหนดข้อมูล, ลักษณะการแสดงผล และพฤติกรรมของแผนภูมิผ่านโค้ด—ตั้งแต่พิกัดจุดจนถึงสัญลักษณ์มาร์คเกอร์—โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง วิธีนี้เหมาะสำหรับการสร้างรายงานอัตโนมัติ, พรีเซนเทชันที่ขับเคลื่อนด้วยข้อมูล, หรือสถานการณ์ใด ๆ ที่ต้องการการสร้างภาพคุณภาพสูงแบบทำซ้ำได้

## ทำไมต้องปรับแต่ง scatter chart ด้วย Aspose.Slides?
- **ควบคุมได้เต็มที่** – ปรับประเภทซีรีส์, สไตล์มาร์คเกอร์, สี ฯลฯ ผ่านโค้ด Java  
- **อัตโนมัติ** – สร้างแผนภูมิจำนวนหลายสิบหรือหลายร้อยชิ้นบน fly สำหรับแดชบอร์ดหรือรายงานชุด  
- **ข้ามแพลตฟอร์ม** – ทำงานบน OS ใดก็ได้ที่รองรับ Java, ไม่ต้องติดตั้ง Office  
- **ประสิทธิภาพ** – API เบา ๆ ที่จัดการชุดข้อมูลขนาดใหญ่ได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

เพื่อทำตามขั้นตอนนี้ โปรดตรวจสอบว่าคุณมี:

- **Aspose.Slides for Java** (v25.4 หรือใหม่กว่า)  
- **Java Development Kit (JDK)** 8 + ติดตั้งแล้ว  
- Maven หรือ Gradle สำหรับจัดการ dependency (หรือคุณสามารถดาวน์โหลด JAR ด้วยตนเอง)  
- ความรู้พื้นฐานของ Java และคุ้นเคยกับเครื่องมือ build ที่คุณเลือกใช้

## การตั้งค่า Aspose.Slides for Java

รวมไลบรารีเข้ากับโปรเจกต์ของคุณโดยใช้วิธีใดวิธีหนึ่งด้านล่าง

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

หรือดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose Releases](https://releases.aspose.com/slides/java/)

#### การรับลิขสิทธิ์
- **Free Trial** – ทดลองใช้ 30 วัน  
- **Temporary License** – ระยะเวลาทดสอบต่อเนื่อง  
- **Full License** – ใช้งานในผลิตภัณฑ์พร้อมการสนับสนุนระดับพรีเมียม

## คู่มือขั้นตอนโดยละเอียดเพื่อปรับแต่ง Scatter Chart Aspose

### 1️⃣ เตรียมโฟลเดอร์สำหรับไฟล์พรีเซนเทชันของคุณ
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*ทำไมต้องทำ:* การตรวจสอบให้โฟลเดอร์ปลายทางมีอยู่แล้วจะช่วยป้องกัน `FileNotFoundException` เมื่อคุณบันทึก PPTX ในขั้นตอนต่อไป

### 2️⃣ สร้างพรีเซนเทชันใหม่และดึงสไลด์แรกออกมา
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
`Presentation` ใหม่ให้แคนวาสว่างเปล่า; สไลด์แรกคือที่เราจะวางแผนภูมิ

### 3️⃣ เพิ่ม scatter chart พร้อมเส้นโค้งเรียบ
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` สร้าง scatter chart ที่มีเส้นโค้งเรียบ เหมาะสำหรับการแสดงแนวโน้ม

### 4️⃣ ลบซีรีส์เริ่มต้นและเพิ่มซีรีส์ของคุณเอง
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
การลบซีรีส์เริ่มต้นทำให้คุณควบคุมข้อมูลที่แสดงได้เต็มที่

### 5️⃣ เติมข้อมูลจุดให้ซีรีส์แรก
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` รับเซลล์ค่า X และค่า Y สร้างจุด scatter ทีละจุด

### 6️⃣ ปรับประเภทซีรีส์และลักษณะมาร์คเกอร์
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
ที่นี่เราจะ **customize the scatter chart aspose** โดยสลับเป็นเส้นตรง, ขยายขนาดมาร์คเกอร์, และเลือกสัญลักษณ์ที่แตกต่าง (ดาว vs. วงกลม) เพื่อความชัดเจนในการมองเห็น

### 7️⃣ บันทึกพรีเซนเทชัน
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
การบันทึกเป็น `Pptx` จะเก็บการปรับแต่งทั้งหมดของแผนภูมิและทำให้ไฟล์พร้อมแชร์หรือแก้ไขต่อไป

## กรณีการใช้งานทั่วไปของ Scatter Chart ที่ปรับแต่งแล้ว
- **แดชบอร์ดการเงิน** – แสดงราคาหุ้นเทียบกับปริมาณการซื้อขาย  
- **งานวิจัยวิทยาศาสตร์** – แสดงผลการทดลองพร้อมมาร์คเกอร์แสดงความคลาดเคลื่อน  
- **การจัดการโครงการ** – เปรียบเทียบความพยายามที่วางแผนกับความพยายามจริงตามงานต่าง ๆ  

## เคล็ดลับด้านประสิทธิภาพ
- ปิดการใช้งานอ็อบเจกต์ `Presentation` (`pres.dispose()`) หลังบันทึกเพื่อคืนทรัพยากรเนทีฟ  
- สำหรับชุดข้อมูลขนาดใหญ่ ให้เติมข้อมูลใน `IChartDataWorkbook` ก่อนแล้วค่อยผูกซีรีส์เพื่อหลีกเลี่ยงการรีเฟรช UI ซ้ำ ๆ  
- ใช้ instance ของ `IChartDataWorkbook` เดียวเมื่อต้องเพิ่มหลายซีรีส์

## คำถามที่พบบ่อย

### วิธีเปลี่ยนสีของมาร์คเกอร์ได้อย่างไร?
ใช้ `series.getMarker().getFillFormat().setFillColor(Color)` โดย `Color` เป็นอ็อบเจกต์ของ `java.awt.Color` (เช่น `Color.RED`)

### สามารถเพิ่มซีรีส์มากกว่าสองชุดใน scatter chart ได้หรือไม่?
ทำได้แน่นอน เพียงเรียก `chart.getChartData().getSeries().add(...)` ซ้ำสำหรับแต่ละซีรีส์เพิ่มเติมและเติมข้อมูลจุดของมันตามต้องการ

### สามารถตั้งค่าตำนาน (legend) แบบกำหนดเองสำหรับแต่ละซีรีส์ได้หรือไม่?
ได้ หลังจากสร้างซีรีส์แล้วเรียก `series.getLegend().setText("Your Legend Text")` เพื่อแทนที่ชื่อเริ่มต้น

### วิธีส่งออกแผนภูมิเป็นรูปภาพแทนการบันทึกเป็น PPTX ทำอย่างไร?
เรียก `chart.getImage().save("chart.png", ImageFormat.Png)` หลังจากตั้งค่าแผนภูมิแล้ว จะได้ไฟล์ PNG แยกอิสระ

### ถ้าต้องการทำให้จุด scatter มีการเคลื่อนไหวทำอย่างไร?
Aspose.Slides รองรับเอฟเฟกต์แอนิเมชัน ใช้ `chart.getTimeline().getMainSequence().addEffect(...)` เพื่อเพิ่มเอฟเฟกต์การเข้าหรือเน้นให้กับแผนภูมิหรือซีรีส์แต่ละชุด

---

**อัปเดตล่าสุด:** 2026-02-24  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}