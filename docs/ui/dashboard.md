# FinPilot AI - Especificacion del Dashboard

## Objetivo

El Dashboard debe ser la pantalla mas importante del producto. Debe responder en menos de diez segundos:

- Cual es mi patrimonio neto?
- Como ha cambiado este mes?
- Donde esta mi dinero?
- Hay algo que deba hacer?
- Cual es mi salud financiera?

## Estructura de la pantalla

### Header

Contenido:

- Logo FinPilot AI.
- Fecha o periodo actual.
- Selector de moneda.
- Boton de notificaciones.
- Indice de salud financiera.
- Avatar o acceso a perfil.

Indice ejemplo:

```text
88/100
Salud financiera
```

Estado visual:

- Verde: 80-100
- Amarillo: 60-79
- Rojo: 0-59

### Coach Financiero

Debe aparecer arriba del todo, antes de los graficos secundarios.

Ejemplo:

```text
Coach Financiero
Este mes tu patrimonio ha aumentado un 1,7 %. Mantienes un 18 % del patrimonio en liquidez, por encima del objetivo del 10 %. Podrias invertir aproximadamente 6.000 EUR sin comprometer tu fondo de emergencia.
```

Botones rapidos:

- Donde invierto este mes?
- Como va mi patrimonio?
- Voy camino de mis objetivos?
- Riesgos detectados

### Patrimonio Neto

Contenido:

```text
Patrimonio Neto
128.540 EUR
+2.140 EUR este mes (+1,69 %)
```

Debe incluir:

- Valor actual.
- Variacion absoluta.
- Variacion porcentual.
- Comparacion con mes anterior.

### Grafica de evolucion

Grafica principal de linea o area.

Opciones de periodo:

- 1M
- 3M
- 6M
- 1A
- Todo

Estados:

- Positivo: linea verde/azul.
- Negativo: linea roja discreta.
- Sin datos: placeholder con llamada a conectar cuentas o anadir activos.

### Distribucion del patrimonio

Visualizacion recomendada:

- Desktop: donut + leyenda con importes y porcentajes.
- Mobile: barras horizontales apiladas + lista.

Categorias iniciales:

- Banco A
- Banco B
- Bitcoin
- ETF
- Efectivo
- Oro
- Otros

### Tarjetas por clase de activo

#### Liquidez

```text
Liquidez
Banco Santander - 4.250 EUR
BBVA - 2.180 EUR
Revolut - 1.430 EUR
Efectivo - 320 EUR
```

Debe mostrar:

- Total liquidez.
- Porcentaje sobre patrimonio.
- Indicador contra objetivo.

#### Bolsa

```text
Bolsa
ETF - 38.000 EUR
Acciones - 12.000 EUR
```

Debe mostrar:

- Valor actual.
- Rentabilidad mensual.
- Rentabilidad acumulada.

#### Criptomonedas

```text
Criptomonedas
Bitcoin - 18.000 EUR
Ethereum - 2.300 EUR
```

Debe mostrar:

- Valor actual.
- Volatilidad o nivel de riesgo.
- Porcentaje sobre patrimonio.

#### Metales

```text
Metales
Oro - 8.500 EUR
```

#### Otros activos

```text
Otros activos
Barco
Coche
Moto
Vivienda
```

Debe permitir valoraciones manuales y fecha de ultima actualizacion.

## Panel de salud financiera

Al pulsar el indice `88/100`, se abre un panel con:

```text
Liquidez: 95/100
Diversificacion: 80/100
Rentabilidad: 91/100
Riesgo: 75/100
Endeudamiento: 100/100
Ahorro mensual: 89/100
```

Cada metrica debe tener:

- Puntuacion.
- Explicacion breve.
- Regla usada.
- Accion sugerida si aplica.

## Acciones inteligentes

Ejemplos de mensajes:

- No hagas nada este mes.
- Es buen momento para aumentar tu inversion periodica.
- Has acumulado demasiado efectivo.
- Conviene reequilibrar tu cartera.
- Ese gasto importante es compatible con tus objetivos.
- No compres ese barco todavia; espera tres meses.

## Datos de ejemplo para prototipo

```json
{
  "netWorth": 128540,
  "monthlyChange": 2140,
  "monthlyChangePct": 1.69,
  "financialHealth": 88,
  "liquidityPct": 18,
  "targetLiquidityPct": 10,
  "investableCash": 6000
}
```

