---
"description": "สำรวจโลกแห่งการนำเสนอ PowerPoint แบบไดนามิกด้วย Aspose.Slides สำหรับ .NET เรียนรู้วิธีการสร้างรูปทรงสี่เหลี่ยมผืนผ้าที่น่าสนใจในสไลด์ด้วยคู่มือทีละขั้นตอนนี้"
"linktitle": "การสร้างรูปทรงสี่เหลี่ยมผืนผ้าเรียบง่ายในสไลด์การนำเสนอโดยใช้ Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การสร้างรูปทรงสี่เหลี่ยมผืนผ้าด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างรูปทรงสี่เหลี่ยมผืนผ้าด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
หากคุณต้องการปรับปรุงแอปพลิเคชัน .NET ของคุณด้วยการนำเสนอ PowerPoint แบบไดนามิกและสวยงาม Aspose.Slides สำหรับ .NET คือโซลูชันที่คุณต้องการ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างรูปสี่เหลี่ยมผืนผ้าเรียบง่ายในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มเรียนรู้บทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนเครื่องพัฒนาของคุณแล้ว
- Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ .NET จาก [ที่นี่](https://releases-aspose.com/slides/net/).
- ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญ
## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio ตรวจสอบว่า Aspose.Slides สำหรับ .NET มีการอ้างอิงอย่างถูกต้องในโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // โค้ดของคุณสำหรับขั้นตอนต่อไปจะอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: รับสไลด์แรก
```csharp
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 4: เพิ่มรูปสี่เหลี่ยมผืนผ้าอัตโนมัติ
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
โค้ดนี้จะเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าที่พิกัด (50, 150) โดยมีความกว้าง 150 และความสูง 50
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
ขั้นตอนนี้จะบันทึกการนำเสนอโดยมีรูปสี่เหลี่ยมผืนผ้าที่เพิ่มลงในไดเร็กทอรีที่ระบุ
## บทสรุป
ขอแสดงความยินดี! คุณได้สร้างรูปสี่เหลี่ยมผืนผ้าเรียบง่ายในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว นี่เป็นเพียงจุดเริ่มต้นเท่านั้น Aspose.Slides นำเสนอคุณลักษณะมากมายเพื่อปรับแต่งและปรับปรุงการนำเสนอของคุณให้ดียิ่งขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ในสภาพแวดล้อม Windows และ Linux ได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET ไม่ขึ้นอยู่กับแพลตฟอร์มและสามารถใช้ได้ในสภาพแวดล้อมทั้ง Windows และ Linux
### มี Aspose.Slides สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถรับสิทธิ์ทดลองใช้ฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อการสนับสนุนชุมชน
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
อ้างอิงเอกสารประกอบ [ที่นี่](https://reference-aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}