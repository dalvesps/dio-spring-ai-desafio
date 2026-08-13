# 🤖 API Inteligente de Orçamento Financeiro com Spring Boot & Spring AI
> **Desafio de Projeto — Digital Innovation One (DIO)**  
> *Abordagem: Arquitetura da Solução e Guia Estruturado de Engenharia de Prompts para Desenvolvimento Assistido por IA.*

---

## 📌 1. Sobre o Projeto

Este projeto apresenta a especificação arquitetural e o **Roteiro Estruturado de Engenharia de Prompts** para a construção e evolução de uma **API Inteligente de Orçamento Financeiro**.

A aplicação utiliza o **Spring Boot 3** integrado ao módulo **Spring AI** para processar comandos de voz em linguagem natural, converter áudio em texto (Speech-to-Text), interpretar a intenção do usuário por meio de LLMs e executar ações reais no banco de dados através da técnica de **Tool Calling (Function Calling)**.

> [!NOTE]
> **Diferencial desta Entrega:** Ao invés de apresentar apenas código estático, este repositório documenta a **metodologia de desenvolvimento orientado a IA**, contendo a sequência exata de prompts, prioridades de software e justificativas técnicas necessárias para construir a API do zero até a implantação.

---

## 🏗️ 2. Arquitetura da Solução e Fluxo de Dados

O fluxo principal da API inteligência segue a pipeline apresentada abaixo:

```mermaid
sequenceDiagram
    autonumber
    actor Cliente as Usuário (Voz)
    participant API as Spring Boot Controller
    participant STT as Spring AI (Whisper STT)
    participant LLM as Spring AI (ChatClient)
    participant Tool as Tool Calling / Java Service
    participant DB as Banco de Dados (H2)

    Cliente->>API: 1. Envia arquivo de áudio (.mp3 / .wav)
    API->>STT: 2. Solicita transcrição de áudio
    STT-->>API: 3. Retorna texto transcrito ("Gastei R$ 50 no almoço")
    API->>LLM: 4. Envia texto + Registro de Tools Disponíveis
    LLM->>Tool: 5. LLM decide e invoca a função `cadastrarTransacao()`
    Tool->>DB: 6. Persiste a transação no banco de dados
    DB-->>Tool: 7. Confirmação da gravação
    Tool-->>LLM: 8. Retorna o resultado da execução em JSON
    LLM-->>API: 9. Gerador de resposta amigável para o usuário
    API-->>Cliente: 10. Resposta final (Texto / Áudio)
