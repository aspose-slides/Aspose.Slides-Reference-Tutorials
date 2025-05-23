---
"description": "เรียนรู้วิธีแก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "แก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกใน Java Slides"
"url": "/th/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกใน Java Slides


## บทนำเกี่ยวกับการแก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกใน Java Slides

ในคู่มือนี้ เราจะสาธิตวิธีแก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกโดยใช้ Aspose.Slides สำหรับ Java คุณจะได้เรียนรู้วิธีแก้ไขข้อมูลแผนภูมิภายในโปรแกรมการนำเสนอ PowerPoint ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโครงการของคุณแล้ว

## ข้อกำหนดเบื้องต้น

- Aspose.Slides สำหรับ Java
- สภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีแผนภูมิที่มีข้อมูลที่เราต้องการแก้ไข แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงแผนภูมิ

เมื่อโหลดงานนำเสนอแล้ว เราจำเป็นต้องเข้าถึงแผนภูมิภายในงานนำเสนอ ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่ในสไลด์แรกและเป็นรูปร่างแรกในสไลด์นั้น

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## ขั้นตอนที่ 3: แก้ไขข้อมูลแผนภูมิ

ตอนนี้เรามาปรับเปลี่ยนข้อมูลแผนภูมิกัน เราจะเน้นที่การเปลี่ยนแปลงจุดข้อมูลเฉพาะในแผนภูมิ ในตัวอย่างนี้ เราตั้งค่าจุดข้อมูลแรกในชุดข้อมูลแรกเป็น 100 คุณสามารถปรับเปลี่ยนค่านี้ได้ตามต้องการ

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

หลังจากทำการเปลี่ยนแปลงข้อมูลแผนภูมิตามที่จำเป็นแล้ว ให้บันทึกการนำเสนอที่แก้ไขลงในไฟล์ใหม่ คุณสามารถระบุเส้นทางและรูปแบบของไฟล์เอาต์พุตตามความต้องการของคุณได้

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## ขั้นตอนที่ 5: การทำความสะอาด

อย่าลืมกำจัดวัตถุการนำเสนอเพื่อปล่อยทรัพยากรใดๆ

```java
if (pres != null) pres.dispose();
```

ตอนนี้คุณได้แก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกในงานนำเสนอ PowerPoint ของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งโค้ดนี้ให้เหมาะกับความต้องการเฉพาะของคุณและรวมเข้ากับแอปพลิเคชัน Java ของคุณได้

## ซอร์สโค้ดที่สมบูรณ์

```java
        // สังเกตว่าเส้นทางไปยังสมุดงานภายนอกแทบจะไม่ได้รับการบันทึกไว้ในงานนำเสนอ
        // ดังนั้นโปรดคัดลอกไฟล์ externalWorkbook.xlsx จากไดเร็กทอรี Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ ก่อนที่จะรันตัวอย่าง
        // เส้นทางไปยังไดเร็กทอรีเอกสาร
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## บทสรุป

ในคู่มือที่ครอบคลุมนี้ เราได้อธิบายวิธีการแก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกภายในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับ คุณจะได้รับความรู้และทักษะในการแก้ไขข้อมูลแผนภูมิด้วยโปรแกรมได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ฉันจะระบุแผนภูมิหรือสไลด์อื่นได้อย่างไร

หากต้องการเข้าถึงแผนภูมิหรือสไลด์อื่น ให้แก้ไขดัชนีที่เหมาะสมใน `getSlides().get_Item()` และ `getShapes().get_Item()` วิธีการ จำไว้ว่าการจัดทำดัชนีเริ่มจาก 0

### ฉันสามารถแก้ไขข้อมูลในหลายแผนภูมิภายในงานนำเสนอเดียวกันได้หรือไม่

ใช่ คุณสามารถแก้ไขข้อมูลในแผนภูมิหลายรายการภายในงานนำเสนอเดียวกันได้ โดยการทำซ้ำขั้นตอนการแก้ไขข้อมูลแผนภูมิสำหรับแผนภูมิแต่ละรายการ

### จะเกิดอะไรขึ้นหากฉันต้องการแก้ไขข้อมูลในเวิร์กบุ๊กภายนอกที่มีรูปแบบที่แตกต่างกัน?

คุณสามารถปรับแต่งโค้ดเพื่อจัดการรูปแบบเวิร์กบุ๊กภายนอกที่แตกต่างกันได้โดยใช้คลาสและวิธีการ Aspose.Cells ที่เหมาะสมสำหรับการอ่านและเขียนข้อมูลในรูปแบบนั้น

### ฉันจะทำให้กระบวนการนี้เป็นแบบอัตโนมัติสำหรับการนำเสนอหลาย ๆ ครั้งได้อย่างไร

คุณสามารถสร้างลูปในการประมวลผลการนำเสนอหลายรายการ โหลดแต่ละรายการ ทำการเปลี่ยนแปลงตามต้องการ และบันทึกการนำเสนอที่แก้ไขทีละรายการ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}