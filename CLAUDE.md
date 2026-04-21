# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Propósito do repositório

Catálogo de prompts em Markdown organizados por categoria / área de domínio. Não há código executável, build, testes ou pipeline — é um repositório documental cuja qualidade é medida pela clareza dos prompts e pela consistência da estrutura.

## Estrutura obrigatória

```
<categoria>/
  <nome-do-prompt>/
    prompt.md    # o prompt em si (conteúdo que será copiado/usado)
    README.md    # metadados e documentação do prompt
```

Regras:
- **Categoria** = pasta na raiz (ex.: `engenharia-software/`, `escrita/`, `analise-dados/`). Uma categoria por área de domínio; não aninhar categorias.
- **Prompt** = subpasta dentro de uma categoria, nomeada em `kebab-case` descrevendo o objetivo do prompt.
- **`prompt.md`** contém apenas o texto do prompt — nada de explicações sobre ele. Deve ser utilizável por copiar-e-colar.
- **`README.md`** descreve o prompt: objetivo, quando usar, variáveis/placeholders esperados, exemplo de uso/saída, limitações conhecidas.

A separação `prompt.md` × `README.md` é intencional: ferramentas podem consumir `prompt.md` diretamente, enquanto `README.md` é para o humano decidir se o prompt serve ao caso.

## Ao adicionar um novo prompt

1. Escolher a categoria existente que melhor se encaixa antes de criar uma nova.
2. Se criar categoria nova, adicionar um `README.md` na raiz da categoria explicando o escopo dela.
3. Nomear a pasta do prompt descrevendo o *resultado*, não a técnica (ex.: `revisar-pr` é melhor que `prompt-chain-of-thought`).
4. Manter `prompt.md` autocontido — não referenciar o `README.md` nem outros arquivos do repo, pois o prompt será extraído do contexto.

## Convenções de conteúdo

- Prompts e documentação em **português (pt-BR)** por padrão, salvo quando o prompt for especificamente voltado a tooling/modelos que exijam inglês — nesse caso, registrar o motivo no `README.md`.
- Placeholders em `prompt.md` usar o formato `{{nome_variavel}}` e listar cada um no `README.md`.

## Manutenção da documentação

Sempre que um prompt ou uma categoria for **incluído ou alterado**, revisar e atualizar:

1. **`CLAUDE.md`** — verificar se as regras, estrutura ou convenções aqui descritas continuam refletindo o estado real do repositório; ajustar seções desatualizadas.
2. **`README.md` da raiz** — índice geral do catálogo; atualizar a listagem de categorias e/ou prompts quando algo for adicionado, renomeado ou removido.
3. **`README.md` da categoria** — garantir que o escopo descrito ainda contempla os prompts existentes; atualizar quando um prompt novo ampliar ou redefinir o escopo.
4. **`README.md` do prompt** — manter objetivo, variáveis/placeholders, exemplo de uso e limitações alinhados ao conteúdo atual de `prompt.md`.

A revisão da documentação faz parte da mesma entrega que a mudança do prompt — não deve ficar para depois.

## Git

- Semantic commit, mensagem de uma linha.
- Escopo do commit costuma ser a categoria (ex.: `feat(escrita): adiciona prompt de revisão de email`).
