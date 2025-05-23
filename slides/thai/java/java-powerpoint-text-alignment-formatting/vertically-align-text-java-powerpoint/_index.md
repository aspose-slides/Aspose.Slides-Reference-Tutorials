---
"description": "เรียนรู้วิธีจัดตำแหน่งข้อความแนวตั้งในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides เพื่อการจัดรูปแบบสไลด์ที่ราบรื่น"
"linktitle": "จัดแนวข้อความแนวตั้งใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "จัดแนวข้อความแนวตั้งใน Java PowerPoint"
"url": "/th/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# จัดแนวข้อความแนวตั้งใน Java PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดแนวข้อความในเซลล์ตารางในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การจัดแนวข้อความในแนวตั้งถือเป็นส่วนสำคัญของการออกแบบสไลด์ ช่วยให้มั่นใจได้ว่าเนื้อหาของคุณจะถูกนำเสนออย่างเรียบร้อยและเป็นมืออาชีพ Aspose.Slides มีคุณสมบัติอันทรงพลังในการจัดการและจัดรูปแบบงานนำเสนอด้วยโปรแกรม ช่วยให้คุณควบคุมทุกแง่มุมของสไลด์ได้อย่างเต็มที่
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- JDK (Java Development Kit) ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse ติดตั้งอยู่

## แพ็คเกจนำเข้า
ก่อนจะดำเนินการตามบทช่วยสอน โปรดแน่ใจว่าได้นำเข้าแพ็กเกจ Aspose.Slides ที่จำเป็นลงในไฟล์ Java ของคุณแล้ว:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ Java ของคุณ
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่มไลบรารี Aspose.Slides ลงในเส้นทางการสร้างโปรเจ็กต์ของคุณแล้ว
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
สร้างอินสแตนซ์ของ `Presentation` ชั้นเรียนเพื่อเริ่มทำงานกับการนำเสนอ PowerPoint ใหม่:
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
รับสไลด์แรกจากการนำเสนอเพื่อเพิ่มเนื้อหาลงไป:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: กำหนดขนาดตารางและเพิ่มตาราง
กำหนดความกว้างของคอลัมน์และความสูงของแถวสำหรับตารางของคุณ จากนั้นเพิ่มรูปร่างตารางลงในสไลด์:
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## ขั้นตอนที่ 5: ตั้งค่าเนื้อหาข้อความในเซลล์ตาราง
กำหนดเนื้อหาข้อความสำหรับแถวที่ระบุในตาราง:
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## ขั้นตอนที่ 6: เข้าถึงกรอบข้อความและจัดรูปแบบข้อความ
เข้าถึงกรอบข้อความและจัดรูปแบบข้อความภายในเซลล์ที่ระบุ:
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## ขั้นตอนที่ 7: จัดตำแหน่งข้อความตามแนวตั้ง
ตั้งค่าการจัดตำแหน่งแนวตั้งสำหรับข้อความภายในเซลล์:
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## ขั้นตอนที่ 8: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุบนดิสก์ของคุณ:
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 9: การล้างทรัพยากร
กำจัดของ `Presentation` คัดค้านการปล่อยทรัพยากร:
```java
if (presentation != null) presentation.dispose();
```

## บทสรุป
หากทำตามขั้นตอนเหล่านี้ คุณจะสามารถจัดแนวข้อความในเซลล์ตารางในงานนำเสนอ Java PowerPoint ของคุณได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Slides ความสามารถนี้จะช่วยเพิ่มความน่าสนใจและความคมชัดของสไลด์ของคุณ ทำให้มั่นใจได้ว่าเนื้อหาของคุณจะถูกนำเสนออย่างมืออาชีพ

## คำถามที่พบบ่อย
### ฉันสามารถจัดแนวข้อความตามแนวตั้งในรูปทรงอื่นนอกเหนือจากตารางได้หรือไม่
ใช่ Aspose.Slides มีวิธีการจัดเรียงข้อความในแนวตั้งเป็นรูปทรงต่างๆ รวมถึงกล่องข้อความและช่องว่าง
### Aspose.Slides รองรับการจัดตำแหน่งข้อความในแนวนอนด้วยหรือไม่
ใช่ คุณสามารถจัดตำแหน่งข้อความในแนวนอนได้โดยใช้ตัวเลือกการจัดตำแหน่งต่างๆ ที่ให้ไว้ใน Aspose.Slides
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกเวอร์ชันหรือไม่
Aspose.Slides รองรับการสร้างงานนำเสนอที่เข้ากันได้กับ Microsoft PowerPoint เวอร์ชันหลักทั้งหมด
### ฉันสามารถหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
เยี่ยมชม [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำที่ครอบคลุม เอกสารอ้างอิง API และตัวอย่างโค้ด
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides ได้อย่างไร
สำหรับความช่วยเหลือด้านเทคนิคและการสนับสนุนชุมชน โปรดไปที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}