---
title: Alterar o layout SmartArt no PowerPoint com Java
linktitle: Alterar o layout SmartArt no PowerPoint com Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como manipular layouts SmartArt em apresentações do PowerPoint usando Java com Aspose.Slides for Java.
weight: 19
url: /pt/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alterar o layout SmartArt no PowerPoint com Java

## Introdução
Neste tutorial, exploraremos como manipular layouts SmartArt em apresentações do PowerPoint usando Java. SmartArt é um recurso poderoso do PowerPoint que permite aos usuários criar gráficos visualmente atraentes para diversos fins, como ilustrar processos, hierarquias, relacionamentos e muito mais.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter o seguinte:
1. Ambiente de desenvolvimento Java: certifique-se de ter o Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Slides: Baixe e instale a biblioteca Aspose.Slides para Java em[aqui](https://releases.aspose.com/slides/java/).
3. Compreensão básica de Java: A familiaridade com os fundamentos da linguagem de programação Java será útil.
4. Ambiente de Desenvolvimento Integrado (IDE): Escolha um IDE de sua preferência, como Eclipse ou IntelliJ IDEA.

## Importar pacotes
Para começar, importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Etapa 1: Configure seu ambiente de projeto Java
Certifique-se de que seu projeto Java esteja configurado corretamente no IDE escolhido. Crie um novo projeto Java e inclua a biblioteca Aspose.Slides nas dependências do seu projeto.
## Etapa 2: crie uma nova apresentação
Instancie um novo objeto Presentation para criar uma nova apresentação do PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Etapa 3: adicionar gráfico SmartArt
Adicione um gráfico SmartArt à sua apresentação. Especifique a posição e as dimensões do gráfico SmartArt no slide.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Etapa 4: alterar o layout SmartArt
Altere o layout do gráfico SmartArt para o tipo de layout desejado.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Etapa 5: salvar a apresentação
Salve a apresentação modificada em um diretório especificado em seu sistema.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Conclusão
Manipular layouts SmartArt em apresentações do PowerPoint usando Java é um processo simples com Aspose.Slides for Java. Seguindo este tutorial, você pode modificar facilmente os gráficos SmartArt para atender às suas necessidades de apresentação.
## Perguntas frequentes
### Posso personalizar a aparência dos gráficos SmartArt usando Aspose.Slides for Java?
Sim, você pode personalizar vários aspectos dos gráficos SmartArt, como cores, estilos e efeitos.
### O Aspose.Slides é compatível com diferentes versões do PowerPoint?
Aspose.Slides oferece suporte a apresentações em PowerPoint criadas em várias versões do PowerPoint, garantindo compatibilidade entre diferentes plataformas.
### O Aspose.Slides oferece suporte para outras linguagens de programação?
Sim, Aspose.Slides está disponível para várias linguagens de programação, incluindo .NET, Python e JavaScript.
### Posso criar gráficos SmartArt do zero usando Aspose.Slides?
Com certeza, você pode criar gráficos SmartArt programaticamente ou modificar os existentes para atender às suas necessidades.
### Existe um fórum da comunidade onde posso procurar ajuda em relação ao Aspose.Slides?
 Sim, você pode visitar o fórum Aspose.Slides[aqui](https://forum.aspose.com/c/slides/11) para fazer perguntas e interagir com a comunidade.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
