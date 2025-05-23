---
"description": "เรียนรู้วิธีปรับปรุงการนำเสนอ PowerPoint ของคุณโดยการตั้งค่ารูปแบบการเชื่อมเส้นสำหรับรูปร่างต่างๆ โดยใช้ Aspose.Slides สำหรับ Java ทำตามคำแนะนำทีละขั้นตอนของเรา"
"linktitle": "รูปแบบการรวมสไตล์ใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รูปแบบการรวมสไตล์ใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รูปแบบการรวมสไตล์ใน PowerPoint

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าสนใจอาจเป็นงานที่น่ากังวล โดยเฉพาะอย่างยิ่งเมื่อคุณต้องการให้ทุกรายละเอียดสมบูรณ์แบบ นี่คือจุดที่ Aspose.Slides สำหรับ Java มีประโยชน์ ซึ่งเป็น API ที่มีประสิทธิภาพที่ช่วยให้คุณสร้าง จัดการ และจัดการงานนำเสนอด้วยโปรแกรม หนึ่งในฟีเจอร์ที่คุณสามารถใช้ได้คือการตั้งค่ารูปแบบการต่อเส้นสำหรับรูปร่างต่างๆ ซึ่งสามารถเพิ่มความสวยงามให้กับสไลด์ของคุณได้อย่างมาก ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีการใช้ Aspose.Slides สำหรับ Java เพื่อตั้งค่ารูปแบบการต่อเส้นสำหรับรูปร่างในงานนำเสนอ PowerPoint 
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์ของออราเคิล](https://www-oracle.com/java/technologies/javase-jdk11-downloads.html).
2. ไลบรารี Aspose.Slides สำหรับ Java: คุณต้องดาวน์โหลดและรวม Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณ คุณสามารถรับได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): ใช้ IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans เพื่อเขียนและดำเนินการโค้ด Java ของคุณ
4. ความรู้พื้นฐานเกี่ยวกับ Java: ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java จะช่วยให้คุณติดตามบทช่วยสอนได้
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Slides ซึ่งถือเป็นสิ่งสำคัญในการเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการจัดการการนำเสนอของเรา
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีโครงการ
เริ่มต้นด้วยการสร้างไดเร็กทอรีเพื่อจัดเก็บไฟล์งานนำเสนอของเรา วิธีนี้จะช่วยให้ไฟล์ทั้งหมดของเราได้รับการจัดระเบียบและเข้าถึงได้ง่าย
```java
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
ในขั้นตอนนี้ เราจะกำหนดเส้นทางไดเรกทอรีและตรวจสอบว่ามีหรือไม่ หากไม่มี เราจะสร้างไดเรกทอรีขึ้นมาเอง นี่เป็นวิธีง่ายๆ แต่มีประสิทธิภาพในการจัดระเบียบไฟล์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
ถัดไปเราจะสร้างตัวอย่าง `Presentation` คลาสซึ่งแสดงไฟล์ PowerPoint ของเรา นี่คือรากฐานที่เราจะใช้สร้างสไลด์และรูปทรงต่างๆ
```java
Presentation pres = new Presentation();
```
โค้ดบรรทัดนี้จะสร้างการนำเสนอใหม่ ลองนึกภาพว่ากำลังเปิดไฟล์ PowerPoint เปล่าๆ ที่คุณจะเพิ่มเนื้อหาทั้งหมดลงไป
## ขั้นตอนที่ 3: เพิ่มรูปร่างลงในสไลด์
### รับสไลด์แรก
ก่อนที่จะเพิ่มรูปร่าง เราจะต้องได้รับการอ้างอิงถึงสไลด์แรกในงานนำเสนอของเราเสียก่อน โดยค่าเริ่มต้น งานนำเสนอใหม่จะมีสไลด์ว่างหนึ่งสไลด์
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### เพิ่มรูปทรงสี่เหลี่ยมผืนผ้า
ตอนนี้เรามาเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าสามรูปลงในสไลด์ของเรา รูปทรงเหล่านี้จะแสดงรูปแบบการเชื่อมเส้นที่แตกต่างกัน
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
ในขั้นตอนนี้ เราจะเพิ่มสี่เหลี่ยมผืนผ้าสามรูปในตำแหน่งที่กำหนดบนสไลด์ สี่เหลี่ยมผืนผ้าแต่ละรูปจะมีรูปแบบที่แตกต่างกันในภายหลังเพื่อแสดงรูปแบบการเข้าร่วมที่หลากหลาย
## ขั้นตอนที่ 4: จัดแต่งรูปทรง
### ตั้งค่าสีเติม
เราต้องการให้สี่เหลี่ยมของเราเต็มไปด้วยสีทึบ ที่นี่เราเลือกสีดำเป็นสีเติม
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### ตั้งค่าความกว้างและสีของเส้น
ต่อไป เราจะกำหนดความกว้างของเส้นและสีของสี่เหลี่ยมผืนผ้าแต่ละอัน ซึ่งจะช่วยในการแยกความแตกต่างของรูปแบบการเข้าร่วมได้อย่างชัดเจน
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## ขั้นตอนที่ 5: ใช้รูปแบบการเข้าร่วม
จุดเด่นของบทช่วยสอนนี้คือการกำหนดรูปแบบการเชื่อมเส้น เราจะใช้รูปแบบที่แตกต่างกันสามแบบ ได้แก่ มุมเฉียง มุมเฉียง และมุมโค้งมน
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
รูปแบบการเชื่อมเส้นแต่ละแบบทำให้รูปร่างต่างๆ มีรูปลักษณ์เฉพาะตัวที่มุมที่เส้นมาบรรจบกัน ซึ่งอาจมีประโยชน์อย่างยิ่งในการสร้างไดอะแกรมหรือภาพประกอบที่มีเอกลักษณ์เฉพาะตัว
## ขั้นตอนที่ 6: เพิ่มข้อความลงในรูปร่าง
เพื่อให้ชัดเจนว่ารูปร่างแต่ละรูปร่างแสดงถึงอะไร เราจึงเพิ่มข้อความลงในแต่ละสี่เหลี่ยมผืนผ้าเพื่ออธิบายรูปแบบการเข้าร่วมที่ใช้
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
การเพิ่มข้อความช่วยในการระบุรูปแบบที่แตกต่างกันเมื่อคุณนำเสนอหรือแชร์สไลด์
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้ายเราบันทึกการนำเสนอของเราไปยังไดเร็กทอรีที่ระบุ
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
คำสั่งนี้จะเขียนการนำเสนอลงในไฟล์ PPTX ซึ่งคุณสามารถเปิดด้วย Microsoft PowerPoint หรือซอฟต์แวร์ที่เข้ากันได้อื่น ๆ
## บทสรุป
และแล้วคุณก็ทำได้! คุณเพิ่งสร้างสไลด์ PowerPoint ที่มีสี่เหลี่ยมผืนผ้าสามรูป โดยแต่ละรูปจะแสดงรูปแบบการเชื่อมบรรทัดที่แตกต่างกันโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้ไม่เพียงช่วยให้คุณเข้าใจพื้นฐานของ Aspose.Slides เท่านั้น แต่ยังแสดงวิธีปรับปรุงการนำเสนอของคุณด้วยรูปแบบเฉพาะตัวอีกด้วย นำเสนอให้สนุก!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังสำหรับการสร้าง จัดการ และจัดการการนำเสนอ PowerPoint ด้วยโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ใน IDE ใด ๆ ได้หรือไม่
ใช่ คุณสามารถใช้ Aspose.Slides สำหรับ Java ใน IDE ที่รองรับ Java เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
### มี Aspose.Slides สำหรับ Java ให้ใช้ฟรีหรือไม่
ใช่ คุณสามารถรับการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### รูปแบบการรวมบรรทัดใน PowerPoint คืออะไร
รูปแบบการเชื่อมเส้นหมายถึงรูปร่างของมุมที่เส้นสองเส้นมาบรรจบกัน รูปแบบทั่วไปได้แก่ มุมเฉียง มุมเฉียง และมุมโค้งมน
### ฉันสามารถหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารรายละเอียดได้ [ที่นี่](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}