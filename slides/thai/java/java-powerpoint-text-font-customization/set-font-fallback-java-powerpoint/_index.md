---
title: ตั้งค่าทางเลือกแบบอักษรใน Java PowerPoint
linktitle: ตั้งค่าทางเลือกแบบอักษรใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าทางเลือกแบบอักษรใน Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพื่อให้แน่ใจว่าการแสดงข้อความสอดคล้องกัน
type: docs
weight: 16
url: /th/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกความซับซ้อนของการตั้งค่าแบบอักษรทางเลือกในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การใช้แบบอักษรสำรองมีความสำคัญอย่างยิ่งในการทำให้ข้อความในงานนำเสนอของคุณแสดงอย่างถูกต้องบนอุปกรณ์และระบบปฏิบัติการต่างๆ แม้ว่าจะไม่มีแบบอักษรที่ต้องการก็ตาม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ขั้นแรก รวม Aspose.Slides ที่จำเป็นสำหรับแพ็คเกจ Java ในคลาส Java ของคุณ:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## ขั้นตอนที่ 1: เริ่มต้นกฎทางเลือกแบบอักษร
หากต้องการตั้งค่าแบบอักษรสำรอง คุณต้องกำหนดกฎที่ระบุช่วง Unicode และแบบอักษรสำรองที่สอดคล้องกัน ต่อไปนี้คือวิธีที่คุณสามารถเริ่มต้นกฎเหล่านี้:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## ขั้นตอนที่ 2: ใช้กฎทางเลือกแบบอักษร
จากนั้น คุณจะใช้กฎเหล่านี้กับงานนำเสนอหรือสไลด์ที่ต้องตั้งค่าทางเลือกแบบอักษร ด้านล่างนี้เป็นตัวอย่างการใช้กฎเหล่านี้กับสไลด์ในงานนำเสนอ PowerPoint:
```java
// สมมติว่าสไลด์เป็นวัตถุสไลด์ของคุณ
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## บทสรุป
การตั้งค่าทางเลือกแบบอักษรในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นสิ่งจำเป็นสำหรับการแสดงข้อความที่สอดคล้องกันในสภาพแวดล้อมที่แตกต่างกัน ด้วยการกำหนดกฎทางเลือกตามที่แสดงในบทช่วยสอนนี้ คุณสามารถจัดการกับสถานการณ์ที่แบบอักษรเฉพาะไม่พร้อมใช้งาน โดยรักษาความสมบูรณ์ของการนำเสนอของคุณ

## คำถามที่พบบ่อย
### ทางเลือกแบบอักษรในงานนำเสนอ PowerPoint คืออะไร
ทางเลือกแบบอักษรช่วยให้มั่นใจได้ว่าข้อความจะแสดงอย่างถูกต้องโดยการแทนที่แบบอักษรที่มีอยู่สำหรับแบบอักษรที่ไม่ได้ติดตั้ง
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
### Aspose.Slides สำหรับ Java เข้ากันได้กับ Java IDE ทั้งหมดหรือไม่
ใช่ Aspose.Slides สำหรับ Java เข้ากันได้กับ Java IDE ยอดนิยม เช่น IntelliJ IDEA และ Eclipse
### ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับผลิตภัณฑ์ Aspose ได้หรือไม่
ใช่ สามารถรับใบอนุญาตชั่วคราวสำหรับผลิตภัณฑ์ Aspose ได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 สำหรับการสนับสนุนที่เกี่ยวข้องกับ Aspose.Slides สำหรับ Java โปรดไปที่[ฟอรั่ม Aspose](https://forum.aspose.com/c/slides/11).