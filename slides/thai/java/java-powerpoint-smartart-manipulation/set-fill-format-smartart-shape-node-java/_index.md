---
title: ตั้งค่ารูปแบบการเติมสำหรับโหนดรูปร่าง SmartArt ใน Java
linktitle: ตั้งค่ารูปแบบการเติมสำหรับโหนดรูปร่าง SmartArt ใน Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่ารูปแบบการเติมสำหรับโหนดรูปร่าง SmartArt ใน Java โดยใช้ Aspose.Slides ปรับปรุงการนำเสนอของคุณด้วยสีสันที่สดใสและภาพที่น่าดึงดูด
weight: 12
url: /th/java/java-powerpoint-smartart-manipulation/set-fill-format-smartart-shape-node-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในภูมิทัศน์แบบไดนามิกของการสร้างเนื้อหาดิจิทัล Aspose.Slides สำหรับ Java โดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับการสร้างสรรค์งานนำเสนอที่สวยงามน่าทึ่งได้อย่างง่ายดายและมีประสิทธิภาพ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น การเรียนรู้ศิลปะในการจัดการรูปร่างภายในสไลด์เป็นสิ่งสำคัญสำหรับการสร้างงานนำเสนอที่น่าดึงดูดซึ่งสร้างความประทับใจไม่รู้ลืมให้กับผู้ชมของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกโลกแห่งการตั้งค่ารูปแบบการเติมสำหรับโหนดรูปร่าง SmartArt ใน Java โดยใช้ Aspose.Slides ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK เวอร์ชันล่าสุดได้จาก Oracle[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides สำหรับไลบรารี Java: รับ Aspose.Slides สำหรับไลบรารี Java จากเว็บไซต์ Aspose คุณสามารถดาวน์โหลดได้จากลิงก์ที่ให้ไว้ในบทช่วยสอน[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่คุณต้องการสำหรับการพัฒนา Java ตัวเลือกยอดนิยม ได้แก่ IntelliJ IDEA, Eclipse และ NetBeans

## แพ็คเกจนำเข้า
ในบทช่วยสอนนี้ เราจะใช้แพ็คเกจต่างๆ จากไลบรารี Aspose.Slides เพื่อจัดการรูปร่าง SmartArt และโหนด ก่อนที่เราจะเริ่ม เรามานำเข้าแพ็คเกจเหล่านี้เข้าสู่โปรเจ็กต์ Java ของเราก่อน:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ
เริ่มต้นวัตถุการนำเสนอเพื่อเริ่มทำงานกับสไลด์:
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์
ดึงสไลด์ที่คุณต้องการเพิ่มรูปร่าง SmartArt:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างและโหนด SmartArt
เพิ่มรูปร่าง SmartArt ให้กับสไลด์และแทรกโหนดลงไป:
```java
ISmartArt chevron = slide.getShapes().addSmartArt(10, 10, 800, 60, SmartArtLayoutType.ClosedChevronProcess);
ISmartArtNode node = chevron.getAllNodes().addNode();
node.getTextFrame().setText("Some text");
```
## ขั้นตอนที่ 4: ตั้งค่าสีเติมโหนด
ตั้งค่าสีเติมสำหรับแต่ละรูปร่างภายในโหนด SmartArt:
```java
for (ISmartArtShape item : node.getShapes()) {
    item.getFillFormat().setFillType(FillType.Solid);
    item.getFillFormat().getSolidFillColor().setColor(Color.RED);
}
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกงานนำเสนอหลังจากทำการแก้ไขทั้งหมด:
```java
presentation.save(dataDir + "FillFormat_SmartArt_ShapeNode_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
การเรียนรู้ศิลปะแห่งการตั้งค่ารูปแบบการเติมสำหรับโหนดรูปร่าง SmartArt ใน Java โดยใช้ Aspose.Slides ช่วยให้คุณสร้างงานนำเสนอที่ดึงดูดสายตาซึ่งโดนใจผู้ชมของคุณ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้ประโยชน์จากฟีเจอร์อันทรงพลังของ Aspose.Slides คุณสามารถปลดล็อกความเป็นไปได้ไม่รู้จบในการสร้างงานนำเสนอที่น่าสนใจ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับไลบรารี Java อื่นได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java สามารถผสานรวมกับไลบรารี Java อื่นๆ ได้อย่างราบรื่น เพื่อปรับปรุงกระบวนการสร้างงานนำเสนอของคุณ
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ Java ฟรีได้จากลิงก์ที่ให้ไว้ในบทช่วยสอน
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาทรัพยากรสนับสนุนที่ครอบคลุม รวมถึงฟอรัมและเอกสารประกอบได้บนเว็บไซต์ Aspose
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของรูปร่าง SmartArt เพิ่มเติมได้หรือไม่
อย่างแน่นอน! Aspose.Slides สำหรับ Java มีตัวเลือกการปรับแต่งที่หลากหลายเพื่อปรับแต่งรูปลักษณ์ของรูปร่าง SmartArt ตามความต้องการของคุณ
### Aspose.Slides สำหรับ Java เหมาะสำหรับทั้งผู้เริ่มต้นและนักพัฒนาที่มีประสบการณ์หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับนักพัฒนาทุกระดับทักษะ โดยนำเสนอ API ที่ใช้งานง่ายและเอกสารประกอบที่ครอบคลุมเพื่ออำนวยความสะดวกในการบูรณาการและการใช้งานที่ง่ายดาย
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
