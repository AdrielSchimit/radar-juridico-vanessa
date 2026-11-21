# Radar Jurídico — Vanessa Gonçalves

Painel interno de triagem de reclamações públicas para análise jurídica. Lista somente reclamações comprovadamente publicadas na data corrente (America/Sao_Paulo), sem coleta de dados pessoais ou contatos para prospecção.

Site publicado: https://radar-juridico-vanessa.vercel.app

## Funcionamento

- Cada entrada contém assunto, resumo, documentos a conferir, próximo passo e link público para checagem.
- Relatos de consumidores são alegações, não provas de ilicitude.
- O painel esconde automaticamente os dados de datas anteriores; não transfere casos de ontem como novos.
- Nenhum scraping em massa ou abordagem comercial direcionada a reclamantes é autorizado.
- Requer curadoria de resultados públicos e atualização do JSON de dados no HTML, seguida de publicação.

## Atualização

O HTML contém um bloco JSON de dados (`script#radar-data`). A pesquisa agendada verifica somente reclamações com **data de publicação** correspondente ao dia atual no fuso de Brasília. Se não houver ocorrências verificadas, o array `cases` fica vazio. O agendamento não é um scraper ou API oficial do Reclame Aqui.

## Ética

Uso como pesquisa de demanda e preparação de conteúdo jurídico geral. Contratação e atendimento individual somente por iniciativa do interessado, com análise da advogada e observância da OAB e LGPD.
