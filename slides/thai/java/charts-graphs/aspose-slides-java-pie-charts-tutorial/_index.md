---
date: '2026-02-19'
description: เรียนรู้วิธีสร้างแผนภูมิวงกลมใน Java ด้วย Aspose.Slides และปรับแต่งสีของแผนภูมิวงกลม,
  เพิ่มชุดข้อมูลแผนภูมิ, ทำงานกับแผ่นงานข้อมูลของแผนภูมิ, และตั้งค่ามุมการหมุน.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: วิธีปรับแต่งสีของแผนภูมิวงกลมใน Java ด้วย Aspose.Slides – คู่มือฉบับสมบูรณ์
url: /th/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างแผนภูมิวงกลมด้วย Aspose.Slides for Java: บทเรียนครบถ้วน

## คำแนะนำ
การสร้างงานนำเสนอที่เคลื่อนไหวและมีความสวยงามเป็นสิ่งสำคัญสำหรับการสื่อสารข้อมูลที่มีผลกระทบอย่างเต็มที่ ด้วย Aspose.Slides for Java คุณสามารถผสานแผนภูมิที่ซับซ้อนอย่างแผนภูมิวงกลมเข้าไปในสไลด์ได้อย่างราบรื่น, **customize pie chart colors**, และเพิ่มประสิทธิภาพการแสดงผลข้อมูลได้อย่างง่ายดาย คู่มือฉบับสมบูรณ์นี้จะพาคุณผ่านขั้นตอนการสร้างและปรับแต่งแผนภูมิวงกลมด้วย Aspose.Slides Java, แก้ไขปัญหาการนำเสนอที่พบบ่อยได้อย่างไม่ยากเย็น

**สิ่งที่คุณจะได้เรียนรู้:**
- การเริ่มต้นงานนำเสนอและการเพิ่มสไลด์
- การสร้างและกำหนดค่าแผนภูมิวงกลมบนสไลด์ของคุณ
- การตั้งชื่อแผนภูมิ, ป้ายข้อมูล, และ **customize pie chart colors**
- การเพิ่มประสิทธิภาพการทำงานและการจัดการทรัพยากรอย่างมีประสิทธิผล
- การผสาน Aspose.Slides เข้าในโครงการ Java ด้วย Maven หรือ Gradle

มาเริ่มกันโดยตรวจสอบให้แน่ใจว่าคุณมีเครื่องมือและความรู้ที่จำเป็นทั้งหมดเพื่อทำตามขั้นตอนได้!

## คำตอบสั้น
- **คลาสหลักที่ใช้เริ่มงานนำเสนอคืออะไร?** `Presentation` จาก `com.aspose.slides`
- **เมธอดใดที่เพิ่มแผนภูมิวงกลมลงในสไลด์?** `addChart(ChartType.Pie, …)`
- **จะเปิดใช้งานสีที่แตกต่างสำหรับแต่ละส่วนได้อย่างไร?** ตั้งค่า `setColorVaried(true)` บนกลุ่มซีรีส์
- **สามารถหมุนแผนภูมิวงกลมได้หรือไม่?** ได้, ใช้ `setRotationAngle(double)` บนวัตถุแผนภูมิ
- **ต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Slides สำหรับการใช้งานเชิงพาณิชย์

## “customize pie chart colors” คืออะไร?
การ **customize pie chart colors** หมายถึงการกำหนดสีเติมที่แตกต่างให้กับแต่ละชิ้นของแผนภูมิวงกลม เพื่อเพิ่มความอ่านง่ายและผลกระทบทางสายตา ใน Aspose.Slides คุณทำได้โดยเปิดใช้งานสีที่หลากหลายแล้วตั้งค่าสีเติมแบบทึบสำหรับจุดข้อมูลแต่ละจุด

## ทำไมต้องใช้ Aspose.Slides for Java เพื่อสร้างแผนภูมิวงกลม?
- **การควบคุมเต็มรูปแบบ** ของลักษณะแผนภูมิโดยไม่ต้องพึ่ง Microsoft Office
- **ความเข้ากันได้ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS
- **API ที่ครอบคลุม** สำหรับการผูกข้อมูล, การสไตลิ่ง, และการส่งออกเป็น PPTX, PDF หรือรูปภาพ
- **ความยืดหยุ่นของไลเซนส์** – เริ่มต้นด้วยการทดลองใช้ฟรีและอัปเกรดเมื่อคุณต้องการฟีเจอร์เต็มรูปแบบ

## ข้อกำหนดเบื้องต้น
ก่อนจะดำเนินการตามบทเรียนนี้, โปรดตรวจสอบให้แน่ใจว่าคุณได้เตรียมสิ่งต่อไปนี้เรียบร้อยแล้ว:

### ไลบรารี, เวอร์ชัน, และการพึ่งพาที่จำเป็น
- **Aspose.Slides for Java**: เวอร์ชัน 25.4 หรือใหม่กว่า
- **Java Development Kit (JDK)**: เวอร์ชัน 16 หรือสูงกว่า

### ความต้องการการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่ติดตั้งและกำหนดค่า Java ไว้แล้ว
- Integrated Development Environment (IDE) เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

### ความรู้พื้นฐานที่ต้องมี
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java
- ความคุ้นเคยกับ Maven หรือ Gradle สำหรับการจัดการการพึ่งพา

## การตั้งค่า Aspose.Slides for Java
เพื่อเริ่มใช้ Aspose.Slides ในโครงการ Java ของคุณ, คุณต้องเพิ่มไลบรารีเป็นการพึ่งพา ต่อไปนี้เป็นวิธีทำด้วยเครื่องมือสร้างต่าง ๆ:

**Maven**  
เพิ่มโค้ดส่วนนี้ลงในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
ใส่โค้ดต่อไปนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**ดาวน์โหลดโดยตรง**  
หากคุณไม่ต้องการใช้เครื่องมือสร้าง, ดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

### ขั้นตอนการรับไลเซนส์
- **ทดลองใช้ฟรี**: เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติของ Aspose.Slides  
- **ไลเซนส์ชั่วคราว**: รับไลเซนส์ชั่วคราวสำหรับการใช้งานต่อเนื่องโดยไม่มีข้อจำกัด  
- **ซื้อไลเซนส์**: พิจารณาซื้อหากต้องการเข้าถึงแบบถาวรระยะยาว

**การเริ่มต้นและการตั้งค่าเบื้องต้น**  
เพื่อเริ่มใช้ Aspose.Slides, เริ่มต้นโครงการของคุณด้วยการสร้างอ็อบเจ็กต์งานนำเสนอใหม่:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## คู่มือการดำเนินการ
ต่อไปนี้เป็นการแบ่งกระบวนการเพิ่มและปรับแต่งแผนภูมิวงกลมเป็นขั้นตอนย่อยที่จัดการได้ง่าย

### เริ่มต้นงานนำเสนอและสไลด์
ตั้งค่างานนำเสนอใหม่และเข้าถึงสไลด์แรก ซึ่งจะเป็นผืนแคนวาสสำหรับสร้างแผนภูมิ:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### เพิ่มแผนภูมิวงกลมลงในสไลด์
แทรกแผนภูมิวงกลมในตำแหน่งที่กำหนดพร้อมชุดข้อมูลเริ่มต้น:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### ตั้งชื่อแผนภูมิ
ปรับแต่งแผนภูมิของคุณโดยตั้งค่าและจัดกึ่งกลางชื่อเรื่อง:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### กำหนดค่าป้ายข้อมูลสำหรับซีรีส์
ทำให้ป้ายข้อมูลแสดงค่าตัวเลขเพื่อความชัดเจน:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### เตรียมแผ่นงานข้อมูลของแผนภูมิ
ล้างซีรีส์และหมวดหมู่ที่มีอยู่เดิมออกจากแผ่นงานข้อมูลของแผนภูมิ:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### เพิ่มหมวดหมู่ลงในแผนภูมิ
กำหนดหมวดหมู่สำหรับแผนภูมิวงกลมของคุณ:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### เพิ่มซีรีส์และเติมข้อมูลจุด
สร้างซีรีส์และเติมข้อมูลจุด – นี่คือขั้นตอนที่เราจะ **add chart series**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### ปรับแต่งสีและขอบของซีรีส์
เพิ่มความสวยงามโดยตั้งค่าสีและปรับขอบ – ขั้นตอนนี้ **customizes pie chart colors** โดยตรง:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### ตั้งค่าป้ายข้อมูลแบบกำหนดเอง
ปรับจูนป้ายข้อมูลสำหรับแต่ละจุดข้อมูล:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### ตั้งค่ามุมการหมุนและบันทึกงานนำเสนอ
สรุปแผนภูมิวงกลมของคุณด้วยการ **set rotation angle** แล้วบันทึกไฟล์:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|--------|
| **ส่วนทั้งหมดมีสีเดียวกัน** | ไม่ได้เรียก `setColorVaried(true)` | ตรวจสอบให้แน่ใจว่าคุณเปิดใช้งานสีที่หลากหลายบนกลุ่มซีรีส์ |
| **ป้ายข้อมูลไม่แสดง** | ฟลัก `showValue` ถูกปิด | เรียก `setShowValue(true)` บนรูปแบบป้ายข้อมูลที่เหมาะสม |
| **การหมุนไม่มีผล** | ใช้ Aspose.Slides เวอร์ชันเก่า | อัปเกรดเป็นเวอร์ชัน 25.4 หรือใหม่กว่า |
| **เกิดข้อยกเว้นไลเซนส์ขณะรันไทม์** | ไฟล์ไลเซนส์หายหรือไม่ถูกต้อง | ก่อนสร้าง `Presentation` ให้โหลดไลเซนส์ด้วย `License license = new License(); license.setLicense("Aspose.Slides.lic");` |

## คำถามที่พบบ่อย

**ถาม: จะขอไลเซนส์ Aspose.Slides สำหรับ Java ได้อย่างไร?**  
ตอบ: คุณสามารถขอทดลองใช้ฟรีจากเว็บไซต์ Aspose แล้วซื้อไลเซนส์ถาวร โหลดไลเซนส์ในเวลารันตามที่แสดงในตารางปัญหาทั่วไป

**ถาม: สามารถใช้โค้ดนี้กับ JDK เวอร์ชันเก่าได้หรือไม่?**  
ตอบ: API ต้องการ JDK 16 หรือสูงกว่า; เวอร์ชันเก่าจะไม่รองรับ

**ถาม: สามารถส่งออกแผนภูมิเป็นรูปภาพแทน PPTX ได้หรือไม่?**  
ตอบ: ได้, เรียก `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` หลังจากเรนเดอร์

**ถาม: ถ้าต้องการเพิ่มซีรีส์มากกว่าหนึ่งชุดในแผนภูมิวงกลมทำอย่างไร?**  
ตอบ: แผนภูมิวงกลมโดยทั่วไปแสดงซีรีส์เดียว; หากต้องการหลายชุดให้พิจารณาใช้แผนภูมิดอนัทแทน

**ถาม: ไลบรารีทำงานบนเซิร์ฟเวอร์ Linux ได้หรือไม่?**  
ตอบ: แน่นอน – Aspose.Slides for Java เป็นแบบแพลตฟอร์มอิสระและทำงานบน OS ใด ๆ ที่มี JDK ที่เข้ากันได้

---

**อัปเดตล่าสุด:** 2026-02-19  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}