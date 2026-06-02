# Automação de Lembrete de Demandas Atrasadas

Automação desenvolvida no Power Automate para uso periódico em ambiente de trabalho.

O fluxo realiza uma consulta programada em uma base de controle, filtra os registros que ainda não foram respondidos e verifica quais demandas estão com o prazo vencido. Quando uma pendência é identificada, o Power Automate envia automaticamente um e-mail de lembrete para os responsáveis, contendo as principais informações da demanda.

## Objetivo

Evitar que demandas pendentes fiquem sem acompanhamento, automatizando a verificação periódica de prazos e o envio de alertas para os responsáveis.

## Como funciona

1. O fluxo é executado automaticamente a cada intervalo definido.
2. Uma requisição HTTP consulta uma base de dados externa.
3. O Power Automate filtra os registros ainda não respondidos.
4. O fluxo compara o prazo de resposta com a data atual.
5. Quando encontra uma demanda atrasada, envia um e-mail de lembrete.

## Tecnologias utilizadas

- Microsoft Power Automate
- Requisição HTTP
- Integração com base de dados/API externa
- Envio de e-mail pelo Outlook/Office 365
- Expressões do Power Automate

## Observação sobre segurança

Este projeto foi sanitizado para fins de portfólio. Tokens, IDs internos, e-mails, conexão real, tenant, base de dados e demais informações sensíveis foram substituídos por placeholders.
