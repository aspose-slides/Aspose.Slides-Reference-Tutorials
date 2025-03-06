---
title: Aplicar efeitos de sombra externa em Java PowerPoint
linktitle: Aplicar efeitos de sombra externa em Java PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como aplicar facilmente efeitos de sombra externa em apresentações Java PowerPoint usando Aspose.Slides com nosso guia passo a passo detalhado.
weight: 11
url: /pt/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
A criação de apresentações envolventes geralmente requer a adição de vários efeitos para melhorar o apelo visual dos seus slides. Um desses efeitos é a sombra externa, que pode destacar seus elementos e adicionar profundidade ao seu conteúdo. Neste tutorial, percorreremos o processo de aplicação de efeitos de sombra externa a formas em uma apresentação do PowerPoint usando Aspose.Slides para Java.
## Pré-requisitos
Antes de mergulharmos no guia passo a passo, vamos garantir que você tenha tudo o que precisa:
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em sua máquina. Você pode baixá-lo em[Site da Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Biblioteca Aspose.Slides para Java: Baixe a versão mais recente em[Aspose.Slides para Java](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Use um IDE como IntelliJ IDEA ou Eclipse para escrever e executar seu código Java.
4.  Uma licença Suponha válida: você pode comprar uma licença de[Aspose](https://purchase.aspose.com/buy) ou obter um[licença temporária](https://purchase.aspose.com/temporary-license/) para avaliação.
## Importar pacotes
Primeiro, você precisará importar os pacotes necessários para Aspose.Slides. Isso prepara o terreno para a utilização das poderosas funcionalidades fornecidas pela biblioteca.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Vamos dividir o processo de aplicação de efeitos de sombra externa em etapas gerenciáveis:
## Etapa 1: configurar o diretório do projeto
Antes de começar a escrever seu código, você precisa configurar o diretório do projeto onde seus arquivos PowerPoint serão armazenados e acessados.
Certifique-se de que o diretório do seu projeto exista. Caso contrário, crie-o usando o seguinte código:
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Etapa 2: inicializar a apresentação
Agora precisamos inicializar a apresentação onde adicionaremos nossas formas e efeitos.

 Crie uma nova instância do`Presentation` class para começar a trabalhar com um novo arquivo PowerPoint.
```java
// Instanciar uma classe PPTX
Presentation pres = new Presentation();
```
## Etapa 3: adicionar um slide e uma forma
Em seguida, adicione um slide à sua apresentação e, em seguida, adicione uma forma à qual aplicará o efeito de sombra.
### Obtenha referência ao slide
Recuperar uma referência ao primeiro slide da apresentação.
```java
// Obtenha referência do slide
ISlide sld = pres.getSlides().get_Item(0);
```
### Adicionar uma AutoForma
Adicione uma AutoForma retangular ao slide nas coordenadas especificadas.
```java
// Adicione uma AutoForma do tipo Retângulo
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Etapa 4: personalize a forma
Adicione texto à sua forma e ajuste as configurações de preenchimento para tornar o efeito de sombra mais visível.
### Adicione TextFrame à forma
Insira o texto na forma de retângulo.
```java
// Adicione TextFrame ao retângulo
aShp.addTextFrame("Aspose TextBox");
```
### Desativar preenchimento de forma
Desative o preenchimento da forma para enfatizar a sombra do texto.
```java
// Desative o preenchimento de forma caso queiramos obter sombra do texto
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Etapa 5: aplicar efeito de sombra externa
Agora é hora de aplicar o efeito de sombra externa à forma.
### Ativar efeito de sombra externa
Ative o efeito de sombra externa para a forma.
```java
// Adicione sombra externa e defina todos os parâmetros necessários
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Configurar parâmetros de sombra
Defina várias propriedades da sombra, como raio de desfoque, direção, distância, alinhamento e cor.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Etapa 6: salve a apresentação
Por fim, salve a apresentação em disco.
```java
//Grave a apresentação no disco
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Passo 7: Descarte de Recursos
Certifique-se de liberar recursos descartando o objeto de apresentação.
```java
// Limpar recursos
if (pres != null) pres.dispose();
```
## Conclusão
E aí está! Você aplicou com êxito um efeito de sombra externa a uma forma em uma apresentação do PowerPoint usando Aspose.Slides para Java. Esse efeito pode melhorar significativamente o apelo visual dos seus slides, destacando o seu conteúdo.
 Se você tiver algum problema ou precisar de mais assistência, não hesite em verificar o[Documentação do Aspose.Slides](https://reference.aspose.com/slides/java/) ou visite o[Fórum de suporte](https://forum.aspose.com/c/slides/11). Boa codificação!
## Perguntas frequentes
### O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma biblioteca poderosa que permite criar, manipular e converter apresentações do PowerPoint em aplicativos Java.
### Como posso obter uma avaliação gratuita do Aspose.Slides para Java?
 Você pode baixar uma versão de teste gratuita no site[Aspor site](https://releases.aspose.com/).
### Posso usar Aspose.Slides for Java com qualquer IDE?
Sim, você pode usar Aspose.Slides for Java com qualquer IDE Java como IntelliJ IDEA, Eclipse ou NetBeans.
### Como obtenho uma licença temporária do Aspose.Slides?
 Você pode obter uma licença temporária do[Aspor site](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar mais exemplos e documentação para Aspose.Slides?
 Você pode encontrar mais exemplos e documentação detalhada no[Página de documentação do Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
