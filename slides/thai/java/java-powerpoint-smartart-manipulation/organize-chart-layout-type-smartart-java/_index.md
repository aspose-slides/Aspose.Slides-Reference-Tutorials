---
title: จัดระเบียบประเภทเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java
linktitle: จัดระเบียบประเภทเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: จัดระเบียบประเภทเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java กับ Aspose.Slides ปรับปรุงภาพการนำเสนอได้อย่างง่ายดาย
weight: 13
url: /th/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดระเบียบประเภทเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java

## การแนะนำ
ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการจัดระเบียบประเภทเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java โดยใช้ประโยชน์จากไลบรารี Aspose.Slides โดยเฉพาะ SmartArt ในงานนำเสนอสามารถปรับปรุงรูปลักษณ์ที่สวยงามและความชัดเจนของข้อมูลของคุณได้อย่างมาก ทำให้จำเป็นต้องเชี่ยวชาญการจัดการข้อมูล
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  ดาวน์โหลดและตั้งค่าไลบรารี Aspose.Slides หากยังไม่มี ให้ดาวน์โหลดจาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็น:
```java
import com.aspose.slides.*;
```
เรามาแยกย่อยตัวอย่างที่ให้ไว้เป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
สร้างวัตถุการนำเสนอใหม่
## ขั้นตอนที่ 2: เพิ่ม SmartArt ลงในสไลด์
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
เพิ่ม SmartArt ลงในสไลด์ที่ต้องการด้วยขนาดและประเภทเค้าโครงที่ระบุ
## ขั้นตอนที่ 3: ตั้งค่าเค้าโครงแผนผังองค์กร
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
ตั้งค่าชนิดโครงร่างแผนผังองค์กร ในตัวอย่างนี้ เรากำลังใช้เค้าโครง Left Hanging
## ขั้นตอนที่ 4: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอด้วยเค้าโครงแผนภูมิที่จัดระเบียบ

## บทสรุป
การเรียนรู้การจัดประเภทเค้าโครงแผนภูมิใน SmartArt โดยใช้ Java ช่วยให้คุณสามารถสร้างงานนำเสนอที่ดึงดูดสายตาได้อย่างง่ายดาย ด้วย Aspose.Slides กระบวนการจะมีความคล่องตัวและมีประสิทธิภาพ ช่วยให้คุณสามารถมุ่งเน้นไปที่การสร้างเนื้อหาที่มีผลกระทบ
## คำถามที่พบบ่อย
### Aspose.Slides เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ที่แตกต่างกันหรือไม่
ใช่ Aspose.Slides เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ต่างๆ ทำให้มั่นใจได้ถึงความยืดหยุ่นสำหรับนักพัฒนา
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏขององค์ประกอบ SmartArt โดยใช้ Aspose.Slides ได้หรือไม่
แน่นอนว่า Aspose.Slides มีตัวเลือกการปรับแต่งที่ครอบคลุมสำหรับองค์ประกอบ SmartArt ซึ่งช่วยให้คุณปรับแต่งองค์ประกอบเหล่านั้นให้ตรงตามความต้องการเฉพาะของคุณได้
### Aspose.Slides มีเอกสารที่ครอบคลุมสำหรับนักพัฒนาหรือไม่
ใช่ นักพัฒนาสามารถดูเอกสารประกอบโดยละเอียดที่ Aspose.Slides สำหรับ Java มอบให้ ซึ่งให้ข้อมูลเชิงลึกเกี่ยวกับฟังก์ชันและการใช้งาน
### มี Aspose.Slides รุ่นทดลองใช้งานหรือไม่
ใช่ คุณสามารถเข้าถึง Aspose.Slides เวอร์ชันทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ต่างๆ ก่อนตัดสินใจซื้อ
### ฉันจะขอรับการสนับสนุนสำหรับคำถามที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
 สำหรับความช่วยเหลือหรือข้อสงสัยเกี่ยวกับ Aspose.Slides คุณสามารถไปที่ฟอรัมสนับสนุนได้[ที่นี่](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
