---
date: '2026-09-28'
description: เรียนรู้วิธีเพิ่มแอนิเมชันสไลด์, เปลี่ยนสีแอนิเมชัน, ซ่อนวัตถุเมื่อคลิกหรือหลังจากแอนิเมชัน,
  และบันทึกไฟล์ PPTX ด้วย Aspose.Slides Maven. คู่มือนี้ครอบคลุมการทำแอนิเมชันสไลด์ขั้นสูงสำหรับนักพัฒนา
  Java.
keywords:
- aspose slides maven
- add slide animation
- change animation color
- generate powerpoint java
- hide object after animation
- hide object on click
lastmod: '2026-09-28'
og_description: aspose slides maven ช่วยให้นักพัฒนา Java สามารถเพิ่มแอนิเมชันสไลด์,
  เปลี่ยนสีแอนิเมชัน, ซ่อนวัตถุเมื่อคลิกหรือหลังจากแอนิเมชัน, และส่งออกไฟล์ PPTX.
  ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อสร้างงานนำเสนอที่ไดนามิก
og_image_alt: Guide showing how to add advanced slide animations using Aspose.Slides
  Maven for Java
og_title: เชี่ยวชาญการทำแอนิเมชันสไลด์ขั้นสูงด้วย aspose slides maven ใน Java
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to add slide animation, change animation color, hide objects
    on click or after animation, and save PPTX using Aspose.Slides Maven. This guide
    covers advanced slide animations for Java developers.
  headline: How to master advanced slide animations with aspose slides maven in Java
  type: TechArticle
- questions:
  - answer: After adding the shape to the slide, create an `IEffect` via `slide.getTimeline().getMainSequence().addEffect(shape,
      EffectType.Fade, EffectSubtype.None, 0);` and then set the desired `AfterAnimationType`.
    question: How do I add animation to a newly created shape?
  - answer: Absolutely – replace `Color.GREEN` with any `java.awt.Color` value, such
      as `Color.RED` or `new Color(255, 165, 0)` for orange.
    question: Can I change the after‑animation color to something other than green?
  - answer: Yes, any `IShape` that has an associated `IEffect` can use `AfterAnimationType.HideOnNextMouseClick`.
    question: Is “hide on click java” supported on all slide objects?
  - answer: A single license covers all environments (development, testing, production)
      as long as you comply with the licensing terms.
    question: Do I need a separate license for each deployment environment?
  - answer: The examples target Aspose.Slides 25.4 (jdk16) but earlier 24.x versions
      also support the shown APIs.
    question: What version of Aspose.Slides is required for these features?
  type: FAQPage
tags:
- aspose slides
- java animations
- powerpoint generation
- maven integration
title: วิธีเชี่ยวชาญการทำแอนิเมชันสไลด์ขั้นสูงด้วย aspose slides maven ใน Java
url: /th/java/animations-transitions/advanced-slide-animations-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose slides maven: สร้างแอนิเมชันสไลด์ขั้นสูงใน Java

ในโลกการนำเสนอที่เคลื่อนที่อย่างรวดเร็วในปัจจุบัน, **aspose slides maven** ให้คุณมีพลังในการสร้างแอนิเมชันที่ดึงดูดสายตาโดยไม่ต้องต่อสู้กับ API ระดับต่ำ ไม่ว่าคุณจะกำลังสร้างการบรรยายเพื่อการศึกษา, การสาธิตผลิตภัณฑ์, หรือการนำเสนอให้กับนักลงทุนระดับสูง, แอนิเมชันสไลด์ที่เหมาะสมสามารถทำให้ผู้ชมของคุณมีสมาธิและเพิ่มการจดจำข้อความได้ คู่มือนี้จะพาคุณผ่านการใช้ **Aspose.Slides** สำหรับ Java กับ **Maven** เพื่อสร้าง, ปรับแต่ง, และบันทึกแอนิเมชันสไลด์ขั้นสูงอย่างรวดเร็วและเชื่อถือได้.

## คำตอบด่วน
- **วิธีหลักในการเพิ่ม Aspose.Slides ไปยังโครงการ Java คืออะไร?** Use the Maven dependency `com.aspose:aspose-slides`.
- **ฉันจะซ่อนวัตถุหลังจากคลิกเมาส์ได้อย่างไร?** Set `AfterAnimationType.HideOnNextMouseClick` on the effect.
- **เมธอดใดที่บันทึกการนำเสนอเป็น PPTX?** `presentation.save(path, SaveFormat.Pptx)`.
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** A free trial works for evaluation; a license is required for production.
- **ฉันสามารถเปลี่ยนสีหลังแอนิเมชันได้หรือไม่?** Yes, by setting `AfterAnimationType.Color` and specifying the color.

## aspose slides maven คืออะไร?
การรวม Aspose.Slides Maven คือชุดของไลบรารี Java ที่จัดจำหน่ายผ่าน Maven ซึ่งทำให้คุณสามารถสร้าง, แก้ไข, และเรนเดอร์ไฟล์ PowerPoint ด้วยโปรแกรมได้ มันทำให้รูปแบบไฟล์ PowerPoint เป็นนามธรรมเพื่อให้คุณสามารถจัดการสไลด์, รูปร่าง, และแอนิเมชันโดยใช้โค้ด Java ธรรมดา.

## ทำไมแอนิเมชันสไลด์ขั้นสูงจึงสำคัญ
แอนิเมชันขั้นสูงช่วยให้คุณควบคุมการไหลของภาพในชุดสไลด์, เน้นข้อมูลสำคัญ, และซ่อนสิ่งรบกวนในเวลาที่เหมาะสม ด้วย aspose slides maven คุณจะได้เข้าถึงคุณสมบัติของแอนิเมชันทุกอย่างผ่านโปรแกรม, ทำให้สามารถสร้างสไลด์แบบไดนามิกที่ UI ของ PowerPoint ทำไม่ได้ ผลลัพธ์คือการนำเสนอที่น่าสนใจและมีประสิทธิภาพมากขึ้น.

## สิ่งที่คุณจะได้เรียนรู้
- **Loading presentations** – โหลดไฟล์ที่มีอยู่อย่างราบรื่น.  
- **Manipulating slides** – คัดลอกสไลด์และเพิ่มเป็นสไลด์ใหม่.  
- **Customizing animations** – เปลี่ยนเอฟเฟกต์แอนิเมชัน, ซ่อนเมื่อคลิก, เปลี่ยนสี, และซ่อนหลังแอนิเมชัน.  
- **Saving presentations** – ส่งออกเด็คที่แก้ไขเป็น PPTX.

## ข้อกำหนดเบื้องต้น

### ไลบรารีและการพึ่งพาที่จำเป็น
- Java Development Kit (JDK) 16 หรือสูงกว่า  
- **Aspose.Slides for Java** library (เพิ่มผ่าน Maven, Gradle, หรือดาวน์โหลดโดยตรง)

### ความต้องการการตั้งค่าสภาพแวดล้อม
กำหนดค่า Maven หรือ Gradle เพื่อจัดการการพึ่งพา Aspose.Slides.

### ความรู้เบื้องต้นที่ต้องมี
ความรู้พื้นฐานการเขียนโปรแกรม Java และแนวคิดการจัดการไฟล์.

## การตั้งค่า Aspose.Slides สำหรับ Java

ต่อไปนี้คือสามวิธีที่รองรับเพื่อเพิ่ม Aspose.Slides เข้าไปในโครงการของคุณ.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct download:**  
Download the latest release from [การปล่อย Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/).

### การให้ลิขสิทธิ์
เริ่มต้นด้วยการทดลองใช้งานฟรีหรือรับไลเซนส์ชั่วคราวเพื่อเข้าถึงคุณสมบัติทั้งหมด ไลเซนส์ที่ซื้อจะลบข้อจำกัดการประเมินผล.

### การเริ่มต้นและการตั้งค่าพื้นฐาน
```java
import com.aspose.slides.*;

// Load your presentation file into Aspose.Slides environment
String presentationPath = "YOUR_DOCUMENT_DIRECTORY/AnimationAfterEffect.pptx";
Presentation pres = new Presentation(presentationPath);
```

## วิธีใช้ aspose slides maven สำหรับแอนิเมชันสไลด์ขั้นสูง
เพื่อใช้แอนิเมชันขั้นสูง, ก่อนอื่นให้โหลดอ็อบเจ็กต์ Presentation, ค้นหาสไลด์เป้าหมาย, และเพิ่ม IEffect ไปยังลำดับหลักของมัน จากนั้นตั้งค่า AfterAnimationType ที่ต้องการ เช่น HideOnNextMouseClick, Color, หรือ HideAfterAnimation และอาจกำหนดคุณสมบัติเพิ่มเติมเช่นสีเติม สุดท้ายบันทึกการนำเสนอด้วย SaveFormat.Pptx เพื่อรักษาเอฟเฟกต์ทั้งหมด.

### ฟีเจอร์ 1: การโหลดการนำเสนอ

#### ภาพรวม
การโหลดการนำเสนอที่มีอยู่เป็นขั้นตอนแรกสำหรับการจัดการใด ๆ.

#### คำอธิบาย
`Presentation` คือคลาสหลักของ Aspose.Slides ที่แสดงไฟล์ PowerPoint ในหน่วยความจำ, ให้การเข้าถึงสไลด์, รูปร่าง, และไทม์ไลน์ของแอนิเมชัน.

#### การดำเนินการแบบขั้นตอน
**Load presentation**  
```java
import com.aspose.slides.*;

String presentationPath = "YOUR_DOCUMENT_DIRECTORY/AnimationAfterEffect.pptx";
Presentation pres = new Presentation(presentationPath);
```

**Cleanup resources**  
```java
void cleanup(Presentation pres) {
    if (pres != null) pres.dispose();
}

try {
    // Proceed with additional operations...
} finally {
    cleanup(pres);
}
```  
*ทำไมจึงสำคัญ?* การจัดการทรัพยากรอย่างเหมาะสมป้องกันการรั่วไหลของหน่วยความจำ, โดยเฉพาะเมื่อจัดการกับเด็คขนาดใหญ่.

### ฟีเจอร์ 2: การเพิ่มสไลด์ใหม่และคัดลอกสไลด์ที่มีอยู่ (create new slide java)

#### ภาพรวม
การคัดลอกสไลด์ทำให้คุณสามารถใช้เนื้อหาเดิมได้โดยไม่ต้องสร้างใหม่จากศูนย์, เป็นความต้องการทั่วไปเมื่อคุณต้องการ **create new slide java** อย่างโปรแกรม.

#### คำอธิบาย
`ISlide` แสดงสไลด์เดียวภายใน `Presentation`; การคัดลอกจะสร้างสำเนาที่เหมือนกันของรูปร่างทั้งหมด, แอนิเมชัน, และการตั้งค่าเลย์เอาต์.

#### การดำเนินการแบบขั้นตอน
**Clone slide**  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/AnimationAfterEffect.pptx");
try {
    ISlide clonedSlide = pres.getSlides().addClone(pres.getSlides().get_Item(0));
} finally {
    cleanup(pres);
}
```

### ฟีเจอร์ 3: การเปลี่ยนประเภทหลังแอนิเมชันเป็น “hide on next mouse click” (hide on click java)

#### ภาพรวม
ซ่อนวัตถุหลังจากคลิกเมาส์ครั้งถัดไปเพื่อให้ผู้ชมมุ่งเน้นไปที่เนื้อหาใหม่.

#### คำอธิบาย
`AfterAnimationType.HideOnNextMouseClick` สั่งให้เอนจินสไลด์ทำให้รูปร่างเป้าหมายเป็นที่มองไม่เห็นทันทีที่ผู้ใช้คลิกครั้งต่อไป.

#### การดำเนินการแบบขั้นตอน
**Change animation effect**  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/AnimationAfterEffect.pptx");
try {
    ISlide slide1 = pres.getSlides().addClone(pres.getSlides().get_Item(0));
    ISequence seq = slide1.getTimeline().getMainSequence();

    for (IEffect effect : seq) {
        effect.setAfterAnimationType(AfterAnimationType.HideOnNextMouseClick);
    }
} finally {
    cleanup(pres);
}
```

### ฟีเจอร์ 4: การเปลี่ยนประเภทหลังแอนิเมชันเป็น “color” และตั้งค่าคุณสมบัติสี (change animation color java)

#### ภาพรวม
ใช้การเปลี่ยนสีหลังจากแอนิเมชันเสร็จสิ้นเพื่อดึงดูดความสนใจ.

#### คำอธิบาย
`AfterAnimationType.Color` ให้คุณระบุสีเติมสุดท้ายสำหรับรูปร่างเมื่อแอนิเมชันของมันเสร็จสิ้น.

#### การดำเนินการแบบขั้นตอน
**Set animation color**  
```java
import com.aspose.slides.*;
import java.awt.Color;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/AnimationAfterEffect.pptx");
try {
    ISlide slide2 = pres.getSlides().addClone(pres.getSlides().get_Item(0));
    ISequence seq = slide2.getTimeline().getMainSequence();

    for (IEffect effect : seq) {
        effect.setAfterAnimationType(AfterAnimationType.Color);
        effect.getAfterAnimationColor().setColor(Color.GREEN); // Set to green color
    }
} finally {
    cleanup(pres);
}
```

### ฟีเจอร์ 5: การเปลี่ยนประเภทหลังแอนิเมชันเป็น “hide after animation”

#### ภาพรวม
ซ่อนวัตถุโดยอัตโนมัติเมื่อแอนิเมชันของมันเสร็จสิ้นเพื่อการเปลี่ยนผ่านที่เรียบร้อย.

#### คำอธิบาย
`AfterAnimationType.HideAfterAnimation` จะลบรูปร่างออกจากมุมมองทันทีหลังจากเอฟเฟกต์ที่เกี่ยวข้องเล่นจบ.

#### การดำเนินการแบบขั้นตอน
**Implement hide after animation**  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/AnimationAfterEffect.pptx");
try {
    ISlide slide3 = pres.getSlides().addClone(pres.getSlides().get_Item(0));
    ISequence seq = slide3.getTimeline().getMainSequence();

    for (IEffect effect : seq) {
        effect.setAfterAnimationType(AfterAnimationType.HideAfterAnimation);
    }
} finally {
    cleanup(pres);
}
```

### ฟีเจอร์ 6: การบันทึกการนำเสนอ

#### ภาพรวม
บันทึกการเปลี่ยนแปลงทั้งหมดโดยบันทึกไฟล์เป็น PPTX.

#### คำอธิบาย
`presentation.save(path, SaveFormat.Pptx)` เขียนอ็อบเจ็กต์ `Presentation` ที่อยู่ในหน่วยความจำไปยังไฟล์ PowerPoint, โดยใช้รูปแบบ PPTX ที่รักษาแอนิเมชันและสื่อทั้งหมด.

#### การดำเนินการแบบขั้นตอน
**Save presentation**  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/AnimationAfterEffect.pptx");
String outputPath = "YOUR_OUTPUT_DIRECTORY/AnimationAfterEffect-out.pptx";
try {
    // Make necessary modifications to the presentation
    pres.save(outputPath, SaveFormat.Pptx);
} finally {
    cleanup(pres);
}
```

## การประยุกต์ใช้งานจริง
- **Educational presentations** – เน้นแนวคิดสำคัญด้วยแอนิเมชันการเปลี่ยนสี.  
- **Business meetings** – ซ่อนกราฟิกสนับสนุนหลังจากคลิกเพื่อให้ผู้พูดเป็นจุดสนใจ.  
- **Product launches** – เปิดเผยคุณสมบัติอย่างไดนามิกโดยใช้เอฟเฟกต์ hide‑after‑animation.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ทำการกำจัดอ็อบเจ็กต์ `Presentation` อย่างทันท่วงที.  
- ใช้เวอร์ชันล่าสุดของ Aspose.Slides เพื่อปรับปรุงประสิทธิภาพ.  
- ตรวจสอบการใช้ heap ของ Java เมื่อประมวลผลเด็คขนาดใหญ่; Aspose.Slides สามารถสตรีมไฟล์หลายร้อยหน้าโดยไม่ต้องใช้หน่วยความจำเต็ม.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **การรั่วไหลของหน่วยความจำหลังจากการดำเนินการสไลด์หลายครั้ง** | ควรเรียก `presentation.dispose()` เสมอในบล็อก `finally` (ตามที่แสดง). |
| **ประเภทแอนิเมชันไม่ถูกนำไปใช้** | ตรวจสอบว่าคุณกำลังวนลูปผ่าน `ISequence` ที่ถูกต้อง (ลำดับหลัก) และว่าเอฟเฟกต์มีอยู่บนสไลด์. |
| **ไฟล์ที่บันทึกเสียหาย** | ตรวจสอบว่าไดเรกทอรีของเส้นทางออกมีอยู่และคุณมีสิทธิ์เขียน. |

## คำถามที่พบบ่อย

**Q: ฉันจะเพิ่มแอนิเมชันให้กับรูปร่างที่สร้างใหม่ได้อย่างไร?**  
A: หลังจากเพิ่มรูปร่างลงในสไลด์, สร้าง `IEffect` ผ่าน `slide.getTimeline().getMainSequence().addEffect(shape, EffectType.Fade, EffectSubtype.None, 0);` แล้วตั้งค่า `AfterAnimationType` ที่ต้องการ.

**Q: ฉันสามารถเปลี่ยนสีหลังแอนิเมชันเป็นสีอื่นที่ไม่ใช่สีเขียวได้หรือไม่?**  
A: แน่นอน – แทนที่ `Color.GREEN` ด้วยค่า `java.awt.Color` ใด ๆ, เช่น `Color.RED` หรือ `new Color(255, 165, 0)` สำหรับสีส้ม.

**Q: “hide on click java” รองรับบนวัตถุสไลด์ทั้งหมดหรือไม่?**  
A: ใช่, `IShape` ใด ๆ ที่มี `IEffect` เชื่อมโยงสามารถใช้ `AfterAnimationType.HideOnNextMouseClick`.

**Q: ฉันต้องการไลเซนส์แยกต่างหากสำหรับแต่ละสภาพแวดล้อมการปรับใช้หรือไม่?**  
A: ไลเซนส์เดียวครอบคลุมทุกสภาพแวดล้อม (การพัฒนา, การทดสอบ, การผลิต) ตราบใดที่คุณปฏิบัติตามเงื่อนไขการให้ลิขสิทธิ์.

**Q: ต้องการเวอร์ชันของ Aspose.Slides ใดสำหรับฟีเจอร์เหล่านี้?**  
A: ตัวอย่างนี้ใช้ Aspose.Slides 25.4 (jdk16) แต่เวอร์ชัน 24.x ก่อนหน้านี้ก็สนับสนุน API ที่แสดงเช่นกัน.

---

**อัปเดตล่าสุด:** 2026-09-28  
**ทดสอบกับ:** Aspose.Slides 25.4 (jdk16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มแอนิเมชันให้กับแผนภูมิ PowerPoint ด้วย Aspose.Slides สำหรับ Java – คู่มือแบบขั้นตอน](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [เพิ่มแอนิเมชัน Fly ใน Powerpoint ด้วย Aspose Slides Java](/slides/java/animations-transitions/add-fly-animation-powerpoint-aspose-slides-java/)
- [สร้าง Powerpoint แบบไดนามิกด้วย Java – คู่มือประเภทแอนิเมชันของ Aspose.Slides](/slides/java/animations-transitions/aspose-slides-java-animation-comparison-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}