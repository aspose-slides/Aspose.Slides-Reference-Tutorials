---
date: '2026-06-08'
description: เรียนรู้วิธีการสร้างแผนภูมิ PowerPoint ด้วย Java และ Aspose.Slides, ตั้งค่า
  Maven dependency, เพิ่ม clustered column chart, และบันทึกเป็น PPTX.
keywords:
- java create powerpoint chart
- maven dependency aspose slides
- chart manipulation in presentations
- java presentation library
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to java create powerpoint chart with Aspose.Slides, set up
    the Maven dependency, add a clustered column chart, and save as PPTX.
  headline: Java create powerpoint chart using Aspose.Slides
  type: TechArticle
- questions:
  - answer: Use the `ChartType` enum (e.g., `ChartType.Pie`, `ChartType.Line`) when
      calling `addChart`.
    question: How do I add other chart types?
  - answer: Yes, modify the series’ fill format or the chart’s palette via the `IChart`
      API.
    question: Can I customize chart colors?
  - answer: Verify that the output directory path is correct, exists, and is writable.
      Also ensure no other process holds a lock on the file.
    question: My presentation won’t save—what’s wrong?
  - answer: Process slides in batches, dispose of each `Presentation` after use, and
      consider increasing the JVM heap size if needed.
    question: How can I handle very large presentations efficiently?
  - answer: A free trial is available for evaluation, but a purchased license is required
      for commercial deployment.
    question: Is Aspose.Slides free for commercial projects?
  type: FAQPage
title: Java สร้างแผนภูมิ PowerPoint ด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java สร้างแผนภูมิ PowerPoint ด้วย Aspose.Slides

## บทนำ
ในคู่มือนี้คุณจะ **java create powerpoint chart** อย่างง่ายดายด้วย Aspose.Slides สำหรับ Java เราจะอธิบายขั้นตอนการติดตั้งแพคเกจ Maven หรือ Gradle, การเริ่มต้น `Presentation`, การแทรกแผนภูมิคอลัมน์แบบกลุ่ม, การปรับแต่งพื้นที่พล็อต, และสุดท้ายการบันทึกผลลัพธ์เป็นไฟล์ PPTX เมื่อเสร็จคุณจะได้สคริปต์พร้อมใช้งานที่ทำงานในโครงการ Java ใดก็ได้ ไม่ว่าจะเป็นการสร้างรายงานธุรกิจหรือเครื่องสร้างสไลด์อัตโนมัติ

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีเพิ่มการพึ่งพา Maven สำหรับ Aspose.Slides  
- วิธี **java create powerpoint chart** และแทรกแผนภูมิคอลัมน์แบบกลุ่ม  
- วิธีปรับพื้นที่พล็อต (ตำแหน่ง, ขนาด, ประเภทเป้าหมายการจัดวาง)  
- วิธี **save presentation as pptx** พร้อมทำความสะอาดทรัพยากรอย่างเหมาะสม  

พร้อมหรือยังที่จะเปลี่ยนข้อมูลดิบให้เป็นสไลด์ที่ดึงดูดสายตา? เริ่มกันเลย!

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Slides for Java (พร้อมใช้งานผ่าน Maven หรือ Gradle).  
- **ประเภทแผนภูมิที่แสดงคืออะไร?** แผนภูมิคอลัมน์แบบกลุ่ม.  
- **ฉันจะบันทึกไฟล์อย่างไร?** เรียก `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้งานฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **ฉันสามารถเปลี่ยนพื้นที่พล็อตได้หรือไม่?** ได้ – ตั้งค่า X, Y, width, height และเลือกประเภทเป้าหมายการจัดวาง.  

## java create powerpoint chart คืออะไร?
`java create powerpoint chart` หมายถึงการสร้างวัตถุแผนภูมิโดยโปรแกรม, เติมข้อมูลลงไป, และฝังลงในสไลด์ PowerPoint ด้วยไลบรารี Java. Aspose.Slides ทำให้การทำงานกับรูปแบบ Open XML ง่ายขึ้นเพื่อให้คุณมุ่งเน้นที่การออกแบบภาพแทนการจัดการไฟล์ภายใน.

## ทำไมต้องเพิ่มแผนภูมิคอลัมน์แบบกลุ่มด้วย Aspose.Slides?
แผนภูมิคอลัมน์แบบกลุ่มเหมาะอย่างยิ่งสำหรับการเปรียบเทียบหลายชุดข้อมูลเคียงข้างกัน. มันถูกใช้อย่างกว้างขวางในรายงานธุรกิจ, แดชบอร์ด, และการนำเสนอ. Aspose.Slides ให้คุณควบคุมสี, มาร์คเกอร์, แกน, และการจัดวางได้เต็มที่โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง. มันช่วยให้คุณเน้นแนวโน้มในแต่ละหมวดหมู่, ทำให้ข้อมูลเชิงลึกชัดเจนยิ่งขึ้นสำหรับผู้มีส่วนได้ส่วนเสีย. ด้วย Aspose.Slides คุณสามารถปรับรูปแบบซีรีส์, การสเกลแกน, และป้ายข้อมูลแบบโปรแกรมได้, ทำให้แผนภูมิตรงกับแบรนด์และมาตรฐานภาพขององค์กรคุณ.

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** (เวอร์ชัน 25.4 หรือใหม่กว่า).  
- **JDK 16** หรือใหม่กว่า.  
- IDE เช่น IntelliJ IDEA หรือ Eclipse.  
- ความรู้พื้นฐานของ Java.

## การตั้งค่า Aspose.Slides สำหรับ Java
### Maven
เพิ่มการพึ่งพาในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```

### Gradle
รวมไลบรารีในไฟล์ `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose's official site](https://releases.aspose.com/slides/java/).

#### การรับไลเซนส์
ใช้การทดลองใช้งานฟรีหรือไลเซนส์ชั่วคราวสำหรับการทดสอบ. ซื้อไลเซนส์เต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.

## การเริ่มต้นและการตั้งค่าเบื้องต้น
`Presentation` class เป็นจุดเริ่มต้นสำหรับการสร้างและจัดการไฟล์ PowerPoint. เริ่มคลาส Java ใหม่และนำเข้า class หลัก:

```java
import com.aspose.slides.Presentation;
```

## คู่มือการดำเนินการ
เราจะอธิบายแต่ละขั้นตอนพร้อมคำอธิบายที่ชัดเจน.

### การเริ่มต้น Presentation และการจัดการสไลด์
#### จุดยึดนิยาม
`Presentation` เป็นอ็อบเจกต์ระดับบนของ Aspose.Slides ที่แทนไฟล์ PowerPoint ทั้งไฟล์ในหน่วยความจำ.

#### ภาพรวม
แรกเริ่มให้สร้าง Presentation ใหม่และดึงสไลด์แรกที่แผนภูมิจะถูกวางไว้.

**1. สร้างและเริ่มต้น Presentation**

```java
Presentation presentation = new Presentation();
```

**2. เข้าถึงสไลด์แรก**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. เพิ่มแผนภูมิคอลัมน์แบบกลุ่ม**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **เคล็ดลับ:** ควรห่อการใช้ presentation ไว้ในบล็อก `try‑finally` และเรียก `presentation.dispose()` ในส่วน `finally` เพื่อปล่อยทรัพยากรเนทีฟ

### การกำหนดค่าพื้นที่พล็อต
#### ภาพรวม
ปรับแต่งพื้นที่พล็อตของแผนภูมิเพื่อควบคุมตำแหน่งการแสดงข้อมูลภายในสไลด์.

**1. ตั้งค่าตำแหน่งและขนาด**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. กำหนดประเภทเป้าหมายการจัดวาง**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### การบันทึก Presentation
#### ภาพรวม
หลังจากปรับแต่งแผนภูมิแล้ว ให้บันทึก Presentation เป็นไฟล์ PPTX.

**1. บันทึกเป็นไฟล์**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **คำเตือน:** ตรวจสอบให้แน่ใจว่าไดเรกทอรีปลายทางมีอยู่และแอปพลิเคชันมีสิทธิ์เขียน; หากไม่เช่นนั้นการบันทึกจะล้มเหลว

## กรณีการใช้งานทั่วไป
- **รายงานธุรกิจ:** ฝังแนวโน้มการขายและ KPI ทางการเงิน.  
- **สไลด์การศึกษา:** แสดงผลการทดลองหรือข้อมูลสถิติ.  
- **ข้อเสนอโปรเจกต์:** เน้นจุดสำคัญและการจัดสรรทรัพยากร.  
- **สไลด์การตลาด:** แสดงผลการทำแคมเปญด้วยแผนภูมิที่ชัดเจน.  
- **การวางแผนงานอีเวนต์:** แสดงข้อมูลประชากรผู้เข้าร่วมหรือการแบ่งตารางเวลา.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ปล่อยวัตถุ `Presentation` ทันทีเพื่อหลีกเลี่ยงการรั่วไหลของหน่วยความจำ.  
- สำหรับชุดข้อมูลขนาดใหญ่, เติมข้อมูลซีรีส์ของแผนภูมิเป็นขั้นตอนแทนการโหลดทั้งหมดพร้อมกัน.  
- ใช้เครื่องมือ profiling ในตัวของ Java เพื่อตรวจสอบการใช้ heap ระหว่างการสร้างแผนภูมิ.

## คำถามที่พบบ่อย

**ถาม: ฉันจะเพิ่มประเภทแผนภูมิอื่นได้อย่างไร?**  
**ตอบ:** ใช้ enum `ChartType` (เช่น `ChartType.Pie`, `ChartType.Line`) เมื่อเรียก `addChart`.

**ถาม: ฉันสามารถปรับสีของแผนภูมิได้หรือไม่?**  
**ตอบ:** ได้, ปรับรูปแบบการเติมของซีรีส์หรือพาเลตของแผนภูมิผ่าน API `IChart`.

**ถาม: Presentation ของฉันไม่สามารถบันทึกได้—มีอะไรผิดพลาด?**  
**ตอบ:** ตรวจสอบว่าเส้นทางไดเรกทอรีปลายทางถูกต้อง, มีอยู่, และสามารถเขียนได้. นอกจากนี้ตรวจสอบว่าไม่มีโปรเซสอื่นล็อกไฟล์อยู่.

**ถาม: ฉันจะจัดการกับ Presentation ขนาดใหญ่อย่างมีประสิทธิภาพได้อย่างไร?**  
**ตอบ:** ประมวลผลสไลด์เป็นชุด, ปล่อย `Presentation` แต่ละอันหลังการใช้, และพิจารณาเพิ่มขนาด heap ของ JVM หากจำเป็น.

**ถาม: Aspose.Slides ใช้ได้ฟรีสำหรับโครงการเชิงพาณิชย์หรือไม่?**  
**ตอบ:** มีการทดลองใช้งานฟรีสำหรับการประเมิน, แต่ต้องซื้อไลเซนส์สำหรับการใช้งานเชิงพาณิชย์.

## แหล่งข้อมูล
- [เอกสาร](https://reference.aspose.com/slides/java/)
- [ดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java/)
- [ซื้อไลเซนส์](https://purchase.aspose.com/buy)
- [ทดลองใช้ฟรี](https://releases.aspose.com/slides/java/)
- [ไลเซนส์ชั่วคราว](https://purchase.aspose.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.aspose.com/c/slides/11)

เริ่มสร้างงานนำเสนอที่สวยงามด้วย Aspose.Slides สำหรับ Java วันนี้!

---

**อัปเดตล่าสุด:** 2026-06-08  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มใน Java ด้วย Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [วิธีเพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [สร้าง PowerPoint แบบเคลื่อนไหวใน Java – ทำแอนิเมชันแผนภูมิ PowerPoint ด้วย Aspose.Slides](/slides/java/animations-transitions/animate-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}