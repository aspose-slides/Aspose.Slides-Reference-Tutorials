---
"description": "Domine os tipos de layout de organograma no SmartArt usando Java com Aspose.Slides, aprimorando os visuais da apresentação sem esforço."
"linktitle": "Organizar o tipo de layout do gráfico no SmartArt usando Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Organizar o tipo de layout do gráfico no SmartArt usando Java"
"url": "/pt/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Organizar o tipo de layout do gráfico no SmartArt usando Java

## Introdução
Neste tutorial, abordaremos o processo de organização de layouts de gráficos no SmartArt usando Java, utilizando especificamente a biblioteca Aspose.Slides. O SmartArt em apresentações pode aprimorar significativamente o apelo visual e a clareza dos seus dados, tornando essencial dominar sua manipulação.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado no seu sistema.
2. Biblioteca Aspose.Slides baixada e configurada. Se ainda não o fez, baixe-a em [aqui](https://releases.aspose.com/slides/java/).
3. Noções básicas de programação Java.

## Pacotes de importação
Primeiro, importe os pacotes necessários:
```java
import com.aspose.slides.*;
```
Vamos dividir o exemplo fornecido em várias etapas:
## Etapa 1: Inicializar objeto de apresentação
```java
Presentation presentation = new Presentation();
```
Crie um novo objeto de apresentação.
## Etapa 2: adicionar SmartArt ao slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Adicione SmartArt ao slide desejado com dimensões e tipo de layout especificados.
## Etapa 3: Defina o layout do organograma
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Defina o tipo de layout do organograma. Neste exemplo, estamos usando o layout "Esquerda Suspensa".
## Etapa 4: Salvar apresentação
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Salve a apresentação com o layout do gráfico organizado.

## Conclusão
Dominar a organização de tipos de layout de gráfico no SmartArt usando Java permite que você crie apresentações visualmente envolventes com facilidade. Com o Aspose.Slides, o processo se torna simplificado e eficiente, permitindo que você se concentre na criação de conteúdo impactante.
## Perguntas frequentes
### O Aspose.Slides é compatível com diferentes ambientes de desenvolvimento Java?
Sim, o Aspose.Slides é compatível com vários ambientes de desenvolvimento Java, garantindo flexibilidade para desenvolvedores.
### Posso personalizar a aparência dos elementos SmartArt usando o Aspose.Slides?
Com certeza, o Aspose.Slides oferece amplas opções de personalização para elementos SmartArt, permitindo que você os adapte às suas necessidades específicas.
### O Aspose.Slides oferece documentação abrangente para desenvolvedores?
Sim, os desenvolvedores podem consultar a documentação detalhada fornecida pelo Aspose.Slides para Java, que oferece insights sobre suas funcionalidades e uso.
### Existe uma versão de teste disponível para o Aspose.Slides?
Sim, você pode acessar uma versão de teste gratuita do Aspose.Slides para explorar seus recursos antes de tomar uma decisão de compra.
### Onde posso buscar suporte para dúvidas relacionadas ao Aspose.Slides?
Para qualquer assistência ou dúvidas sobre o Aspose.Slides, você pode visitar o fórum de suporte [aqui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}