---
title: เชื่อมต่อรูปร่างโดยใช้ไซต์การเชื่อมต่อใน PowerPoint
linktitle: เชื่อมต่อรูปร่างโดยใช้ไซต์การเชื่อมต่อใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการเชื่อมต่อรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ทำให้การนำเสนอของคุณเป็นแบบอัตโนมัติได้อย่างง่ายดาย
weight: 19
url: /th/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเชื่อมต่อรูปร่างโดยใช้ไซต์การเชื่อมต่อใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ช่วยให้เราจัดการงานนำเสนอ PowerPoint ด้วยโปรแกรม ทำให้งานต่างๆ เช่น การเชื่อมต่อรูปร่างต่างๆ ราบรื่นและมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งได้จาก[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE สำหรับการพัฒนา Java เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: การเข้าถึงคอลเลกชันรูปร่าง
เข้าถึงคอลเลกชันรูปร่างสำหรับสไลด์ที่เลือก:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## ขั้นตอนที่ 2: การเพิ่มรูปร่างตัวเชื่อมต่อ
เพิ่มรูปร่างตัวเชื่อมต่อให้กับคอลเลกชันรูปร่างสไลด์:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## ขั้นตอนที่ 3: การเพิ่มรูปร่างอัตโนมัติ
เพิ่มรูปร่างอัตโนมัติ เช่น วงรีและสี่เหลี่ยมผืนผ้า:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## ขั้นตอนที่ 4: การรวมรูปร่างเข้ากับตัวเชื่อมต่อ
เข้าร่วมรูปร่างกับตัวเชื่อมต่อ:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## ขั้นตอนที่ 5: การตั้งค่าดัชนีไซต์การเชื่อมต่อ
ตั้งค่าดัชนีไซต์การเชื่อมต่อที่ต้องการสำหรับรูปร่าง:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเชื่อมต่อรูปร่างโดยใช้ไซต์การเชื่อมต่อใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยความรู้นี้ คุณสามารถทำให้งานนำเสนอ PowerPoint ของคุณเป็นแบบอัตโนมัติและปรับแต่งได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java สามารถใช้สำหรับงานจัดการ PowerPoint อื่น ๆ ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java มีฟังก์ชันการทำงานที่หลากหลายสำหรับการสร้าง แก้ไข และแปลงงานนำเสนอ PowerPoint
### Aspose.Slides สำหรับ Java ใช้งานได้ฟรีหรือไม่
 Aspose.Slides for Java เป็นไลบรารีเชิงพาณิชย์ แต่คุณสามารถสำรวจฟีเจอร์ต่าง ๆ ของมันได้ด้วยการทดลองใช้ฟรี เยี่ยม[ที่นี่](https://releases.aspose.com/) ที่จะเริ่มต้น.
### ฉันจะได้รับการสนับสนุนหรือไม่หากฉันพบปัญหาใดๆ ในขณะที่ใช้ Aspose.Slides สำหรับ Java
 ใช่ คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose[ที่นี่](https://forum.aspose.com/c/slides/11).
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ ใบอนุญาตชั่วคราวมีไว้เพื่อการทดสอบและประเมินผล คุณสามารถได้รับอย่างใดอย่างหนึ่ง[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถซื้อใบอนุญาตได้จากเว็บไซต์ Aspose[ที่นี่](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
