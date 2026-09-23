---
date: '2026-09-22'
description: เรียนรู้วิธีบันทึก PowerPoint พร้อม animation โดยใช้ Aspose.Slides for
  Java, วิธีเพิ่ม animation, และวิธีกำหนดค่า Aspose Slides Maven dependency
keywords:
- how to save powerpoint
- how to add animation
- save powerpoint with animation
- aspose slides maven dependency
- java add slide animation
lastmod: '2026-09-22'
og_description: วิธีบันทึก PowerPoint พร้อม animation โดยใช้ Aspose.Slides for Java.
  คู่มือนี้แสดงวิธีเพิ่ม animation, กำหนดค่า Maven dependency, และสร้างสไลด์แบบไดนามิก
og_image_alt: 'Developer guide: save PowerPoint with animation using Aspose.Slides
  for Java'
og_title: วิธีบันทึก PowerPoint พร้อม animation โดยใช้ Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to save PowerPoint with animation using Aspose.Slides for
    Java, how to add animation, and how to configure the Aspose Slides Maven dependency.
  headline: How to save PowerPoint with animation using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to save PowerPoint with animation using Aspose.Slides for
    Java, how to add animation, and how to configure the Aspose Slides Maven dependency.
  name: How to save PowerPoint with animation using Aspose.Slides for Java
  steps:
  - name: initialize the presentation object
    text: 'Create and initialize a `Presentation` object that points to your existing
      PowerPoint file: Here, we’re opening an existing presentation named `Presentation1.pptx`.
      The constructor automatically parses the file structure, making every slide
      and shape available through the object model.'
  - name: access the target slide and shape
    text: 'Retrieve the first slide and its first auto‑shape (which contains the text
      you want to animate): We assume the shape is an `AutoShape` with a text frame,
      which is the most common container for paragraph‑level animations.'
  - name: apply the fly animation effect
    text: 'Add a **fly animation PowerPoint** effect to the first paragraph of the
      shape. This example configures the animation to fly in from the left and trigger
      on a mouse click: The `EffectTriggerType` enum determines when the animation
      starts (e.g., `OnClick` or `AfterPrevious`). The `EffectSubtype` enum '
  - name: save the presentation with animation
    text: 'Persist the changes by saving the file. This step **saves the presentation
      with animation** intact: Saving as `SaveFormat.Pptx` guarantees that all animation
      data is written to the output file.'
  type: HowTo
- questions:
  - answer: Modify the `EffectSubtype` parameter in the `addEffect()` call to `Right`,
      `Top`, or `Bottom`.
    question: How do I change the animation direction?
  - answer: Yes. Loop through each paragraph in the shape’s text frame and call `addEffect`
      for each one.
    question: Can I apply the fly animation to multiple paragraphs at once?
  - answer: Double‑check your Maven/Gradle configuration, ensure the correct classifier
      (`jdk16`), and verify that the Aspose license is correctly loaded.
    question: What should I do if I encounter errors during setup?
  - answer: Visit the [temporary Aspose license page](https://purchase.aspose.com/temporary-license/)
      and follow the request process.
    question: How do I obtain a temporary Aspose license for testing?
  - answer: Wrap file‑access and animation code in try‑catch blocks, and always close
      the `Presentation` object in a finally block or use try‑with‑resources.
    question: What is the best way to handle exceptions when working with presentations?
  type: FAQPage
tags:
- save PowerPoint
- Aspose.Slides
- Java animation
- fly animation
- PowerPoint API
title: วิธีบันทึก PowerPoint พร้อม animation โดยใช้ Aspose.Slides for Java
url: /th/java/animations-transitions/add-fly-animation-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีบันทึก PowerPoint พร้อมแอนิเมชันโดยใช้ Aspose.Slides for Java

## บทนำ

ในคู่มือนี้คุณจะได้ค้นพบ **วิธีบันทึก PowerPoint** พร้อมคงแอนิเมชันที่ซับซ้อนไว้ คุณจะได้เรียนรู้การเพิ่มเอฟเฟกต์ fly‑in ให้กับย่อหน้า ตั้งค่า trigger ของแอนิเมชัน และสร้างไฟล์ `.pptx` สุดท้ายที่ดูเหมือนสไลด์เด็คที่สร้างด้วยมืออย่างแม่นยำ โดยใช้ **Aspose.Slides for Java** คุณสามารถอัตโนมัติการสร้างงานนำเสนอบนเซิร์ฟเวอร์โดยไม่ต้องติดตั้ง Microsoft Office ซึ่งเหมาะอย่างยิ่งสำหรับการประมวลผลแบบแบตช์, เว็บเซอร์วิส, และ CI pipelines

## คำตอบสั้น
- **ไลบรารีใดที่เพิ่มแอนิเมชันแบบบินเข้าใน PowerPoint?** Aspose.Slides for Java.  
- **เครื่องมือสร้างใดที่ฉันสามารถใช้ได้?** ทั้ง Maven (`aspose‑slides` Maven dependency) และ Gradle รองรับ.  
- **ฉันจะตั้งค่า trigger ของแอนิเมชันอย่างไร?** ใช้ `EffectTriggerType.OnClick` หรือ `AfterPrevious` ในการเรียก `addEffect`.  
- **ฉันสามารถทดสอบโดยไม่ต้องมีลิขสิทธิ์ที่ชำระเงินได้หรือไม่?** ใช่—ใช้การทดลองฟรีหรือ **temporary Aspose license** ระหว่างการพัฒนา.  
- **ควรบันทึกเป็นรูปแบบใดเพื่อคงแอนิเมชัน?** บันทึกเป็น `.pptx`; รูปแบบเก่าจะตัดข้อมูลแอนิเมชันออก.  

## ทำไมต้องใช้ Aspose.Slides for Java?

โหลดงานนำเสนอของคุณ, ใส่แอนิเมชันแบบบินเข้า, แล้วบันทึก—ทั้งหมดในสองบล็อกโค้ดสั้น ๆ Aspose.Slides รองรับ **50+ input and output formats** และสามารถประมวลผลงานนำเสนอที่มี **over 500 slides** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้เป็นหนึ่งในไลบรารี Java ที่สามารถสเกลได้สูงสุดสำหรับการอัตโนมัติสไลด์

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่ม, ตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK) 16 or higher** installed.  
- IDE เช่น IntelliJ IDEA, Eclipse, หรือ NetBeans.  
- ความคุ้นเคยพื้นฐานกับ Java file I/O และเครื่องมือสร้าง Maven หรือ Gradle.  

### ไลบรารีที่จำเป็น
- **Aspose.Slides for Java** – version 25.4 or later (the latest release is recommended).  

### ความรู้เบื้องต้นที่จำเป็น
- ความเข้าใจเกี่ยวกับการสร้างอินสแตนซ์คลาส Java และการจัดการข้อยกเว้น.  
- การรับรู้แนวคิดของ PowerPoint เช่น สไลด์, รูปร่าง, และเอฟเฟกต์แอนิเมชัน.  

## การตั้งค่า Aspose.Slides for Java

เริ่มต้นโดยเพิ่มไลบรารี Aspose.Slides ไปยังโปรเจคของคุณ.

### การพึ่งพา Maven สำหรับ Aspose Slides
เพิ่มการพึ่งพานี้ไปยังไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การตั้งค่า Gradle
ใส่นี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
Download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### ขั้นตอนการรับลิขสิทธิ์
- **ทดลองใช้ฟรี** – เริ่มต้นด้วยการทดลองเพื่อสำรวจคุณสมบัติทั้งหมด.  
- **ลิขสิทธิ์ชั่วคราว** – รับลิขสิทธิ์ชั่วคราวเพื่อเข้าถึงเต็มที่ในระหว่างการพัฒนา.  
- **ซื้อ** – พิจารณาลิขสิทธิ์เต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  

เมื่อการตั้งค่าเสร็จสมบูรณ์, เราจะไปสู่การทำ **fly animation PowerPoint** ต่อ.

## วิธีบันทึก PowerPoint พร้อมแอนิเมชันโดยใช้ Aspose.Slides for Java

ด้านล่างเป็นคู่มือขั้นตอน‑โดย‑ขั้นตอนที่พาคุณผ่านกระบวนการทั้งหมด ตั้งแต่การโหลดไฟล์จนถึงการบันทึกผลลัพธ์ที่มีแอนิเมชัน

### คลาส Presentation คืออะไร?
คลาส `Presentation` แทนไฟล์ PowerPoint ในหน่วยความจำ, ให้การเข้าถึงสไลด์, รูปร่าง, และแอนิเมชัน โหลดไฟล์ต้นฉบับของคุณ, แก้ไข, แล้วบันทึกกลับ—ทั้งหมดโดยไม่ต้องสัมผัสระบบไฟล์จนกว่าจะเรียก `save` สุดท้าย.

### ขั้นตอนที่ 1: เริ่มต้นอ็อบเจกต์ Presentation
สร้างและเริ่มต้นอ็อบเจกต์ `Presentation` ที่ชี้ไปยังไฟล์ PowerPoint ที่มีอยู่ของคุณ:
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation presentation = new Presentation(dataDir + "/Presentation1.pptx");
```
ที่นี่เรากำลังเปิดงานนำเสนอที่มีชื่อ `Presentation1.pptx`. ตัวสร้างจะทำการพาร์สโครงสร้างไฟล์โดยอัตโนมัติ, ทำให้ทุกสไลด์และรูปร่างพร้อมใช้งานผ่านโมเดลอ็อบเจกต์.

### ขั้นตอนที่ 2: เข้าถึงสไลด์และรูปร่างเป้าหมาย
ดึงสไลด์แรกและ auto‑shape แรกของมัน (ซึ่งมีข้อความที่คุณต้องการทำแอนิเมชัน):
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape autoShape = (IAutoShape) slide.getShapes().get_Item(0);
```
เราสมมติว่ารูปร่างเป็น `AutoShape` ที่มี text frame, ซึ่งเป็นคอนเทนเนอร์ที่พบบ่อยที่สุดสำหรับแอนิเมชันระดับย่อหน้า.

### ขั้นตอนที่ 3: ใช้เอฟเฟกต์แอนิเมชันแบบบินเข้า
เพิ่ม **fly animation PowerPoint** ให้กับย่อหน้าแรกของรูปร่าง ตัวอย่างนี้ตั้งค่าให้แอนิเมชันบินเข้าจากด้านซ้ายและทำงานเมื่อคลิกเมาส์:
```java
IParagraph paragraph = autoShape.getTextFrame().getParagraphs().get_Item(0);
IEffect effect = slide.getTimeline().getMainSequence().addEffect(
    paragraph,
    EffectType.Fly,
    EffectSubtype.Left,
    EffectTriggerType.OnClick
);
```
`EffectTriggerType` enum กำหนดว่าแอนิเมชันจะเริ่มเมื่อใด (เช่น `OnClick` หรือ `AfterPrevious`).  
`EffectSubtype` enum ระบุทิศทางของแอนิเมชันแบบบินเข้า (เช่น `Left`, `Right`).  
คุณสามารถเปลี่ยน `EffectSubtype` เป็น `Right`, `Top`, หรือ `Bottom` เพื่อปรับทิศทาง, และแก้ `EffectTriggerType` เป็น `AfterPrevious` หากต้องการให้เริ่มอัตโนมัติ.

#### กำหนดค่า trigger ของแอนิเมชัน
พารามิเตอร์ `EffectTriggerType` ให้คุณ **configure animation trigger** พฤติกรรม. `OnClick` รอการคลิกของผู้ใช้, ในขณะที่ `AfterPrevious` เริ่มอัตโนมัติหลังจากแอนิเมชันก่อนหน้าเสร็จ.

### ขั้นตอนที่ 4: บันทึกการนำเสนอพร้อมแอนิเมชัน
บันทึกการเปลี่ยนแปลงโดยการบันทึกไฟล์ ขั้นตอนนี้ **saves the presentation with animation** อย่างครบถ้วน:
```java
presentation.save("YOUR_OUTPUT_DIRECTORY/AnimationEffectinParagraph.pptx", SaveFormat.Pptx);
```
การบันทึกเป็น `SaveFormat.Pptx` รับประกันว่าข้อมูลแอนิเมชันทั้งหมดจะถูกเขียนลงไฟล์ผลลัพธ์.

## การประยุกต์ใช้งานจริง

Fly animations สามารถใช้ในหลายสถานการณ์จริง:

- **การนำเสนอเพื่อการศึกษา** – เน้นแนวคิดสำคัญหรือเปิดเผยหัวข้อย่อยทีละข้อ.  
- **การประชุมองค์กร** – เน้นผลไตรมาส, แผนภูมิ, หรือโครงการเชิงกลยุทธ์.  
- **แคมเปญการตลาด** – สร้างสไลด์เปิดตัวผลิตภัณฑ์แบบไดนามิกที่ดึงดูดความสนใจของผู้ชม.  

เนื่องจากผลลัพธ์เป็น `.pptx` มาตรฐาน, ตัวดูงานนำเสนอสมัยใหม่ใด ๆ (PowerPoint, Google Slides, LibreOffice) จะเรนเดอร์แอนิเมชันได้อย่างถูกต้อง.

## ข้อควรพิจารณาด้านประสิทธิภาพ

แม้ Aspose.Slides จะมีประสิทธิภาพสูง, ควรคำนึงถึงเคล็ดลับต่อไปนี้เพื่อรักษาประสิทธิภาพที่ดีที่สุด:

- **จัดสรรพื้นที่ heap เพียงพอ** – ชุดสไลด์ขนาดใหญ่ (หลายร้อยสไลด์) อาจต้องการ `-Xmx2g` หรือมากกว่า.  
- **ปล่อยทรัพยากรโดยเร็ว** – ใช้ try‑with‑resources หรือบล็อก `finally` เพื่อปิดอ็อบเจกต์ `Presentation`.  
- **หลีกเลี่ยงการวนลูปที่ไม่จำเป็น** – ปรับแต่งเฉพาะสไลด์และรูปร่างที่ต้องการ; การทำงานแบบกลุ่มอาจเพิ่มความกดดันของหน่วยความจำ.  

## ปัญหาทั่วไปและวิธีแก้

| Issue | Solution |
|-------|----------|
| **OutOfMemoryError** when processing large files | Increase JVM heap (`-Xmx`) and process slides in batches. |
| **License not found** error | Load the temporary or purchased license file before creating the `Presentation` object. |
| **Animation not visible after saving** | Verify you saved as `SaveFormat.Pptx`; older formats drop animation data. |

## คำถามที่พบบ่อย

**Q: How do I change the animation direction?**  
A: Modify the `EffectSubtype` parameter in the `addEffect()` call to `Right`, `Top`, or `Bottom`.

**Q: Can I apply the fly animation to multiple paragraphs at once?**  
A: Yes. Loop through each paragraph in the shape’s text frame and call `addEffect` for each one.

**Q: What should I do if I encounter errors during setup?**  
A: Double‑check your Maven/Gradle configuration, ensure the correct classifier (`jdk16`), and verify that the Aspose license is correctly loaded.

**Q: How do I obtain a temporary Aspose license for testing?**  
A: Visit the [temporary Aspose license page](https://purchase.aspose.com/temporary-license/) and follow the request process.

**Q: What is the best way to handle exceptions when working with presentations?**  
A: Wrap file‑access and animation code in try‑catch blocks, and always close the `Presentation` object in a finally block or use try‑with‑resources.

## แหล่งข้อมูล

- **Documentation**: [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)  
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial**: [Get a Free License](https://releases.aspose.com/slides/java/)  
- **Temporary license**: [Apply for Temporary Access](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Forums](https://forum.aspose.com/c/slides/11)

เริ่มต้นอัตโนมัติการสร้างสไลด์เด็คของคุณวันนี้และเพลิดเพลินกับการเพิ่มประสิทธิภาพการทำงานที่มาจากการเพิ่มแอนิเมชันที่ซับซ้อนโดยโปรแกรม

---

**อัปเดตล่าสุด:** 2026-09-22  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Create Dynamic Powerpoint Java – Aspose.Slides Animation Types Guide](/slides/java/animations-transitions/aspose-slides-java-animation-comparison-guide/)
- [How to Create an Animation Analysis Tool - Retrieve PowerPoint Animation Effects Using Aspose.Slides for Java](/slides/java/animations-transitions/retrieve-powerpoint-animations-aspose-slides-java/)
- [How to Set Transitions in PowerPoint Slides Using Aspose.Slides for Java](/slides/java/animations-transitions/master-slide-transitions-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}