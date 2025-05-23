---
"description": "ปรับปรุงการนำเสนอ PowerPoint ของคุณใน .NET โดยใช้ Aspose.Slides ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อเพิ่มบรรทัดธรรมดาได้อย่างง่ายดาย"
"linktitle": "การเพิ่มเส้นธรรมดาลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การเพิ่มเส้นธรรมดาลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides"
"url": "/th/net/shape-effects-and-manipulation-in-slides/adding-plain-lines/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่มเส้นธรรมดาลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าสนใจและดึงดูดสายตา มักเกี่ยวข้องกับการรวมเอารูปทรงและองค์ประกอบต่างๆ เข้าด้วยกัน หากคุณกำลังทำงานกับ .NET Aspose.Slides เป็นเครื่องมืออันทรงพลังที่ช่วยลดความซับซ้อนของกระบวนการ บทช่วยสอนนี้เน้นที่การเพิ่มเส้นเรียบๆ ลงในสไลด์งานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำที่ทำตามได้ง่ายนี้เพื่อปรับปรุงงานนำเสนอของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มเรียนรู้บทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET
- ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่น ๆ ที่ต้องการ
- ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/net/).
## นำเข้าเนมสเปซ
ในโครงการ .NET ของคุณ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์คลาส PresentationEx
สร้างอินสแตนซ์ของ `Presentation` คลาสที่แสดงไฟล์ PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // โค้ดของคุณสำหรับขั้นตอนต่อไปจะอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: รับสไลด์แรก
เข้าถึงสไลด์แรกของการนำเสนอ:
```csharp
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 4: เพิ่มเส้นรูปร่างอัตโนมัติ
เพิ่มเส้นรูปร่างอัตโนมัติให้กับสไลด์:
```csharp
sld.Shapes.AddAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
ปรับพารามิเตอร์ (ซ้าย, ด้านบน, ความกว้าง, ความสูง) ตามความต้องการของคุณ
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขแล้วลงในดิสก์:
```csharp
pres.Save(dataDir + "LineShape1_out.pptx", SaveFormat.Pptx);
```
บทความนี้เป็นบทสรุปของคำแนะนำทีละขั้นตอนในการเพิ่มบรรทัดธรรมดาลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## บทสรุป
การนำเส้นเรียบง่ายมาใช้กับงานนำเสนอ PowerPoint ของคุณจะช่วยเพิ่มความน่าสนใจให้กับภาพได้อย่างมาก Aspose.Slides สำหรับ .NET มอบวิธีง่ายๆ ในการทำสิ่งนี้ ทดลองใช้รูปทรงและองค์ประกอบต่างๆ เพื่อสร้างงานนำเสนอที่น่าดึงดูด
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์ของเส้นได้หรือไม่?
ตอบ: ใช่ คุณสามารถปรับสี ความหนา และสไตล์โดยใช้ Aspose.Slides API ได้
### ถาม: Aspose.Slides เข้ากันได้กับกรอบงาน .NET ล่าสุดหรือไม่
ตอบ: แน่นอน Aspose.Slides รองรับ .NET framework ล่าสุด
### ถาม: ฉันสามารถหาตัวอย่างและเอกสารเพิ่มเติมได้ที่ไหน
ก. สำรวจเอกสาร [ที่นี่](https://reference-aspose.com/slides/net/).
### ถาม: ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
ก. การเยี่ยมชม [ที่นี่](https://purchase.aspose.com/temporary-license/) สำหรับใบอนุญาตชั่วคราว
### ถาม: ประสบปัญหาหรือไม่? ฉันสามารถขอรับการสนับสนุนได้ที่ไหน?
ก. ขอความช่วยเหลือเรื่อง [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}