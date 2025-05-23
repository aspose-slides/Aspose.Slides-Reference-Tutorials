---
"description": "เชี่ยวชาญการจัดเค้าโครงแผนภูมิองค์กรใน SmartArt โดยใช้ Java ด้วย Aspose.Slides เพื่อปรับปรุงภาพในการนำเสนอได้อย่างง่ายดาย"
"linktitle": "จัดระเบียบเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "จัดระเบียบเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java"
"url": "/th/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# จัดระเบียบเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำขั้นตอนในการจัดระเบียบรูปแบบเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java โดยเฉพาะอย่างยิ่งการใช้ประโยชน์จากไลบรารี Aspose.Slides SmartArt ในงานนำเสนอสามารถเพิ่มความน่าสนใจและความคมชัดของข้อมูลได้อย่างมาก จึงจำเป็นอย่างยิ่งที่จะต้องเชี่ยวชาญการจัดการข้อมูลเหล่านี้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
2. ดาวน์โหลดและตั้งค่าไลบรารี Aspose.Slides แล้ว หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดจาก [ที่นี่](https://releases-aspose.com/slides/java/).
3. ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java

## แพ็คเกจนำเข้า
ประการแรก ให้ทำการนำเข้าแพ็คเกจที่จำเป็น:
```java
import com.aspose.slides.*;
```
ให้เราแบ่งตัวอย่างที่ให้มาเป็นขั้นตอนต่างๆ ดังต่อไปนี้:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
สร้างวัตถุการนำเสนอใหม่
## ขั้นตอนที่ 2: เพิ่ม SmartArt ลงในสไลด์
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
เพิ่ม SmartArt ลงในสไลด์ที่ต้องการโดยใช้ขนาดและประเภทเค้าโครงที่ระบุ
## ขั้นตอนที่ 3: ตั้งค่าเค้าโครงแผนผังองค์กร
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
ตั้งค่ารูปแบบเค้าโครงแผนผังองค์กร ในตัวอย่างนี้ เราจะใช้รูปแบบแขวนด้านซ้าย
## ขั้นตอนที่ 4: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
บันทึกการนำเสนอด้วยเค้าโครงแผนภูมิที่เป็นระเบียบ

## บทสรุป
การจัดระเบียบรูปแบบแผนภูมิใน SmartArt โดยใช้ Java ช่วยให้คุณสามารถสร้างงานนำเสนอที่น่าสนใจได้อย่างง่ายดาย ด้วย Aspose.Slides กระบวนการนี้จึงราบรื่นและมีประสิทธิภาพ ช่วยให้คุณสามารถมุ่งเน้นไปที่การสร้างเนื้อหาที่มีประสิทธิภาพได้
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ที่แตกต่างกันหรือไม่
ใช่ Aspose.Slides เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ต่างๆ ช่วยให้นักพัฒนามีความยืดหยุ่นมากขึ้น
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏขององค์ประกอบ SmartArt โดยใช้ Aspose.Slides ได้หรือไม่
แน่นอนว่า Aspose.Slides มีตัวเลือกการปรับแต่งองค์ประกอบ SmartArt มากมาย ทำให้คุณสามารถปรับแต่งให้ตรงตามความต้องการเฉพาะของคุณได้
### Aspose.Slides มีเอกสารประกอบที่ครอบคลุมสำหรับนักพัฒนาหรือไม่
ใช่ นักพัฒนาสามารถอ่านเอกสารโดยละเอียดที่ Aspose.Slides สำหรับ Java จัดทำไว้ ซึ่งให้ข้อมูลเชิงลึกเกี่ยวกับฟังก์ชันการทำงานและการใช้งาน
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides หรือไม่
ใช่ คุณสามารถเข้าถึงเวอร์ชันทดลองใช้งานฟรีของ Aspose.Slides เพื่อสำรวจฟีเจอร์ต่าง ๆ ก่อนตัดสินใจซื้อ
### ฉันสามารถขอรับการสนับสนุนสำหรับแบบสอบถามที่เกี่ยวข้องกับ Aspose.Slides ได้จากที่ไหน
หากต้องการความช่วยเหลือหรือมีคำถามเกี่ยวกับ Aspose.Slides คุณสามารถเยี่ยมชมฟอรัมสนับสนุนได้ [ที่นี่](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}