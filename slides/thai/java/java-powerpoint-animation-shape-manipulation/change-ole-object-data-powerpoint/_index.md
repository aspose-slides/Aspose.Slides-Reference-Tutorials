---
"description": "เรียนรู้วิธีเปลี่ยนแปลงข้อมูลวัตถุ OLE ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนสำหรับการอัปเดตอย่างมีประสิทธิภาพและง่ายดาย"
"linktitle": "การเปลี่ยนแปลงข้อมูลวัตถุ OLE ใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การเปลี่ยนแปลงข้อมูลวัตถุ OLE ใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเปลี่ยนแปลงข้อมูลวัตถุ OLE ใน PowerPoint

## การแนะนำ
การเปลี่ยนแปลงข้อมูลวัตถุ OLE ในงานนำเสนอ PowerPoint อาจเป็นงานที่สำคัญเมื่อคุณจำเป็นต้องอัปเดตเนื้อหาที่ฝังไว้โดยไม่ต้องแก้ไขแต่ละสไลด์ด้วยตนเอง คู่มือที่ครอบคลุมนี้จะแนะนำคุณตลอดกระบวนการโดยใช้ Aspose.Slides สำหรับ Java ซึ่งเป็นไลบรารีอันทรงพลังที่ออกแบบมาสำหรับการจัดการงานนำเสนอ PowerPoint ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คุณจะพบว่าบทช่วยสอนนี้มีประโยชน์และทำตามได้ง่าย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกโค้ด เรามาตรวจสอบให้แน่ใจก่อนว่าคุณมีทุกสิ่งที่จำเป็นสำหรับการเริ่มต้น
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์ของออราเคิล](https://www-oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก [หน้าดาวน์โหลด Aspose.Slides](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): คุณสามารถใช้ Java IDE ใดๆ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
4. Aspose.Cells สำหรับ Java: จำเป็นสำหรับการปรับเปลี่ยนข้อมูลที่ฝังอยู่ภายในวัตถุ OLE ดาวน์โหลดได้จาก [หน้าดาวน์โหลด Aspose.Cells](https://releases-aspose.com/cells/java/).
5. ไฟล์นำเสนอ: เตรียมไฟล์ PowerPoint ที่มีอ็อบเจ็กต์ OLE ที่ฝังไว้ สำหรับบทช่วยสอนนี้ ให้ตั้งชื่อไฟล์นี้ `ChangeOLEObjectData-pptx`.
## แพ็คเกจนำเข้า
ก่อนอื่นให้เรานำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

ตอนนี้มาแบ่งกระบวนการออกเป็นขั้นตอนง่าย ๆ ที่จัดการได้
## ขั้นตอนที่ 1: โหลดงานนำเสนอ PowerPoint
ในการเริ่มต้น คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีอ็อบเจ็กต์ OLE
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์ที่มีวัตถุ OLE
ถัดไป ให้ดูสไลด์ที่ฝังวัตถุ OLE
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: ค้นหาวัตถุ OLE ในสไลด์
ทำซ้ำผ่านรูปร่างต่างๆ ในสไลด์เพื่อค้นหาวัตถุ OLE
```java
OleObjectFrame ole = null;
// การเคลื่อนที่ในทุกรูปทรงสำหรับเฟรม Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## ขั้นตอนที่ 4: แยกข้อมูลฝังตัวจากวัตถุ OLE
หากพบวัตถุ OLE ให้แยกข้อมูลที่ฝังไว้
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## ขั้นตอนที่ 5: แก้ไขข้อมูลฝังตัวโดยใช้ Aspose.Cells
ตอนนี้ให้ใช้ Aspose.Cells เพื่ออ่านและแก้ไขข้อมูลที่ฝังไว้ ซึ่งในกรณีนี้มักจะเป็นเวิร์กบุ๊ก Excel
```java
    Workbook wb = new Workbook(msln);
    // ปรับเปลี่ยนข้อมูลสมุดงาน
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## ขั้นตอนที่ 6: บันทึกข้อมูลที่แก้ไขกลับไปยังวัตถุ OLE
หลังจากทำการเปลี่ยนแปลงที่จำเป็นแล้ว ให้บันทึกเวิร์กบุ๊กที่แก้ไขกลับเข้าไปในอ็อบเจ็กต์ OLE
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอที่อัปเดต
ขั้นสุดท้าย ให้บันทึกการนำเสนอ PowerPoint ที่อัปเดต
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## บทสรุป
การอัปเดตข้อมูลวัตถุ OLE ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการที่ตรงไปตรงมาเมื่อคุณแบ่งกระบวนการออกเป็นขั้นตอนง่ายๆ คู่มือนี้จะแนะนำคุณตั้งแต่ขั้นตอนการโหลดงานนำเสนอ การเข้าถึงและแก้ไขข้อมูล OLE ที่ฝังไว้ และการบันทึกงานนำเสนอที่อัปเดต ด้วยขั้นตอนเหล่านี้ คุณสามารถจัดการและอัปเดตเนื้อหาที่ฝังไว้ในสไลด์ PowerPoint ของคุณผ่านโปรแกรมได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### OLE Object ใน PowerPoint คืออะไร
อ็อบเจ็กต์ OLE (Object Linking and Embedding) ช่วยให้สามารถฝังเนื้อหาจากแอปพลิเคชันอื่น เช่น สเปรดชีต Excel ลงในสไลด์ PowerPoint ได้
### ฉันสามารถใช้ Aspose.Slides กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ใช่ Aspose.Slides รองรับภาษาหลายภาษา รวมถึง .NET, Python และ C++
### ฉันจำเป็นต้องมี Aspose.Cells เพื่อปรับเปลี่ยนวัตถุ OLE ใน PowerPoint หรือไม่
ใช่ หากวัตถุ OLE เป็นสเปรดชีต Excel คุณจะต้องมี Aspose.Cells เพื่อปรับเปลี่ยน
### มี Aspose.Slides เวอร์ชันทดลองใช้หรือไม่
ใช่ คุณสามารถรับได้ [ทดลองใช้งานฟรี](https://releases.aspose.com/) เพื่อทดสอบคุณสมบัติของ Aspose.Slides
### ฉันสามารถค้นหาเอกสารสำหรับ Aspose.Slides ได้ที่ไหน
คุณสามารถค้นหาเอกสารรายละเอียดได้ที่ [หน้าเอกสาร Aspose.Slides](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}