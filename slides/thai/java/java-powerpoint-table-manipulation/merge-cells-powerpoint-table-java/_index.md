---
"description": "เรียนรู้วิธีการผสานเซลล์ในตาราง PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงเค้าโครงการนำเสนอของคุณด้วยคู่มือทีละขั้นตอนนี้"
"linktitle": "รวมเซลล์ในตาราง PowerPoint ด้วย Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รวมเซลล์ในตาราง PowerPoint ด้วย Java"
"url": "/th/java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รวมเซลล์ในตาราง PowerPoint ด้วย Java

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการผสานเซลล์ภายในตาราง PowerPoint อย่างมีประสิทธิภาพโดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ได้ด้วยโปรแกรม ด้วยการผสานเซลล์ในตาราง คุณสามารถปรับแต่งเค้าโครงและโครงสร้างของสไลด์การนำเสนอของคุณได้ ซึ่งจะทำให้ภาพชัดเจนและสวยงามยิ่งขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- JDK (Java Development Kit) ติดตั้งอยู่บนเครื่องของคุณ
- IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides แล้ว:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก ให้สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในการอ้างอิงโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
สร้างตัวอย่าง `Presentation` คลาสเพื่อแสดงไฟล์ PPTX ที่คุณกำลังทำงานด้วย:
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์
เข้าถึงสไลด์ที่คุณต้องการเพิ่มตาราง ตัวอย่างเช่น หากต้องการเข้าถึงสไลด์แรก ให้ทำดังนี้:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: กำหนดขนาดตาราง
กำหนดคอลัมน์และแถวสำหรับตารางของคุณ ระบุความกว้างของคอลัมน์และความสูงของแถวเป็นอาร์เรย์ของ `double`-
```java
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## ขั้นตอนที่ 5: เพิ่มรูปร่างตารางลงในสไลด์
เพิ่มรูปร่างตารางลงในสไลด์โดยใช้มิติที่กำหนด:
```java
ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## ขั้นตอนที่ 6: ปรับแต่งขอบเขตเซลล์
กำหนดรูปแบบเส้นขอบสำหรับแต่ละเซลล์ในตาราง ตัวอย่างนี้จะกำหนดเส้นขอบทึบสีแดงที่มีความกว้าง 5 สำหรับแต่ละเซลล์:
```java
for (IRow row : table.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        // ตั้งค่ารูปแบบเส้นขอบสำหรับแต่ละด้านของเซลล์
        cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderTop().setWidth(5);
        cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderBottom().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderBottom().setWidth(5);
        cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderLeft().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderLeft().setWidth(5);
        cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderRight().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderRight().setWidth(5);
    }
}
```
## ขั้นตอนที่ 7: รวมเซลล์ในตาราง
หากต้องการผสานเซลล์ในตาราง ให้ใช้ `mergeCells` วิธีการ ตัวอย่างนี้ผสานเซลล์จาก (1, 1) ถึง (2, 1) และจาก (1, 2) ถึง (2, 2):
```java
table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## ขั้นตอนที่ 8: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ PPTX บนดิสก์ของคุณ:
```java
String dataDir = "Your_Document_Directory_Path/";
presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะได้เรียนรู้วิธีการผสานเซลล์ภายในตาราง PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว เทคนิคนี้ช่วยให้คุณสร้างการนำเสนอที่ซับซ้อนและดึงดูดสายตามากขึ้นด้วยโปรแกรม ซึ่งช่วยเพิ่มประสิทธิภาพการทำงานและตัวเลือกในการปรับแต่งของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น Java API สำหรับการสร้าง จัดการ และแปลงการนำเสนอ PowerPoint ด้วยโปรแกรม
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร?
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
### ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
ใช่ คุณสามารถรับรุ่นทดลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีจาก [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารประกอบได้ [ที่นี่](https://reference-aspose.com/slides/java/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Slides ได้ [ที่นี่](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}