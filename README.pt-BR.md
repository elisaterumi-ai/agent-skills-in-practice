# 🧠 AI Skills — Um Guia Prático
> De prompts para sistemas — aprenda a construir skills reutilizáveis com IA.

🌍 Language:
[English](README.md) | [Português](README.pt-BR.md) | [Español](README.es.md)

Skills são um dos principais blocos de construção dos sistemas modernos de IA.

Elas permitem definir capacidades reutilizáveis e específicas para tarefas, que um sistema de IA pode aplicar automaticamente quando relevante — sem a necessidade de repetir instruções toda vez.

⭐ Se este projeto te ajudou, considere dar uma estrela — isso ajuda outras pessoas a encontrá-lo e apoia o trabalho!

---

## 🧠 Guia Rápido de Skills

Uma referência visual rápida para entender como skills funcionam — da estrutura à ativação.

<img src="https://raw.githubusercontent.com/elisaterumi-ai/agent-skills-in-practice/main/img/skills-guide-pt.png" width="600"/>

> 💡 Use isso como referência rápida enquanto constrói suas próprias skills.

---

## Sumário

- [O que são Skills](#o-que-são-skills)
- [Como Skills Funcionam](#como-skills-funcionam)
- [Estrutura de uma Skill](#estrutura-de-uma-skill)
- [Onde as Skills Ficam](#onde-as-skills-ficam)
- [Skills vs Outras Customizações](#skills-vs-outras-customizações)
- [Quando Usar Skills](#quando-usar-skills)
- [Exemplos de Uso](#exemplos-de-uso)
- [Criando sua Primeira Skill](#criando-sua-primeira-skill)
- [Boas Práticas](#boas-práticas)
- [Erros Comuns](#erros-comuns)
- [Conceitos Avançados](#conceitos-avançados)
- [Por que Skills Importam](#por-que-skills-importam)
- [Recursos](#recursos)
- [Reflexão Final](#reflexão-final)
- [Contribuindo](#contribuindo)
- [Conecte-se comigo](#conecte-se-comigo)

---

## O que são Skills?

Uma **skill** é um conjunto estruturado de instruções que ensina um sistema de IA a executar uma tarefa específica.

No Claude Code, uma skill é:

- Um diretório  
- Contendo um arquivo `SKILL.md`  
- Com metadados e instruções  

Uma vez definida, o sistema pode descobrir e usar a skill automaticamente.

> Em vez de repetir prompts, você define o comportamento uma vez — e reutiliza.

---

## Como Skills Funcionam

Skills seguem um fluxo de **matching semântico**:

1. O sistema carrega apenas os **nomes e descrições**
2. Uma solicitação do usuário é recebida
3. O sistema compara a solicitação com as descrições das skills disponíveis
4. Skills relevantes são selecionadas
5. O conteúdo completo da skill é carregado e executado

Isso significa:

- Skills são **carregadas sob demanda**
- Elas **não poluem o contexto desnecessariamente**
- São ativadas **apenas quando relevantes**

---

## Estrutura de uma Skill

Cada skill vive dentro de um diretório e deve conter um arquivo `SKILL.md`.

### Exemplo:

```yaml
---
name: pr-review
description: Analisa pull requests quanto à qualidade do código e boas práticas. Use ao revisar PRs ou mudanças de código.
---
```

Abaixo do frontmatter, você define as instruções:

```yaml
Ao revisar um PR:

1. Analise as mudanças no código
2. Verifique boas práticas
3. Sugira melhorias
4. Formate a saída como feedback estruturado
```

## Onde as Skills Ficam

Skills podem existir em diferentes escopos:

### Skills Pessoais
- Local: `~/.claude/skills`
- Disponíveis em todos os seus projetos
- Ideais para fluxos pessoais

### Skills de Projeto
- Local: `.claude/skills` (dentro do repositório)
- Compartilhadas via versionamento
- Usadas como padrão de equipe

---

## Skills vs Outras Customizações

| Feature           | Comportamento          | Uso                         |
|-------------------|------------------------|------------------------------|
| **Skills**        | Carregadas sob demanda | Expertise específica         |
| **CLAUDE.md**     | Sempre carregado       | Regras globais do projeto    |
| **Slash Commands**| Invocação manual       | Ações explícitas             |

👉 Skills são **automáticas e contextuais**

---

## Quando Usar Skills

Use uma skill quando:

- Você repete as mesmas instruções frequentemente
- Precisa de consistência na saída
- Quer fluxos reutilizáveis
- Deseja compartilhar conhecimento com o time

**Regra de ouro:**
> Se você explica a mesma coisa mais de uma vez, isso deveria virar uma skill.

---

## Exemplos de Uso

- Revisão de código  
- Formatação de commits  
- Templates de documentação  
- Checklists de debugging  
- Processamento de dados  
- Anonimização de textos clínicos  

👉 Explore skills prontas: [exemplos](examples)

> Alguns exemplos são inspirados em repositórios open-source existentes.

---

## 🚀 Criando sua Primeira Skill

### Passo 1 — Criar diretório

```bash
mkdir -p ~/.claude/skills/my-skill
```

### Passo 2 — Criar `SKILL.md` (ou usar o template)

Crie um arquivo `SKILL.md` dentro do diretório da skill, ou copie do [template](templates/skill-template.md).

```yaml
---
name: my-skill
description: Descreva claramente o que a skill faz e quando deve ser usada.
---
```

> 💡 A `description` é o campo mais importante — o sistema usa ela para decidir quando ativar a skill.

### Passo 3 — Adicionar instruções

Defina:

- Passos  
- Regras  
- Formato de saída  

---

## Boas Práticas

- Escreva **descrições claras e específicas** (isso controla a ativação)
- Mantenha instruções **estruturadas e explícitas**
- Defina **formatos de saída esperados**
- Evite skills genéricas demais
- Mantenha o `SKILL.md` conciso (use referências se necessário)

---

## Erros Comuns

- Tratar skills como simples prompts  
- Escrever descrições vagas (a skill não será ativada)  
- Criar uma skill com múltiplas responsabilidades  
- Não definir o formato da saída  

---

## Conceitos Avançados

### Campos de Metadados

- `name` (obrigatório)
- `description` (obrigatório)
- `allowed-tools` (opcional)
- `model` (opcional)

### Progressive Disclosure

- Mantenha o essencial no `SKILL.md`
- Separe conteúdos grandes em:
  - `references/`
  - `scripts/`
  - `assets/`

---

## Por que Skills Importam

Skills transformam a forma como construímos com IA:

- De **prompts → sistemas reutilizáveis**
- De **instruções manuais → comportamento automático**
- De **experimentação → aplicações prontas para produção**

Elas são um bloco fundamental para:

- Agentes de IA  
- Pipelines de automação  
- Sistemas escaláveis  

---

## Recursos

Links, documentações e repositórios selecionados:

👉 [Explorar recursos](docs/resources.md)

---

## Reflexão Final

Skills mudam a forma de pensar:

> “O que devo perguntar ao modelo?”

Para:

> “Qual capacidade este sistema deve ter?”

---

## 🤝 Contribuindo

Contribuições são bem-vindas!

Você pode ajudar:

- Adicionando novas skills ou casos de uso  
- Melhorando documentação e exemplos  
- Reportando problemas ou sugerindo melhorias  

Abra uma issue ou envie um pull request 🚀

---

## 🔗 Conecte-se comigo

Compartilho insights práticos sobre IA, agentes e aplicações reais:

- LinkedIn (Perfil): https://www.linkedin.com/in/elisa-terumi  
- LinkedIn (Página): https://www.linkedin.com/company/exploring-artificial-intelligence  
- Newsletter (português): https://elisaterumi.substack.com/  
- Newsletter (inglês): https://exploringartificialintelligence.substack.com/  
- Medium: https://medium.com/@elisa-terumi
