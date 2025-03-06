---
title: ลบแถวหรือคอลัมน์ในตาราง PowerPoint โดยใช้ Java
linktitle: ลบแถวหรือคอลัมน์ในตาราง PowerPoint โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีลบแถวหรือคอลัมน์ออกจากตาราง PowerPoint โดยใช้ Java กับ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนง่ายๆ สำหรับนักพัฒนา
weight: 18
url: /th/java/java-powerpoint-table-manipulation/remove-row-column-powerpoint-table-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีลบแถวหรือคอลัมน์ออกจากตาราง PowerPoint โดยใช้ Java ด้วยความช่วยเหลือของ Aspose.Slides Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม บทช่วยสอนนี้เน้นที่กระบวนการปรับเปลี่ยนตารางภายในสไลด์ PowerPoint โดยเฉพาะ โดยสาธิตวิธีการลบแถวหรือคอลัมน์เฉพาะออกจากตารางทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/)
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java และแนวคิดเชิงวัตถุ

## แพ็คเกจนำเข้า
ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณนำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ITable;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
ขั้นแรก สร้างวัตถุการนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
 แทนที่`"Your Document Directory"` ด้วยเส้นทางที่คุณต้องการบันทึกไฟล์ PowerPoint ของคุณ
## ขั้นตอนที่ 2: เข้าถึงสไลด์และเพิ่มตาราง
จากนั้น เข้าถึงสไลด์ที่คุณต้องการเพิ่มตารางและสร้างตารางที่มีความกว้างของคอลัมน์และความสูงของแถวที่ระบุ:
```java
ISlide slide = pres.getSlides().get_Item(0);
double[] colWidth = new double[]{100, 50, 30};
double[] rowHeight = new double[]{30, 50, 30};
ITable table = slide.getShapes().addTable(100, 100, colWidth, rowHeight);
```
ปรับพารามิเตอร์ (`100, 100` ในกรณีนี้) เพื่อวางตำแหน่งตารางบนสไลด์ตามต้องการ
## ขั้นตอนที่ 3: ลบแถวออกจากตาราง
 หากต้องการลบแถวใดแถวหนึ่งออกจากตาราง ให้ใช้`removeAt` วิธีการบน`Rows` คอลเลกชันของโต๊ะ:
```java
table.getRows().removeAt(1, false);
```
 แทนที่`1` ด้วยดัชนีของแถวที่คุณต้องการลบ พารามิเตอร์ที่สอง (`false`) ระบุว่าจะลบเนื้อหาที่เกี่ยวข้องบนสไลด์หรือไม่
## ขั้นตอนที่ 4: ลบคอลัมน์ออกจากตาราง
 ในทำนองเดียวกัน หากต้องการลบคอลัมน์ใดคอลัมน์หนึ่งออกจากตาราง ให้ใช้`removeAt` วิธีการบน`Columns` คอลเลกชันของโต๊ะ:
```java
table.getColumns().removeAt(1, false);
```
 แทนที่`1` ด้วยดัชนีของคอลัมน์ที่คุณต้องการลบ
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุบนดิสก์ของคุณ:
```java
pres.save(dataDir + "ModifiedTablePresentation.pptx", SaveFormat.Pptx);
```
 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"ModifiedTablePresentation.pptx"` พร้อมชื่อไฟล์ที่ต้องการ

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีจัดการตาราง PowerPoint โดยการลบแถวและคอลัมน์โดยใช้ Java และ Aspose.Slides เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับแต่งตารางภายในงานนำเสนอของคุณโดยทางโปรแกรมเพื่อให้เหมาะกับความต้องการของคุณมากขึ้น

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มแถวหรือคอลัมน์ลงในตารางโดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ได้ คุณสามารถเพิ่มแถวและคอลัมน์แบบไดนามิกโดยใช้วิธีการที่ได้รับจาก Aspose.Slides API
### Aspose.Slides รองรับการดำเนินการจัดการ PowerPoint อื่นๆ หรือไม่
Aspose.Slides ให้การสนับสนุนที่ครอบคลุมสำหรับการสร้าง การแก้ไข และการแปลงงานนำเสนอ PowerPoint รวมถึงการสร้างสไลด์ การจัดรูปแบบข้อความ และอื่นๆ
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 เอกสารรายละเอียดและตัวอย่างสามารถดูได้ที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) หน้าหนังสือ.
### Aspose.Slides เหมาะสำหรับระบบอัตโนมัติ PowerPoint ระดับองค์กรหรือไม่
ใช่ Aspose.Slides ถูกนำมาใช้กันอย่างแพร่หลายในสภาพแวดล้อมขององค์กรสำหรับการทำงาน PowerPoint อัตโนมัติ เนื่องจากมีคุณสมบัติและประสิทธิภาพที่แข็งแกร่ง
### ฉันสามารถลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Slides รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
