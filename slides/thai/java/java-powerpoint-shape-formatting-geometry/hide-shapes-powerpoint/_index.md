---
title: ซ่อนรูปร่างใน PowerPoint
linktitle: ซ่อนรูปร่างใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีซ่อนรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java พร้อมคำแนะนำทีละขั้นตอนโดยละเอียดของเรา เหมาะสำหรับนักพัฒนา Java ทุกระดับ
weight: 27
url: /th/java/java-powerpoint-shape-formatting-geometry/hide-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ซ่อนรูปร่างใน PowerPoint

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการซ่อนรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java! หากคุณจำเป็นต้องซ่อนรูปร่างเฉพาะในงานนำเสนอ PowerPoint ของคุณโดยทางโปรแกรม แสดงว่าคุณมาถูกที่แล้ว คู่มือนี้จะอธิบายแต่ละขั้นตอนในรูปแบบการสนทนาที่เรียบง่าย ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นใช้งาน Java เราก็พร้อมช่วยคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides สำหรับ Java Library: ดาวน์โหลดเวอร์ชันล่าสุดจาก[Aspose.Slides สำหรับรุ่น Java](https://releases.aspose.com/slides/java/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE): Java IDE ใดๆ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
- ความเข้าใจพื้นฐานของ Java: แม้ว่าบทช่วยสอนนี้เหมาะสำหรับผู้เริ่มต้น แต่ความเข้าใจพื้นฐานเกี่ยวกับ Java จะเป็นประโยชน์
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Slides ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.*;

```
ในส่วนนี้ เราจะแจกแจงขั้นตอนการซ่อนรูปร่างใน PowerPoint ให้เป็นขั้นตอนที่ง่ายต่อการปฏิบัติตาม แต่ละขั้นตอนประกอบด้วยหัวข้อและคำอธิบายโดยละเอียด
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ก่อนอื่น คุณต้องตั้งค่าโปรเจ็กต์ Java ของคุณและรวม Aspose.Slides เป็นสิ่งอ้างอิง มีวิธีดังนี้:
### สร้างโปรเจ็กต์ Java ใหม่
 เปิด IDE ของคุณและสร้างโครงการ Java ใหม่ ตั้งชื่อสิ่งที่เกี่ยวข้องเช่น`HideShapesInPowerPoint`.
### เพิ่มไลบรารี Aspose.Slides
 ดาวน์โหลดไฟล์ Aspose.Slides JAR จากไฟล์[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/slides/java/) และเพิ่มลงใน classpath ของโครงการของคุณ ขั้นตอนนี้อาจแตกต่างกันเล็กน้อยขึ้นอยู่กับ IDE ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
เอาล่ะ มาเริ่มเขียนโค้ดกันดีกว่า คุณต้องเริ่มต้นวัตถุการนำเสนอที่แสดงถึงไฟล์ PowerPoint ของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึง PPTX
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
ถัดไป คุณจะต้องเข้าถึงสไลด์แรกในงานนำเสนอของคุณ
```java
// รับสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างลงในสไลด์
สำหรับตัวอย่างนี้ เราจะเพิ่มสองรูปร่างลงในสไลด์ ได้แก่ สี่เหลี่ยมผืนผ้าและรูปทรงดวงจันทร์
```java
// เพิ่มรูปร่างอัตโนมัติของประเภทสี่เหลี่ยมผืนผ้า
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## ขั้นตอนที่ 5: กำหนดข้อความแสดงแทนและซ่อนรูปร่าง
เมื่อต้องการระบุรูปร่างที่คุณต้องการซ่อน ให้ตั้งค่าข้อความแสดงแทนสำหรับรูปร่างเหล่านั้น จากนั้น วนซ้ำรูปร่างทั้งหมดและซ่อนรูปร่างที่ตรงกับข้อความแสดงแทน
```java
String alttext = "User Defined";
int iCount = sld.getShapes().size();
for (int i = 0; i < iCount; i++) {
    AutoShape ashp = (AutoShape) sld.getShapes().get_Item(i);
    if (ashp.getAlternativeText().equals(alttext)) {
        ashp.setHidden(true);
    }
}
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่คุณต้องการ
```java
// บันทึกการนำเสนอลงดิสก์
pres.save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีซ่อนรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เรียบร้อยแล้ว คำแนะนำทีละขั้นตอนนี้ครอบคลุมทุกอย่างตั้งแต่การจัดเตรียมโปรเจ็กต์ของคุณไปจนถึงการบันทึกการนำเสนอขั้นสุดท้าย ด้วยทักษะเหล่านี้ คุณสามารถทำให้งานนำเสนอ PowerPoint เป็นอัตโนมัติและปรับแต่งได้อย่างมีประสิทธิภาพมากขึ้น
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides for Java เป็น API ที่ทรงพลังสำหรับจัดการไฟล์ PowerPoint โดยทางโปรแกรม ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการงานนำเสนอได้โดยไม่ต้องใช้ Microsoft PowerPoint
### ฉันจะซ่อนรูปร่างใน PowerPoint โดยใช้ Java ได้อย่างไร
 คุณสามารถซ่อนรูปร่างได้โดยการตั้งค่า`setHidden` ทรัพย์สินเพื่อ`true`- ซึ่งเกี่ยวข้องกับการระบุรูปร่างด้วยข้อความแสดงแทนและการวนซ้ำรูปร่างบนสไลด์
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Slides พร้อมใช้งานสำหรับภาษาการเขียนโปรแกรมต่างๆ รวมถึง .NET, Python และ C-- อย่างไรก็ตาม คู่มือนี้ครอบคลุมถึง Java โดยเฉพาะ
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจาก[ฟอรั่มการสนับสนุน Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
