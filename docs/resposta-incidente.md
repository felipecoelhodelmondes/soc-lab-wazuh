# Resposta ao Incidente

## Objetivo

Definir uma resposta defensiva para o cenário de tentativas anômalas de autenticação SSH observado no laboratório.

## Fluxo de resposta

```text
Detecção
   ↓
Triage
   ↓
Investigação
   ↓
Contenção
   ↓
Erradicação
   ↓
Validação
   ↓
Encerramento
```

## 1. Detecção

O Wazuh identificou eventos relacionados à autenticação SSH.

## 2. Triage

O analista verifica origem, destino, usuário, quantidade de tentativas e existência de autenticações bem-sucedidas.

## 3. Investigação

Devem ser analisados os logs do sistema e outros eventos do endpoint para identificar possíveis atividades posteriores à autenticação.

## 4. Contenção

Em um ambiente real, medidas possíveis incluem:

- bloquear temporariamente a origem;
- restringir acesso SSH;
- desabilitar ou proteger uma conta comprometida;
- exigir autenticação por chave;
- aplicar controles de acesso;
- isolar o endpoint caso existam evidências adicionais de comprometimento.

## 5. Erradicação

Caso seja confirmado comprometimento, remover persistência, corrigir a causa e alterar credenciais afetadas.

## 6. Validação

Após as medidas de contenção, verificar se:

- novas tentativas continuam ocorrendo;
- não existem sessões suspeitas;
- não houve criação de usuários indevidos;
- os serviços permanecem íntegros.

## 7. Encerramento

Registrar evidências, causa provável, ações realizadas e recomendações.

## Resultado esperado

O incidente deve ser encerrado somente após a confirmação de que a atividade suspeita cessou e não existem indicadores adicionais de comprometimento.
