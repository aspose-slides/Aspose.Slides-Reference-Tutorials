---
title: รับข้อมูลที่มีประสิทธิภาพของ Shape Bevel ใน PowerPoint
linktitle: รับข้อมูลที่มีประสิทธิภาพของ Shape Bevel ใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีดึงข้อมูลที่มีประสิทธิภาพของรูปร่างเอียงใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงการนำเสนอของคุณด้วยเอฟเฟ็กต์ภาพที่น่าทึ่ง
type: docs
weight: 26
url: /th/java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---
## การแนะนำ
ในการนำเสนอทางธุรกิจสมัยใหม่ การดึงดูดสายตามีบทบาทสำคัญในการถ่ายทอดข้อมูลอย่างมีประสิทธิภาพ องค์ประกอบหนึ่งที่สามารถเพิ่มผลกระทบต่อการมองเห็นของรูปร่างในงานนำเสนอ PowerPoint คือเอฟเฟกต์มุมเอียง Aspose.Slides สำหรับ Java มีเครื่องมืออันทรงพลังในการเข้าถึงและจัดการคุณสมบัติต่างๆ ของรูปร่าง รวมถึงเอฟเฟกต์มุมเอียงด้วย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการดึงข้อมูลที่มีประสิทธิภาพของรูปร่างเอียงโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
2. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
3.  ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีการนำเสนอ PowerPoint:
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดการนำเสนอ
โหลดงานนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides:
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## ขั้นตอนที่ 3: ดึงข้อมูลที่มีประสิทธิภาพของ Bevel
เข้าถึงข้อมูลมุมเอียงที่มีประสิทธิภาพของรูปร่าง:
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## ขั้นตอนที่ 4: พิมพ์คุณสมบัติเอียง
พิมพ์คุณสมบัติบรรเทาใบหน้าด้านบนของรูปทรงที่มีประสิทธิภาพ:
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้สาธิตวิธีการดึงข้อมูลรูปร่างเอียงที่มีประสิทธิภาพใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถเข้าถึงและจัดการคุณสมบัติต่างๆ ของรูปร่างได้อย่างง่ายดาย เพื่อเพิ่มความสวยงามให้กับงานนำเสนอของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้เอฟเฟกต์เอียงกับรูปร่างหลาย ๆ แบบพร้อมกันได้หรือไม่
ได้ คุณสามารถวนซ้ำรูปร่างในสไลด์และใช้เอฟเฟ็กต์มุมเอียงได้ตามต้องการ
### Aspose.Slides รองรับเอฟเฟกต์ 3D อื่น ๆ นอกเหนือจากมุมเอียงหรือไม่
ใช่ Aspose.Slides มีเอฟเฟกต์ 3D มากมายที่คุณสามารถนำไปใช้กับรูปร่างในงานนำเสนอ PowerPoint
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
Aspose.Slides รับประกันความเข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ช่วยให้คุณทำงานได้อย่างราบรื่นในสภาพแวดล้อมที่แตกต่างกัน
### ฉันสามารถปรับแต่งคุณสมบัติเอฟเฟกต์มุมเอียงเพิ่มเติมได้หรือไม่
คุณสามารถควบคุมคุณสมบัติเอฟเฟกต์มุมเอียงได้อย่างเต็มที่ และสามารถปรับแต่งได้ตามความต้องการของคุณ
### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับคำถาม การสนับสนุน หรือแหล่งข้อมูลเพิ่มเติม