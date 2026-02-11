# Exercício – Prompt Engineering para Análise de Pull Requests IaC

**Nome:** José Augusto Gomes da Cruz

## Objetivo

Demonstrar evolução de domínio em prompt engineering por meio da criação progressiva de prompts para análise automática de Pull Requests de Infraestrutura como Código (IaC), com foco em segurança, custo, compliance e boas práticas.

## Estratégia de construção dos prompts

### Prompt v1 – Baseline
A primeira versão utiliza linguagem natural e instruções abertas, com foco em clareza e entendimento do problema. O modelo possui liberdade para estruturar a resposta, o que gera resultados variáveis e pouco previsíveis.

### Prompt v2 – Structured
Na segunda versão, foi introduzida uma estrutura fixa de resposta. Isso reduz ambiguidades, melhora a consistência entre análises e facilita a comparação entre PRs, embora ainda não haja proteção contra prompt injection. 

No v2, a estrutura é soft-structured (por prompt), enquanto structured outputs mais sofisticados são hard-structured (por contrato).

### Prompt v3 – Schema + Segurança
A terceira versão aplica princípios de uso seguro de LLMs em ambientes produtivos:
- Separação clara entre instruções do sistema e dados do PR
- Regras explícitas para ignorar instruções contidas no input (guardrails)
- Saída em formato JSON estrito
- Conjunto fechado de valores permitidos

Essa abordagem torna o prompt robusto contra prompt injection e adequado para automação em pipelines de CI/CD.

## Estrutura do repositório

- `prompts/`: versões incrementais dos prompts
- `resultados/`: prints das execuções dos prompts contra os PRs de teste