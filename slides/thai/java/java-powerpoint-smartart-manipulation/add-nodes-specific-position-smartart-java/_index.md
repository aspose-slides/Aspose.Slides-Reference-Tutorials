---
title: เพิ่มโหนดที่ตำแหน่งเฉพาะใน SmartArt โดยใช้ Java
linktitle: เพิ่มโหนดที่ตำแหน่งเฉพาะใน SmartArt โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ค้นพบวิธีเพิ่มโหนดที่ตำแหน่งเฉพาะใน SmartArt โดยใช้ Java กับ Aspose.Slides สร้างงานนำเสนอแบบไดนามิกได้อย่างง่ายดาย
weight: 16
url: /th/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มโหนดที่ตำแหน่งเฉพาะใน SmartArt โดยใช้ Java

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มโหนดที่ตำแหน่งเฉพาะใน SmartArt โดยใช้ Java กับ Aspose.Slides SmartArt เป็นฟีเจอร์ใน PowerPoint ที่ช่วยให้คุณสามารถสร้างไดอะแกรมและแผนภูมิที่ดึงดูดสายตาได้
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  ดาวน์โหลด Aspose.Slides สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของเรา:
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
## ขั้นตอนที่ 4: เข้าถึงโหนด SmartArt
เข้าถึงโหนด SmartArt ตามดัชนีที่ต้องการ:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## ขั้นตอนที่ 5: เพิ่มโหนดลูกในตำแหน่งเฉพาะ
เพิ่มโหนดลูกใหม่ในตำแหน่งเฉพาะในโหนดหลัก:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## ขั้นตอนที่ 6: เพิ่มข้อความลงในโหนด
ตั้งค่าข้อความสำหรับโหนดที่เพิ่มใหม่:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไข:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเพิ่มโหนดที่ตำแหน่งเฉพาะใน SmartArt โดยใช้ Java กับ Aspose.Slides ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการรูปร่าง SmartArt โดยทางโปรแกรมเพื่อสร้างงานนำเสนอแบบไดนามิกได้
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มหลายโหนดพร้อมกันได้หรือไม่
ได้ คุณสามารถเพิ่มหลายโหนดโดยทางโปรแกรมได้โดยการวนซ้ำตำแหน่งที่ต้องการ
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides รองรับรูปแบบ PowerPoint ที่หลากหลาย ทำให้มั่นใจได้ถึงความเข้ากันได้กับเวอร์ชันส่วนใหญ่
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของโหนด SmartArt ได้หรือไม่
ใช่ คุณสามารถปรับแต่งรูปลักษณ์ของโหนด รวมถึงขนาด สี และสไตล์ได้
### Aspose.Slides รองรับภาษาการเขียนโปรแกรมอื่นๆ หรือไม่
ใช่ Aspose.Slides มีไลบรารีสำหรับภาษาการเขียนโปรแกรมหลายภาษา รวมถึง .NET และ Python
### มี Aspose.Slides รุ่นทดลองใช้งานหรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
