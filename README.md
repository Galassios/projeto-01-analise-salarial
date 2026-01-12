# 📊 Análise Salarial por Área

## 📌 Objetivo
Analisar os salários médios por área de atuação, identificando quais setores possuem maior remuneração média e a quantidade de profissionais por área.

---

## 🗂️ Base de Dados
Arquivo CSV contendo informações de pessoas, incluindo:
- nome
- área
- salário
- cidade

Os dados passaram por uma etapa de limpeza para remoção de registros duplicados.

---

## 🛠️ Ferramentas Utilizadas
- SQL (MySQL)
- Python (Pandas)
- Excel (validação inicial)

---

## 🔍 Etapas do Projeto

### 1️⃣ Limpeza dos Dados
- Remoção de registros duplicados
- Verificação de tipos de dados

### 2️⃣ Análise com SQL
- Cálculo da média salarial por área
- Contagem de pessoas por área
- Ordenação pelos maiores salários médios

```sql
WITH tabela_limpa AS (
    SELECT DISTINCT *
    FROM dados_pessoas
)
SELECT
    area,
    ROUND(AVG(salario), 2) AS media,
    COUNT(nome) AS quant
FROM tabela_limpa
GROUP BY area
ORDER BY media DESC, quant DESC;
