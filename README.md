# Oficina

1. Clientes
id_cliente (PK): Identificador único de cada cliente.
nome: Nome completo do cliente.
telefone: Número de telefone de contato.
email: Endereço de e-mail do cliente.
endereço: Localização do cliente (rua, cidade, CEP).
✅ Finalidade: Armazenar as informações pessoais dos clientes para contato e registro de serviços prestados.

2. Veículos
id_veiculo (PK): Identificador único de cada veículo.
id_cliente (FK): Referência ao cliente que possui o veículo.
placa: Placa do veículo (ex: ABC-1234).
modelo: Modelo do veículo (ex: Corolla).
marca: Marca do veículo (ex: Toyota).
ano: Ano de fabricação do veículo.
✅ Finalidade: Registrar os veículos que pertencem aos clientes para associá-los às ordens de serviço.

3. Serviços
id_servico (PK): Identificador único de cada serviço.
nome_servico: Descrição do serviço (ex: Troca de óleo, alinhamento).
preco: Preço do serviço.
✅ Finalidade: Listar os serviços disponíveis na oficina com seus respectivos valores.

4. Ordem_de_Serviço
id_ordem (PK): Identificador único de cada ordem de serviço.
id_veiculo (FK): Referência ao veículo que está sendo atendido.
data_servico: Data em que o serviço foi realizado.
custo_total: Valor total da ordem de serviço (soma dos serviços).
status: Estado da ordem (ex: Pendente, Em andamento, Concluído).
✅ Finalidade: Registrar cada serviço prestado em um veículo, incluindo a data e o custo total.

5. Detalhes_da_Ordem
id_detalhe (PK): Identificador único do detalhe.
id_ordem (FK): Referência à ordem de serviço correspondente.
id_servico (FK): Referência ao serviço realizado.
quantidade: Quantidade de vezes que o serviço foi executado.
preco_por_servico: Valor do serviço em cada execução.
✅ Finalidade: Relacionar cada ordem de serviço com os serviços específicos realizados (muitos-para-muitos).

6. Funcionários
id_funcionario (PK): Identificador único de cada funcionário.
nome: Nome do funcionário.
cargo: Cargo ou função do funcionário (ex: Mecânico, Recepcionista).
telefone: Telefone de contato do funcionário.
✅ Finalidade: Armazenar informações dos funcionários responsáveis pelos serviços.

7. Atribuições
id_atribuicao (PK): Identificador único da atribuição.
id_ordem (FK): Referência à ordem de serviço.
id_funcionario (FK): Referência ao funcionário responsável.
✅ Finalidade: Rastrear qual funcionário executou cada serviço em uma ordem de serviço.

💡 Resumo dos relacionamentos principais:

Um cliente pode ter muitos veículos.
Um veículo pode ter muitas ordens de serviço.
Uma ordem de serviço pode envolver muitos serviços.
Muitos funcionários podem estar envolvidos em muitas ordens (muitos-para-muitos)
