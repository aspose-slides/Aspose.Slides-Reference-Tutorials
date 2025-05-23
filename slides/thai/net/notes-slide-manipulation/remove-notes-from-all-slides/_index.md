---
"description": "เรียนรู้วิธีลบบันทึกย่อออกจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ทำให้การนำเสนอของคุณดูสะอาดตาและเป็นมืออาชีพมากขึ้น"
"linktitle": "ลบบันทึกจากสไลด์ทั้งหมด"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "ลบบันทึกจากสไลด์ทั้งหมด"
"url": "/th/net/notes-slide-manipulation/remove-notes-from-all-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ลบบันทึกจากสไลด์ทั้งหมด


หากคุณเป็นนักพัฒนา .NET ที่ทำงานกับงานนำเสนอ PowerPoint คุณอาจพบว่าจำเป็นต้องลบบันทึกย่อออกจากสไลด์ทั้งหมดในงานนำเสนอของคุณ ซึ่งอาจมีประโยชน์เมื่อคุณต้องการทำความสะอาดสไลด์และลบข้อมูลเพิ่มเติมใดๆ ที่ไม่ได้มีไว้สำหรับผู้ชมของคุณ ในคู่มือทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการใช้ Aspose.Slides สำหรับ .NET เพื่อให้บรรลุภารกิจนี้ได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้นใช้งานบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Visual Studio: คุณควรติดตั้ง Visual Studio ไว้ในเครื่องพัฒนาของคุณ

2. Aspose.Slides สำหรับ .NET: คุณต้องติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์](https://releases-aspose.com/slides/net/).

3. การนำเสนอ PowerPoint: คุณควรมีการนำเสนอ PowerPoint (PPTX) ที่มีบันทึกย่อในสไลด์

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides คุณสามารถทำได้ดังนี้:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

ตอนนี้คุณมีข้อกำหนดเบื้องต้นแล้ว มาแบ่งกระบวนการในการลบโน้ตจากสไลด์ทั้งหมดเป็นคำแนะนำทีละขั้นตอนกัน

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx");
```

ในขั้นตอนนี้ คุณต้องโหลดการนำเสนอ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ .NET แทนที่ `"Your Document Directory"` และ `"YourPresentation.pptx"` ด้วยเส้นทางและชื่อไฟล์ที่เหมาะสม

## ขั้นตอนที่ 2: การลบบันทึก

ตอนนี้เรามาทำซ้ำในแต่ละสไลด์ในงานนำเสนอและลบบันทึกจากสไลด์เหล่านั้น:

```csharp
INotesSlideManager mgr = null;
for (int i = 0; i < presentation.Slides.Count; i++)
{
    mgr = presentation.Slides[i].NotesSlideManager;
    mgr.RemoveNotesSlide();
}
```

ลูปนี้จะผ่านสไลด์ทั้งหมดในงานนำเสนอของคุณ เข้าถึงตัวจัดการสไลด์บันทึกย่อสำหรับสไลด์แต่ละสไลด์ และลบบันทึกย่อออกจากนั้น

## ขั้นตอนที่ 3: บันทึกการนำเสนอ

เมื่อคุณลบบันทึกจากสไลด์ทั้งหมดแล้ว คุณสามารถบันทึกการนำเสนอที่แก้ไขได้:

```csharp
presentation.Save(dataDir + "PresentationWithoutNotes.pptx", SaveFormat.Pptx);
```

รหัสนี้จะบันทึกการนำเสนอโดยไม่มีหมายเหตุเป็นไฟล์ใหม่ที่ชื่อ `"PresentationWithoutNotes.pptx"`คุณสามารถเปลี่ยนชื่อไฟล์เป็นผลลัพธ์ที่คุณต้องการได้

เพียงเท่านี้ก็เรียบร้อย! คุณได้ลบบันทึกย่อออกจากสไลด์ทั้งหมดในงานนำเสนอ PowerPoint ของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET

ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญในการบรรลุภารกิจนี้อย่างมีประสิทธิภาพ หากคุณพบปัญหาใดๆ หรือมีคำถามเพิ่มเติม คุณสามารถดู Aspose.Slides สำหรับ .NET ได้ [เอกสารประกอบ](https://reference.aspose.com/slides/net/) หรือขอความช่วยเหลือได้ที่ [ฟอรั่มสนับสนุน Aspose](https://forum-aspose.com/).

## บทสรุป

การลบบันทึกย่อออกจากสไลด์ PowerPoint จะช่วยให้คุณนำเสนองานนำเสนอที่ดูสะอาดและเป็นมืออาชีพต่อผู้ฟังได้ Aspose.Slides สำหรับ .NET ช่วยให้งานนี้ง่ายขึ้น ช่วยให้คุณสามารถจัดการงานนำเสนอ PowerPoint ได้อย่างง่ายดาย เพียงทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณก็จะสามารถลบบันทึกย่อออกจากสไลด์ทั้งหมดในงานนำเสนอได้อย่างรวดเร็ว ทำให้งานนำเสนอมีความชัดเจนและสวยงามยิ่งขึ้น

## คำถามที่พบบ่อย (FAQs)

### 1. ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ร่วมกับภาษาการเขียนโปรแกรมอื่น ๆ ได้หรือไม่

ใช่ Aspose.Slides ยังใช้ได้กับ Java, C++ และภาษาการเขียนโปรแกรมอื่นๆ อีกมากมาย

### 2. Aspose.Slides สำหรับ .NET เป็นไลบรารีฟรีหรือไม่?

Aspose.Slides สำหรับ .NET ไม่ใช่ไลบรารีฟรี คุณสามารถค้นหาข้อมูลราคาและใบอนุญาตได้ที่ [เว็บไซต์](https://purchase-aspose.com/buy).

### 3. ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อได้หรือไม่

ใช่ คุณสามารถรับรุ่นทดลองใช้งาน Aspose.Slides สำหรับ .NET ได้ฟรีจาก [ที่นี่](https://releases-aspose.com/).

### 4. ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร

คุณสามารถขอใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์การทดสอบและการพัฒนาได้จาก [ที่นี่](https://purchase-aspose.com/temporary-license/).

### 5. Aspose.Slides สำหรับ .NET รองรับรูปแบบ PowerPoint ล่าสุดหรือไม่

ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบ PowerPoint มากมาย รวมถึงเวอร์ชันล่าสุดด้วย คุณสามารถดูรายละเอียดเพิ่มเติมได้ในเอกสารประกอบ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}