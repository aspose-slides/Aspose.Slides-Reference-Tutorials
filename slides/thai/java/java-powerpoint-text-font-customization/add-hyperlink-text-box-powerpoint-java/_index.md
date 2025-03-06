---
title: เพิ่มไฮเปอร์ลิงก์ลงในกล่องข้อความใน PowerPoint โดยใช้ Java
linktitle: เพิ่มไฮเปอร์ลิงก์ลงในกล่องข้อความใน PowerPoint โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มไฮเปอร์ลิงก์ลงในกล่องข้อความ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างสำหรับนักพัฒนา Java
weight: 23
url: /th/java/java-powerpoint-text-font-customization/add-hyperlink-text-box-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไฮเปอร์ลิงก์ลงในกล่องข้อความใน PowerPoint โดยใช้ Java

## การแนะนำ
ในยุคดิจิทัลปัจจุบัน การสร้างงานนำเสนอแบบไดนามิกที่มีส่วนร่วมและให้ข้อมูลเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ นักพัฒนา Java ที่ต้องการปรับปรุงแอปพลิเคชันของตนด้วยฟีเจอร์โต้ตอบมักจะหันมาใช้ Aspose.Slides สำหรับ Java ซึ่งเป็นไลบรารีอันทรงพลังที่ช่วยให้จัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมได้ บทช่วยสอนนี้จะเจาะลึกถึงฟีเจอร์หนึ่งดังกล่าว: การเพิ่มไฮเปอร์ลิงก์ลงในกล่องข้อความในงานนำเสนอ PowerPoint โดยใช้ Java ในตอนท้ายของคู่มือนี้ คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการใช้งานฟังก์ชันนี้กับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่า คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- ติดตั้ง Integrated Development Environment (IDE) เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ก่อนที่จะเจาะลึกตัวอย่าง ตรวจสอบให้แน่ใจว่าได้นำเข้าแพ็คเกจที่จำเป็น:
```java
import com.aspose.slides.*;
import java.io.File;
```
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ
ขั้นแรก สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงงานนำเสนอ PowerPoint
```java
String dataDir = "Your Document Directory";
Presentation pptxPresentation = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงและแก้ไขสไลด์
รับสไลด์แรกจากงานนำเสนอเพื่อจัดการ
```java
ISlide slide = pptxPresentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างอัตโนมัติ (กล่องข้อความ)
เพิ่มรูปร่างอัตโนมัติประเภทสี่เหลี่ยมผืนผ้าลงในสไลด์ตามพิกัดที่ระบุ
```java
IShape pptxShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 150, 50);
```
## ขั้นตอนที่ 4: เข้าถึงกรอบข้อความ
ส่งรูปร่างไปที่รูปร่างอัตโนมัติและเข้าถึงกรอบข้อความ
```java
IAutoShape pptxAutoShape = (IAutoShape) pptxShape;
pptxAutoShape.addTextFrame("");
ITextFrame textFrame = pptxAutoShape.getTextFrame();
```
## ขั้นตอนที่ 5: เพิ่มข้อความลงในกรอบข้อความ
เพิ่มเนื้อหาข้อความที่ต้องการลงในกรอบข้อความ
```java
textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0).setText("Aspose.Slides");
```
## ขั้นตอนที่ 6: ตั้งค่าไฮเปอร์ลิงก์สำหรับข้อความ
ตั้งค่าไฮเปอร์ลิงก์สำหรับส่วนข้อความที่เพิ่มในขั้นตอนก่อนหน้า
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
IHyperlinkManager hyperlinkManager = portion.getPortionFormat().getHyperlinkManager();
hyperlinkManager.setExternalHyperlinkClick("http://www.aspose.com");
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุ
```java
pptxPresentation.save(dataDir + "hLinkPPTX_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
เมื่อทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธีเพิ่มไฮเปอร์ลิงก์ลงในกล่องข้อความในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้สำเร็จ ความสามารถนี้ช่วยให้คุณสร้างเนื้อหาแบบไดนามิกและโต้ตอบภายในแอปพลิเคชัน Java ของคุณ ปรับปรุงการมีส่วนร่วมและการโต้ตอบของผู้ใช้
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่
 ใช่ คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 มีเอกสารรายละเอียดให้[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะได้รับความช่วยเหลือได้อย่างไรหากฉันประสบปัญหา
 คุณสามารถรับการสนับสนุนจากชุมชน Aspose[ที่นี่](https://forum.aspose.com/c/slides/11).
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้หรือไม่
 ใช่ ใบอนุญาตชั่วคราวพร้อมสำหรับการซื้อ[ที่นี่](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides เข้ากันได้กับไลบรารี Java อื่น ๆ หรือไม่
Aspose.Slides ทำงานร่วมกับไลบรารี Java ต่างๆ ได้ดีเพื่อการจัดการ PowerPoint ที่ครอบคลุม
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
