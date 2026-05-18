## Consultas

### 1. Quais quartos possuem determinadas características?

```javascript
db.Quartos.find(
  { comodidades: { $all: ["vista para o mar", "banheira"] } },
  { _id: 0, numero: 1, tipo: 1, preco_diaria: 1 }
)
```
### Resposta:
```
[
  { "numero": 221, "tipo": "Luxo", "preco_diaria": 550 },
  { "numero": 222, "tipo": "Presidential Suite", "preco_diaria": 1200 }
]
```
---

### 2. Quais hóspedes reservaram mais de uma vez?

```javascript
db.Reservas.aggregate([
  { $group: { _id: "$hospede.email", nome: { $first: "$hospede.nome" }, totalReservas: { $sum: 1 } } },
  { $match: { totalReservas: { $gt: 1 } } }
])
```
### Resposta:
```
[
  { "_id": "miguel.bueno@email.com", "nome": "Miguel Bueno", "totalReservas": 2 }
]
```

---

### 3. Quanto o hotel faturou em um período?

```javascript
db.Hospedagens.aggregate([
  { $unwind: "$pagamentos" },
  { $match: { 
      "pagamentos.pago": true, 
      "pagamentos.data": { 
        $gte: ISODate("2026-04-01T00:00:00Z"), 
        $lte: ISODate("2026-04-30T23:59:59Z") 
      } 
    } 
  },
  { $group: { _id: null, faturamentoTotal: { $sum: "$pagamentos.valor" } } },
  { $project: { _id: 0, faturamentoTotal: 1 } }
])
```
### Resposta:
```
[
  { "faturamentoTotal": 3445 }
]
```