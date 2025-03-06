---
title: จัดรูปแบบการรวมสไตล์ใน PowerPoint
linktitle: จัดรูปแบบการรวมสไตล์ใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับปรุงงานนำเสนอ PowerPoint ของคุณโดยการตั้งค่าสไตล์การรวมบรรทัดต่างๆ สำหรับรูปร่างโดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเรา
weight: 15
url: /th/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่ดึงดูดสายตาอาจเป็นงานที่น่ากังวล โดยเฉพาะอย่างยิ่งเมื่อคุณต้องการให้ทุกรายละเอียดสมบูรณ์แบบ นี่คือจุดที่ Aspose.Slides สำหรับ Java มีประโยชน์ เป็น API อันทรงพลังที่ช่วยให้คุณสร้าง จัดการ และจัดการการนำเสนอโดยทางโปรแกรม หนึ่งในคุณสมบัติที่คุณสามารถใช้ได้คือการตั้งค่าสไตล์การรวมเส้นที่แตกต่างกันสำหรับรูปร่าง ซึ่งสามารถเพิ่มความสวยงามให้กับสไลด์ของคุณได้อย่างมาก ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีที่คุณสามารถใช้ Aspose.Slides สำหรับ Java เพื่อตั้งค่าสไตล์การรวมสำหรับรูปร่างในงานนำเสนอ PowerPoint 
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ของออราเคิล](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java Library: คุณต้องดาวน์โหลดและรวม Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณ คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans เพื่อเขียนและรันโค้ด Java ของคุณ
4. ความรู้พื้นฐานของ Java: ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java จะช่วยให้คุณปฏิบัติตามบทช่วยสอน
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Slides นี่เป็นสิ่งสำคัญในการเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการจัดการการนำเสนอของเรา
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีโครงการ
เริ่มต้นด้วยการสร้างไดเร็กทอรีเพื่อจัดเก็บไฟล์การนำเสนอของเรา เพื่อให้แน่ใจว่าไฟล์ทั้งหมดของเราได้รับการจัดระเบียบและเข้าถึงได้ง่าย
```java
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
ในขั้นตอนนี้ เราจะกำหนดเส้นทางไดเรกทอรีและตรวจสอบว่ามีอยู่หรือไม่ หากไม่เป็นเช่นนั้น เราจะสร้างไดเร็กทอรีขึ้นมา นี่เป็นวิธีที่เรียบง่ายแต่มีประสิทธิภาพในการจัดระเบียบไฟล์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
 ต่อไป เราจะยกตัวอย่าง`Presentation` คลาสซึ่งแสดงถึงไฟล์ PowerPoint ของเรา นี่คือรากฐานที่เราจะสร้างสไลด์และรูปร่างของเรา
```java
Presentation pres = new Presentation();
```
โค้ดบรรทัดนี้จะสร้างงานนำเสนอใหม่ คิดว่าเป็นการเปิดไฟล์ PowerPoint เปล่าที่คุณจะเพิ่มเนื้อหาทั้งหมดของคุณ
## ขั้นตอนที่ 3: เพิ่มรูปร่างลงในสไลด์
### รับสไลด์แรก
ก่อนที่จะเพิ่มรูปร่าง เราจำเป็นต้องได้รับข้อมูลอ้างอิงไปยังสไลด์แรกในงานนำเสนอของเรา ตามค่าเริ่มต้น งานนำเสนอใหม่จะมีสไลด์เปล่าหนึ่งสไลด์
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### เพิ่มรูปทรงสี่เหลี่ยมผืนผ้า
ตอนนี้ เรามาเพิ่มรูปทรงสี่เหลี่ยมสามรูปลงในสไลด์ของเรา รูปร่างเหล่านี้จะสาธิตสไตล์การรวมเส้นที่แตกต่างกัน
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
ในขั้นตอนนี้ เราจะเพิ่มสี่เหลี่ยมสามรูปในตำแหน่งที่ระบุบนสไลด์ แต่ละสี่เหลี่ยมผืนผ้าจะได้รับการออกแบบที่แตกต่างกันในภายหลังเพื่อแสดงสไตล์การรวมต่างๆ
## ขั้นตอนที่ 4: จัดสไตล์รูปร่าง
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
ต่อไป เราจะกำหนดความกว้างของเส้นและสีของสี่เหลี่ยมแต่ละอัน ซึ่งจะช่วยในการมองเห็นความแตกต่างสไตล์การรวม
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
## ขั้นตอนที่ 5: ใช้สไตล์การเข้าร่วม
จุดเด่นของบทช่วยสอนนี้คือการตั้งค่าสไตล์การรวมบรรทัด เราจะใช้สไตล์ที่แตกต่างกันสามแบบ: Mitre, Bevel และ Round
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
สไตล์การรวมเส้นแต่ละเส้นทำให้รูปทรงมีรูปลักษณ์เฉพาะตัวที่มุมที่เส้นบรรจบกัน สิ่งนี้มีประโยชน์อย่างยิ่งสำหรับการสร้างไดอะแกรมหรือภาพประกอบที่ชัดเจน
## ขั้นตอนที่ 6: เพิ่มข้อความลงในรูปร่าง
เพื่อให้ชัดเจนว่าแต่ละรูปร่างแสดงถึงอะไร เราจะเพิ่มข้อความลงในแต่ละสี่เหลี่ยมผืนผ้าเพื่ออธิบายสไตล์การรวมที่ใช้
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
การเพิ่มข้อความช่วยในการระบุสไตล์ต่างๆ เมื่อคุณนำเสนอหรือแชร์สไลด์
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้าย เราจะบันทึกการนำเสนอของเราลงในไดเร็กทอรีที่ระบุ
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
คำสั่งนี้เขียนงานนำเสนอเป็นไฟล์ PPTX ซึ่งคุณสามารถเปิดด้วย Microsoft PowerPoint หรือซอฟต์แวร์อื่นที่เข้ากันได้
## บทสรุป
และคุณก็ได้แล้ว! คุณเพิ่งสร้างสไลด์ PowerPoint ที่มีสี่เหลี่ยมสามรูป โดยแต่ละรูปแสดงสไตล์การรวมบรรทัดที่แตกต่างกันโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้ไม่เพียงแต่ช่วยให้คุณเข้าใจพื้นฐานของ Aspose.Slides เท่านั้น แต่ยังแสดงวิธีปรับปรุงงานนำเสนอของคุณด้วยสไตล์ที่เป็นเอกลักษณ์อีกด้วย มีความสุขในการนำเสนอ!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่มีประสิทธิภาพสำหรับการสร้าง จัดการ และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ใน IDE ใด ๆ ได้หรือไม่
ได้ คุณสามารถใช้ Aspose.Slides สำหรับ Java ใน IDE ใดๆ ที่รองรับ Java เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
### มีการทดลองใช้ Aspose.Slides สำหรับ Java ฟรีหรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### สไตล์การรวมบรรทัดใน PowerPoint คืออะไร
ลักษณะการรวมเส้นหมายถึงรูปร่างของมุมที่เส้นสองเส้นมาบรรจบกัน สไตล์ทั่วไป ได้แก่ ตุ้มปี่ เอียง และกลม
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถค้นหาเอกสารรายละเอียดได้[ที่นี่](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
