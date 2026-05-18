## Descrição das Coleções

O banco de dados é composto por 6 coleções principais:

### 1. `Quartos`
* **O que contém:** Informações físicas e comerciais de cada acomodação do hotel.
* **Dados incluídos:** Número do quarto, tipo (Standard, Luxo, Suíte), preço da diária, capacidade máxima de pessoas, lista de comodidades (como Wi-Fi, vista para o mar, banheira) e se ele está disponível no momento.

### 2. `Hospedes`
* **O que contém:** O cadastro e os dados de contato de todos os clientes que já se registraram no hotel.
* **Dados incluídos:** Nome completo, documento de identificação (CPF), e-mail e telefone de contato.

### 3. `Reservas`
* **O que contém:** O planejamento das estadias futuras e o histórico de intenções de compra dos clientes.
* **Dados incluídos:** Identificação do hóspede (nome e e-mail), quarto escolhido, datas previstas de check-in e check-out, status da reserva (confirmada, finalizada) e o valor total calculado apenas para as diárias.

### 4. `Hospedagens`
* **O que contém:** O registro real e financeiro do que aconteceu durante o período em que o hóspede esteve fisicamente no hotel.
* **Dados incluídos:** Vinculo com a reserva e o quarto, as datas exatas e horários em que o hóspede entrou e saiu, os serviços extras consumidos (como SPA e Frigobar com seus respectivos preços e datas) e o histórico de pagamentos realizados (método, valor e se foi quitado).

### 5. `Avaliacoes`
* **O que contém:** O feedback dos clientes sobre a experiência vivida no hotel.
* **Dados incluídos:** Identificação do quarto avaliado, identificação do hóspede, nota dada (de 1 a 5), comentário por escrito e a data em que a avaliação foi feita.

### 6. `Profissionais`
* **O que contém:** O controle da equipe interna do hotel.
* **Dados incluídos:** Nome do funcionário, cargo, departamento, e-mail, telefone, escala de trabalho (horário de início/fim e dias da semana), especialidades técnicas, salário e status do contrato (se está ativo).

---

## Por que escolher esses dados para um Hotel?

Organizar o banco de dados dessa forma traz vantagens estratégicas fundamentais para a administração do hotel:

* **Separação entre Planejamento e Realidade (`Reservas` vs `Hospedagens`):** Uma coisa é o que o cliente planeja (reserva), outra é o que acontece de verdade (hospedagem). Registrar o consumo do frigobar ou serviços de SPA na coleção de `Hospedagens` evita bagunçar a reserva inicial e permite cobrar exatamente o que foi consumido no momento do checkout.
* **Foco na Experiência do Cliente (`Avaliacoes` e `Quartos`):** Ao conectar as avaliações diretamente aos quartos, a gerência consegue identificar se um quarto específico precisa de manutenção (ex: ar-condicionado quebrado) ou se um ponto forte (como a banheira de hidromassagem) está gerando comentários positivos.
* **Gestão de Equipe e Escalas (`Profissionais`):** Saber os turnos e especialidades dos funcionários ajuda a garantir que sempre haverá recepcionistas fluentes ou equipes de limpeza VIP disponíveis nos horários de maior movimento (check-in e check-out).
* **Análise de Faturamento e Preferências:** Guardar os métodos de pagamento (Pix, Cartão) e os serviços mais consumidos ajuda o hotel a criar promoções direcionadas e a entender melhor o comportamento financeiro dos hóspedes.

---