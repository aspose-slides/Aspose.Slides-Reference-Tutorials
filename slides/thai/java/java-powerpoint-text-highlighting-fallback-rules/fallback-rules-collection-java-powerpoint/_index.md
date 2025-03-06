---
title: คอลเลกชันกฎทางเลือกใน Java PowerPoint
linktitle: คอลเลกชันกฎทางเลือกใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดการกฎทางเลือกแบบอักษรในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงความเข้ากันได้ระหว่างอุปกรณ์ต่างๆ ได้อย่างง่ายดาย
weight: 11
url: /th/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีจัดการกฎทางเลือกแบบอักษรโดยใช้ Aspose.Slides สำหรับ Java การใช้แบบอักษรสำรองมีความสำคัญอย่างยิ่งในการทำให้งานนำเสนอของคุณแสดงได้อย่างถูกต้องในสภาพแวดล้อมที่แตกต่างกัน โดยเฉพาะอย่างยิ่งเมื่อแบบอักษรบางประเภทไม่พร้อมใช้งาน เราจะแนะนำคุณเกี่ยวกับการนำเข้าแพ็คเกจที่จำเป็น การตั้งค่าสภาพแวดล้อม และการใช้กฎทางเลือกทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่า คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- ติดตั้ง IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse แล้ว
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## การตั้งค่าวัตถุการนำเสนอ
ขั้นแรก เริ่มต้นออบเจ็กต์การนำเสนอที่คุณจะกำหนดกฎทางเลือกแบบอักษรของคุณ
```java
Presentation presentation = new Presentation();
```
## การสร้างคอลเลกชันกฎทางเลือกแบบอักษร
ถัดไป สร้างออบเจ็กต์ FontFallBackRulesCollection เพื่อจัดการกฎการใช้แทนแบบอักษรแบบกำหนดเองของคุณ
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## การเพิ่มกฎทางเลือกแบบอักษร
ตอนนี้ ให้เพิ่มกฎทางเลือกแบบอักษรเฉพาะโดยใช้ช่วง Unicode และชื่อแบบอักษรทางเลือก
### ขั้นตอนที่ 1: กำหนดช่วง Unicode และแบบอักษร
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
บรรทัดนี้จะตั้งค่ากฎทางเลือกสำหรับช่วง Unicode 0x0B80 ถึง 0x0BFF เพื่อใช้แบบอักษร "Vijaya" หากแบบอักษรหลักไม่พร้อมใช้งาน
### ขั้นตอนที่ 2: กำหนดช่วง Unicode และแบบอักษรอื่น
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
ในที่นี้ กฎระบุว่าช่วง Unicode 0x3040 ถึง 0x309F ควรถอยกลับไปเป็นแบบอักษร "MS Mincho" หรือ "MS Gothic"
## การใช้กฎทางเลือกแบบอักษรกับการนำเสนอ
ใช้คอลเลกชันกฎทางเลือกแบบอักษรที่สร้างขึ้นกับ FontsManager ของงานนำเสนอ
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## กำจัดวัตถุการนำเสนอ
สุดท้าย ตรวจสอบให้แน่ใจว่ามีการจัดการทรัพยากรที่เหมาะสมโดยการกำจัดออบเจ็กต์การนำเสนอภายในบล็อกลองสุดท้าย
```java
try {
    // ใช้วัตถุการนำเสนอตามความจำเป็น
} finally {
    if (presentation != null) presentation.dispose();
}
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีจัดการกฎทางเลือกแบบอักษรโดยใช้ Aspose.Slides สำหรับ Java การทำความเข้าใจและการใช้ทางเลือกแบบอักษรทำให้มั่นใจได้ว่าการแสดงผลแบบอักษรจะสอดคล้องและเชื่อถือได้บนแพลตฟอร์มและสภาพแวดล้อมที่แตกต่างกัน เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับแต่งลักษณะการทำงานของแบบอักษรสำรองเพื่อให้ตรงตามข้อกำหนดการนำเสนอเฉพาะได้อย่างราบรื่น

## คำถามที่พบบ่อย
### กฎการใช้ทางเลือกแบบอักษรคืออะไร
กฎทางเลือกแบบอักษรจะกำหนดแบบอักษรทางเลือกที่จะใช้เมื่อแบบอักษรที่ระบุไม่พร้อมใช้งาน เพื่อให้มั่นใจว่าการแสดงข้อความมีความสอดคล้องกัน
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถรับเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 มีเอกสารรายละเอียดให้[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
หากต้องการการสนับสนุน โปรดไปที่ฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
