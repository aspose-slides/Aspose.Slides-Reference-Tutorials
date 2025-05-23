---
"date": "2025-04-17"
"description": "เรียนรู้วิธีสร้างและปรับแต่งแผนภูมิซันเบิร์สต์ใน PowerPoint ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ครอบคลุมถึงการตั้งค่า การปรับแต่ง และการใช้งานจริง"
"title": "สร้างและปรับแต่งแผนภูมิ Sunburst ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java"
"url": "/th/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างและปรับแต่งแผนภูมิ Sunburst ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java

## การแนะนำ

การสร้างงานนำเสนอที่น่าสนใจมักเกี่ยวข้องกับการรวมแผนภูมิที่สะดุดตาซึ่งถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ แผนภูมิดังกล่าวคือแผนภูมิซันเบิร์สต์ ซึ่งเป็นวิธีที่ไม่เหมือนใครในการแสดงข้อมูลแบบลำดับชั้นด้วยเค้าโครงแบบรัศมี อย่างไรก็ตาม การเพิ่มและปรับแต่งแผนภูมิเหล่านี้อาจเป็นงานที่น่ากลัวหากไม่มีเครื่องมือที่เหมาะสม คู่มือนี้จะแนะนำคุณเกี่ยวกับการสร้างและปรับเปลี่ยนแผนภูมิซันเบิร์สต์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าสภาพแวดล้อมของคุณสำหรับ Aspose.Slides
- การสร้างงานนำเสนอใหม่ด้วยแผนภูมิซันเบิร์สต์
- การปรับแต่งจุดข้อมูลภายในแผนภูมิ
- การนำทักษะเหล่านี้ไปใช้ในโลกแห่งความเป็นจริง

มาเจาะลึกกันว่าคุณสามารถลดความซับซ้อนของกระบวนการนี้ได้อย่างไรโดยใช้ Aspose.Slides สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนาของคุณพร้อมแล้ว คุณจะต้องมี:
- **ชุดพัฒนา Java (JDK)** เวอร์ชัน 16 ขึ้นไป
- หนึ่ง **สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE)** เช่น IntelliJ IDEA หรือ Eclipse
- ความรู้พื้นฐานเกี่ยวกับ **ชวา** และการนำเสนอ PowerPoint

## การตั้งค่า Aspose.Slides สำหรับ Java

### การพึ่งพา Maven

หากต้องการรวม Aspose.Slides ในโครงการของคุณ ให้เพิ่มการอ้างอิงต่อไปนี้ให้กับโครงการของคุณ `pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การอ้างอิงของ Gradle

หากคุณใช้ Gradle โปรดรวมสิ่งต่อไปนี้ไว้ใน `build.gradle`-
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง

หรือดาวน์โหลด JAR เวอร์ชันล่าสุดจาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

### การขอใบอนุญาต

การใช้ Aspose.Slides โดยไม่มีข้อจำกัดในการประเมิน:
- **ทดลองใช้งานฟรี:** เริ่มต้นด้วยใบอนุญาตชั่วคราวเพื่อสำรวจคุณสมบัติทั้งหมด
- **ใบอนุญาตชั่วคราว:** ขอใบอนุญาตชั่วคราวได้ที่ [เว็บไซต์อาโพส](https://purchase-aspose.com/temporary-license).
- **ซื้อ:** สำหรับโครงการที่กำลังดำเนินการ โปรดพิจารณาซื้อการสมัครสมาชิก

### การเริ่มต้นขั้นพื้นฐาน

นี่คือวิธีการเริ่มต้น Aspose.Slides ในแอปพลิเคชัน Java ของคุณ:
```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // เริ่มต้น Aspose.Slides ด้วยใบอนุญาตหากมี
        Presentation pres = new Presentation();
        try {
            // รหัสของคุณที่นี่...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## คู่มือการใช้งาน

### สร้างการนำเสนอและเพิ่มแผนภูมิซันเบิร์สต์

#### ภาพรวม

ฟีเจอร์นี้สาธิตวิธีการสร้างงานนำเสนอ PowerPoint ตั้งแต่เริ่มต้นและเพิ่มแผนภูมิซันเบิร์สต์

#### ขั้นตอน:
##### ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // แทนที่ด้วยเส้นทางของคุณ
```

##### ขั้นตอนที่ 2: เพิ่มแผนภูมิซันเบิร์สต์
เพิ่มแผนภูมิซันเบิร์สต์ลงในสไลด์แรกที่ตำแหน่ง (100, 100) และมีขนาด (450x400)
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

##### ขั้นตอนที่ 3: บันทึกการนำเสนอ
บันทึกการนำเสนอของคุณเพื่อให้แน่ใจว่าได้เก็บการเปลี่ยนแปลงทั้งหมดไว้
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### ปรับเปลี่ยนจุดข้อมูลในแผนภูมิ

#### ภาพรวม
เรียนรู้วิธีการปรับเปลี่ยนจุดข้อมูล รวมถึงป้ายกำกับและสีภายในแผนภูมิซันเบิร์สต์

#### ขั้นตอน:
##### ขั้นตอนที่ 1: การรวบรวมจุดข้อมูลการเข้าถึง
เข้าถึงคอลเลกชันจุดข้อมูลของชุดแรกจากแผนภูมิ
```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

##### ขั้นตอนที่ 2: แสดงค่าสำหรับจุดข้อมูลเฉพาะ
แก้ไขฉลากเพื่อแสดงค่าในระดับที่เฉพาะเจาะจง
```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

##### ขั้นตอนที่ 3: ปรับเปลี่ยนรูปแบบฉลาก
ปรับการตั้งค่าฉลาก เช่น ความสามารถในการมองเห็นชื่อหมวดหมู่และสีข้อความ
```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

##### ขั้นตอนที่ 4: ตั้งค่าสีเติมสำหรับจุดข้อมูล
ปรับแต่งสีเติมของจุดข้อมูลที่เฉพาะเจาะจง
```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

##### ขั้นตอนที่ 5: บันทึกการนำเสนอที่แก้ไขแล้ว
บันทึกการเปลี่ยนแปลงของคุณเสมอเพื่อทำให้เสร็จสมบูรณ์
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## การประยุกต์ใช้งานจริง

1. **การวิเคราะห์ธุรกิจ:** ใช้แผนภูมิซันเบิร์สต์เพื่อแสดงลำดับชั้นของข้อมูลที่ซับซ้อน เช่น ข้อมูลการขายตามภูมิภาคและหมวดหมู่
2. **การจัดการโครงการ:** แสดงงานโครงการที่แบ่งออกเป็นงานย่อยโดยใช้แผนภูมิวงกลมเพื่อให้มองเห็นได้ง่าย
3. **การศึกษา:** เป็นตัวแทนโมดูลหลักสูตรและการบรรยายของแต่ละโมดูลในการนำเสนอทางการศึกษา

## การพิจารณาประสิทธิภาพ

- **เพิ่มประสิทธิภาพการใช้ทรัพยากร:** ตรวจสอบให้แน่ใจว่าแอปพลิเคชันของคุณจัดการหน่วยความจำอย่างมีประสิทธิภาพ โดยเฉพาะอย่างยิ่งเมื่อจัดการชุดข้อมูลขนาดใหญ่หรือแผนภูมิหลายรายการ
- **การจัดการหน่วยความจำ Java:** ใช้แนวทางปฏิบัติที่ดีที่สุด เช่น กำจัดวัตถุทันทีเพื่อป้องกันการรั่วไหลของหน่วยความจำ

## บทสรุป

การสร้างและปรับแต่งแผนภูมิซันเบิร์สต์โดยใช้ Aspose.Slides สำหรับ Java เป็นวิธีที่มีประสิทธิภาพในการปรับปรุงการนำเสนอของคุณ เมื่อปฏิบัติตามคู่มือนี้ คุณจะเรียนรู้สิ่งสำคัญในการตั้งค่าสภาพแวดล้อม การนำคุณลักษณะแผนภูมิไปใช้ และการปรับเปลี่ยนจุดข้อมูลอย่างมีประสิทธิภาพ

**ขั้นตอนต่อไป:**
- สำรวจประเภทแผนภูมิเพิ่มเติมที่มีอยู่ใน Aspose.Slides
- ทดลองใช้ตัวเลือกการปรับแต่งที่แตกต่างกันสำหรับแผนภูมิของคุณ

**คำกระตุ้นการตัดสินใจ:** ลองนำโซลูชั่นเหล่านี้ไปใช้ในโครงการการนำเสนอครั้งต่อไปของคุณเพื่อดูว่าโซลูชั่นเหล่านี้สามารถเพิ่มประสิทธิภาพความพยายามในการสร้างภาพข้อมูลของคุณได้อย่างไร!

## ส่วนคำถามที่พบบ่อย

1. **แผนภูมิซันเบิร์สต์คืออะไร?**
   - แผนภูมิซันเบิร์สต์จะแสดงข้อมูลแบบลำดับชั้นในแนวรัศมี เหมาะสำหรับการแสดงความสัมพันธ์แบบซ้อนกัน
2. **ฉันจะติดตั้ง Aspose.Slides สำหรับ Java โดยใช้ Maven ได้อย่างไร**
   - เพิ่มการพึ่งพาของคุณ `pom.xml` ไฟล์ดังที่แสดงในส่วนการตั้งค่าด้านบน
3. **ฉันสามารถปรับเปลี่ยนแผนภูมิประเภทอื่นด้วย Aspose.Slides ได้หรือไม่**
   - ใช่ Aspose.Slides รองรับแผนภูมิประเภทต่างๆ เช่น แผนภูมิคอลัมน์ แผนภูมิเส้น และแผนภูมิวงกลม
4. **ฉันควรทำอย่างไรหากการนำเสนอของฉันไม่ได้รับการบันทึกอย่างถูกต้อง?**
   - ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ของคุณถูกต้องและคุณมีสิทธิ์ในการเขียนสำหรับไดเร็กทอรี
5. **ฉันจะได้รับความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Slides ได้อย่างไร**
   - เยี่ยมชม [ฟอรั่ม Aspose](https://forum.aspose.com/c/slides/11) หรือตรวจสอบเอกสารได้ที่ [อ้างอิง Aspose.Slides](https://reference-aspose.com/slides/java/).

## ทรัพยากร
- **เอกสารประกอบ:** [อ้างอิง Aspose.Slides](https://reference.aspose.com/slides/java)
- **ฟอรั่ม:** [ฟอรั่ม Aspose](https://forum.aspose.com/c/slides)
- **ดาวน์โหลด:** [ดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}