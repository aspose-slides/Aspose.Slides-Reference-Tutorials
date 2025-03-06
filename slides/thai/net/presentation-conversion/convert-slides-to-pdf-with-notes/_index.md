---
title: แปลงสไลด์เป็น PDF ด้วย Notes
linktitle: แปลงสไลด์เป็น PDF ด้วย Notes
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: แปลงสไลด์การนำเสนอด้วยบันทึกของผู้บรรยายเป็น PDF ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ .NET เก็บรักษาเนื้อหาและบริบทได้อย่างลงตัว
weight: 18
url: /th/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงสไลด์เป็น PDF ด้วย Notes


# เขียนคำแนะนำทีละขั้นตอนเกี่ยวกับการแปลงสไลด์เป็น PDF ด้วย Notes โดยใช้ Aspose.Slides สำหรับ .NET

คุณกำลังมองหาวิธีที่เชื่อถือได้ในการแปลงสไลด์ PowerPoint ของคุณเป็นรูปแบบ PDF ในขณะที่ยังคงรักษาบันทึกย่อที่สำคัญทั้งหมดไว้หรือไม่? ไม่ต้องมองอีกต่อไป! ในบทช่วยสอนที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดกระบวนการใช้ Aspose.Slides สำหรับ .NET เพื่อให้งานนี้สำเร็จทีละขั้นตอน

## 1. บทนำ

การแปลงสไลด์ PowerPoint เป็น PDF พร้อมบันทึกย่ออาจเป็นเครื่องมืออันทรงคุณค่าสำหรับการแชร์งานนำเสนอ ในขณะเดียวกันก็ช่วยรักษาบริบทและความคิดเห็นที่สำคัญเอาไว้ Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับงานนี้

## 2. การตั้งค่าสภาพแวดล้อมของคุณ

ก่อนที่เราจะเจาะลึกกระบวนการเขียนโค้ด ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมที่จำเป็นแล้ว คุณจะต้องการ:

- Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ
- ติดตั้ง Aspose.Slides สำหรับไลบรารี .NET แล้ว
- งานนำเสนอ PowerPoint พร้อมบันทึกย่อที่คุณต้องการแปลง

## 3. กำลังโหลดการนำเสนอ

ในโค้ด C# คุณต้องโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลง ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. การโคลนสไลด์

เพื่อให้แน่ใจว่า PDF ของคุณรวมสไลด์ที่จำเป็นทั้งหมดพร้อมบันทึกย่อ คุณสามารถคัดลอกสไลด์เหล่านั้นจากงานนำเสนอต้นฉบับได้ มีวิธีดังนี้:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. การปรับขนาดสไลด์

คุณอาจต้องการปรับขนาดสไลด์ให้พอดีกับ PDF ของคุณ Aspose.Slides สำหรับ .NET ช่วยให้คุณทำสิ่งนี้ได้อย่างง่ายดาย:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. การกำหนดค่าตัวเลือก PDF

หากต้องการควบคุมวิธีการแสดงบันทึกย่อของคุณในรูปแบบ PDF คุณสามารถกำหนดค่าตัวเลือก PDF ได้:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. บันทึกเป็น PDF พร้อมบันทึกย่อ

สุดท้ายนี้ คุณสามารถบันทึกงานนำเสนอเป็น PDF พร้อมหมายเหตุได้:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. บทสรุป

ยินดีด้วย! คุณได้แปลงสไลด์ PowerPoint ของคุณเป็นรูปแบบ PDF เรียบร้อยแล้วโดยยังคงรักษาบันทึกย่อที่สำคัญทั้งหมดไว้ Aspose.Slides สำหรับ .NET ทำให้กระบวนการนี้ตรงไปตรงมาและมีประสิทธิภาพ

## 9. คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับแต่งเค้าโครงของบันทึกย่อใน PDF ได้หรือไม่

 ใช่ คุณสามารถปรับแต่งเค้าโครงของบันทึกย่อได้โดยใช้`INotesCommentsLayoutingOptions` ในตัวเลือก PDF

### คำถามที่ 2: Aspose.Slides สำหรับ .NET รองรับรูปแบบเอาต์พุตอื่นๆ นอกเหนือจาก PDF หรือไม่

ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบเอาต์พุตที่หลากหลาย รวมถึง PPTX, DOCX และอื่นๆ

### คำถามที่ 3: Aspose.Slides สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่

 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรีที่[https://releases.aspose.com/](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน

 คุณสามารถค้นหาการสนับสนุนและการสนทนาในชุมชนได้ที่[https://forum.aspose.com/](https://forum.aspose.com/).

### คำถามที่ 5: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่

 ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้ที่[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

โดยสรุป เมื่อใช้ Aspose.Slides สำหรับ .NET คุณสามารถแปลงสไลด์ PowerPoint เป็นรูปแบบ PDF ได้อย่างง่ายดายโดยมีบันทึกย่อครบถ้วน เป็นเครื่องมืออันมีค่าสำหรับมืออาชีพที่ต้องการแบ่งปันการนำเสนอกับเพื่อนร่วมงานและลูกค้า ในขณะเดียวกันก็ทำให้มั่นใจว่าบริบทที่สำคัญจะไม่สูญหายไป
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
