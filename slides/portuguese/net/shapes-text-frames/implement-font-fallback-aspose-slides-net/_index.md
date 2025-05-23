---
"date": "2025-04-16"
"description": "Aprenda a implementar regras de fallback de fontes no Aspose.Slides para .NET para garantir que suas apresentações exibam o texto corretamente em diferentes idiomas e scripts."
"title": "Como definir regras de fallback de fonte no Aspose.Slides para .NET - Um guia completo"
"url": "/pt/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como definir regras de fallback de fonte no Aspose.Slides para .NET: um guia completo

## Introdução

Criar apresentações com o Aspose.Slides para .NET às vezes exige o tratamento de caracteres que fontes específicas não suportam, como tâmil ou hiragana japonês. Definir regras de fallback de fontes é essencial para garantir que sua apresentação exiba o texto corretamente em vários idiomas e símbolos.

Neste tutorial, guiaremos você pela implementação de regras de fallback de fontes usando o Aspose.Slides para .NET. Da instalação às aplicações práticas, este guia garante que suas apresentações mantenham a consistência visual, independentemente do conteúdo.

**O que você aprenderá:**
- Defina intervalos Unicode para diferentes scripts.
- Configure fontes alternativas para caracteres não suportados.
- Aplique fallback de fonte em cenários de apresentação do mundo real.
- Dicas para otimizar o desempenho e a integração com outros sistemas.

Vamos começar revisando os pré-requisitos.

## Pré-requisitos

Antes de começar, certifique-se de ter:

- **Aspose.Slides para .NET** biblioteca instalada. Instale usando qualquer um destes métodos:
  - **.NET CLI**: Correr `dotnet add package Aspose.Slides`
  - **Gerenciador de Pacotes**: Executar `Install-Package Aspose.Slides`
  - **Interface do usuário do gerenciador de pacotes NuGet**: Pesquise e instale a versão mais recente.
- Um ambiente de desenvolvimento configurado com .NET Core ou .NET Framework (versão 4.5 ou posterior).
- Noções básicas de programação em C#.

## Configurando o Aspose.Slides para .NET

Para começar a usar o Aspose.Slides, adquira uma licença da [Site Aspose](https://purchase.aspose.com/buy). Veja como configurar:

1. **Instalação**: Siga os passos de instalação mencionados acima.
2. **Configuração de licença**:
   - Carregue seu arquivo de licença em seu projeto usando:
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

Esta configuração permite que você comece a trabalhar com o Aspose.Slides para .NET.

## Guia de Implementação

Nesta seção, descreveremos o processo de definição de regras de fallback de fontes em etapas claras.

### 1. Defina intervalos Unicode e fontes alternativas

Cada script ou conjunto de símbolos requer intervalos Unicode específicos e fontes alternativas correspondentes para garantir a exibição correta.

#### Escrita tâmil

- **Visão geral**: Use "Vijaya" para caracteres tâmeis quando a fonte principal não for compatível.

**Etapas de implementação:**

##### Etapa 1: Definir intervalo Unicode
```csharp
uint startUnicodeIndexTamil = 0x0B80; // Início da distribuição do Tamil
uint endUnicodeIndexTamil = 0x0BFF;   // Fim da extensão tâmil
```
Este trecho define o intervalo Unicode para caracteres tâmeis.

##### Etapa 2: Criar regra de fallback
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
Aqui, criamos uma regra de fallback usando "Vijaya" como fonte alternativa.

#### Hiragana japonês

- **Visão geral**: Use "MS Mincho" ou "MS Gothic" para caracteres Hiragana não suportados.

**Etapas de implementação:**

##### Etapa 1: Definir intervalo Unicode
```csharp
uint startUnicodeIndexHiragana = 0x3040; // Início da gama Hiragana
uint endUnicodeIndexHiragana = 0x309F;   // Fim da gama Hiragana
```
Este trecho define os limites Unicode para Hiragana.

##### Etapa 2: Criar regra de fallback
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
Esta regra especifica várias fontes alternativas para caracteres Hiragana.

#### Personagens Emoji

- **Visão geral**: Certifique-se de que os emojis sejam exibidos usando fontes apropriadas, como "Segoe UI Emoji".

**Etapas de implementação:**

##### Etapa 1: Definir intervalo Unicode
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // Início do intervalo de emojis
uint endUnicodeIndexEmoji = 0x1F64F;   // Fim do intervalo de emojis
```
Isso define o intervalo Unicode para emojis.

##### Etapa 2: Criar regra de fallback
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}