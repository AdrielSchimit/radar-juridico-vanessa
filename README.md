# Radar Jurídico — Vanessa Gonçalves

Painel simples de pesquisa para **avaliar reclamações públicas e temas jurídicos**, sem transformar consumidores em listas de contatos.

**Site:** https://radar-juridico-vanessa.vercel.app

## Arquivos

- `index.html`: interface responsiva, com pesquisa, filtros, síntese jurídica e documentos para análise.
- `data.json`: lote de reclamações **da data corrente**.
- `README.md`: estas instruções.

## Regra principal: somente as publicadas hoje

A interface calcula a data em `America/Sao_Paulo` e só exibe um lote com `day` igual a essa data. Também valida `cases[].publishedAt` por item. Se o arquivo não for atualizado, **não exibe reclamações antigas**.

A tarefa agendada pesquisa duas vezes por dia (aproximadamente 10h e 16h, horário de Brasília), confere a **data original de publicação**, e substitui `data.json`. Os resultados dependem de dados públicos indexados: sem garantia de cobertura completa ou coleta em tempo real. Não se deve confundir atualização da reclamação, resposta da empresa ou data de indexação com publicação.

### Formato do data.json

```json
{
  "day": "2026-11-21",
  "checkedAt": "2026-11-21T12:04:00-03:00",
  "coverage": "Amostra pública não exaustiva.",
  "cases": [
    {
      "id": "id-estavel",
      "publishedAt": "2026-11-21T08:38:00-03:00",
      "area": "Imobiliário",
      "organization": "Empresa",
      "title": "Título sintético",
      "summary": "Relato do consumidor, sem afirmação de ilícito comprovado.",
      "priority": "Avaliar primeiro",
      "action": "O que a Vanessa deve conferir juridicamente.",
      "docs": "Documentação a solicitar se houver atendimento voluntário.",
      "url": "https://www.reclameaqui.com.br/..."
    }
  ]
}
```

Se não houver casos confirmados para a data, usar `cases: []`. Nunca manter registros anteriores no lote do dia.

## Publicação

O projeto Vercel `radar-juridico-vanessa` está no time `adrielschimits-projects` (projeto `prj_JzntogUzR7gXtln7oVJIrQjooPGx`). Uma publicação usando a fonte `github / AdrielSchimit / radar-juridico-vanessa / main` já foi concluída, mantendo o endereço do site.

O agendamento deve atualizar `data.json` pelo GitHub e verificar se o commit novo já foi publicado na Vercel. Se não, disparar deployment `production` com `gitSource` apontando para `main` e conferir `READY`.

## Proteção de dados e ética profissional

Não realizar scraping em massa sem autorização, não extrair nomes, telefones, CPF ou dados sensíveis, e não identificar pessoas para contato comercial não solicitado. O painel é pesquisa informativa; **não autoriza abordagem dirigida a reclamantes**. Antes de qualquer atendimento, a pessoa deve procurar o escritório por iniciativa própria. A advogada avalia os fundamentos, riscos e a contratação segundo normas da OAB e da LGPD.

Todos os textos são resumos de alegações públicas, não conclusões de responsabilidade ou promessa de resultado.
