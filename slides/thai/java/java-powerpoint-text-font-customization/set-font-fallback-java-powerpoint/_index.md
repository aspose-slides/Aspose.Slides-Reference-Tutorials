---
"description": "เรียนรู้วิธีตั้งค่าฟอนต์สำรองใน Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพื่อให้แน่ใจว่าการแสดงข้อความมีความสอดคล้องกัน"
"linktitle": "ตั้งค่าฟอนต์สำรองใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าฟอนต์สำรองใน Java PowerPoint"
"url": "/th/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าฟอนต์สำรองใน Java PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกถึงความซับซ้อนของการตั้งค่าฟอนต์สำรองในงานนำเสนอ PowerPoint ที่ใช้ Java โดยใช้ Aspose.Slides สำหรับ Java ฟอนต์สำรองมีความสำคัญอย่างยิ่งในการทำให้มั่นใจว่าข้อความในงานนำเสนอของคุณแสดงอย่างถูกต้องบนอุปกรณ์และระบบปฏิบัติการต่างๆ แม้ว่าฟอนต์ที่จำเป็นจะไม่พร้อมใช้งานก็ตาม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse

## แพ็คเกจนำเข้า
ขั้นแรก รวมแพ็คเกจ Aspose.Slides ที่จำเป็นสำหรับ Java ไว้ในคลาส Java ของคุณ:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## ขั้นตอนที่ 1: เริ่มต้นกฎการสำรองแบบอักษร
หากต้องการตั้งค่าแบบอักษรสำรอง คุณต้องกำหนดกฎที่ระบุช่วง Unicode และแบบอักษรสำรองที่เกี่ยวข้อง ต่อไปนี้คือวิธีเริ่มต้นกฎเหล่านี้:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## ขั้นตอนที่ 2: ใช้กฎการสำรองแบบอักษร
ขั้นต่อไป คุณจะใช้กฎเหล่านี้กับงานนำเสนอหรือสไลด์ที่จำเป็นต้องตั้งค่าแบบอักษรสำรอง ด้านล่างนี้เป็นตัวอย่างการใช้กฎเหล่านี้กับสไลด์ในงานนำเสนอ PowerPoint:
```java
// ถือว่าสไลด์เป็นวัตถุสไลด์ของคุณ
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## บทสรุป
การตั้งค่าฟอนต์สำรองในงานนำเสนอ PowerPoint ในรูปแบบ Java โดยใช้ Aspose.Slides สำหรับ Java ถือเป็นสิ่งสำคัญสำหรับการรับรองการแสดงข้อความที่สอดคล้องกันในสภาพแวดล้อมที่แตกต่างกัน การกำหนดกฎสำรองตามที่แสดงในบทช่วยสอนนี้จะช่วยให้คุณจัดการกับสถานการณ์ที่ฟอนต์เฉพาะบางแบบไม่สามารถใช้ได้ และรักษาความสมบูรณ์ของงานนำเสนอของคุณไว้ได้

## คำถามที่พบบ่อย
### ฟอนต์สำรองในงานนำเสนอ PowerPoint คืออะไร
แบบอักษรสำรองจะช่วยให้มั่นใจว่าข้อความจะแสดงอย่างถูกต้องโดยการแทนที่แบบอักษรที่มีอยู่ให้กับแบบอักษรที่ไม่ได้ติดตั้ง
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร?
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
### Aspose.Slides สำหรับ Java เข้ากันได้กับ Java IDE ทั้งหมดหรือไม่
ใช่ Aspose.Slides สำหรับ Java เข้ากันได้กับ IDE ยอดนิยมของ Java เช่น IntelliJ IDEA และ Eclipse
### ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับผลิตภัณฑ์ Aspose ได้หรือไม่
ใช่ ใบอนุญาตชั่วคราวสำหรับผลิตภัณฑ์ Aspose สามารถขอได้จาก [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถค้นหาการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
สำหรับการสนับสนุนที่เกี่ยวข้องกับ Aspose.Slides สำหรับ Java โปรดไปที่ [ฟอรั่ม Aspose](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}