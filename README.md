# ⏰ Automação de Lembrete de Demandas Atrasadas

Automação desenvolvida no Power Automate para uso periódico em ambiente de trabalho.

O fluxo realiza uma consulta programada em uma base de controle, analisa o status das demandas e atualiza automaticamente os registros conforme a situação encontrada. Quando uma demanda está com o prazo vencido e ainda não foi respondida, o Power Automate marca o item como atrasado e envia um e-mail de lembrete para cada responsável cadastrado.

> Este repositório contém uma versão sanitizada do projeto, com dados sensíveis substituídos por placeholders para evitar exposição de informações internas, credenciais, e-mails, IDs e dados da empresa.

## 🎯 Objetivo

Evitar que demandas pendentes fiquem sem acompanhamento, automatizando a verificação periódica de prazos, a atualização de status e o envio de alertas para os responsáveis.

## ⚙️ Como funciona

1. O fluxo é iniciado automaticamente por uma recorrência configurada no Power Automate.
2. Uma ação HTTP consulta os registros armazenados em uma base de controle.
3. O retorno da consulta é tratado em formato JSON.
4. O fluxo percorre os registros retornados.
5. Se a demanda estiver marcada como respondida, o status é atualizado para `Respondido`.
6. Se a demanda não estiver respondida e o prazo estiver vencido, o status é atualizado para `Atrasado`.
7. Para demandas atrasadas, o fluxo percorre o campo de responsáveis e envia um e-mail individual para cada pessoa.
8. Se a demanda ainda estiver dentro do prazo, o status é mantido ou atualizado como `Em andamento`.

## 🧩 Principais regras do fluxo

- Demandas respondidas recebem o status `Respondido`.
- Demandas não respondidas com prazo vencido recebem o status `Atrasado`.
- Demandas ainda dentro do prazo recebem o status `Em andamento`.
- O envio de e-mail é feito com base nos responsáveis cadastrados no próprio registro.
- A comparação de datas considera o fuso horário configurado para o Brasil.

## 🛠️ Tecnologias utilizadas

- Microsoft Power Automate
- Requisição HTTP
- Integração com base de dados/API externa
- Envio de e-mail pelo Outlook/Office 365
- Expressões do Power Automate
- Tratamento de dados em JSON
- Atualização de registros via método PATCH


## 🔐 Observação sobre segurança

A automação original é utilizada em ambiente de trabalho, porém os arquivos publicados neste repositório foram sanitizados para fins de portfólio.

Tokens, IDs internos, e-mails, conexão real, tenant, base de dados e demais informações sensíveis foram substituídos por placeholders.
