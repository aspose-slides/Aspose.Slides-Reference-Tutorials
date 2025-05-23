---
"description": "ค้นพบวิธีการอัปเดตข้อความโหนด SmartArt ใน PowerPoint โดยใช้ Java กับ Aspose.Slides เพื่อปรับปรุงการปรับแต่งการนำเสนอ"
"linktitle": "การเปลี่ยนข้อความบน SmartArt Node โดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การเปลี่ยนข้อความบน SmartArt Node โดยใช้ Java"
"url": "/th/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเปลี่ยนข้อความบน SmartArt Node โดยใช้ Java

## การแนะนำ
SmartArt ใน PowerPoint เป็นฟีเจอร์อันทรงพลังสำหรับการสร้างไดอะแกรมที่ดึงดูดสายตา Aspose.Slides สำหรับ Java ให้การสนับสนุนที่ครอบคลุมในการจัดการองค์ประกอบ SmartArt ด้วยโปรแกรม ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการเปลี่ยนแปลงข้อความบนโหนด SmartArt โดยใช้ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ดาวน์โหลดและอ้างอิงในโปรเจ็กต์ Java ของคุณ
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides ในโค้ด Java ของคุณ
```java
import com.aspose.slides.*;
```
ให้เราแบ่งตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
สร้างอินสแตนซ์ใหม่ของ `Presentation` ชั้นเรียนเพื่อทำงานกับการนำเสนอ PowerPoint
## ขั้นตอนที่ 2: เพิ่ม SmartArt ลงในสไลด์
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
เพิ่ม SmartArt ลงในสไลด์แรก ในตัวอย่างนี้ เราจะใช้ `BasicCycle` เค้าโครง
## ขั้นตอนที่ 3: เข้าถึง SmartArt Node
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
รับการอ้างอิงถึงโหนดรากที่สองของ SmartArt
## ขั้นตอนที่ 4: ตั้งค่าข้อความบนโหนด
```java
node.getTextFrame().setText("Second root node");
```
ตั้งค่าข้อความสำหรับโหนด SmartArt ที่เลือก
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุ

## บทสรุป
ในบทช่วยสอนนี้ เราได้สาธิตวิธีการเปลี่ยนข้อความบนโหนด SmartArt โดยใช้ Java และ Aspose.Slides ด้วยความรู้ดังกล่าว คุณสามารถจัดการองค์ประกอบ SmartArt ในงานนำเสนอ PowerPoint ของคุณได้อย่างไดนามิก ช่วยเพิ่มความสวยงามและความชัดเจนให้กับองค์ประกอบเหล่านี้
## คำถามที่พบบ่อย
### ฉันสามารถเปลี่ยนเค้าโครงของ SmartArt หลังจากเพิ่มลงในสไลด์แล้วได้หรือไม่
ใช่ คุณสามารถเปลี่ยนเค้าโครงได้โดยการเข้าถึง `SmartArt.setAllNodes(LayoutType)` วิธี.
### Aspose.Slides เข้ากันได้กับ Java 11 หรือไม่
ใช่ Aspose.Slides สำหรับ Java สามารถใช้งานได้กับ Java 11 และเวอร์ชันใหม่กว่า
### ฉันสามารถปรับแต่งรูปลักษณ์ของโหนด SmartArt โดยโปรแกรมได้หรือไม่
แน่นอน คุณสามารถปรับเปลี่ยนคุณสมบัติต่างๆ เช่น สี ขนาด และรูปร่าง โดยใช้ Aspose.Slides API
### Aspose.Slides รองรับเค้าโครง SmartArt ประเภทอื่นๆ หรือไม่
ใช่ Aspose.Slides รองรับเค้าโครง SmartArt ที่หลากหลาย ช่วยให้คุณสามารถเลือกเค้าโครงที่เหมาะกับความต้องการในการนำเสนอของคุณได้
### ฉันสามารถหาทรัพยากรและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
คุณสามารถเยี่ยมชม [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับข้อมูลอ้างอิงและบทช่วยสอน API โดยละเอียด นอกจากนี้ คุณยังสามารถขอความช่วยเหลือจาก [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) หรือพิจารณาซื้อ [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อการสนับสนุนอย่างมืออาชีพ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}