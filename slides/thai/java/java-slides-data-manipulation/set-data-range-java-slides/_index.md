---
title: ตั้งค่าช่วงข้อมูลใน Java Slides
linktitle: ตั้งค่าช่วงข้อมูลใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าช่วงข้อมูลในสไลด์ Java ได้อย่างง่ายดายด้วย Aspose.Slides สำหรับ Java สร้างงานนำเสนอแบบไดนามิกและขับเคลื่อนด้วยข้อมูลด้วยคำแนะนำทีละขั้นตอนนี้
weight: 18
url: /th/java/data-manipulation/set-data-range-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## รู้เบื้องต้นเกี่ยวกับการตั้งค่าช่วงข้อมูลใน Java Slides

การนำเสนอมักประกอบด้วยแผนภูมิและกราฟเพื่อถ่ายทอดข้อมูลอย่างมีประสิทธิภาพ Aspose.Slides สำหรับ Java ช่วยให้กระบวนการทำงานกับแผนภูมิในงานนำเสนอ PowerPoint ง่ายขึ้น ในบทช่วยสอนนี้ เราจะมุ่งเน้นไปที่งานที่สำคัญในการตั้งค่าช่วงข้อมูลสำหรับแผนภูมิภายในงานนำเสนอ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนาจาวา
-  Aspose.Slides สำหรับ Java API (คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/java/-)
-  งานนำเสนอ PowerPoint พร้อมแผนภูมิ (เราจะเรียกมันว่า`ExistingChart.pptx`-

## ขั้นตอนที่ 1: เริ่มต้นใช้งาน

ในการเริ่มต้น ให้ตั้งค่าสภาพแวดล้อม Java ของเราและโหลดงานนำเสนอ PowerPoint ที่มีอยู่ซึ่งมีแผนภูมิที่เราต้องการทำงานด้วย

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
// เข้าถึงสไลด์แรกและเพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## ขั้นตอนที่ 2: การตั้งค่าช่วงข้อมูล

ตอนนี้เรามีการนำเสนอและวัตถุแผนภูมิแล้ว เรามาตั้งค่าช่วงข้อมูลสำหรับแผนภูมิกันดีกว่า ช่วงข้อมูลจะระบุว่าเซลล์ใดจากสเปรดชีตที่ใช้ในการเติมข้อมูลแผนภูมิ

```java
chart.getChartData().setRange("Sheet1!A1:B4");
```

ในตัวอย่างนี้ เรากำลังตั้งค่าช่วงข้อมูลเพื่อรวมเซลล์ A1 ถึง B4 จาก "Sheet1" ในสเปรดชีตของเรา

## ขั้นตอนที่ 3: บันทึกการนำเสนอ

หลังจากตั้งค่าช่วงข้อมูลแล้ว จำเป็นต้องบันทึกงานนำเสนอที่แก้ไขแล้วของเรา

```java
presentation.save(dataDir + "SetDataRange_out.pptx", SaveFormat.Pptx);
```

 บรรทัดโค้ดนี้จะบันทึกงานนำเสนอเป็นไฟล์ใหม่ชื่อ`SetDataRange_out.pptx` ในไดเร็กทอรีที่ระบุ

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับการตั้งค่าช่วงข้อมูลใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
// เข้าถึง SlideMarker แรกและเพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
chart.getChartData().setRange("Sheet1!A1:B4");
presentation.save(dataDir + "SetDataRange_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าช่วงข้อมูลสำหรับแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API นี้ทำให้กระบวนการทำงานกับการนำเสนอง่ายขึ้น และช่วยให้นักพัฒนาทำงานอัตโนมัติได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการติดตั้ง Aspose.Slides สำหรับ Java ให้ทำตามขั้นตอนเหล่านี้:

1.  ดาวน์โหลด API จาก[ที่นี่](https://releases.aspose.com/slides/java/).
2. เพิ่มไฟล์ JAR ที่ดาวน์โหลดไปยังโปรเจ็กต์ Java ของคุณ
3. ตอนนี้คุณพร้อมที่จะใช้ Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว

### ฉันสามารถตั้งค่าช่วงข้อมูลแบบไดนามิกสำหรับแผนภูมิของฉันได้หรือไม่

ใช่ คุณสามารถตั้งค่าช่วงข้อมูลแบบไดนามิกสำหรับแผนภูมิของคุณได้โดยใช้ตัวแปรในโค้ด Java ของคุณ ซึ่งช่วยให้คุณสามารถอัปเดตช่วงข้อมูลตามการเปลี่ยนแปลงข้อมูลในแอปพลิเคชันของคุณ

### Aspose.Slides สำหรับ Java เหมาะสำหรับใช้ในเชิงพาณิชย์หรือไม่

ใช่ Aspose.Slides สำหรับ Java เหมาะสำหรับการใช้งานส่วนตัวและเชิงพาณิชย์ มีชุดคุณลักษณะที่มีประสิทธิภาพสำหรับการทำงานกับงานนำเสนอ PowerPoint ในแอปพลิเคชัน Java

### ฉันจะเข้าถึงสไลด์และรูปร่างเฉพาะภายในงานนำเสนอได้อย่างไร

คุณสามารถเข้าถึงสไลด์และรูปร่างเฉพาะภายในงานนำเสนอได้โดยใช้ Aspose.Slides สำหรับ Java API ข้อมูลโค้ดที่ให้ไว้ในบทช่วยสอนนี้สาธิตวิธีเข้าถึงสไลด์แรกและรูปร่างแรก (แผนภูมิ) บนสไลด์นั้น

### ฉันจะหาเอกสารและตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมสำหรับ Aspose.Slides สำหรับ Java บนเว็บไซต์เอกสารประกอบของ Aspose:[Aspose.Slides สำหรับการอ้างอิง Java API](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
