# Datos

## `transactions.csv`

Dataset de transacciones de Ethereum usado en el análisis.

| Campo | Descripción |
|-------|-------------|
| `from_address` | Dirección de origen (quién envía) |
| `to_address` | Dirección de destino (quién recibe) |
| `block_number` | Número de bloque |
| `transaction_hash` | Identificador único de la transacción |
| `value` | Monto transferido (wei) |

- Registros originales: **5.000**
- Usados en el grafo tras limpieza: **4.999** (se excluyó 1 fila sin `to_address`)
- SHA-256: `712bb757578f5430f2d67b5f8d445a057041bf2c011c835a730df863599fc2ab`

El notebook carga este archivo desde:

```python
pd.read_csv("data/transactions.csv")
```
