# XA-TRUST DoD - Evidence / DoD

## Status atual
- Especificacao: v2.0
- Matriz: DOD-45-CAPABILITY-MATRIX.csv - 45 capabilities, 7 pilares
- mapping_status: PROPOSED
- implementation_status: NOT_ASSESSED
- evidence_status: NOT_ASSESSED
- Nomes oficiais DoD: PENDING_SOURCE_VERIFICATION

Esta matriz e um inventario documental. Nao prova implementacao,
teste ou verificacao independente.

## Implementacao BCVL v2 - em progresso, NAO promovida
- E7: NOT_PROMOTED
- E8: NOT_ESTABLISHED

### Regras
- API-11: Somente rfc8785.dumps para hashing. json.dumps PROIBIDO para hash.
- API-12: sha256(rfc8785.dumps(payload)). O hash deve ser o output real do producer.
- API-22: Merkle com leaf = sha256(0x00 || JCS(payload)),
  node = sha256(0x01 || left_bytes || right_bytes),
  hash_input = RAW_BYTES, nao hex string.
- position = posicao do sibling em relacao ao atual.

### Arquivos previstos
- xa-trust/producer.py
- xa-trust/tests/jcs/reconciler.py
- xa-trust/evidence/test_execution.json

