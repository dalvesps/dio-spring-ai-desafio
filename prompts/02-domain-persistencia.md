Na pasta `src/main/java/com/dio/orcamento/domain/`, crie as seguintes classes:
1. `model/TipoTransacao.java` (Enum: RECEITA, DESPESA).
2. `model/CategoriaTransacao.java` (Enum: ALIMENTACAO, TRANSPORTE, MORADIA, LAZER, SALARIO, OUTROS).
3. `model/Transacao.java` (Entidade JPA com id, descricao, valor, tipo, categoria, dataHora).
4. `repository/TransacaoRepository.java` (Interface JpaRepository).
