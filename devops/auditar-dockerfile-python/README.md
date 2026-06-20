---
nome: Auditar Dockerfile Python
descricao: Analisa um Dockerfile Python identificando problemas de segurança e performance, entregando lista priorizada de recomendações e versão corrigida do arquivo.
versao: 1.0.0
tags: [docker, segurança, python, devops, containers]
inputs: []
---

# Auditar Dockerfile Python

## Objetivo

Atuar como engenheiro DevOps/SRE sênior especializado em segurança de containers (CIS Docker Benchmark, OWASP Container Security) para analisar um Dockerfile Python fornecido, identificar problemas de segurança e de performance/tamanho, e entregar: (1) lista priorizada de recomendações classificadas por criticidade (Crítico, Alto, Médio, Baixo) e (2) Dockerfile final com todas as correções aplicadas.

## Quando usar

- Antes de commitar ou publicar uma imagem Docker, para revisar segurança e eficiência.
- Ao receber um Dockerfile de terceiros e querer avaliação antes de incorporá-lo.
- Em auditorias de segurança de infraestrutura de containers Python.
- Quando o objetivo for reduzir o tamanho da imagem ou melhorar tempo de build e aproveitamento de cache.

## Exemplo de uso

Cole o conteúdo do Dockerfile diretamente na conversa (e opcionalmente o `requirements.txt`, framework e ambiente). O modelo retornará o resumo de achados, as recomendações priorizadas e o Dockerfile corrigido — sem repetir o arquivo original nem narrar o raciocínio interno.

## Limitações conhecidas

- Focado em aplicações Python; para outras linguagens a análise de imagem base e dependências pode ser incompleta.
- Não executa scanners externos de CVE (Trivy, Grype etc.) — a varredura é textual sobre o Dockerfile fornecido.
- A análise de `requirements.txt` depende do conteúdo fornecido pelo usuário; sem ele, pins de versão não são verificáveis.
