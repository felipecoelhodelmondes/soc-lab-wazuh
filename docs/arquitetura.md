# Arquitetura do Laboratório

## Visão geral

O laboratório utiliza três máquinas virtuais conectadas em uma rede privada `192.168.100.0/24`.

### Componentes

| Host | IP | Função |
|---|---|---|
| Wazuh Server | `192.168.100.10` | Centralização e análise |
| Kali Linux | `192.168.100.20` | Simulação controlada |
| Vítima | `192.168.100.30` | Endpoint monitorado |

## Fluxo

```text
Kali Linux
192.168.100.20
      │
      │ Eventos de autenticação SSH
      ▼
Ubuntu Vítima
192.168.100.30
      │
      │ Logs
      ▼
Wazuh
192.168.100.10
      │
      ▼
Dashboard / Analista SOC
```

## Validação da infraestrutura

O endereço `192.168.100.20` foi identificado na interface `eth0` do Kali.

O Wazuh Server apresentou o endereço `192.168.100.10` na interface `eth0`.

O serviço `wazuh-indexer` estava em estado **active (running)** durante a validação.

## Objetivo arquitetural

A separação das máquinas permite representar três papéis comuns em um laboratório de segurança:

1. **Origem da atividade suspeita**
2. **Ativo potencialmente afetado**
3. **Plataforma de monitoramento e análise**
