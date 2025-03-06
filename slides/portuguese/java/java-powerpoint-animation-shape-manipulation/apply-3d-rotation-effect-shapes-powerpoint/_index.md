---
title: Aplicar efeito de rotação 3D em formas no PowerPoint
linktitle: Aplicar efeito de rotação 3D em formas no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como aplicar efeitos de rotação 3D em formas no PowerPoint usando Aspose.Slides for Java com este tutorial passo a passo abrangente.
weight: 12
url: /pt/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
Você está pronto para levar suas apresentações em PowerPoint para o próximo nível? Adicionar efeitos de rotação 3D pode tornar seus slides mais dinâmicos e envolventes. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este tutorial passo a passo mostrará como aplicar efeitos de rotação 3D a formas no PowerPoint usando Aspose.Slides para Java. Vamos mergulhar de cabeça!
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte em vigor:
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixá-lo no[Site da Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides para Java: Baixe a versão mais recente do Aspose.Slides para Java em[Link para Download](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Use um IDE como IntelliJ IDEA ou Eclipse para codificação.
4.  Uma licença válida: Se você não tiver uma licença, poderá obter uma[licença temporária](https://purchase.aspose.com/temporary-license/) para experimentar os recursos.
## Importar pacotes
Primeiro, vamos importar os pacotes necessários para o seu projeto Java. Essas importações irão ajudá-lo a lidar com apresentações e formas com Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Etapa 1: configure seu projeto
Antes de mergulhar no código, configure o ambiente do seu projeto. Certifique-se de ter adicionado Aspose.Slides for Java às dependências do seu projeto.
Adicione Aspose.Slides ao seu projeto:
1.  Baixe os arquivos JAR Aspose.Slides do[página de download](https://releases.aspose.com/slides/java/).
2. Adicione esses arquivos JAR ao caminho de construção do seu projeto.
## Etapa 2: crie uma nova apresentação em PowerPoint
Nesta etapa, criaremos uma nova apresentação em PowerPoint.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie uma instância da classe Presentation
Presentation pres = new Presentation();
```
Este trecho de código inicializa um novo objeto de apresentação onde adicionaremos nossas formas.
## Etapa 3: adicionar uma forma retangular
A seguir, vamos adicionar uma forma retangular ao primeiro slide.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Este código adiciona uma forma de retângulo na posição e tamanho especificados no primeiro slide.
## Etapa 4: aplicar rotação 3D ao retângulo
Agora, vamos aplicar um efeito de rotação 3D à forma retangular.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Aqui, definimos a profundidade, os ângulos de rotação da câmera, o tipo de câmera e o tipo de iluminação para dar ao nosso retângulo uma aparência 3D.
## Etapa 5: adicionar um formato de linha
Vamos adicionar outra forma, desta vez uma linha, ao slide.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Este código coloca uma forma de linha no slide.
## Etapa 6: aplicar rotação 3D à linha
Finalmente, aplicaremos um efeito de rotação 3D ao formato da linha.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Semelhante ao retângulo, definimos as propriedades 3D para o formato da linha.
## Etapa 7: salve a apresentação
Após adicionar e configurar suas formas, salve a apresentação.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Este código salva sua apresentação com o nome de arquivo especificado no formato desejado.
## Conclusão
 Parabéns! Você aplicou com êxito efeitos de rotação 3D a formas em uma apresentação do PowerPoint usando Aspose.Slides para Java. Seguindo essas etapas, você pode criar apresentações dinâmicas e visualmente atraentes. Para maior personalização e recursos mais avançados, consulte o[Documentação do Aspose.Slides](https://reference.aspose.com/slides/java/).
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma API poderosa para criar, modificar e manipular apresentações do PowerPoint de forma programática.
### Posso experimentar o Aspose.Slides para Java gratuitamente?
 Sim, você pode obter um[teste grátis](https://releases.aspose.com/) ou um[licença temporária](https://purchase.aspose.com/temporary-license/) para testar os recursos.
### A quais tipos de formas posso adicionar efeitos 3D no Aspose.Slides?
Você pode adicionar efeitos 3D a várias formas, como retângulos, linhas, elipses e formas personalizadas.
### Como obtenho suporte para Aspose.Slides para Java?
 Você pode visitar o[Fórum de suporte](https://forum.aspose.com/c/slides/11) para assistência e para discutir quaisquer questões.
### Posso usar Aspose.Slides for Java em projetos comerciais?
 Sim, mas você precisa comprar uma licença. Você pode comprar um no[página de compra](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
