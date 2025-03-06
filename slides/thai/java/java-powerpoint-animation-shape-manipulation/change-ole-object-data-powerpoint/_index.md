---
title: เปลี่ยนข้อมูลวัตถุ OLE ใน PowerPoint
linktitle: เปลี่ยนข้อมูลวัตถุ OLE ใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการเปลี่ยนข้อมูลวัตถุ OLE ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนเพื่อการอัพเดตที่มีประสิทธิภาพและง่ายดาย
weight: 14
url: /th/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การเปลี่ยนข้อมูลวัตถุ OLE ในงานนำเสนอ PowerPoint อาจเป็นงานที่สำคัญเมื่อคุณต้องการอัปเดตเนื้อหาที่ฝังโดยไม่ต้องแก้ไขแต่ละสไลด์ด้วยตนเอง คู่มือที่ครอบคลุมนี้จะแนะนำคุณตลอดกระบวนการโดยใช้ Aspose.Slides สำหรับ Java ซึ่งเป็นไลบรารีอันทรงพลังที่ออกแบบมาเพื่อจัดการงานนำเสนอ PowerPoint ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คุณจะพบว่าบทช่วยสอนนี้มีประโยชน์และง่ายต่อการปฏิบัติตาม
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่จำเป็นในการเริ่มต้นแล้ว
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ของออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก[หน้าดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): คุณสามารถใช้ Java IDE ใดก็ได้ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
4.  Aspose.Cells สำหรับ Java: สิ่งนี้จำเป็นสำหรับการแก้ไขข้อมูลที่ฝังตัวภายในออบเจ็กต์ OLE ดาวน์โหลดได้จาก[หน้าดาวน์โหลด Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  ไฟล์การนำเสนอ: เตรียมไฟล์ PowerPoint พร้อมวัตถุ OLE ที่ฝังอยู่ สำหรับบทช่วยสอนนี้ เรามาตั้งชื่อกัน`ChangeOLEObjectData.pptx`.
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณกันก่อน
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

ตอนนี้ เรามาแบ่งกระบวนการออกเป็นขั้นตอนง่ายๆ ที่จัดการได้
## ขั้นตอนที่ 1: โหลดงานนำเสนอ PowerPoint
ในการเริ่มต้น คุณจะต้องโหลดงานนำเสนอ PowerPoint ที่มีวัตถุ OLE
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์ที่มีวัตถุ OLE
ถัดไป รับสไลด์ที่ฝังวัตถุ OLE
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: ค้นหาวัตถุ OLE ในสไลด์
วนซ้ำรูปร่างในสไลด์เพื่อค้นหาวัตถุ OLE
```java
OleObjectFrame ole = null;
// ทะลุทุกรูปทรงสำหรับกรอบโอเล่
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## ขั้นตอนที่ 4: แยกข้อมูลที่ฝังตัวออกจากวัตถุ OLE
หากพบวัตถุ OLE ให้แยกข้อมูลที่ฝังตัว
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## ขั้นตอนที่ 5: แก้ไขข้อมูลที่ฝังไว้โดยใช้ Aspose.Cells
ตอนนี้ ให้ใช้ Aspose.Cells เพื่ออ่านและแก้ไขข้อมูลที่ฝังอยู่ ซึ่งในกรณีนี้น่าจะเป็นสมุดงาน Excel
```java
    Workbook wb = new Workbook(msln);
    // ปรับเปลี่ยนข้อมูลสมุดงาน
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## ขั้นตอนที่ 6: บันทึกข้อมูลที่แก้ไขกลับไปยังวัตถุ OLE
หลังจากทำการเปลี่ยนแปลงที่จำเป็นแล้ว ให้บันทึกสมุดงานที่แก้ไขกลับเข้าไปในวัตถุ OLE
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## ขั้นตอนที่ 7: บันทึกงานนำเสนอที่อัปเดต
สุดท้าย ให้บันทึกงานนำเสนอ PowerPoint ที่อัปเดตแล้ว
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## บทสรุป
การอัปเดตข้อมูลอ็อบเจ็กต์ OLE ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการที่ไม่ซับซ้อนเมื่อคุณแบ่งย่อยออกเป็นขั้นตอนง่ายๆ คู่มือนี้จะแนะนำคุณตลอดขั้นตอนการโหลดงานนำเสนอ การเข้าถึงและการแก้ไขข้อมูล OLE ที่ฝังไว้ และการบันทึกงานนำเสนอที่อัปเดต ด้วยขั้นตอนเหล่านี้ คุณสามารถจัดการและอัปเดตเนื้อหาที่ฝังอยู่ในสไลด์ PowerPoint ของคุณได้อย่างมีประสิทธิภาพโดยทางโปรแกรม
## คำถามที่พบบ่อย
### วัตถุ OLE ใน PowerPoint คืออะไร?
ออบเจ็กต์ OLE (การเชื่อมโยงและการฝังวัตถุ) อนุญาตให้ฝังเนื้อหาจากแอปพลิเคชันอื่น เช่น สเปรดชีต Excel ลงในสไลด์ PowerPoint
### ฉันสามารถใช้ Aspose.Slides กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ใช่ Aspose.Slides รองรับหลายภาษา รวมถึง .NET, Python และ C-.
### ฉันจำเป็นต้องมี Aspose.Cells เพื่อแก้ไขวัตถุ OLE ใน PowerPoint หรือไม่
ใช่ หากวัตถุ OLE เป็นสเปรดชีต Excel คุณจะต้องใช้ Aspose.Cells เพื่อแก้ไข
### มี Aspose.Slides เวอร์ชันทดลองหรือไม่
 ใช่ คุณจะได้รับ[ทดลองฟรี](https://releases.aspose.com/) เพื่อทดสอบคุณสมบัติของ Aspose.Slides
### ฉันจะหาเอกสารสำหรับ Aspose.Slides ได้ที่ไหน
 คุณสามารถดูเอกสารรายละเอียดได้ที่[หน้าเอกสารประกอบของ Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
