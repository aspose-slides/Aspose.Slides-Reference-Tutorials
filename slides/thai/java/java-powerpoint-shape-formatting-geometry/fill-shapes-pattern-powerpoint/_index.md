---
"description": "เรียนรู้การเติมรูปทรงด้วยรูปแบบใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนง่ายๆ ของเราเพื่อปรับปรุงการนำเสนอของคุณให้สวยงามยิ่งขึ้น"
"linktitle": "เติมรูปร่างด้วยรูปแบบใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เติมรูปร่างด้วยรูปแบบใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เติมรูปร่างด้วยรูปแบบใน PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญในการดึงดูดผู้ฟัง วิธีหนึ่งในการปรับปรุงสไลด์ PowerPoint ของคุณคือการเติมรูปแบบลงในรูปร่าง ในบทช่วยสอนนี้ เราจะแนะนำขั้นตอนในการเติมรูปแบบลงในรูปร่างโดยใช้ Aspose.Slides สำหรับ Java คู่มือนี้ได้รับการออกแบบมาสำหรับนักพัฒนาที่ต้องการใช้ประโยชน์จากคุณสมบัติอันทรงพลังของ Aspose.Slides เพื่อสร้างงานนำเสนอที่สวยงามด้วยโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่จะดำดิ่งลงไปในโค้ด ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Java Development Kit (JDK) ติดตั้งอยู่บนเครื่องของคุณ
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
## แพ็คเกจนำเข้า
ก่อนอื่นให้เรานำเข้าแพ็กเกจที่จำเป็นสำหรับตัวอย่างของเรา
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ก่อนที่จะเขียนโค้ด โปรดตรวจสอบให้แน่ใจว่าโครงการของคุณได้รับการตั้งค่าอย่างถูกต้อง สร้างโครงการ Java ใหม่ใน IDE ของคุณ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโครงการของคุณ
## ขั้นตอนที่ 2: สร้างไดเรกทอรีเอกสาร
เพื่อจัดการไฟล์ของคุณอย่างมีประสิทธิภาพ ให้สร้างไดเร็กทอรีที่เราจะบันทึกงานนำเสนอ PowerPoint ของเรา
```java
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
สไนปเป็ตนี้จะตรวจสอบว่าไดเร็กทอรีมีอยู่หรือไม่ และสร้างขึ้นใหม่ถ้าไม่มี
## ขั้นตอนที่ 3: สร้างอินสแตนซ์คลาสการนำเสนอ
ถัดไปเราต้องสร้างอินสแตนซ์ของ `Presentation` คลาสซึ่งแสดงถึงไฟล์ PowerPoint ของเรา
```java
Presentation pres = new Presentation();
```
นี่เป็นการเริ่มต้นวัตถุการนำเสนอใหม่ซึ่งเราจะใช้เพื่อเพิ่มสไลด์และรูปร่าง
## ขั้นตอนที่ 4: เข้าถึงสไลด์แรก
ในการเริ่มต้น เราต้องเข้าถึงสไลด์แรกของงานนำเสนอของเรา นี่คือจุดที่เราจะเพิ่มรูปทรงของเรา
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 5: เพิ่มรูปทรงสี่เหลี่ยมผืนผ้า
มาเพิ่มรูปสี่เหลี่ยมผืนผ้าให้กับสไลด์ของเรากันเถอะ สี่เหลี่ยมผืนผ้านี้จะถูกเติมด้วยลวดลาย
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
โค้ดชิ้นนี้จะเพิ่มสี่เหลี่ยมผืนผ้าลงในสไลด์ในตำแหน่งและขนาดที่ระบุ
## ขั้นตอนที่ 6: ตั้งค่าประเภทการเติมเป็นรูปแบบ
ตอนนี้ เราต้องตั้งค่าประเภทการเติมของรูปสี่เหลี่ยมให้เป็นการเติมรูปแบบ
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## ขั้นตอนที่ 7: เลือกสไตล์รูปแบบ
Aspose.Slides มีรูปแบบลวดลายต่างๆ มากมาย ในตัวอย่างนี้ เราจะใช้รูปแบบ "Trellis"
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## ขั้นตอนที่ 8: ตั้งค่าสีรูปแบบ
เราสามารถปรับแต่งสีของลวดลายได้ โดยให้สีพื้นหลังเป็นสีเทาอ่อน และสีพื้นหน้าเป็นสีเหลือง
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## ขั้นตอนที่ 9: บันทึกการนำเสนอ
หลังจากตั้งค่ารูปร่างด้วยรูปแบบที่ต้องการแล้ว เราจะต้องบันทึกการนำเสนอลงในไฟล์
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
การดำเนินการนี้จะบันทึกการนำเสนอในไดเร็กทอรีที่ระบุโดยมีชื่อไฟล์ "RectShpPatt_out.pptx"
## ขั้นตอนที่ 10: ทำความสะอาดทรัพยากร
ถือเป็นแนวทางปฏิบัติที่ดีในการกำจัดวัตถุการนำเสนอเพื่อปลดปล่อยทรัพยากร
```java
if (pres != null) pres.dispose();
```
## บทสรุป
ขอแสดงความยินดี! คุณได้เติมรูปร่างด้วยรูปแบบในสไลด์ PowerPoint สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ช่วยให้คุณสร้างและจัดการการนำเสนอได้อย่างง่ายดาย เพิ่มสัมผัสแห่งความเป็นมืออาชีพให้กับโปรเจ็กต์ของคุณ
หากทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถปรับปรุงการนำเสนอของคุณด้วยรูปแบบต่างๆ ที่ทำให้การนำเสนอน่าสนใจและน่ามองมากขึ้น หากต้องการฟีเจอร์ขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม โปรดตรวจสอบ [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงการนำเสนอ PowerPoint ในแอปพลิเคชัน Java ได้
### ฉันจะรับ Aspose.Slides สำหรับ Java ได้อย่างไร?
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
### มี Aspose.Slides สำหรับ Java ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถรับการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อจัดการการนำเสนอที่มีอยู่ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java ช่วยให้คุณเปิด แก้ไข และบันทึกการนำเสนอ PowerPoint ที่มีอยู่ได้
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้จากที่ไหน
คุณสามารถรับการสนับสนุนได้จาก [ฟอรั่มสนับสนุน Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}