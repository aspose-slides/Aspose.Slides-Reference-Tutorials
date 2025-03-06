---
title: Aggiungi commenti dei genitori alla diapositiva utilizzando Aspose.Slides
linktitle: Aggiungi commenti dei genitori alla diapositiva
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere commenti interattivi e risposte alle tue presentazioni PowerPoint utilizzando Aspose.Slides per .NET. Migliorare il coinvolgimento e la collaborazione.
weight: 12
url: /it/net/slide-comments-manipulation/add-parent-comments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Stai cercando di migliorare le tue presentazioni PowerPoint con funzionalità interattive? Aspose.Slides per .NET ti consente di incorporare commenti e risposte, creando un'esperienza dinamica e coinvolgente per il tuo pubblico. In questo tutorial passo passo, ti mostreremo come aggiungere commenti principali alle diapositive utilizzando Aspose.Slides per .NET. Immergiamoci ed esploriamo questa entusiasmante funzionalità.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Slides per .NET: assicurati di avere Aspose.Slides per .NET installato. Puoi scaricarlo[Qui](https://releases.aspose.com/slides/net/).

2. Visual Studio: avrai bisogno di Visual Studio per creare ed eseguire la tua applicazione .NET.

3. Conoscenza di base di C#: questo tutorial presuppone che tu abbia una conoscenza di base della programmazione C#.

Ora che abbiamo coperto i prerequisiti, procediamo con l'importazione degli spazi dei nomi necessari.

## Importazione di spazi dei nomi

Innanzitutto, dovrai importare gli spazi dei nomi rilevanti nel tuo progetto. Questi spazi dei nomi forniscono le classi e i metodi necessari per lavorare con Aspose.Slides per .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Una volta impostati i prerequisiti e gli spazi dei nomi, suddividiamo il processo in più passaggi per aggiungere commenti principali a una diapositiva.

## Passaggio 1: crea una presentazione

Per iniziare, è necessario creare una nuova presentazione utilizzando Aspose.Slides per .NET. Questa presentazione sarà la tela su cui aggiungerai i tuoi commenti.

```csharp
// Il percorso della directory di output.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Il tuo codice per aggiungere commenti andrà qui.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 Nel codice sopra, sostituisci`"Output Path"` con il percorso desiderato per la presentazione di output.

## Passaggio 2: aggiungere gli autori dei commenti

Prima di aggiungere commenti, è necessario definire gli autori di questi commenti. In questo esempio abbiamo due autori, "Autore_1" e "Autore_2", ciascuno rappresentato da un'istanza di`ICommentAuthor`.

```csharp
// Aggiungi un commento
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Aggiungi risposta al commento1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

In questo passaggio creiamo due autori di commenti e aggiungiamo il commento iniziale e una risposta al commento.

## Passaggio 3: aggiungi altre risposte

Per creare una struttura gerarchica di commenti, puoi aggiungere più risposte ai commenti esistenti. Qui aggiungiamo una seconda risposta a "commento1".

```csharp
// Aggiungi risposta al commento1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Ciò stabilisce un flusso di conversazione all'interno della presentazione.

## Passaggio 4: aggiungi risposte nidificate

I commenti possono avere anche risposte nidificate. Per dimostrarlo, aggiungiamo una risposta a "risposta 2 per commento 1", creando una sotto-risposta.

```csharp
// Aggiungi risposta alla risposta
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Questo passaggio evidenzia la versatilità di Aspose.Slides per .NET nella gestione delle gerarchie dei commenti.

## Passaggio 5: ulteriori commenti e risposte

Puoi continuare ad aggiungere altri commenti e risposte secondo necessità. In questo esempio, aggiungiamo altri due commenti e una risposta a uno di essi.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Questo passaggio dimostra come creare contenuti accattivanti e interattivi per le tue presentazioni.

## Passaggio 6: visualizzare la gerarchia

Per visualizzare la gerarchia dei commenti, puoi visualizzarla sulla console. Questo passaggio è facoltativo ma può essere utile per eseguire il debug e comprendere la struttura.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## Passaggio 7: rimuovi i commenti

In alcuni casi, potrebbe essere necessario rimuovere i commenti e le relative risposte. Lo snippet di codice seguente mostra come rimuovere "commento1" e tutte le relative risposte.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Questo passaggio è utile per gestire e aggiornare il contenuto della presentazione.

Con questi passaggi, puoi creare presentazioni con commenti interattivi e risposte utilizzando Aspose.Slides per .NET. Che tu stia cercando di coinvolgere il tuo pubblico o di collaborare con i membri del team, questa funzionalità offre un'ampia gamma di possibilità.

## Conclusione

Aspose.Slides per .NET fornisce un potente set di strumenti per migliorare le tue presentazioni PowerPoint. Con la possibilità di aggiungere commenti e risposte, puoi creare contenuti dinamici e interattivi che affascinano il tuo pubblico. Questa guida passo passo ti ha mostrato come aggiungere commenti principali alle diapositive, stabilire gerarchie e persino rimuovere commenti quando necessario. Seguendo questi passaggi ed esplorando la documentazione di Aspose.Slides[Qui](https://reference.aspose.com/slides/net/), puoi portare le tue presentazioni al livello successivo.

## Domande frequenti

### Posso aggiungere commenti a diapositive specifiche all'interno della mia presentazione?
Sì, puoi aggiungere commenti a qualsiasi diapositiva della presentazione specificando la diapositiva di destinazione durante la creazione di un commento.

### È possibile personalizzare l'aspetto dei commenti nella presentazione?
Aspose.Slides per .NET ti consente di personalizzare l'aspetto dei commenti, incluso il testo, le informazioni sull'autore e la posizione sulla diapositiva.

### Posso esportare i commenti e le risposte in un file separato?
Sì, puoi esportare commenti e risposte in un file di presentazione separato, come dimostrato nel passaggio 7.

### Aspose.Slides per .NET è compatibile con le ultime versioni di PowerPoint?
Aspose.Slides per .NET è progettato per funzionare con un'ampia gamma di versioni di PowerPoint, garantendo la compatibilità con le ultime versioni.

### Sono disponibili opzioni di licenza per Aspose.Slides per .NET?
 Sì, puoi esplorare le opzioni di licenza, comprese le licenze temporanee, sul sito Web Aspose[Qui](https://purchase.aspose.com/buy) oppure prova la prova gratuita[Qui](https://releases.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
