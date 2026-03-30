### Formulação Matemática – Otimização de Alocação de Ofertas (MILP)

#### Problema de alocações: 
Preciso alocar os produtos de crédito para os segmentos de clientes de forma a **maximizar a receita esperada**, respeitando o volume total de ofertas disponível no mês (18,13 milhões de pessoas) e sem oferecer mais de um produto por cliente.

**Sets**  
- $P$: Produtos [1,2,...,$i$]  
- $S$: Segmentos (combinações de: faixa de score × faixa de renda × faixa etária × negativado) [1,2,...,$s$]

**Parameters**  
- $c_{i,s}$: Taxa de conversão esperada do produto $i$ no segmento $s$  
- $r_i$: Ticket médio do produto $i$  
- $n_s$: Número de clientes **elegíveis** no segmento $s$  
- $B$: Total de ofertas (volume atual de “Possuem Oferta” = 18,13 milhões de pessoas)

**Variáveis**  
- $x_{i,s}$: Número de clientes do segmento $s$ que receberão o produto $i$

**Função Objetivo**  
$$
\max \sum_{i \in P} \sum_{s \in S} c_{i,s} \cdot x_{i,s} \cdot r_i
$$

**Restrições**

$$
\sum_{i \in P} x_{i,s} \leq n_s \quad \forall s \in S \tag{1}
$$

$$
\sum_{i \in P} \sum_{s \in S} x_{i,s} = B \tag{2}
$$

$$\sum_{s \in S} x_{i,s} \geq \frac{0.5}{|P|} \times B \quad \forall \ i \in P \tag{3}$$

$$\sum_{s \in S} x_{i,s} \leq \min\left(\frac{3}{|P|}, 0.35\right) \times B \quad \forall \ i \in P \tag{4}$$

$$\sum_{i \in P} x_{i,s} \geq 0.10 \times n_s \quad \forall \ s \in S \tag{5}$$

$$
x_{i,s} \in \mathbb{Z} \tag{3}
$$

$$
x_{i,s} \geq 0 \tag{4}
$$

**Descrição**  
- (1) garante que **nenhum cliente receba mais de um produto** (no máximo 1 oferta por pessoa em cada segmento);  
- (2) respeita o **orçamento total de ofertas** (mantemos exatamente o mesmo volume de 18,13 milhões de pessoas que já estamos ofertando hoje);  
- (3) garante que **cada produto receba no mínimo metade da fração uniforme** do orçamento (evita que algum produto fique com zero ou muito pouco volume);  
- (4) impede que **qualquer produto domine mais de 35%** do orçamento total (limite superior de concentração);  
- (5) garante que **cada segmento receba pelo menos 10% de seus elegíveis** (evita que grandes segmentos fiquem praticamente sem oferta);  
- (6) define que $x_{i,s}$ é uma variável inteira e não-negativa.