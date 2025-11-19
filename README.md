# Interpretação Automática de Imagens com Modelos Multimodais

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=black)

Protótipo desenvolvido como parte da Global Solution da FIAP, que demonstra um sistema completo de interpretação automática de imagens utilizando a API do modelo multimodal `gpt-4o-mini` da OpenAI.

## 👥 Integrantes

| Nome Completo   | RM       |
| --------------- | -------- |
| André Rovai     | RM555848 |
| Alan de Souza   | RM557088 |
| Leonardo Zago   | RM558691 |

## 📜 Sobre o Projeto

O objetivo deste desafio é desenvolver um sistema de interpretação automática de imagens que combina visão computacional moderna com modelos multimodais de linguagem. O projeto demonstra como a IA atual é capaz de compreender, descrever e analisar cenas visuais com alto nível de detalhamento.

A solução realiza duas funções essenciais:
1.  **Geração de Descrições Textuais:** Cria descrições completas e coerentes para cada imagem, identificando objetos, ações e o contexto geral da cena.
2.  **Extração de Informações Estruturadas:** Detecta objetos, pessoas, equipamentos e realiza a leitura de texto (OCR) para enriquecer a compreensão visual da imagem.

## 🛠️ Tecnologias Utilizadas

*   **Linguagem:** Python 3
*   **Ambiente de Execução:** Google Colab
*   **Modelo de IA:** `gpt-4o-mini` da OpenAI
*   **Bibliotecas Principais:**
    *   `openai`: Para interação com a API da OpenAI.
    *   `requests`: Para o download das imagens a partir de URLs.
    *   `base64`: Para a codificação das imagens antes do envio para a API.

## 🚀 Como Executar

O projeto foi desenvolvido em um único notebook (`.ipynb`) e pode ser executado facilmente no Google Colab.

1.  **Abra o Notebook:**
    *   Faça o upload do arquivo `Interpretação_Automática_de_Imagens.ipynb` para o seu Google Drive.
    *   Abra o notebook com o Google Colaboratory.

2.  **Configure a Chave de API:**
    *   No menu à esquerda do Colab, clique no ícone de chave (🔑) chamado **Secrets**.
    *   Crie um novo "Secret" com o nome `OPENAI_API_KEY`.
    *   No campo "Value", cole a sua chave de API oficial da OpenAI.
    *   Certifique-se de que a opção "Notebook access" está ativada.

3.  **Execute o Código:**
    *   No menu superior, clique em `Ambiente de execução` > `Executar tudo`.
    *   O script irá instalar as dependências, carregar a chave, baixar e analisar todas as 20 imagens da lista. Os resultados serão exibidos diretamente no notebook.

## 📊 Resumo da Análise Crítica do Sistema

O protótipo demonstrou ser altamente eficaz e versátil. A análise de seu desempenho revelou os seguintes pontos:

#### Pontos Fortes
*   **Excelente Compreensão Contextual:** O modelo foi capaz de interpretar o contexto das cenas, usando termos como "ambiente colaborativo" e "reunião de brainstorming", em vez de apenas listar objetos.
*   **Análise Precisa de Interações Humanas:** Descreveu com sucesso ações complexas como "gesticulando enquanto fala" e "escutando atentamente", demonstrando uma forte capacidade de análise social.
*   **Sucesso do OCR em Texto Digital e Impresso:** O sistema leu com alta precisão textos em telas de computador, documentos e apresentações, validando sua funcionalidade de OCR.

#### Limitações Identificadas
*   **Dificuldade com Texto Manuscrito:** A principal falha foi na leitura de texto manuscrito em post-its e quadros brancos, onde o modelo muitas vezes não conseguiu extrair o conteúdo.
*   **Falta de Conhecimento Especializado:** Em ambientes técnicos (laboratórios, indústrias), o modelo identificou o contexto geral (ex: "braço robótico"), mas não conseguiu fornecer detalhes específicos sobre equipamentos, modelos ou funções, permanecendo em um nível superficial.

#### Oportunidades de Melhoria
*   **Integração com OCR Especializado:** Para cenários que dependem de texto manuscrito, o sistema poderia ser integrado a serviços de OCR mais específicos, usando o GPT-4o para a interpretação contextual do resultado.
*   **Abordagem Híbrida para Ambientes Técnicos:** Para aplicações industriais, uma solução híbrida seria ideal: usar um modelo de visão computacional customizado (como YOLOv8) para detectar equipamentos específicos e enviar essa informação para o `gpt-4o-mini` enriquecer a descrição final.

## 📄 Exemplo de Análise

Abaixo, um exemplo da saída gerada pelo sistema para uma das imagens.

**URL:** `https://images.unsplash.com/photo-1554224155-6726b3ff858f?q=80&w=1911`

```
### Descrição Textual
A imagem retrata uma cena de trabalho onde documentos relacionados a impostos estão espalhados sobre uma superfície de madeira clara. A mão de uma pessoa está visível segurando um envelope. Na mesa, há várias folhas, incluindo uma que diz "Tax Withholding and Estimated Tax" e "For use in 2019". Ao lado dos documentos, há um smartphone com uma calculadora visível na tela, sugerindo que a pessoa está realizando cálculos financeiros.

### Informação Estruturada
- **Objetos Detectados:**
  - Documentos (vários formulários fiscais)
  - Envelope
  - Smartphone
  - Caneta
- **Pessoas:**
  - Apenas uma mão visível, segurando um envelope.
- **Equipamentos:**
  - Smartphone (com calculadora visível)
  - Caneta
- **Texto Visível (OCR):**
  - "Tax Withholding and Estimated Tax"
  - "For use in 2019"
  - Outros formulários e informações fiscais (detalhes estão parcialmente visíveis).
```
