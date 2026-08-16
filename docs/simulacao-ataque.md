# Simulação de Ataque

## Objetivo

Gerar eventos de autenticação SSH em um ambiente controlado para validar a capacidade de monitoramento e detecção do Wazuh.

## Cenário

A máquina Kali Linux foi utilizada para gerar múltiplas tentativas de autenticação contra a máquina Ubuntu vítima.

**Origem:** `192.168.100.20`

**Destino:** `192.168.100.30`

**Serviço:** SSH

A ferramenta utilizada para a simulação foi o Hydra.

> Os testes foram realizados exclusivamente entre máquinas virtuais pertencentes ao laboratório.

## Resultado

A atividade produziu eventos de autenticação que puderam ser visualizados no dashboard do Wazuh.

O dashboard apresentou:

- 576 eventos totais;
- 520 falhas de autenticação;
- 6 autenticações bem-sucedidas;
- 0 alertas de nível 12 ou superior.

## Interpretação

A grande quantidade de falhas em relação ao comportamento normal de autenticação é um indicador que merece investigação.

Em um ambiente corporativo, o analista deveria verificar:

- origem dos eventos;
- conta(s) alvo;
- frequência das tentativas;
- existência de autenticações bem-sucedidas;
- horário da atividade;
- outros eventos relacionados ao mesmo IP;
- alterações posteriores no endpoint.

## Evidências

As imagens utilizadas neste projeto estão em `../screenshots/`.

O objetivo da documentação é demonstrar o processo de análise defensiva, não fornecer instruções para atacar sistemas fora do laboratório.
