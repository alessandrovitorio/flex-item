# flex-item# 🎯 **Flex Items no Flexbox**

Os **Flex Items** são os elementos filhos diretos de um **Flex Container**. Eles herdam as propriedades do container e podem ser manipulados individualmente usando diversas propriedades.  

## 📌 **1. O que define um Flex Item?**  
Um elemento se torna um **Flex Item** quando seu elemento pai tem a propriedade:  
```css
display: flex;
```
📌 **Exemplo:**  
```html
<div class="container">
    <div class="item">1️⃣</div>
    <div class="item">2️⃣</div>
    <div class="item">3️⃣</div>
</div>
```
```css
.container {
    display: flex;
    background: lightgray;
}

.item {
    background: steelblue;
    color: white;
    padding: 10px;
    margin: 5px;
}
```

---

## ⚙️ **2. Propriedades dos Flex Items**

Os Flex Items possuem propriedades específicas para controle de tamanho e alinhamento:

### 🚀 **2.1. flex-grow** (Expansão)  
📌 Determina quanto o item pode crescer dentro do container.  
- 🔹 **Valor padrão:** `0` (não cresce)  
- ✨ **Exemplo:**
```css
.item {
    flex-grow: 1;
}
```
📌 Se todos os itens tiverem `flex-grow: 1;`, eles crescerão igualmente para ocupar o espaço disponível.

---

### ⚡ **2.2. flex-shrink** (Encolhimento)  
📌 Determina quanto um item pode **encolher** se não houver espaço suficiente no container.  
- 🔹 **Valor padrão:** `1` (pode encolher)  
- ✨ **Exemplo:**  
```css
.item {
    flex-shrink: 0;
}
```
📌 Se `flex-shrink: 0;`, o item **não encolhe** quando o espaço for reduzido.

---

### 📏 **2.3. flex-basis** (Tamanho inicial)  
📌 Define o **tamanho inicial** do item antes da distribuição do espaço extra.  
- Pode ser `auto`, `px`, `%`, `em`, etc.  
- ✨ **Exemplo:**  
```css
.item {
    flex-basis: 100px;
}
```
📌 Isso faz com que o item tenha **100px de largura** antes do crescimento ou encolhimento.

---

### 🎯 **2.4. flex** (Atalho)  
📌 É uma forma curta para `flex-grow`, `flex-shrink` e `flex-basis`, nessa ordem:  
```css
.item {
    flex: 1 1 150px; /* grow: 1, shrink: 1, basis: 150px */
}
```
Outro exemplo:  
```css
.item {
    flex: 0 0 200px; /* Fixar o item com 200px sem crescer nem encolher */
}
```

---

## 🎯 **3. Alinhamento de Itens Individuais**

Cada item pode ser alinhado individualmente dentro do Flex Container usando **align-self**.

### 🎯 **3.1. align-self**
📌 Permite alterar o alinhamento vertical do item dentro do flex container.  
Valores possíveis:  
- 🎯 `auto` (herda do `align-items` do container)  
- 🔝 `flex-start` (alinha no topo)  
- 🔚 `flex-end` (alinha na base)  
- 🎯 `center` (centraliza)  
- 🔤 `baseline` (alinha com base no texto)  
- 📏 `stretch` (ocupa todo o espaço disponível)  

✨ **Exemplo:**  
```css
.item:nth-child(2) {
    align-self: flex-end;
}
```
📌 Isso alinha **apenas o segundo item** na parte inferior do container.

---

## 🔄 **4. Ordem dos Itens**

A propriedade **order** permite mudar a posição dos itens sem alterar o HTML.

### 🔄 **4.1. order**
📌 O valor padrão é `0`. Quanto **menor** o número, mais **antes** ele aparece.  
✨ **Exemplo:**  
```css
.item:first-child {
    order: 2;
}

.item:last-child {
    order: -1;
}
```
📌 Isso colocará o último item **antes** dos outros, e o primeiro item **depois** dos demais.

---

## 🎨 **5. Exemplo Completo**  
Aqui está um exemplo visual:  
```html
<div class="container">
    <div class="item" style="flex: 1">Item 1️⃣</div>
    <div class="item" style="flex: 2; align-self: center;">Item 2️⃣</div>
    <div class="item" style="flex: 1; order: -1;">Item 3️⃣</div>
</div>
```
```css
.container {
    display: flex;
    background: lightgray;
    height: 200px;
}

.item {
    background: steelblue;
    color: white;
    padding: 20px;
    margin: 5px;
}
```
📌 **Explicação:**  
- ✨ `Item 2` cresce duas vezes mais que os outros (`flex: 2`).  
- 🔄 `Item 3` aparece **antes** dos outros (`order: -1`).  
- 🎯 `Item 2` está centralizado verticalmente (`align-self: center`).  

