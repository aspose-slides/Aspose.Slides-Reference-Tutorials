---
title: ตั้งค่าความโปร่งใสของข้อความในเงาโดยใช้ Java
linktitle: ตั้งค่าความโปร่งใสของข้อความในเงาโดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับความโปร่งใสของเงาข้อความใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงการนำเสนอของคุณโดยทางโปรแกรม
weight: 20
url: /th/java/java-powerpoint-text-font-customization/set-transparency-text-shadow-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการความโปร่งใสของเงาข้อความในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การปรับความโปร่งใสของเงาข้อความสามารถเพิ่มความน่าสนใจให้กับสไลด์ของคุณได้อย่างมาก ทำให้สไลด์มีความไดนามิกและเป็นมืออาชีพมากขึ้น Aspose.Slides สำหรับ Java มีฟังก์ชันที่มีประสิทธิภาพในการควบคุมองค์ประกอบต่างๆ ของสไลด์ด้วยโปรแกรมได้อย่างแม่นยำ ทำให้มั่นใจได้ว่างานนำเสนอของคุณตรงตามมาตรฐานการออกแบบสูงสุด
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): Aspose.Slides สำหรับ Java ต้องใช้ JDK 1.8 หรือใหม่กว่า
2. Aspose.Slides สำหรับ Java JAR: ดาวน์โหลด Aspose.Slides สำหรับไลบรารี Java ล่าสุดจาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE ที่คุณเลือก เช่น IntelliJ IDEA หรือ Eclipse สำหรับการพัฒนา Java
4. ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java: ความคุ้นเคยกับไวยากรณ์ Java และแนวคิดการเขียนโปรแกรมเชิงวัตถุ

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจ Aspose.Slides ที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
ขั้นแรก ให้โหลดงานนำเสนอ PowerPoint ที่มีสไลด์ที่คุณต้องการปรับความโปร่งใสของเงาข้อความ
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "transparency.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงรูปร่างและกรอบข้อความ
ระบุรูปร่างเฉพาะ (เช่น รูปร่างอัตโนมัติ) ที่มีข้อความที่มีเงาที่คุณต้องการแก้ไข
```java
IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```
## ขั้นตอนที่ 3: ดึงเอฟเฟกต์เงา
เข้าถึงรูปแบบเอฟเฟกต์ของส่วนข้อความภายในรูปร่างเพื่อดึงเอฟเฟกต์เงาภายนอก
```java
IEffectFormat effects = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().getEffectFormat();
IOuterShadow outerShadowEffect = effects.getOuterShadowEffect();
```
## ขั้นตอนที่ 4: รับสีเงาและความโปร่งใสปัจจุบัน
รับสีเงาปัจจุบันและคำนวณเปอร์เซ็นต์ความโปร่งใส
```java
Color shadowColor = outerShadowEffect.getShadowColor().getColor();
float transparencyPercentage = ((float) (shadowColor.getAlpha() & 0xFF) / (Byte.MIN_VALUE & 0xFF)) * 100;
System.out.println(String.format("{0} - transparency is: {1}", shadowColor, transparencyPercentage));
```
## ขั้นตอนที่ 5: ปรับความโปร่งใส
ตั้งค่าระดับความโปร่งใสที่ต้องการ (ในกรณีนี้คือทึบแสงทั้งหมด) สำหรับสีของเงา
```java
outerShadowEffect.getShadowColor().setColor(new java.awt.Color(shadowColor.getRed(), shadowColor.getGreen(), shadowColor.getBlue(), 255));
```
## ขั้นตอนที่ 6: บันทึกงานนำเสนอที่แก้ไข
บันทึกงานนำเสนอด้วยความโปร่งใสของเงาข้อความที่ปรับแล้ว
```java
pres.save(dataDir + "transparency-2.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้สาธิตวิธีการปรับความโปร่งใสของเงาข้อความในสไลด์ PowerPoint โดยใช้โปรแกรม Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มสุนทรียภาพของการนำเสนอของคุณแบบไดนามิกผ่านโค้ด เพื่อให้มั่นใจว่าสไลด์ของคุณตรงตามมาตรฐานการออกแบบที่ต้องการ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น Java API ที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถขอรับเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 สามารถดูเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 สำหรับการสนับสนุนและการโต้ตอบกับชุมชน โปรดไปที่ฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
