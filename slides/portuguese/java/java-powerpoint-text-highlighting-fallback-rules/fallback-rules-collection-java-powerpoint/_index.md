---
title: Coleção de regras substitutas em Java PowerPoint
linktitle: Coleção de regras substitutas em Java PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como gerenciar regras de substituição de fontes em apresentações do PowerPoint usando Aspose.Slides para Java. Melhore a compatibilidade entre dispositivos sem esforço.
weight: 11
url: /pt/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
Neste tutorial, nos aprofundaremos em como gerenciar regras de fallback de fontes usando Aspose.Slides para Java. Os substitutos de fontes são cruciais para garantir que suas apresentações sejam exibidas corretamente em diferentes ambientes, especialmente quando fontes específicas não estão disponíveis. Iremos orientá-lo na importação dos pacotes necessários, na configuração do ambiente e na implementação de regras de fallback passo a passo.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
- Conhecimento básico de programação Java.
- JDK (Java Development Kit) instalado em seu sistema.
-  Biblioteca Aspose.Slides para Java baixada e configurada. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).
- IDE (Ambiente de Desenvolvimento Integrado), como IntelliJ IDEA ou Eclipse instalado.
## Importar pacotes
Comece importando os pacotes necessários para o seu projeto Java:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## Configurando um objeto de apresentação
Primeiro, inicialize um objeto Presentation onde você definirá suas regras de fallback de fonte.
```java
Presentation presentation = new Presentation();
```
## Criando uma coleção de regras substitutas de fontes
Em seguida, crie um objeto FontFallBackRulesCollection para gerenciar suas regras de fallback de fontes personalizadas.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## Adicionando regras de substituição de fontes
Agora, adicione regras específicas de substituição de fontes usando intervalos Unicode e nomes de fontes alternativas.
### Etapa 1: definir intervalo e fonte Unicode
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
Esta linha define uma regra de fallback para o intervalo Unicode 0x0B80 a 0x0BFF para usar a fonte "Vijaya" se a fonte primária não estiver disponível.
### Etapa 2: definir outro intervalo e fonte Unicode
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
Aqui, a regra especifica que o intervalo Unicode 0x3040 a 0x309F deve recorrer às fontes "MS Mincho" ou "MS Gothic".
## Aplicando regras de substituição de fonte à apresentação
Aplique a coleção de regras de fallback de fontes criada ao FontsManager da apresentação.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## Descartar objeto de apresentação
Por fim, garanta o gerenciamento adequado de recursos descartando o objeto Presentation em um bloco try-finally.
```java
try {
    // Use o objeto de apresentação conforme necessário
} finally {
    if (presentation != null) presentation.dispose();
}
```
## Conclusão
Neste tutorial, exploramos como gerenciar regras de fallback de fonte usando Aspose.Slides para Java. Compreender e implementar substitutos de fontes garante uma renderização de fontes consistente e confiável em diferentes plataformas e ambientes. Seguindo essas etapas, você pode personalizar o comportamento de fallback da fonte para atender perfeitamente aos requisitos específicos de apresentação.

## Perguntas frequentes
### Quais são as regras de substituição de fontes?
As regras de substituição de fontes definem fontes alternativas a serem usadas quando a fonte especificada não estiver disponível, garantindo a exibição consistente do texto.
### Como faço o download do Aspose.Slides para Java?
 Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/slides/java/).
### Posso experimentar o Aspose.Slides para Java antes de comprar?
 Sim, você pode obter uma versão de avaliação gratuita[aqui](https://releases.aspose.com/).
### Onde posso encontrar documentação para Aspose.Slides for Java?
 Documentação detalhada está disponível[aqui](https://reference.aspose.com/slides/java/).
### Como obtenho suporte para Aspose.Slides para Java?
Para suporte, visite o fórum Aspose.Slides[aqui](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
