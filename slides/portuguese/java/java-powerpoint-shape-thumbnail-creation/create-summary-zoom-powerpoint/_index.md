---
title: Criar resumo Zoom no PowerPoint
linktitle: Criar resumo Zoom no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar um zoom resumido no PowerPoint usando Aspose.Slides para Java com este tutorial passo a passo abrangente.
weight: 16
url: /pt/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar resumo Zoom no PowerPoint

## Introdução
Bem-vindo ao nosso tutorial abrangente sobre como criar um zoom de resumo no PowerPoint usando Aspose.Slides para Java. Se você deseja adicionar um elemento dinâmico e interativo às suas apresentações, o Summary Zoom é um recurso fantástico. Ele permite que você crie um único slide que pode ampliar diferentes seções da sua apresentação, oferecendo uma experiência mais envolvente e navegável para o seu público.
Neste guia passo a passo, orientaremos você durante todo o processo, desde a configuração do seu ambiente de desenvolvimento até a criação e personalização de um quadro de Zoom de resumo. Quer você seja um desenvolvedor Java experiente ou esteja apenas começando, você achará este guia fácil de seguir e repleto de informações valiosas.
## Pré-requisitos
Antes de mergulhar no código, vamos ter certeza de que você tem tudo o que precisa para começar:
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em sua máquina. Você pode baixá-lo no[Site da Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides para Java: Baixe a biblioteca do[Página de lançamentos do Aspose](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Use um IDE como IntelliJ IDEA, Eclipse ou NetBeans para uma experiência de desenvolvimento mais integrada.
4. Conhecimento básico de Java: A familiaridade com os conceitos de programação Java o ajudará a compreender e implementar as etapas deste guia.
## Importar pacotes
Antes de começarmos, você precisa importar os pacotes necessários. Certifique-se de incluir Aspose.Slides for Java nas dependências do seu projeto.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## Etapa 1: configure seu projeto
Primeiro, certifique-se de que seu ambiente de desenvolvimento esteja configurado corretamente. Siga estas etapas para configurar seu projeto:
### Crie um novo projeto
1. Abra seu IDE.
2. Crie um novo projeto Java.
3.  Adicione a biblioteca Aspose.Slides para Java ao caminho de construção do seu projeto. Você pode baixar o arquivo JAR do[Página de lançamentos do Aspose](https://releases.aspose.com/slides/java/) e inclua-o em seu projeto.
### Inicialize a apresentação
A seguir, inicialize um novo objeto de apresentação onde você adicionará seus slides e seções.
```java
Presentation pres = new Presentation();
```
## Etapa 2: adicionar slides e seções
Nesta etapa, adicionaremos slides à apresentação e os organizaremos em seções. Esta organização é crucial para a criação de um Zoom de Resumo.
### Adicionar um novo slide e seção
1. Adicionar um slide vazio: adicione um novo slide à apresentação.
2. Personalize o plano de fundo do slide: defina uma cor de preenchimento sólida para o plano de fundo do slide.
3. Adicionar uma seção: agrupe o slide em uma seção.
Aqui está o código para conseguir isso:
```java
// Adicione o primeiro slide
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// Adicione a primeira seção
pres.getSections().addSection("Section 1", slide);
```
### Repita para seções adicionais
Repita o processo para adicionar mais slides e seções:
```java
// Adicione o segundo slide e seção
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// Adicione o terceiro slide e seção
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// Adicione o quarto slide e seção
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## Etapa 3: crie o quadro de zoom de resumo
Agora, criaremos um quadro Summary Zoom no primeiro slide. Este quadro atuará como um elemento interativo que permite aos usuários ampliar diferentes seções.

1. Localize o primeiro slide: recupere o primeiro slide onde você adicionará o quadro de zoom de resumo.
2.  Adicione o quadro de zoom de resumo: use o`addSummaryZoomFrame` método para adicionar o quadro.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## Etapa 4: salve a apresentação
Por fim, salve a apresentação no local desejado. Esta etapa garante que todas as suas alterações sejam gravadas em um arquivo.
### Salve o arquivo
1. Defina o Caminho de Saída: Especifique o caminho onde a apresentação será salva.
2.  Salve a apresentação: use o`save` método para salvar o arquivo no formato PPTX.
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### Descarte o objeto de apresentação
Descarte o objeto de apresentação para liberar quaisquer recursos que ele esteja usando:
```java
if (pres != null) pres.dispose();
```
## Conclusão
 Parabéns! Você criou com sucesso um Zoom de resumo no PowerPoint usando Aspose.Slides para Java. Este recurso aprimora suas apresentações, tornando-as mais interativas e envolventes. Seguindo este guia, você agora terá as habilidades necessárias para implementar esse recurso em seus próprios projetos. Lembre-se de explorar o[Documentação Aspose.Slides para Java](https://reference.aspose.com/slides/java/)para recursos mais avançados e opções de personalização.
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar e manipular apresentações do PowerPoint programaticamente usando Java.
### Posso usar Aspose.Slides for Java para criar outros tipos de conteúdo no PowerPoint?
Sim, Aspose.Slides for Java oferece suporte a uma ampla gama de recursos, incluindo criação de slides, adição de formas, gráficos, tabelas e muito mais.
### Existe um teste gratuito disponível para Aspose.Slides for Java?
Sim, você pode baixar uma avaliação gratuita do Aspose.Slides for Java no site[local na rede Internet](https://releases.aspose.com/).
### Como obtenho uma licença temporária do Aspose.Slides for Java?
 Você pode obter uma licença temporária do[Aspose página de compra](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar mais exemplos e suporte para Aspose.Slides for Java?
 Você pode encontrar mais exemplos e buscar apoio no site[Fórum de suporte Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
