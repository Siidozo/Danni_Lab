## 2. Requisitos

### 2.1 Requisitos Funcionais

**Prioridade:** Alta / Média / Baixa

<table>
<thead>
<tr align="center">
<th width="100px">ID</th>
<th width="650px">Descrição</th>
<th width="100px">Prioridade</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>RF01</strong></td>
<td>Permitir o login de funcionários por meio de código e senha.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RF02</strong></td>
<td>Permitir cadastrar, listar, editar e excluir produtos.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RF03</strong></td>
<td>Gerar automaticamente o código do produto quando não informado.</td>
<td>Média</td>
</tr>
<tr>
<td><strong>RF04</strong></td>
<td>Alertar sobre produtos com estoque igual ou abaixo da quantidade mínima definida.</td>
<td>Média</td>
</tr>
<tr>
<td><strong>RF05</strong></td>
<td>Permitir cadastrar, listar, editar e excluir funcionários.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RF06</strong></td>
<td>Permitir registrar pedidos contendo múltiplos itens.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RF07</strong></td>
<td>Registrar movimentações de estoque (entrada e saída) vinculadas ao produto, funcionário e pedido.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RF08</strong></td>
<td>Exibir o histórico de movimentações de estoque de um produto.</td>
<td>Média</td>
</tr>
<tr>
<td><strong>RF09</strong></td>
<td>Permitir que o usuário navegue entre as diferentes páginas da aplicação.</td>
<td>Média</td>
</tr>
<tr>
<td><strong>RF10</strong></td>
<td>Exibir uma saudação personalizada ao funcionário após o login.</td>
<td>Baixa</td>
</tr>
</tbody>
</table>

### 2.2 Requisitos Não Funcionais

**Prioridade:** Alta / Média / Baixa

<table>
<thead>
<tr align="center">
<th width="100px">ID</th>
<th width="650px">Descrição</th>
<th width="100px">Prioridade</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>RNF01</strong></td>
<td>A API deve ser hospedada em um servidor próprio (VPS), com disponibilidade contínua e gerenciamento do processo por meio do PM2.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RNF02</strong></td>
<td>O acesso ao banco de dados deve ser restrito por meio de uma lista de IPs autorizados.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RNF03</strong></td>
<td>As senhas dos funcionários devem ser armazenadas utilizando hash com bcrypt, nunca em texto puro.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RNF04</strong></td>
<td>A aplicação desktop deve manter uma identidade visual consistente em todas as telas.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RNF05</strong></td>
<td>A API deve utilizar o formato JSON para comunicação e seguir as convenções arquiteturais REST.</td>
<td>Alta</td>
</tr>
<tr>
<td><strong>RNF06</strong></td>
<td>Erros de validação, não localização de recursos e conflitos de dados devem retornar códigos HTTP apropriados, como 400, 404 e 409.</td>
<td>Alta</td>
</tr>
</tbody>
</table>

### 2.3 Restrições

* Na versão atual, não há controle de permissões por tipo de usuário, como administrador e funcionário comum.
* A autenticação atual não utiliza tokens de sessão, como JWT, sendo realizada somente no momento do login.
* A integração com a API da Shopee depende da aprovação do cadastro na Shopee Open Platform, que ainda não foi obtida.
* A comunicação entre a aplicação e a API ocorre via HTTP, sem certificado SSL/TLS nesta fase do projeto.

### 2.4 Tecnologias Utilizadas

| Camada                            | Tecnologia                                        |
| --------------------------------- | ------------------------------------------------- |
| **Frontend**                      | Flutter (Dart) — aplicação desktop para Windows   |
| **Backend**                       | Node.js com framework Express                     |
| **Banco de dados**                | MySQL, gerenciado por meio do phpMyAdmin          |
| **Autenticação de senha**         | bcryptjs — geração e validação de hash de senha   |
| **Hospedagem da API**             | VPS Ubuntu, com PM2 como gerenciador de processos |
| **Testes de API**                 | Insomnia — testes manuais dos endpoints           |
| **Gerenciamento de dependências** | npm                                               |
