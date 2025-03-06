---
title: แก้ไขข้อมูลแผนภูมิในสมุดงานภายนอกใน Java Slides
linktitle: แก้ไขข้อมูลแผนภูมิในสมุดงานภายนอกใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแก้ไขข้อมูลแผนภูมิในสมุดงานภายนอกโดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
weight: 17
url: /th/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แก้ไขข้อมูลแผนภูมิในสมุดงานภายนอกใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการแก้ไขข้อมูลแผนภูมิในสมุดงานภายนอกใน Java Slides

ในคู่มือนี้ เราจะสาธิตวิธีแก้ไขข้อมูลแผนภูมิในเวิร์กบุ๊กภายนอกโดยใช้ Aspose.Slides สำหรับ Java คุณจะได้เรียนรู้วิธีแก้ไขข้อมูลแผนภูมิภายในงานนำเสนอ PowerPoint โดยทางโปรแกรม ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว

## ข้อกำหนดเบื้องต้น

- Aspose.Slides สำหรับ Java
- สภาพแวดล้อมการพัฒนาจาวา

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

 ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีแผนภูมิข้อมูลที่เราต้องการแก้ไข แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงแผนภูมิ

เมื่อโหลดงานนำเสนอแล้ว เราจำเป็นต้องเข้าถึงแผนภูมิภายในงานนำเสนอ ในตัวอย่างนี้ เราถือว่าแผนภูมิอยู่บนสไลด์แรกและเป็นรูปร่างแรกบนสไลด์นั้น

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## ขั้นตอนที่ 3: แก้ไขข้อมูลแผนภูมิ

ตอนนี้ เรามาแก้ไขข้อมูลแผนภูมิกันดีกว่า เราจะมุ่งเน้นไปที่การเปลี่ยนแปลงจุดข้อมูลเฉพาะในแผนภูมิ ในตัวอย่างนี้ เราตั้งค่าของจุดข้อมูลแรกในชุดแรกเป็น 100 คุณสามารถปรับค่านี้ได้ตามต้องการ

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

หลังจากทำการเปลี่ยนแปลงที่จำเป็นกับข้อมูลแผนภูมิแล้ว ให้บันทึกงานนำเสนอที่แก้ไขแล้วเป็นไฟล์ใหม่ คุณสามารถระบุพาธของไฟล์เอาต์พุตและรูปแบบได้ตามความต้องการของคุณ

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## ขั้นตอนที่ 5: การล้างข้อมูล

อย่าลืมกำจัดออบเจ็กต์การนำเสนอเพื่อเผยแพร่ทรัพยากรใดๆ

```java
if (pres != null) pres.dispose();
```

ตอนนี้ คุณได้แก้ไขข้อมูลแผนภูมิในสมุดงานภายนอกภายในงานนำเสนอ PowerPoint ของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งโค้ดนี้ให้เหมาะกับความต้องการเฉพาะของคุณและรวมเข้ากับแอปพลิเคชัน Java ของคุณ

## กรอกซอร์สโค้ดให้สมบูรณ์

```java
        // โปรดทราบว่าเส้นทางไปยังสมุดงานภายนอกแทบจะไม่ได้รับการบันทึกในงานนำเสนอ
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

ในคู่มือที่ครอบคลุมนี้ เราได้สำรวจวิธีแก้ไขข้อมูลแผนภูมิในสมุดงานภายนอกภายในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ด คุณจะได้รับความรู้และทักษะในการแก้ไขข้อมูลแผนภูมิโดยทางโปรแกรมได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ฉันจะระบุแผนภูมิหรือสไลด์อื่นได้อย่างไร

 หากต้องการเข้าถึงแผนภูมิหรือสไลด์อื่น ให้แก้ไขดัชนีที่เหมาะสมใน`getSlides().get_Item()` และ`getShapes().get_Item()`วิธีการ โปรดจำไว้ว่าการจัดทำดัชนีเริ่มต้นจาก 0

### ฉันสามารถแก้ไขข้อมูลในหลายแผนภูมิภายในงานนำเสนอเดียวกันได้หรือไม่

ได้ คุณสามารถแก้ไขข้อมูลในหลายแผนภูมิภายในงานนำเสนอเดียวกันได้โดยการทำซ้ำขั้นตอนการแก้ไขข้อมูลแผนภูมิสำหรับแต่ละแผนภูมิ

### จะเกิดอะไรขึ้นถ้าฉันต้องการแก้ไขข้อมูลในเวิร์กบุ๊กภายนอกที่มีรูปแบบอื่น

คุณสามารถปรับใช้โค้ดเพื่อจัดการรูปแบบเวิร์กบุ๊กภายนอกที่แตกต่างกันได้โดยใช้คลาสและวิธีการ Aspose.Cells ที่เหมาะสมสำหรับการอ่านและเขียนข้อมูลในรูปแบบนั้น

### ฉันจะทำให้กระบวนการนี้เป็นอัตโนมัติสำหรับการนำเสนอหลายรายการได้อย่างไร

คุณสามารถสร้างลูปเพื่อประมวลผลงานนำเสนอหลายรายการ โหลดแต่ละรายการ ทำการเปลี่ยนแปลงที่ต้องการ และบันทึกงานนำเสนอที่แก้ไขทีละรายการ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
