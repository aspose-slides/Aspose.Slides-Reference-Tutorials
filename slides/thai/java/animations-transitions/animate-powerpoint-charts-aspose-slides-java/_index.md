---
date: '2026-02-04'
description: เรียนรู้วิธีใช้ Aspose.Slides for Java เพื่อทำแอนิเมชันให้กับแผนภูมิ
  PowerPoint, เพิ่มแอนิเมชันให้กับองค์ประกอบของแผนภูมิ, และบันทึกไฟล์ PPTX ที่มีแอนิเมชันด้วย
  Aspose.Slides for Java.
keywords:
- create animated powerpoint java
- animate PowerPoint charts
- add animation PowerPoint chart
- Aspose.Slides for Java
title: aspose slides java – สร้างแผนภูมิ PowerPoint แบบเคลื่อนไหวด้วย Aspose.Slides
url: /th/java/animations-transitions/animate-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides java – สร้างแผนภูมิ PowerPoint แบบเคลื่อนไหวด้วย Aspose.Slides
## วิธีสร้างงานนำเสนอ PowerPoint Java แบบ
### แบบเคลื่อนไหว** ที่ดึงดูดความสนใจด้วยแอนิเมชันของแผนภูมิหรือไม่? ด้วย **aspose slides java** การเพิ่มการเคลื่อนไหวให้กับองค์ประกอบทราคุณจะเป็นนักพัฒนาที่ต้องการอัตโนมัติการสร้างรายงานหรือเป็นนักวิเคราะห์ข้อมูลที่ต้องการปรับแต่งสไลด์ การสอนนี้จะแสดงให้คุณเห็นขั้นตอนการทำแอนิเมชันให้กับแผนภูมิ PowerPoint อย่างละเอียดเพื่อให้เรื่องราวของคุณน่าสนใจยิ่งขึ้น  

ในไม่กี่นาทีต่อไป เราจะพาคุณผ่านการโหลดไฟล์ PPTX ที่มีอยู่แล้ว, การเข้าถึงสไลด์และรูปร่าง, การใช้เอฟเฟกต์แอนิเมชันกับซีรีส์ของแผนภูมิ, และสุดท้ายการบันทึกไฟล์ที่ได้รับการปรับปรุง เมื่อเสร็จสิ้นคุณจะพร้อม **เพิ่มแอนิเมชันให้กับสไตล์แผนภูมิ** ในงานนำเสนอดเร็ว
- **ต้องอะไร?ใหม่กว่ารีส์?** ได้ – คุณสามารถกำหนดเป้าหมายแต่ละองค์ประกอบในซีรีส์ได้  
- **ต้องใช้ลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีได้สำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์เต็มสำหรับการใช้ง?การทำ ป้อยกว่า 15 นาทีสำหรับแอนิเมชันแผนภูมิพื้นฐาน

## “aspose slides java” คืออะไร?
หมายถึงการสร้างหรือแก้ไขไฟล์ PowerPoint (.pptx) ด้วย Java อย่างโปรแกรมเมติกและการใช้เอฟเฟกต์แอนิเมชันกับองค์ประกอบภาพเช่นแผนภูมิ, รูปร่าง หรือข้อความ ด้วย Aspose.Slides คุณสามารถควบคุมไทม์ไลน์ของแอนิเมชันได้อย่างเต็มที่โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง

## ทำไมต้องแอนิเมชันแผนภูมิ PowerPoint?
- **เพิ่มการมีส่วนร่วมของผู้ชม** – การเคลื่อนไหวดึงความสนใจไปยังจุดข้อมูลสำคัญ  
- **ทำให้แนวโน้มข้อมูลชัดเจน** – การเปิดเผยแบบต่อเนื่องช่วยอธิบายการเปลี่ยนแปลงทีละขั้นตอน  
- **อัตโนมัติการรายงาน** – สร้างเด็คที่มีแอนิเมชันได้ทันทีจากสายข้อมูล

## ข้อกำหนดเบื้องต้น
- **Java Development Kit** 16 หรือใหม่กว่า  
- ไลบรารี **aspose slides java** (เพิ่มผ่าน Maven หรือ Gradle)  
- ไฟล์ PowerPoint ตัวอย่างที่มีอย่างน้อยหนึ่งแผนภูมิ (เช่น `ExistingChart.pptx`)  

### ไลบรารีที่ต้องการ
**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

คุณยังสามารถดาวน์โหลด JAR ล่าสุดจากหน้าการปล่อยอย่างเป็นทางการได้:  
[การปล่อย Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/)

### ตัวเลือกลิขสิทธิ์
- **ทดลองใช้ฟรี** – ไม่ต้องใช้ไฟล์ลิขสิทธิ์สำหรับการประเมินผล  
- **ลิขสิทธิ์ชั่วสอบระยะสั้น ([รับได้ที่นี่](https://purchase.aspose.com/temporary-license/))  
- **ลิขสิทธิ์ชินการตามขั้นตอน

### ขั้นตอนที่ 1: โหลดงานนำเสนอ
แรกเริ่มให้สร้างอ็อบเจ็กต์ `Presentation` ที่ชี้ไปยังไฟล์ PPTX ที่มีอยู่ของคุณ  

```java
import com.aspose.slides.Presentation;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation presentation = new Presentation(dataDir + "/ExistingChart.pptx");
```

### ขั้นตอนที่ 2: เข้
ภูมิและดึงรูปร่างแผนภูมิออกมา  

```java
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;

ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0); // Assumes the first shape is a chart
```

### ขั้นตอนที่ 3: เพิ่มเอฟเฟกต์แอนิเมชันให้กับแผนภูมิ
ต่อไปเราจะเพิ่มการเฟด‑อินให้กับแผนภูมิทั้งหมดและจากนั้นทำแอนิเมชันให้กับแต่ละจุดข้อมูลแยกกัน  

```java
import com.aspose.slides.IEffect;
import com.aspose.slides.EffectType;
import com.aspose.slides.EffectSubtype;
import com.aspose.slides.EffectTriggerType;
import com.aspose.slides.EffectChartMinorGroupingType;
import com.aspose.slides.Sequence;

ISlide slide = presentation.getSlides().get_Item(0);
Sequence mainSequence = (Sequence) slide.getTimeline().getMainSequence();

// Fade‑in the entire chart
IEffect fadeEffect = mainSequence.addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

int[][] table = {
    {0, 0}, {0, 1}, {0, 2}, {0, 3},
    {1, 0}, {1, 1}, {1, 2}, {1, 3},
    {2, 0}, {2, 1}, {2, 2}, {2, 3}
};

// Animate each element in the series
for (int[] indices : table) {
    mainSequence.addEffect(
        chart,
        EffectChartMinorGroupingType.ByElementInSeries,
        indices[0],
        indices[1],
        EffectType.Appear,
        EffectSubtype.None,
        EffectTriggerType.AfterPrevious
    );
}
```

### ขั้นตอนที่ 4: บันทึกงานนำเสนอที่แก้ไขแล้ว
สุดท้ายให้เขียนงานนำเสนอที่มีแอนิเมชันกลับไปยังดิสก์  

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.save(outputDir + "/AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

อย่าลืมปล่อยทรัพยากร:  

```java
presentation.dispose();
```

## วิธีทำแ- **แบบคงที่ให้เป็นเรื่องราวเคลื่อนไหวที่นำผู้บริหารผ่านเมตริกไลด์การศึกษา:** เปิดเผยแนวโน้มทีละขั้นตอนเพื่อช่วยนักเรียนเข้าใจข้อมูลซับซ้อน  
- **ิเมชันที่ดึงดูดสายตาในระหว่างการพรีเซนต์

## เคล็ดลับประสิทธิภาพสำหรับการเพิ่มแอนิเมชันให้กับแผนภูมิ
- **ปล่อยทรัพยากรทันที:** เรียก `presentation.dispose()` เสมอเพื่อคืนหน่วยความจำเนทีฟ  
- **จำกัดจำนวนแอนิเมชัน:** การใช้เอฟเฟกต์มากเกินไปอาจทำให้ไฟล์ใหญ่และเวลาเรนเดอร์เพิ่มขึ้น  
- **ทดสอบบนอุปกรณ์เป้าหมาย:** ตรวจสอบว่าแอนิเมชันทำงานได้อย่างราบรื่นบนเวอร์ชัน PowerPoint ที่ผู้ชมของคุณใช้

## การบันทึก pptx ที่มีแอนิเมชัน – แนวปฏิบัติที่ดีที่สุด
- ใช้ `SaveFormat.Pptx` เวอร์ชันล่าสุดเพื่อเก็บข้อมูลแอนิเมชันทั้งหมด  
- เมื่อสร้างไฟล์หลายไฟล์เป็นชุด ให้ใช้อินสแตนซ์ `Presentation` เดียวซ้ำ ๆ เพื่อ ลดภาระการสร้างใหม่  
- บีบอัดรูปภาพก่อนใส่ลงในสไลด์เพื่อให้ขนาดไฟล์ PPTX สุดท้ายอยู่ในระดับที่จัดการได้

## คำถามที่พบบ่อย

**ถาม:** *ฉันสามารถทำแอนิเมชันให้กับแผนภูมิได้โดยไม่เขียนโค้ด Java หรือไม่?*  
**ตอบ:** ได้, PowerPoint เองมีเครื่องมือแอนิเมชันแบบแมนนวล, แต่การใช้ **aspose slides java** จะช่วยให้คุณอัตโนมัติกระบวนการและสร้างงานนำเสนอหลายไฟล์ได้โดยโปรแกรม

**ถาม:** *ถ้างานนำเสนอของฉันมีหลายแผนภูมิจะทำอย่างไร?*  
**ตอบ:** วนลูปผ่าน `slide.getShapes()` และตรวจสอบประเภทของแต่ละรูปร่าง ใช้ตรรกะแอนิเมชันเดียวกันกับทุก `IChart` ที่พบ

**ถาม:** *มีขีดจำกัดจำนวนแอนิเมชันต่อสไลด์หรือไม่?*  
**ตอบ:** โดยเทคนิคไม่มีข้อจำกัด, แต่การใช้แอนิเมชันมากเกินไปอาจทำให้การเรนเดอร์ช้าและไฟล์ใหญ่ ควรเน้นความชัดเจนมากกว่าปริมาณ

**ถาม:** *ไลบรารีรองรับรูปแบบ PowerPoint เก่า (*.ppt) หรือไม่?*  
**ตอบ:** ใช่, **aspose slides java** สามารถอ่านและเขียนไฟล์ `.ppt` และ `.pptx` ได้ แม้ว่าบางฟีเจอร์แอนิเมชันใหม่อาจจำกัดในรูปแบบเก่า

**ถาม:** *โค้ดนี้ทำงานได้บนคอนเทนเนอร์ Linux หรือไม่?*  
**ตอบ:** แน่นอน. ตราบใดที่คุณมี JDK ที่เข้ากันได้และไฟล์ JAR ของ Aspose.Slides, โค้ดจะทำงานบนระบบปฏิบัติการใด ๆ ที่รองรับ Java

## แหล่งข้อมูล
- [เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/)  
- [ดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/)

---

**อัปเดตล่าสุด:** 2026-02-04  
**ทดสอบด้วย:** Aspose.Slides 25.4 for Java  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}