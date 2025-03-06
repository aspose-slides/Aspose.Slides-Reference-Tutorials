---
title: Definir número de marcadores personalizados em Java PowerPoint
linktitle: Definir número de marcadores personalizados em Java PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir números de marcadores personalizados em Java PowerPoint com Aspose.Slides, melhorando a clareza e a estrutura da apresentação de forma programática.
weight: 15
url: /pt/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
Na era digital de hoje, a criação de apresentações dinâmicas é crucial para comunicar ideias e dados de forma eficaz. Aspose.Slides for Java fornece um kit de ferramentas poderoso para manipular apresentações do PowerPoint de forma programática, oferecendo recursos abrangentes para aprimorar seu processo de construção de apresentações. Este artigo se aprofunda na configuração de números de marcadores personalizados em apresentações Java PowerPoint usando Aspose.Slides. Quer você seja um desenvolvedor experiente ou um novato, este tutorial irá guiá-lo passo a passo através do processo, garantindo que você possa aproveitar esse recurso de forma eficiente.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos configurados em seu ambiente de desenvolvimento:
- Kit de desenvolvimento Java (JDK) instalado
- Ambiente de desenvolvimento integrado (IDE), como IntelliJ IDEA ou Eclipse
-  Aspose.Slides para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/)
- Compreensão básica da linguagem de programação Java e conceitos orientados a objetos

## Importar pacotes
Primeiramente, importe as classes Aspose.Slides necessárias e outras bibliotecas padrão Java:
```java
import com.aspose.slides.*;
```
## Etapa 1: crie um objeto de apresentação
Comece criando uma nova apresentação do PowerPoint usando Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Etapa 2: adicionar uma forma automática com texto
Insira uma AutoForma (Retângulo) no slide e acesse seu quadro de texto.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Etapa 3: remover o parágrafo padrão
Remova o parágrafo padrão existente do quadro de texto.
```java
textFrame.getParagraphs().removeAt(0);
```
## Etapa 4: adicionar marcadores numerados
Adicione parágrafos com marcadores numerados personalizados começando com números específicos.
```java
// Parágrafo de exemplo com marcador começando em 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Parágrafo de exemplo com marcador começando em 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Parágrafo de exemplo com marcador começando em 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Etapa 5: salve a apresentação
Por fim, salve a apresentação modificada no local desejado.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Conclusão
Concluindo, Aspose.Slides for Java simplifica o processo de configuração de números de marcadores personalizados em apresentações do PowerPoint de forma programática. Seguindo as etapas descritas neste tutorial, você pode melhorar a clareza visual e a estrutura de suas apresentações de forma eficiente.
## Perguntas frequentes
### Posso personalizar ainda mais a aparência dos marcadores?
Sim, Aspose.Slides oferece amplas opções para personalizar o tipo, tamanho, cor do marcador e muito mais.
### O Aspose.Slides é compatível com todas as versões do PowerPoint?
Aspose.Slides suporta formatos PowerPoint de 97-2003 até as versões mais recentes.
### Como posso obter suporte técnico para Aspose.Slides?
 Visita[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) para assistência técnica.
### Posso experimentar o Aspose.Slides antes de comprar?
 Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### Onde posso comprar o Aspose.Slides?
 Você pode comprar Aspose.Slides em[aqui](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
