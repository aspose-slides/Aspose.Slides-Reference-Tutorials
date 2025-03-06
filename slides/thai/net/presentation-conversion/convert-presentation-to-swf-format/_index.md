---
title: แปลงการนำเสนอเป็นรูปแบบ SWF
linktitle: แปลงการนำเสนอเป็นรูปแบบ SWF
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ SWF โดยใช้ Aspose.Slides สำหรับ .NET สร้างเนื้อหาแบบไดนามิกได้อย่างง่ายดาย!
weight: 28
url: /th/net/presentation-conversion/convert-presentation-to-swf-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


ในยุคดิจิทัลปัจจุบัน การนำเสนอมัลติมีเดียเป็นวิธีการสื่อสารที่ทรงพลัง บางครั้ง คุณอาจต้องการแบ่งปันงานนำเสนอของคุณในรูปแบบแบบไดนามิกมากขึ้น เช่น การแปลงเป็นรูปแบบ SWF (Shockwave Flash) คู่มือนี้จะแนะนำคุณตลอดกระบวนการแปลงงานนำเสนอเป็นรูปแบบ SWF โดยใช้ Aspose.Slides สำหรับ .NET

## สิ่งที่คุณต้องการ

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

-  Aspose.Slides สำหรับ .NET: หากคุณยังไม่มี คุณก็สามารถทำได้[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/slides/net/).

- ไฟล์การนำเสนอ: คุณจะต้องมีไฟล์งานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็นรูปแบบ SWF

## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมของคุณ

ในการเริ่มต้น ให้สร้างไดเร็กทอรีสำหรับโปรเจ็กต์ของคุณ เรียกมันว่า "ไดเรกทอรีโครงการของคุณ" ภายในไดเร็กทอรีนี้ คุณจะต้องวางซอร์สโค้ดต่อไปนี้:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // การบันทึกหน้าการนำเสนอและบันทึกย่อ
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

 ให้แน่ใจว่าคุณเปลี่ยน`"Your Document Directory"` และ`"Your Output Directory"` พร้อมเส้นทางจริงที่ไฟล์งานนำเสนอของคุณอยู่ และตำแหน่งที่คุณต้องการบันทึกไฟล์ SWF

## ขั้นตอนที่ 2: กำลังโหลดการนำเสนอ

ในขั้นตอนนี้ เราโหลดงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides:

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

 แทนที่`"HelloWorld.pptx"` พร้อมชื่อไฟล์การนำเสนอของคุณ

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการแปลง SWF

เรากำหนดค่าตัวเลือกการแปลง SWF เพื่อปรับแต่งเอาต์พุต:

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

คุณสามารถปรับตัวเลือกเหล่านี้ได้ตามความต้องการของคุณ

## ขั้นตอนที่ 4: บันทึกเป็น SWF

ตอนนี้ เราบันทึกงานนำเสนอเป็นไฟล์ SWF:

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

บรรทัดนี้จะบันทึกงานนำเสนอหลักเป็นไฟล์ SWF

## ขั้นตอนที่ 5: บันทึกด้วยบันทึกย่อ

หากคุณต้องการรวมบันทึกย่อ ให้ใช้รหัสนี้:

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

รหัสนี้จะบันทึกงานนำเสนอพร้อมบันทึกย่อในรูปแบบ SWF

## บทสรุป

ยินดีด้วย! คุณได้แปลงงานนำเสนอ PowerPoint เป็นรูปแบบ SWF ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET สิ่งนี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการแชร์งานนำเสนอของคุณทางออนไลน์หรือฝังลงในหน้าเว็บ

 สำหรับข้อมูลเพิ่มเติมและเอกสารโดยละเอียด คุณสามารถดูได้ที่[Aspose.Slides สำหรับการอ้างอิง .NET](https://reference.aspose.com/slides/net/).

## คำถามที่พบบ่อย

### รูปแบบ SWF คืออะไร?
SWF (Shockwave Flash) เป็นรูปแบบมัลติมีเดียที่ใช้สำหรับภาพเคลื่อนไหว เกม และเนื้อหาเชิงโต้ตอบบนเว็บ

### Aspose.Slides สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 Aspose.Slides สำหรับ .NET ให้ทดลองใช้ฟรี แต่คุณอาจต้องซื้อใบอนุญาตเพื่อให้มีฟังก์ชันการทำงานเต็มรูปแบบ คุณสามารถตรวจสอบราคาและรายละเอียดใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).

### ฉันสามารถลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อใบอนุญาตได้หรือไม่
 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรี[ที่นี่](https://releases.aspose.com/).

### ฉันจำเป็นต้องมีทักษะการเขียนโปรแกรมเพื่อใช้ Aspose.Slides สำหรับ .NET หรือไม่
ใช่ คุณควรมีความรู้เกี่ยวกับการเขียนโปรแกรม C# เพื่อใช้ Aspose.Slides อย่างมีประสิทธิภาพ

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 หากคุณมีคำถามหรือต้องการความช่วยเหลือ คุณสามารถไปที่[Aspose.Slides สำหรับฟอรัม .NET](https://forum.aspose.com/)สำหรับการสนับสนุนและความช่วยเหลือจากชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
