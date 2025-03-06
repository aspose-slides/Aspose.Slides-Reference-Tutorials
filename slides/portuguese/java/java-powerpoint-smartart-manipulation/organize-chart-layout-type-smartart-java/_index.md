---
title: Organize o tipo de layout de gráfico no SmartArt usando Java
linktitle: Organize o tipo de layout de gráfico no SmartArt usando Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Domine a organização de tipos de layout de gráfico em SmartArt usando Java com Aspose.Slides, aprimorando os visuais da apresentação sem esforço.
weight: 13
url: /pt/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
Neste tutorial, percorreremos o processo de organização do tipo de layout de gráfico no SmartArt usando Java, aproveitando especificamente a biblioteca Aspose.Slides. SmartArt em apresentações pode melhorar muito o apelo visual e a clareza de seus dados, tornando essencial dominar sua manipulação.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Slides baixada e configurada. Se ainda não o fez, baixe-o em[aqui](https://releases.aspose.com/slides/java/).
3. Compreensão básica de programação Java.

## Importar pacotes
Primeiramente, importe os pacotes necessários:
```java
import com.aspose.slides.*;
```
Vamos dividir o exemplo fornecido em várias etapas:
## Etapa 1: inicializar o objeto de apresentação
```java
Presentation presentation = new Presentation();
```
Crie um novo objeto de apresentação.
## Etapa 2: adicionar SmartArt ao slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Adicione SmartArt ao slide desejado com dimensões e tipo de layout especificados.
## Etapa 3: definir o layout do organograma
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Defina o tipo de layout do organograma. Neste exemplo, estamos usando o layout Suspenso à Esquerda.
## Etapa 4: salvar a apresentação
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Salve a apresentação com o layout do gráfico organizado.

## Conclusão
Dominar a organização dos tipos de layout de gráfico no SmartArt usando Java permite que você crie apresentações visualmente atraentes com facilidade. Com Aspose.Slides, o processo se torna simplificado e eficiente, permitindo que você se concentre na criação de conteúdo impactante.
## Perguntas frequentes
### O Aspose.Slides é compatível com diferentes ambientes de desenvolvimento Java?
Sim, Aspose.Slides é compatível com diversos ambientes de desenvolvimento Java, garantindo flexibilidade aos desenvolvedores.
### Posso personalizar a aparência dos elementos SmartArt usando Aspose.Slides?
Com certeza, Aspose.Slides oferece amplas opções de personalização para elementos SmartArt, permitindo adaptá-los às suas necessidades específicas.
### O Aspose.Slides oferece documentação abrangente para desenvolvedores?
Sim, os desenvolvedores podem consultar a documentação detalhada fornecida por Aspose.Slides for Java, oferecendo insights sobre suas funcionalidades e uso.
### Existe uma versão de teste disponível para Aspose.Slides?
Sim, você pode acessar uma versão de avaliação gratuita do Aspose.Slides para explorar seus recursos antes de tomar uma decisão de compra.
### Onde posso buscar suporte para dúvidas relacionadas ao Aspose.Slides?
 Para qualquer assistência ou dúvida sobre Aspose.Slides, você pode visitar o fórum de suporte[aqui](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
