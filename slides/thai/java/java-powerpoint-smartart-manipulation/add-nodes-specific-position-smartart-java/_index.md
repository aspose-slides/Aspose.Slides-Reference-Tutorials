---
"description": "ค้นพบวิธีการเพิ่มโหนดในตำแหน่งเฉพาะใน SmartArt โดยใช้ Java กับ Aspose.Slides สร้างการนำเสนอแบบไดนามิกได้อย่างง่ายดาย"
"linktitle": "เพิ่มโหนดในตำแหน่งเฉพาะใน SmartArt โดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มโหนดในตำแหน่งเฉพาะใน SmartArt โดยใช้ Java"
"url": "/th/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มโหนดในตำแหน่งเฉพาะใน SmartArt โดยใช้ Java

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่มโหนดในตำแหน่งเฉพาะใน SmartArt โดยใช้ Java กับ Aspose.Slides SmartArt เป็นฟีเจอร์ใน PowerPoint ที่ช่วยให้คุณสร้างไดอะแกรมและแผนภูมิที่ดึงดูดสายตาได้
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
2. ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
3. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ก่อนอื่นให้เรานำเข้าแพ็คเกจที่จำเป็นลงในโค้ด Java ของเรา:
```java
import com.aspose.slides.*;
import java.io.File;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์การนำเสนอ
เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาสการนำเสนอ:
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์การนำเสนอ
เข้าถึงสไลด์ที่คุณต้องการเพิ่ม SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่าง SmartArt
เพิ่มรูปร่าง SmartArt ลงในสไลด์:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## ขั้นตอนที่ 4: เข้าถึง SmartArt Node
เข้าถึงโหนด SmartArt ที่ดัชนีที่ต้องการ:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## ขั้นตอนที่ 5: เพิ่มโหนดย่อยในตำแหน่งเฉพาะ
เพิ่มโหนดย่อยใหม่ในตำแหน่งเฉพาะในโหนดหลัก:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## ขั้นตอนที่ 6: เพิ่มข้อความลงในโหนด
ตั้งค่าข้อความสำหรับโหนดที่เพิ่มใหม่:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไข:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการเพิ่มโหนดในตำแหน่งเฉพาะใน SmartArt โดยใช้ Java กับ Aspose.Slides เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถจัดการรูปร่าง SmartArt ได้ด้วยการเขียนโปรแกรมเพื่อสร้างการนำเสนอแบบไดนามิก
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มโหนดหลายโหนดพร้อมกันได้ไหม
ใช่ คุณสามารถเพิ่มโหนดหลายโหนดได้โดยการเขียนโปรแกรม โดยการวนซ้ำตามตำแหน่งที่ต้องการ
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกเวอร์ชันหรือไม่
Aspose.Slides รองรับรูปแบบ PowerPoint หลากหลาย เพื่อให้แน่ใจว่าเข้ากันได้กับเวอร์ชันส่วนใหญ่
### ฉันสามารถปรับแต่งลักษณะของโหนด SmartArt ได้หรือไม่
ใช่ คุณสามารถปรับแต่งลักษณะของโหนดได้ รวมถึงขนาด สี และรูปแบบ
### Aspose.Slides รองรับภาษาการเขียนโปรแกรมอื่น ๆ หรือไม่?
ใช่ Aspose.Slides มีไลบรารีสำหรับภาษาการเขียนโปรแกรมหลายภาษา รวมถึง .NET และ Python
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}