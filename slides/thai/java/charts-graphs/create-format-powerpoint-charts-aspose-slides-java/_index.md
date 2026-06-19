---
date: '2026-03-15'
description: เรียนรู้วิธีเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ PowerPoint ด้วย Aspose.Slides
  for Java โดยครอบคลุมขั้นตอนการเพิ่มแผนภูมิลงในสไลด์และสร้างสไลด์ PowerPoint ด้วย
  Java อย่างมีประสิทธิภาพ
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: เพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงใน PPT ด้วย Aspose.Slides Java
url: /th/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เพิ่ม Clustered Column Chart ลงใน PPT ด้วย Aspose.Slides Java

## บทนำ
ในคู่มือนี้คุณจะ **เพิ่ม clustered column chart** ลงในงานนำเสนอ PowerPoint อย่างอัตโนมัติด้วย Aspose.Slides for Java ไม่ว่าคุณจะสร้างรายงานธุรกิจ, สไลด์การศึกษา, หรือสไลด์การตลาด การสร้างแผนภูมิอัตโนมัติจะช่วยประหยัดเวลาและรับประกันความสอดคล้อง เราจะอธิบายขั้นตอนการตั้งค่าไลบรารี, สร้างสไลด์, เพิ่มแผนภูมิ, ปรับสไตล์เส้นและมุมโค้ง, และสุดท้ายบันทึกไฟล์ เมื่อเสร็จคุณจะคุ้นเคยกับกระบวนการทั้งหมดเพื่อ **เพิ่มแผนภูมิลงในสไลด์** และแม้กระทั่ง **สร้าง PowerPoint slide Java**‑based solutions

### คำตอบสั้น
- **คลาสหลักที่ใช้เริ่มต้นคืออะไร?** `Presentation`
- **ประเภทแผนภูมิที่ใช้คืออะไร?** `ChartType.ClusteredColumn`
- **จะเปิดใช้งานมุมโค้งอย่างไร?** `chart.setRoundedCorners(true);`
- **รูปแบบไฟล์ที่แนะนำสำหรับการบันทึกคืออะไร?** `SaveFormat.Pptx`
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีทำงานได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์ที่ซื้อสำหรับการใช้งานจริง

## Clustered column chart คืออะไร?
Clustered column chart จัดกลุ่มหลายชุดข้อมูลเคียงข้างกันสำหรับแต่ละหมวดหมู่ ทำให้เหมาะสำหรับการเปรียบเทียบค่าระหว่างกลุ่มต่าง ๆ Aspose.Slides ช่วยให้คุณสร้างแผนภูมิประเภทนี้ได้ทั้งหมดด้วยโค้ดโดยไม่ต้องเปิด PowerPoint

## ทำไมต้องใช้ Aspose.Slides for Java เพื่อเพิ่ม clustered column chart?
- **อัตโนมัติโดยสมบูรณ์** – ไม่ต้องโต้ตอบ UI ด้วยมือ  
- **ข้ามแพลตฟอร์ม** – ทำงานบน OS ใดก็ได้ที่รองรับ Java  
- **การจัดรูปแบบที่หลากหลาย** – ควบคุมสไตล์เส้น, การเติมสี, มุมโค้ง, และอื่น ๆ  
- **ไม่มีการพึ่งพา COM** – ต่างจาก Office Interop, ทำงานบนเซิร์ฟเวอร์ได้อย่างปลอดภัย

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** (เวอร์ชัน 25.4 หรือใหม่กว่า)  
- **JDK 16** (หรือใหม่กว่า)  
- IDE เช่น IntelliJ IDEA, Eclipse, หรือ NetBeans  

## การตั้งค่า Aspose.Slides for Java
คุณสามารถเพิ่มไลบรารีผ่าน Maven, Gradle หรือดาวน์โหลดโดยตรง

### ใช้ Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ใช้ Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
ดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

#### ขั้นตอนการรับลิขสิทธิ์
- **Free Trial** – ทดลองทุกฟีเจอร์โดยไม่มีข้อจำกัดเวลา  
- **Temporary License** – ขอจากพอร์ทัล Aspose เพื่อประเมินฟีเจอร์เต็มรูปแบบ  
- **Purchase** – ซื้อเพื่อรับลิขสิทธิ์ถาวรสำหรับการใช้งานจริง

## คู่มือการทำงาน

### การสร้าง Presentation และเพิ่มสไลด์
#### ภาพรวม
แรกเริ่มเราจะสร้างอ็อบเจ็กต์ `Presentation` ใหม่และดึงสไลด์เริ่มต้นที่มาพร้อมไฟล์เปล่า

#### ขั้นตอนทีละขั้นตอน
**1. เริ่มต้นอ็อบเจ็กต์ Presentation**
```java
Presentation presentation = new Presentation();
```

**2. เข้าถึงสไลด์แรก**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. ปล่อยทรัพยากร**
```java
if (presentation != null) presentation.dispose();
```

### การเพิ่มแผนภูมิลงในสไลด์
#### ภาพรวม
ต่อไปเราจะฝัง **clustered column chart** ลงในสไลด์ที่เตรียมไว้

#### ขั้นตอนทีละขั้นตอน
**1. เริ่มต้นอ็อบเจ็กต์ Presentation**
```java
Presentation presentation = new Presentation();
```

**2. เข้าถึงสไลด์แรก**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. เพิ่ม Clustered Column Chart**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. ปล่อยทรัพยากร**
```java
if (presentation != null) presentation.dispose();
```

### การจัดรูปแบบเส้นของแผนภูมิและตั้งค่ามุมโค้ง
#### ภาพรวม
เพิ่มความสวยงามโดยใช้การเติมสีเส้นแบบ Solid, สไตล์เส้นเดียว, และมุมโค้ง

#### ขั้นตอนทีละขั้นตอน
**1. เริ่มต้นอ็อบเจ็กต์ Presentation**
```java
Presentation presentation = new Presentation();
```

**2. เข้าถึงสไลด์แรก**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. เพิ่ม Clustered Column Chart**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. ตั้งค่า Line Format ให้เป็น Solid Fill Type**
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. ใช้ Single Line Style**
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. เปิดใช้งาน Rounded Corners สำหรับ Chart Area**
```java
chart.setRoundedCorners(true);
```

**7. ปล่อยทรัพยากร**
```java
if (presentation != null) presentation.dispose();
```

### การบันทึก Presentation
#### ภาพรวม
สุดท้ายเราจะเขียนไฟล์ Presentation ลงดิสก์ในรูปแบบ PPTX

#### ขั้นตอนทีละขั้นตอน
**1. เริ่มต้นอ็อบเจ็กต์ Presentation**
```java
Presentation presentation = new Presentation();
```

**2. กำหนดไดเรกทอรีและชื่อไฟล์เอาต์พุต**
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. บันทึก Presentation ในรูปแบบ PPTX**
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. ปล่อยทรัพยากร**
```java
if (presentation != null) presentation.dispose();
```

## การประยุกต์ใช้ในเชิงปฏิบัติ
- **Business Reports** – อัตโนมัติการสร้างสไลด์การเงินไตรมาสด้วยแผนภูมิไดนามิก  
- **Educational Content** – สร้างสไลด์บรรยายที่ดึงข้อมูลจากฐานข้อมูล  
- **Marketing Presentations** – แสดงแนวโน้มผลิตภัณฑ์ด้วยแผนภูมิที่ดูเป็นมืออาชีพ  

## พิจารณาด้านประสิทธิภาพ
- **การจัดการทรัพยากร** – เรียก `dispose()` เสมอหรือใช้ try‑with‑resources  
- **การเพิ่มประสิทธิภาพหน่วยความจำ** – ประมวลผลชุดข้อมูลขนาดใหญ่เป็นแบตช์ย่อย  
- **แนวทางปฏิบัติที่ดีที่สุด** – ใช้โครงสร้างข้อมูลที่ไม่เปลี่ยนแปลงสำหรับ series ของแผนภูมิเมื่อเป็นไปได้  

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Solution |
|-------|----------|
| **`NullPointerException` on `getSlides()`** | ตรวจสอบให้แน่ใจว่าอ็อบเจ็กต์ `Presentation` ถูกสร้างสำเร็จก่อนเข้าถึงสไลด์ |
| **Chart not appearing** | ยืนยันว่าขนาดของแผนภูมิ (x, y, width, height) อยู่ในขอบเขตของสไลด์ |
| **License not applied** | โหลดไฟล์ลิขสิทธิ์ก่อนสร้างอ็อบเจ็กต์ `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## คำถามที่พบบ่อย

**Q: จะเพิ่มแผนภูมิประเภทอื่นด้วย Aspose.Slides อย่างไร?**  
A: แทนที่ `ChartType.ClusteredColumn` ด้วยค่า enum อื่น เช่น `ChartType.Pie`, `ChartType.Line`, หรือ `ChartType.Bar`

**Q: ถ้าพบข้อผิดพลาดในการคอมไพล์ควรทำอย่างไร?**  
A: ตรวจสอบให้แน่ใจว่ากำลังใช้ JDK 16 หรือใหม่กว่าและว่าการพึ่งพา Maven/Gradle ตรงกับเวอร์ชันที่ระบุข้างต้น

**Q: สามารถเติมข้อมูลให้แผนภูมิจากฐานข้อมูลได้หรือไม่?**  
A: ได้ โดยเข้าถึงคอลเลกชัน `getChartData()` ของแผนภูมิ, สร้าง series และ category, แล้วใส่ค่าที่ดึงมาจาก runtime

**Q: จะปรับปรุงประสิทธิภาพสำหรับ Presentation ขนาดใหญ่มากอย่างไร?**  
A: แบ่งงานเป็นหลาย `Presentation` instance, ใช้เทมเพลตแผนภูมิซ้ำ, และปล่อยอ็อบเจ็กต์ให้เร็วที่สุดเท่าที่จะทำได้  

## สรุป
คุณได้เรียนรู้สูตรครบวงจรสำหรับ **การเพิ่ม clustered column chart** ลงในสไลด์ PowerPoint ด้วย Aspose.Slides for Java ทดลองใช้แผนภูมิประเภทอื่น, เชื่อมต่อแหล่งข้อมูลแบบเรียลไทม์, และผสานตรรกะนี้เข้ากับไลน์การรายงานที่ใหญ่ขึ้นเพื่ออัตโนมัติกระบวนการสร้างสไลด์ของคุณ

---

**Last Updated:** 2026-03-15  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}