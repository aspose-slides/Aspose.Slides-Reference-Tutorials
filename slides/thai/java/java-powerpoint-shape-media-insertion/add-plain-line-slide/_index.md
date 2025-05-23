---
"description": "เรียนรู้วิธีการเพิ่มบรรทัดธรรมดาลงในสไลด์ PowerPoint ด้วยโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java เพิ่มประสิทธิภาพการทำงานของคุณด้วยคู่มือทีละขั้นตอนนี้"
"linktitle": "เพิ่มเส้นธรรมดาลงในสไลด์"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มเส้นธรรมดาลงในสไลด์"
"url": "/th/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มเส้นธรรมดาลงในสไลด์

## การแนะนำ
Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนา Java สามารถทำงานกับการนำเสนอ PowerPoint ได้ด้วยโปรแกรม ด้วย Aspose.Slides คุณสามารถสร้าง แก้ไข และแปลงไฟล์ PowerPoint ได้อย่างง่ายดาย ช่วยประหยัดเวลาและความพยายาม ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มบรรทัดธรรมดาลงในสไลด์ในการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java และเพิ่มลงในโปรเจ็กต์ Java ของคุณแล้ว
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ โดยคุณสามารถทำได้ดังนี้:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม
ขั้นแรก ให้สร้างโปรเจ็กต์ Java ใหม่ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในคลาสพาธของโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
## ขั้นตอนที่ 2: สร้างงานนำเสนอใหม่
ถัดไปสร้างอินสแตนซ์ `Presentation` ชั้นเรียนเพื่อสร้างการนำเสนอ PowerPoint ใหม่
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มสไลด์
รับสไลด์แรกของการนำเสนอและเก็บไว้ในตัวแปร
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างเส้น
ตอนนี้ เพิ่มเส้นชนิดรูปร่างอัตโนมัติลงในสไลด์
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอลงดิสก์
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ขอแสดงความยินดี! คุณได้เพิ่มบรรทัดธรรมดาลงในสไลด์ในงานนำเสนอ PowerPoint สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java ด้วย Aspose.Slides คุณสามารถจัดการไฟล์ PowerPoint ได้อย่างง่ายดายด้วยโปรแกรม ซึ่งเปิดโลกแห่งความเป็นไปได้ให้กับแอปพลิเคชัน Java ของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งคุณสมบัติของรูปร่างเส้นได้หรือไม่?
ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ เช่น สีเส้น ความกว้าง สไตล์ และอื่นๆ ได้โดยใช้ Aspose.Slides API
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ได้หรือไม่
ใช่ Aspose.Slides รองรับรูปแบบ PowerPoint ต่างๆ รวมถึง PPT, PPTX และอื่นๆ เพื่อให้แน่ใจว่าสามารถใช้งานร่วมกับเวอร์ชันต่างๆ ได้
### Aspose.Slides รองรับการเพิ่มรูปร่างอื่น ๆ นอกจากเส้นหรือไม่
แน่นอน! Aspose.Slides มีรูปร่างให้เลือกหลากหลาย เช่น สี่เหลี่ยมผืนผ้า วงกลม ลูกศร และอื่นๆ อีกมากมาย
### ฉันสามารถเพิ่มข้อความลงในสไลด์พร้อมกับรูปร่างเส้นได้หรือไม่
ใช่ คุณสามารถเพิ่มข้อความ รูปภาพ และเนื้อหาอื่นๆ ลงในสไลด์โดยใช้ Aspose.Slides API ได้
### มีรุ่นทดลองใช้งานฟรีสำหรับ Aspose.Slides หรือไม่
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีของ Aspose.Slides ได้จาก [ที่นี่](https://releases-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}