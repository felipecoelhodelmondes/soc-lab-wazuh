# Análise do Incidente

## Identificação

**Tipo:** Tentativas anômalas de autenticação SSH

**Origem:** `192.168.100.20`

**Destino:** `192.168.100.30`

**Tecnologia monitorada:** Linux / SSH

**Plataforma de detecção:** Wazuh

## Indicadores

O dashboard apresentou 520 falhas de autenticação e 6 autenticações bem-sucedidas entre os eventos observados.

Esse padrão pode ser compatível com uma tentativa de **Password Guessing / Brute Force**, especialmente quando existe alta repetição de falhas em curto intervalo.

## Triage

Durante uma triagem inicial, o analista deve responder:

1. Qual é o IP de origem?
2. Qual é o ativo de destino?
3. Qual usuário foi alvo?
4. Quantas tentativas ocorreram?
5. Houve autenticação bem-sucedida?
6. O IP aparece em outros eventos?
7. Houve alguma atividade suspeita após o login?
8. O comportamento é esperado para aquele ambiente?

## Classificação

Para este laboratório, o evento é tratado como uma **atividade suspeita de autenticação** que exige investigação.

A severidade final, em um ambiente real, dependeria de fatores como:

- sucesso da autenticação;
- criticidade do ativo;
- privilégio da conta;
- quantidade de tentativas;
- evidências de comprometimento;
- contexto do usuário e do IP.

## MITRE ATT&CK

Possíveis associações:

- **T1110 — Brute Force**
- **T1110.001 — Password Guessing**
- **T1021.004 — SSH**
- **T1078 — Valid Accounts**, caso exista evidência de uso de credenciais válidas.

## Conclusão da análise

O principal indicador foi a concentração de falhas de autenticação SSH originadas da máquina Kali contra a máquina vítima.

O Wazuh permitiu centralizar os eventos e disponibilizar os dados para análise, reproduzindo uma etapa fundamental de um processo de SOC.
