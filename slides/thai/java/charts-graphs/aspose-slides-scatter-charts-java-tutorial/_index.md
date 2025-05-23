---
"date": "2025-04-17"
"description": "เรียนรู้วิธีสร้างแผนภูมิกระจายแบบไดนามิกโดยใช้ Aspose.Slides สำหรับ Java เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยคุณลักษณะแผนภูมิที่ปรับแต่งได้"
"title": "สร้างและปรับแต่งแผนภูมิแบบกระจายใน Java ด้วย Aspose.Slides"
"url": "/th/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างและปรับแต่งแผนภูมิแบบกระจายใน Java ด้วย Aspose.Slides

เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยการเพิ่มแผนภูมิกระจายแบบไดนามิกโดยใช้ Java ด้วย Aspose.Slides บทช่วยสอนที่ครอบคลุมนี้จะแนะนำคุณเกี่ยวกับการตั้งค่าไดเร็กทอรี การเริ่มต้นการนำเสนอ การสร้างแผนภูมิกระจาย การจัดการข้อมูลแผนภูมิ การปรับแต่งประเภทและเครื่องหมายของชุดข้อมูล และการบันทึกงานของคุณ ทั้งหมดนี้ทำได้อย่างง่ายดาย

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าไดเรกทอรีสำหรับจัดเก็บไฟล์งานนำเสนอ
- การเริ่มต้นและการจัดการการนำเสนอโดยใช้ Aspose.Slides
- การสร้างแผนภูมิแบบกระจายบนสไลด์
- การจัดการและการเพิ่มข้อมูลลงในชุดแผนภูมิ
- การปรับแต่งประเภทและเครื่องหมายของชุดแผนภูมิ
- บันทึกการนำเสนอของคุณด้วยการปรับเปลี่ยน

เริ่มต้นด้วยการตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นที่จำเป็น

## ข้อกำหนดเบื้องต้น

หากต้องการทำตามบทช่วยสอนนี้ ให้แน่ใจว่าคุณมี:
- **Aspose.Slides สำหรับ Java**: ต้องมีเวอร์ชัน 25.4 ขึ้นไป
- **ชุดพัฒนา Java (JDK)**: ต้องมี JDK 8 ขึ้นไป
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java และความคุ้นเคยกับเครื่องมือสร้าง Maven หรือ Gradle

## การตั้งค่า Aspose.Slides สำหรับ Java

ก่อนที่เราจะเริ่มเขียนโค้ด ให้รวม Aspose.Slides เข้ากับโปรเจ็กต์ของคุณโดยใช้หนึ่งในวิธีต่อไปนี้:

### เมเวน
รวมสิ่งที่ต้องพึ่งพานี้ไว้ในของคุณ `pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### แกรเดิล
เพิ่มบรรทัดนี้ลงในของคุณ `build.gradle` ไฟล์:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หรือดาวน์โหลด Aspose.Slides ล่าสุดสำหรับ Java จาก [การเปิดตัว Aspose](https://releases-aspose.com/slides/java/).

#### การขอใบอนุญาต
- **ทดลองใช้งานฟรี**:เริ่มด้วยการทดลองใช้ฟรี 30 วันเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว**: การขอใบอนุญาตชั่วคราวเพื่อการทดสอบขยายเวลา
- **ซื้อ**:ซื้อใบอนุญาตเพื่อการเข้าถึงและการสนับสนุนแบบเต็มรูปแบบ

ตอนนี้ ให้เริ่มต้น Aspose.Slides ในแอปพลิเคชัน Java ของคุณโดยเพิ่มการนำเข้าที่จำเป็นดังแสดงด้านล่าง

## คู่มือการใช้งาน

### การตั้งค่าไดเรกทอรี
ขั้นแรก ให้แน่ใจว่าไดเร็กทอรีของเรามีไว้สำหรับจัดเก็บไฟล์การนำเสนอ ขั้นตอนนี้จะช่วยป้องกันข้อผิดพลาดระหว่างการบันทึกไฟล์

#### สร้างไดเรกทอรีหากไม่มีอยู่
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // สร้างไดเรกทอรี
    new File(dataDir).mkdirs();
}
```
สไนปเป็ตนี้จะตรวจสอบไดเรกทอรีที่ระบุและสร้างขึ้นถ้าไม่มีอยู่ โดยใช้ `File.exists()` เพื่อตรวจสอบการมีอยู่และ `File.mkdirs()` เพื่อสร้างไดเร็กทอรี

### การเริ่มต้นการนำเสนอ

ขั้นต่อไป ให้เริ่มต้นวัตถุการนำเสนอของคุณโดยที่คุณจะเพิ่มแผนภูมิแบบกระจาย

#### เริ่มต้นการนำเสนอของคุณ
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
ที่นี่, `new Presentation()` สร้างการนำเสนอแบบว่างเปล่า เราเข้าถึงสไลด์แรกเพื่อทำงานกับมันโดยตรง

### การสร้างแผนภูมิ
ขั้นตอนต่อไปคือการสร้างแผนภูมิแบบกระจายบนสไลด์เริ่มต้นของเรา

#### เพิ่มแผนภูมิกระจายลงในสไลด์
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
โค้ดสั้นๆ นี้จะเพิ่มแผนภูมิแบบกระจายที่มีเส้นเรียบๆ ลงในสไลด์แรก พารามิเตอร์จะกำหนดตำแหน่งและขนาดของแผนภูมิ

### การจัดการข้อมูลแผนภูมิ
ตอนนี้มาจัดการข้อมูลแผนภูมิของเราโดยการล้างชุดข้อมูลที่มีอยู่และเพิ่มชุดข้อมูลใหม่

#### จัดการแผนภูมิชุด
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// การเพิ่มซีรี่ส์ใหม่ลงในแผนภูมิ
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
ส่วนนี้จะล้างข้อมูลที่มีอยู่และเพิ่มชุดใหม่สองชุดลงในแผนภูมิแบบกระจายของเรา

### การเพิ่มจุดข้อมูลสำหรับซีรีส์กระจัดกระจาย
เพื่อแสดงภาพข้อมูลของเรา เราจะเพิ่มจุดให้กับแต่ละชุดในแผนภูมิแบบกระจาย

#### เพิ่มจุดข้อมูล
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
เราใช้ `addDataPointForScatterSeries()` เพื่อผนวกจุดข้อมูลเข้ากับซีรีส์แรกของเรา พารามิเตอร์จะกำหนดค่า X และ Y

### การปรับเปลี่ยนประเภทซีรีย์และเครื่องหมาย
ปรับแต่งลักษณะที่ปรากฏของแผนภูมิของคุณโดยการเปลี่ยนแปลงประเภทและรูปแบบของเครื่องหมายในแต่ละชุด

#### ปรับแต่งซีรีย์
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// ปรับปรุงซีรีย์ที่ 2
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
การเปลี่ยนแปลงเหล่านี้ช่วยปรับประเภทซีรีส์ให้ใช้เส้นตรงและเครื่องหมาย นอกจากนี้ เรายังกำหนดขนาดเครื่องหมายและสัญลักษณ์สำหรับการแยกความแตกต่างทางภาพด้วย

### การบันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอของคุณพร้อมกับการแก้ไขทั้งหมดที่ทำ

#### บันทึกการนำเสนอของคุณ
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
ใช้ `SaveFormat.Pptx` เพื่อระบุรูปแบบ PowerPoint สำหรับการบันทึกไฟล์ของคุณ ขั้นตอนนี้มีความสำคัญสำหรับการรักษาการเปลี่ยนแปลงทั้งหมด

## การประยุกต์ใช้งานจริง
ต่อไปนี้เป็นกรณีการใช้งานจริงบางส่วน:
1. **การวิเคราะห์ทางการเงิน**:ใช้แผนภูมิแบบกระจายเพื่อแสดงแนวโน้มหุ้นในช่วงเวลาต่างๆ
2. **การวิจัยทางวิทยาศาสตร์**:แสดงจุดข้อมูลการทดลองเพื่อการวิเคราะห์
3. **การจัดการโครงการ**:แสดงภาพการจัดสรรทรัพยากรและมาตรวัดความคืบหน้า

การรวม Aspose.Slides เข้ากับระบบของคุณทำให้คุณสามารถสร้างรายงานแบบอัตโนมัติ เพิ่มผลผลิตและความแม่นยำ

## การพิจารณาประสิทธิภาพ
เพื่อประสิทธิภาพที่เหมาะสมที่สุด:
- จัดการการใช้หน่วยความจำโดยการกำจัดการนำเสนอหลังจากการบันทึก
- ใช้โครงสร้างข้อมูลที่มีประสิทธิภาพสำหรับชุดข้อมูลขนาดใหญ่
- ลดการดำเนินการที่ใช้ทรัพยากรอย่างเข้มข้นภายในลูป

แนวทางปฏิบัติที่ดีที่สุดช่วยให้มั่นใจว่าการดำเนินการจะราบรื่นแม้จะมีการจัดการแผนภูมิที่ซับซ้อนก็ตาม

## บทสรุป
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีตั้งค่าไดเรกทอรี เริ่มต้นการนำเสนอ Aspose.Slides สร้างและปรับแต่งแผนภูมิแบบกระจาย จัดการข้อมูลชุด แก้ไขเครื่องหมาย และบันทึกงานของคุณ หากต้องการศึกษาความสามารถของ Aspose.Slides เพิ่มเติม โปรดพิจารณาเจาะลึกคุณลักษณะขั้นสูง เช่น แอนิเมชันและการเปลี่ยนสไลด์

**ขั้นตอนต่อไป**:ทดลองใช้แผนภูมิประเภทต่างๆ หรือรวมเทคนิคเหล่านี้เข้ากับโปรเจ็กต์ Java ที่ใหญ่กว่า

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของมาร์กเกอร์ได้อย่างไร?
หากต้องการเปลี่ยนสีเครื่องหมาย ให้ใช้ `series.getMarker().getFillFormat().setFillColor(ColorObject)`, ที่ไหน `ColorObject` คือสีที่คุณต้องการ

### ฉันสามารถเพิ่มชุดข้อมูลมากกว่าสองชุดลงในแผนภูมิแบบกระจายได้หรือไม่
ใช่ คุณสามารถเพิ่มซีรีส์ได้มากเท่าที่ต้องการโดยทำซ้ำขั้นตอนการเพิ่มซีรีส์และจุดข้อมูลใหม่

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}