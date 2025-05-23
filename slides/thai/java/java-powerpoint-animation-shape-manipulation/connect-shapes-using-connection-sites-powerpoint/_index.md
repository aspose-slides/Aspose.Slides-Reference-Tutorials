---
"description": "เรียนรู้วิธีเชื่อมต่อรูปทรงใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ทำให้การนำเสนอของคุณเป็นแบบอัตโนมัติได้อย่างง่ายดาย"
"linktitle": "เชื่อมต่อรูปทรงโดยใช้ไซต์การเชื่อมต่อใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เชื่อมต่อรูปทรงโดยใช้ไซต์การเชื่อมต่อใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เชื่อมต่อรูปทรงโดยใช้ไซต์การเชื่อมต่อใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการเชื่อมต่อรูปทรงโดยใช้ไซต์การเชื่อมต่อใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ช่วยให้เราสามารถจัดการการนำเสนอ PowerPoint ได้ด้วยการเขียนโปรแกรม ทำให้การทำงานต่างๆ เช่น การเชื่อมต่อรูปทรงเป็นไปอย่างราบรื่นและมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งได้จาก [เว็บไซต์](https://www-oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก [หน้าดาวน์โหลด](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): เลือก IDE สำหรับการพัฒนา Java เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: การเข้าถึงคอลเลกชันรูปทรง
เข้าถึงคอลเลกชันรูปทรงสำหรับสไลด์ที่เลือก:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร                    
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## ขั้นตอนที่ 2: การเพิ่มรูปร่างตัวเชื่อมต่อ
เพิ่มรูปร่างตัวเชื่อมต่อลงในคอลเลกชันรูปร่างสไลด์:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## ขั้นตอนที่ 3: การเพิ่มรูปร่างอัตโนมัติ
เพิ่มรูปร่างอัตโนมัติเช่นวงรีและสี่เหลี่ยมผืนผ้า:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## ขั้นตอนที่ 4: การรวมรูปทรงเข้ากับตัวเชื่อมต่อ
เชื่อมต่อรูปทรงเข้ากับตัวเชื่อมต่อ:
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
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเชื่อมต่อรูปทรงโดยใช้ไซต์การเชื่อมต่อใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยความรู้ดังกล่าว คุณสามารถทำให้การนำเสนอ PowerPoint ของคุณเป็นแบบอัตโนมัติและปรับแต่งได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### สามารถใช้ Aspose.Slides สำหรับ Java สำหรับงานจัดการ PowerPoint อื่นๆ ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java มีฟังก์ชันต่างๆ มากมายสำหรับการสร้าง แก้ไข และแปลงงานนำเสนอ PowerPoint
### Aspose.Slides สำหรับ Java สามารถใช้งานฟรีได้หรือไม่?
Aspose.Slides สำหรับ Java เป็นไลบรารีเชิงพาณิชย์ แต่คุณสามารถสำรวจคุณลักษณะต่างๆ ได้ด้วยการทดลองใช้ฟรี เยี่ยมชม [ที่นี่](https://releases.aspose.com/) เพื่อเริ่มต้น
### ฉันจะได้รับการสนับสนุนหรือไม่ หากพบปัญหาใดๆ ในระหว่างการใช้ Aspose.Slides สำหรับ Java
ใช่ คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose ได้ [ที่นี่](https://forum-aspose.com/c/slides/11).
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ ใบอนุญาตชั่วคราวมีไว้สำหรับการทดสอบและประเมินผล คุณสามารถขอรับได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถซื้อใบอนุญาตจากเว็บไซต์ Aspose ได้ [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}