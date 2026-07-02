# FinPilot AI - Modelo de datos inicial

## Entidades principales

### User

Representa al propietario de la cuenta.

Campos iniciales:

- id
- name
- email
- base_currency
- risk_profile
- created_at

### Account

Cuenta financiera o contenedor de dinero.

Ejemplos:

- Banco Santander
- BBVA
- Revolut
- Broker
- Wallet cripto
- Efectivo

Campos:

- id
- user_id
- name
- type
- institution
- currency
- current_balance
- connected_provider
- is_manual
- updated_at

Tipos:

- bank
- cash
- broker
- crypto_wallet
- metal_storage
- other

### Asset

Activo patrimonial.

Ejemplos:

- ETF
- Accion
- Bitcoin
- Ethereum
- Oro
- Vivienda
- Barco
- Coche
- Moto

Campos:

- id
- user_id
- account_id
- name
- asset_class
- quantity
- unit_value
- currency
- current_value
- valuation_source
- last_valuation_at

Clases:

- cash
- stock
- etf
- crypto
- metal
- real_estate
- vehicle
- boat
- other

### Liability

Deuda u obligacion.

Campos:

- id
- user_id
- name
- type
- outstanding_balance
- interest_rate
- monthly_payment
- currency
- maturity_date

### Transaction

Movimiento financiero.

Campos:

- id
- user_id
- account_id
- amount
- currency
- type
- category
- merchant
- description
- occurred_at
- source
- ai_category_confidence

Tipos:

- income
- expense
- transfer
- investment_buy
- investment_sell
- dividend
- fee

### Goal

Objetivo financiero.

Campos:

- id
- user_id
- name
- target_amount
- current_amount
- target_date
- priority
- goal_type
- status

Ejemplos:

- Fondo de emergencia
- Comprar barco
- Comprar vivienda
- Independencia financiera
- Jubilacion

### FinancialHealthScore

Snapshot del indice de salud financiera.

Campos:

- id
- user_id
- score
- liquidity_score
- diversification_score
- profitability_score
- risk_score
- debt_score
- monthly_saving_score
- explanation
- calculated_at

## Calculo de patrimonio neto

```text
Patrimonio neto = suma de activos - suma de pasivos
```

## Calculo de liquidez

```text
Liquidez = cuentas bancarias + efectivo + equivalentes de efectivo
Porcentaje liquidez = liquidez / patrimonio neto
```

## Dinero invertible estimado

Primera regla:

```text
Liquidez objetivo = max(gastos mensuales * meses de emergencia, patrimonio neto * objetivo_liquidez_pct)
Dinero invertible = max(0, liquidez actual - liquidez objetivo)
```

