# Relatório de Incidente — SOC Lab

## 1. Identificação

| Campo | Informação |
|---|---|
| ID | SOC-LAB-001 |
| Tipo | Tentativas anômalas de autenticação SSH |
| Origem | `192.168.100.20` |
| Destino | `192.168.100.30` |
| Serviço | SSH |
| Plataforma | Wazuh |
| Ambiente | Laboratório virtualizado |
| Status | Encerrado / simulação |

## 2. Resumo

Durante uma simulação controlada de segurança, foram geradas múltiplas tentativas de autenticação SSH contra um endpoint Ubuntu.

Os eventos foram coletados pelo Wazuh e disponibilizados no dashboard para análise.

## 3. Evidências

O dashboard apresentou:

- **576** eventos totais;
- **520** falhas de autenticação;
- **6** autenticações bem-sucedidas;
- **0** alertas de nível 12 ou superior.

Também foram observadas categorias relacionadas a Password Guessing, Brute Force e SSH.

## 4. Análise

A concentração de falhas de autenticação indica um comportamento incompatível com uma rotina normal de login, sendo compatível com uma tentativa de descoberta/validação de credenciais.

As autenticações bem-sucedidas exigem atenção adicional em um cenário real, pois poderiam indicar que uma credencial válida foi descoberta.

## 5. MITRE ATT&CK

Possíveis técnicas relacionadas:

- T1110 — Brute Force
- T1110.001 — Password Guessing
- T1021.004 — SSH
- T1078 — Valid Accounts

## 6. Resposta

Para fins de laboratório, o incidente foi utilizado para validar a capacidade de detecção e análise.

Em ambiente produtivo, recomenda-se investigar as autenticações bem-sucedidas, validar a legitimidade da conta e, caso necessário, realizar contenção da origem e proteção das credenciais.

## 7. Lições aprendidas

O laboratório demonstrou a importância de:

- centralizar logs;
- monitorar autenticações;
- investigar padrões anômalos;
- correlacionar eventos;
- documentar incidentes;
- utilizar frameworks como MITRE ATT&CK;
- estabelecer procedimentos de resposta.

## 8. Conclusão

O cenário confirmou a capacidade do laboratório de gerar, coletar e visualizar eventos de segurança relacionados a autenticação SSH, permitindo praticar o fluxo de trabalho de um analista SOC desde a detecção até a documentação do incidente.
