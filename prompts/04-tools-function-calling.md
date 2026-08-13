Na pasta `src/main/java/com/dio/orcamento/tools/`, crie as ferramentas para o Spring AI invocar:
1. `CadastrarTransacaoTool.java`: Implementa a interface `Function` do Java para salvar uma transação no banco H2 via `TransacaoRepository` e retornar confirmação em JSON.
2. `ConsultarResumoTool.java`: Implementa a busca de saldo e resumo por categoria.
Adicione anotações `@Description` detalhando cada parâmetro para a LLM entender a finalidade.
