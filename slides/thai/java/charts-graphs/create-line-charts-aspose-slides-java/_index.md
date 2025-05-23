---
"date": "2025-04-17"
"description": "เรียนรู้วิธีสร้างแผนภูมิเส้นด้วยมาร์กเกอร์ใน Java โดยใช้ Aspose.Slides บทช่วยสอนนี้ครอบคลุมถึงการสร้างแผนภูมิ การบวกอนุกรม และการบันทึกการนำเสนออย่างมีประสิทธิภาพ"
"title": "สร้างแผนภูมิเส้นด้วยเครื่องหมายเริ่มต้นโดยใช้ Aspose.Slides สำหรับ Java"
"url": "/th/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิเส้นด้วยเครื่องหมายเริ่มต้นโดยใช้ Aspose.Slides สำหรับ Java
## การแนะนำ
การสร้างแผนภูมิที่ดึงดูดสายตาและให้ข้อมูลเป็นสิ่งสำคัญสำหรับการนำเสนอ รายงาน และแดชบอร์ด การทำให้กระบวนการนี้เป็นอัตโนมัติในการพัฒนาซอฟต์แวร์ช่วยประหยัดเวลาและรับรองความสอดคล้องกันในเอกสารต่างๆ บทช่วยสอนนี้สาธิตวิธีการสร้างแผนภูมิเส้นด้วยเครื่องหมายโดยใช้ Aspose.Slides สำหรับ Java
**Aspose.Slides สำหรับ Java** เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรมโดยไม่ต้องติดตั้ง Microsoft Office ไลบรารีนี้ช่วยลดความยุ่งยากของงานต่างๆ เช่น การสร้าง การแก้ไข และการส่งออกสไลด์ ทำให้ไลบรารีนี้เป็นเครื่องมือสำคัญสำหรับการสร้างเอกสารอัตโนมัติ
**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการเริ่มต้น Aspose.Slides สำหรับ Java
- ขั้นตอนการสร้างแผนภูมิเส้นด้วยเครื่องหมาย
- การเพิ่มซีรีส์และหมวดหมู่ลงในแผนภูมิ
- การกำหนดค่าคำอธิบายแผนภูมิ
- การบันทึกการนำเสนอ
พร้อมที่จะดำดิ่งลงไปหรือยัง? มาตรวจสอบก่อนว่าคุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนาของคุณพร้อมแล้ว:
1. **ห้องสมุดและสิ่งที่ต้องพึ่งพา:**
   - Aspose.Slides สำหรับไลบรารี Java (แนะนำเวอร์ชัน 25.4)
   - Java Development Kit (JDK) เวอร์ชัน 16 ขึ้นไป
2. **การตั้งค่าสภาพแวดล้อม:**
   - IDE ของคุณควรสนับสนุนเครื่องมือสร้าง Maven หรือ Gradle
   - ตรวจสอบให้แน่ใจว่าคุณมีไฟล์ใบอนุญาตที่ถูกต้องหากจำเป็น
3. **ข้อกำหนดความรู้เบื้องต้น:**
   - ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
   - ความคุ้นเคยกับการสร้างโครงการโดยใช้ Maven หรือ Gradle
เมื่อจัดเตรียมสิ่งเหล่านี้แล้ว มาตั้งค่า Aspose.Slides สำหรับโปรเจ็กต์ของคุณกันเลย!
## การตั้งค่า Aspose.Slides สำหรับ Java
หากต้องการใช้ Aspose.Slides สำหรับ Java คุณต้องรวม Aspose.Slides เป็นส่วนที่ต้องพึ่งพาในโปรเจ็กต์ของคุณ การตั้งค่าจะแตกต่างกันเล็กน้อย ขึ้นอยู่กับว่าคุณใช้ Maven หรือ Gradle
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
**ขั้นตอนการรับใบอนุญาต:**
- สำหรับการทดลองใช้ฟรี โปรดไปที่ [หน้าทดลองใช้งานฟรี](https://releases-aspose.com/slides/java/).
- หากต้องการรับใบอนุญาตชั่วคราว ให้ไปที่ [หน้าใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).
- ซื้อใบอนุญาตเต็มรูปแบบผ่าน [พอร์ทัลการซื้อ](https://purchase-aspose.com/buy).
**การเริ่มต้นขั้นพื้นฐาน:**
นี่คือวิธีการเริ่มต้น Aspose.Slides ในแอปพลิเคชัน Java ของคุณ:
```java
import com.aspose.slides.Presentation;
// เริ่มต้นวัตถุการนำเสนอใหม่
Presentation pres = new Presentation();
```
ตอนนี้เรามาเริ่มสร้างแผนภูมิกันเลย!
## คู่มือการใช้งาน
### คุณลักษณะที่ 1: การสร้างแผนภูมิด้วยเครื่องหมายเริ่มต้น
ส่วนนี้จะแสดงวิธีการสร้างแผนภูมิเส้นพร้อมเครื่องหมาย คุณลักษณะนี้มีความจำเป็นสำหรับการแสดงแนวโน้มข้อมูลอย่างมีประสิทธิภาพ
#### การเพิ่มแผนภูมิเส้น
วิธีเพิ่มแผนภูมิเส้นพร้อมเครื่องหมาย:
```java
import com.aspose.slides.*;
// เข้าถึงสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);
// เพิ่มแผนภูมิเส้นพร้อมเครื่องหมายลงในสไลด์ที่ตำแหน่ง (10, 10) พร้อมขนาด (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### การเคลียร์ซีรีย์และหมวดหมู่
การเริ่มต้นใหม่:
```java
// ล้างซีรีย์และหมวดหมู่ที่มีอยู่เพื่อให้แน่ใจว่าไม่มีรายการใดเสียหาย
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// รับสมุดงานข้อมูลของแผนภูมิเพื่อการจัดการเพิ่มเติม
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### คุณสมบัติ 2: การเพิ่มซีรี่ส์และหมวดหมู่
การเพิ่มชุดข้อมูลและหมวดหมู่เป็นสิ่งสำคัญสำหรับการเติมข้อมูลที่มีความหมายลงในแผนภูมิของคุณ
#### การสร้างซีรีย์ใหม่
หากต้องการเพิ่มซีรีย์ใหม่ชื่อ "ซีรีย์ 1":
```java
// เพิ่มซีรีส์ใหม่ลงในแผนภูมิ
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// เข้าถึงซีรีส์แรกสำหรับการรวบรวมข้อมูล
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### การเติมหมวดหมู่และจุดข้อมูล
การเพิ่มหมวดหมู่และจุดข้อมูลที่สอดคล้องกัน:
```java
// เพิ่มชื่อหมวดหมู่และจุดข้อมูลที่เกี่ยวข้อง
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// การจัดการจุดข้อมูลว่างอย่างมีระเบียบ
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### คุณลักษณะที่ 3: การเพิ่มซีรีส์ที่สองและการเติมจุดข้อมูล
การเพิ่มซีรีส์เพิ่มเติมจะทำให้แผนภูมิของคุณมีความลึกมากขึ้น
#### การสร้างและการเติมข้อมูลซีรีส์ที่สอง
เพื่อเพิ่ม "ซีรี่ส์ 2":
```java
// เพิ่มซีรีย์อีกเรื่องชื่อ 'ซีรีย์ 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// เข้าถึงซีรีส์ที่สองสำหรับการเติมข้อมูล
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// เพิ่มจุดข้อมูลสำหรับ 'ซีรี่ส์ 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### คุณลักษณะที่ 4: การกำหนดค่าคำอธิบายแผนภูมิ
การกำหนดค่าคำอธิบายจะช่วยเพิ่มการอ่านแผนภูมิ
#### การปรับแต่งการตั้งค่าตำนาน
การกำหนดค่า:
```java
// เปิดใช้งานตำนานและตั้งค่าไม่ให้ซ้อนทับบนจุดข้อมูล
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### คุณสมบัติ 5: การบันทึกการนำเสนอ
เมื่อแผนภูมิของคุณพร้อมแล้ว ให้บันทึกการนำเสนอลงในไฟล์
```java
try {
    // บันทึกการนำเสนอที่แก้ไขแล้วไปยังไดเร็กทอรีที่ระบุ
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## การประยุกต์ใช้งานจริง
1. **การรายงานทางธุรกิจ:**
   - ใช้แผนภูมิในรายงานทางการเงินเพื่อแสดงแนวโน้มในช่วงเวลาต่างๆ
2. **การวิเคราะห์ข้อมูล:**
   - แสดงภาพรูปแบบข้อมูลและความสัมพันธ์ในระหว่างขั้นตอนการวิเคราะห์
3. **สื่อการเรียนรู้:**
   - สร้างสไลด์ข้อมูลสำหรับการบรรยายหรือการนำเสนอทางวิชาการ
4. **การจัดการโครงการ:**
   - ปรับปรุงกำหนดเวลาของโครงการด้วยองค์ประกอบแผนภูมิภาพ
5. **การนำเสนอการตลาด:**
   - จัดแสดงแนวโน้มการขายและผลลัพธ์ของแคมเปญอย่างมีประสิทธิภาพโดยใช้แผนภูมิ
## บทสรุป
คุณได้เรียนรู้วิธีการสร้างแผนภูมิเส้นด้วยมาร์กเกอร์ใน Java โดยใช้ Aspose.Slides การเพิ่มชุดข้อมูลและหมวดหมู่ การกำหนดค่าคำอธิบาย และการบันทึกการนำเสนอ ทักษะเหล่านี้มีค่าสำหรับการสร้างเนื้อหาวิดีโอแบบไดนามิกในแอปพลิเคชันระดับมืออาชีพต่างๆ
หากต้องการสำรวจเพิ่มเติมเกี่ยวกับฟีเจอร์ของ Aspose.Slides หรือขอรับการสนับสนุนจากชุมชน โปรดไปที่ [เอกสารอย่างเป็นทางการ](https://docs.aspose.com/slides/java/) หรือเข้าร่วมฟอรัมเช่น Stack Overflow
สนุกกับการเขียนโค้ด!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}