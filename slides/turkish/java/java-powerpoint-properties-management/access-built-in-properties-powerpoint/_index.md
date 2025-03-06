---
title: PowerPoint'te Yerleşik Özelliklere Erişin
linktitle: PowerPoint'te Yerleşik Özelliklere Erişin
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint'teki yerleşik özelliklere nasıl erişeceğinizi öğrenin. Bu eğitim, yazarın, oluşturulma tarihinin ve daha fazlasının alınması konusunda size yol gösterir.
weight: 10
url: /tr/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki yerleşik özelliklere nasıl erişilebileceğini keşfedeceğiz. Aspose.Slides, Java geliştiricilerinin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan, özellikleri okuma ve değiştirme gibi görevleri sorunsuz bir şekilde gerçekleştirmesine olanak tanıyan güçlü bir kitaplıktır.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java'yı şu adresten indirip yükleyin:[bu bağlantı](https://releases.aspose.com/slides/java/).

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize aktarmanız gerekir. Java dosyanızın başına aşağıdaki import ifadesini ekleyin:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Adım 1: Sunum Nesnesini Ayarlayın
Çalışmak istediğiniz PowerPoint sunumunu temsil edecek şekilde Sunum nesnesini ayarlayarak başlayın. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
```java
// Sunum dosyasını içeren dizinin yolu
String dataDir = "path_to_your_presentation_directory/";
// Sunum sınıfını somutlaştırın
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Adım 2: Belge Özelliklerine Erişin
Sunum nesnesini ayarladıktan sonra, IDocumentProperties arayüzünü kullanarak sunumun yerleşik özelliklerine erişebilirsiniz. Çeşitli özellikleri şu şekilde alabilirsiniz:
### Kategori
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Şu anki durum
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Oluşturulma tarihi
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Yazar
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Tanım
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Anahtar Kelimeler
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### En son şu kişi tarafından düzenlenmiştir
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Süpervizör
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Değiştirilme Tarihi
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Sunum Formatı
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Son Basım Tarihi
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Yapımcılar Arasında Paylaşılan
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Ders
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Başlık
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Çözüm
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki yerleşik özelliklere nasıl erişeceğimizi öğrendik. Yukarıda özetlenen adımları izleyerek yazar, oluşturulma tarihi ve başlık gibi çeşitli özellikleri programlı olarak kolayca alabilirsiniz.
## SSS'ler
### Aspose.Slides for Java'yı kullanarak bu yerleşik özellikleri değiştirebilir miyim?
Evet, Aspose.Slides'ı kullanarak bu özellikleri değiştirebilirsiniz. IDocumentProperties arayüzü tarafından sağlanan uygun ayarlayıcı yöntemleri kullanmanız yeterlidir.
### Aspose.Slides PowerPoint'in farklı sürümleriyle uyumlu mu?
Aspose.Slides çok çeşitli PowerPoint sürümlerini destekleyerek çeşitli platformlar arasında uyumluluk sağlar.
### Özel özellikleri de alabilir miyim?
Evet, yerleşik özelliklerin yanı sıra Aspose.Slides for Java'yı kullanarak özel özellikleri de alabilir ve değiştirebilirsiniz.
### Aspose.Slides dokümantasyon ve destek sunuyor mu?
 Evet, kapsamlı belgeler bulabilir ve destek forumlarına erişebilirsiniz.[Web sitesi](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
