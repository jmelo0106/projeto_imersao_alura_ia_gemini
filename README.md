# projeto_imersao_alura_ia_gemini
Projeto final para curso de imersão IA com Google Gemini

# Estudo Personalizado com Agentes de IA

## Visão Geral

Este projeto implementa um sistema de estudo personalizado utilizando o framework ADK de agentes do Google e os modelos Gemini. O sistema é composto por quatro agentes distintos que colaboram para fornecer uma experiência de aprendizado interativa e adaptativa:

1.  **Agente Buscador de Conteúdo:** Responsável por buscar informações relevantes sobre a matéria e o assunto especificados pelo usuário, fornecendo uma explicação inicial clara e concisa.
2.  **Agente de Explicação Alternativa:** Oferece explicações alternativas para tópicos que o usuário possa ter dificuldade em compreender, utilizando diferentes abordagens e analogias.
3.  **Agente de Curadoria de Recursos Adicionais:** Recomenda recursos complementares, como vídeos, artigos e simuladores, para aprofundar o estudo do usuário.
4.  **Agente Avaliador:** Gera questões de múltipla escolha para avaliar a compreensão do usuário sobre o material apresentado, fornecendo feedback imediato.

## Pré-requisitos

* **Conta Google Cloud:** Necessário para acessar a API do Gemini.
* **Google Cloud CLI (opcional, mas recomendado):** Para gerenciar recursos do Google Cloud.
* **Python 3.9+:** Linguagem de programação utilizada no projeto.
* **Bibliotecas Python:** As seguintes bibliotecas são instaladas automaticamente durante a execução do script:
    * `google-genai`
    * `google-adk`
    * `requests`
    * `IPython` (para visualização no Colab)

## Configuração

1.  **Obtenção da API Key do Google Gemini:**
    * Acesse o [Google AI Studio](https://makersuite.google.com/).
    * Crie um novo projeto ou selecione um existente.
    * No menu lateral, clique em "API key".
    * Crie uma nova API key e copie-a.

2.  **Configuração da API Key no Google Colab (ou ambiente local):**
    * **Para Google Colab:** Utilize a funcionalidade `userdata` para armazenar sua API key de forma segura. Execute a seguinte célula no seu notebook Colab:
        ```python
        from google.colab import userdata
        userdata.set('GOOGLE_API_KEY', 'SUA_API_KEY') # Substitua 'SUA_API_KEY' pela sua chave
        ```
    * **Para ambiente local:** Defina a variável de ambiente `GOOGLE_API_KEY` com a sua chave de API. Por exemplo, no seu terminal:
        ```bash
        export GOOGLE_API_KEY="SUA_API_KEY"
        ```

## Execução

O código fornecido é um script Python que pode ser executado em um ambiente Python com as bibliotecas necessárias instaladas. A forma mais simples de executar este código é utilizando o Google Colab:

1.  Abra um novo notebook no [Google Colab](https://colab.research.google.com/).
2.  Copie e cole o código completo nas células do notebook.
3.  Execute as células em sequência.

O script irá solicitar a matéria e o assunto que você deseja estudar. Em seguida, os agentes irão interagir para fornecer conteúdo, explicações adicionais, recursos e uma avaliação do seu aprendizado.

## Arquitetura do Sistema

O sistema é composto por quatro agentes que trabalham em conjunto:

1.  **Agente Buscador (`agente_buscador`):**
    * Utiliza a ferramenta de busca do Google (`google_search`) para encontrar informações relevantes sobre a matéria e o assunto fornecidos pelo usuário.
    * Sua instrução o orienta a agir como um tutor virtual, fornecendo uma explicação inicial estruturada com introdução, detalhes, exemplos, analogias (opcional) e pontos chave.

2.  **Agente de Explicação Alternativa (`agente_explicacao_alternativa`):**
    * É acionado quando o usuário solicita uma explicação adicional sobre um tópico específico.
    * Sua instrução o capacita a analisar a possível dificuldade do usuário e oferecer uma nova perspectiva sobre o mesmo conceito, utilizando linguagem simplificada, novas analogias, focando em diferentes aspectos ou dividindo o conceito em partes menores.

3.  **Agente de Curadoria de Recursos Adicionais (`agente_recursos_adicionais`):**
    * Busca e recomenda recursos complementares para aprofundar o estudo, como vídeos, artigos, simuladores e livros.
    * Sua instrução enfatiza a importância de fornecer uma variedade de formatos, informações relevantes sobre cada recurso e priorizar fontes confiáveis.

4.  **Agente Avaliador (`agente_avaliador`):**
    * Gera questões de múltipla escolha com base no conteúdo apresentado para avaliar a compreensão do usuário.
    * Sua instrução o orienta a criar perguntas claras com uma resposta correta e três distratores plausíveis, apresentando as respostas corretas ao final.

O fluxo de interação principal é sequencial: o usuário define a matéria e o assunto, o buscador fornece o conteúdo inicial, o usuário pode pedir explicações alternativas, o agente de recursos sugere materiais adicionais e, por fim, o avaliador testa a compreensão.

## Contribuição

Contribuições para este projeto são bem-vindas. Se você tiver sugestões de melhorias, novos agentes ou funcionalidades, sinta-se à vontade para abrir uma issue ou enviar um pull request.
