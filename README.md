
# Desafio Itaú Junior - API de Transações

Bem-vindo ao repositório do **Desafio Itaú Junior**! Este projeto foi desenvolvido para o processo seletivo do Itaú Unibanco, com o objetivo de criar uma **API REST** para gerenciamento de transações financeiras e cálculo de estatísticas em tempo real. A aplicação utiliza **Java** com **Spring Boot** e segue uma arquitetura limpa, modular e robusta.

## 📖 Sobre o Projeto

A API permite:
- **Cadastrar transações**: Registra transações com valor e data, validando os dados de entrada.
- **Consultar estatísticas**: Calcula estatísticas (soma, média, mínimo, máximo e contagem) com base nas transações registradas.
- **Gerenciamento eficiente**: Processa requisições de forma rápida, com tratamento de erros para entradas inválidas.

O projeto foca em:
- **Código limpo**: Estrutura organizada, legível e fácil de manter.
- **Validações**: Regras de negócio para garantir consistência dos dados.
- **Escalabilidade**: Arquitetura preparada para expansões futuras.
- **Boas práticas**: Injeção de dependências, separação de responsabilidades e tratamento de exceções.

## 🛠 Tecnologias Utilizadas

- **Java**: Versão 17.
- **Spring Boot**: Framework para construção da API REST.
- **Maven**: Gerenciamento de dependências e build.
- **Spring Web**: Para criação de endpoints RESTful.
- **JUnit** (opcional): Para testes unitários (preparado para futura implementação).
- **Lombok** (se usado): Para reduzir boilerplate (com base em padrões comuns).

## 📋 Pré-requisitos

Para rodar o projeto localmente, você precisa ter instalado:
- **Java JDK** 17 ou superior.
- **Maven** 3.6 ou superior.
- **Git** para clonar o repositório.

## 🚀 Como Executar o Projeto

Siga os passos abaixo para rodar a aplicação:

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/pedrohenriquebasilio/Desafio-itau-junior.git
   cd Desafio-itau-junior
   ```

2. **Instale as dependências**:
   ```bash
   mvn clean install
   ```

3. **Execute a aplicação**:
   ```bash
   mvn spring-boot:run
   ```

4. **Acesse a API**:
   A aplicação estará disponível em `http://localhost:8080`. Os endpoints principais são:
   - `POST /transacao`: Cadastra uma nova transação.
     - Exemplo de corpo da requisição:
       ```json
       {
         "valor": 100.50,
         "data": "2025-04-14T10:00:00"
       }
       ```
   - `GET /estatistica`: Retorna estatísticas das transações.
     - Exemplo de resposta:
       ```json
       {
         "soma": 1000.50,
         "media": 200.10,
         "min": 50.00,
         "max": 500.00,
         "contagem": 5
       }
       ```

## 🧪 Executando Testes

O projeto está preparado para inclusão de testes unitários e de integração. Caso sejam adicionados, execute-os com:
```bash
mvn test
```

(Nota: Não há testes nos arquivos fornecidos, mas a estrutura está pronta para futura implementação.)

## 📜 Estrutura do Projeto

O projeto segue uma organização modular, com separação clara entre camadas:

```
Desafio-itau-junior/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/br/transacao_api/
│   │   │       ├── business/
│   │   │       │   ├── services/
│   │   │       │   │   ├── TransacaoService.java    # Lógica de transações
│   │   │       │   │   └── EstatisticasService.java # Cálculo de estatísticas
│   │   │       ├── controller/
│   │   │       │   ├── TransacaoController.java    # Endpoints de transações
│   │   │       │   └── EstatisticasController.java # Endpoints de estatísticas
│   │   │       ├── infrastructure/
│   │   │       │   └── exceptions/
│   │   │       │       └── UnprocessableEntity.java # Exceção personalizada
│   │   │       └── TransacaoApiApplication.java    # Classe principal
│   │   ├── resources/
│   │   │   └── application.properties             # Configurações do Spring
├── pom.xml                                        # Configuração do Maven
└── README.md                                      # Este arquivo
```

### Detalhes das Camadas

- **Controllers** (`TransacaoController`, `EstatisticasController`):
  - Expõem os endpoints REST (`POST /transacao` e `GET /estatistica`).
  - Recebem requisições, delegam para os serviços e retornam respostas.
  - Tratam erros com a exceção `UnprocessableEntity` (status HTTP 422) para entradas inválidas.

- **Services** (`TransacaoService`, `EstatisticasService`):
  - Contêm a lógica de negócio.
  - `TransacaoService`: Valida e processa transações.
  - `EstatisticasService`: Calcula estatísticas em tempo real.

- **Exceptions** (`UnprocessableEntity`):
  - Exceção personalizada para lidar com erros de validação (ex.: dados inválidos ou fora do formato esperado).

## 📈 Funcionalidades Principais

- **Cadastro de transações**:
  - Valida campos obrigatórios (valor e data).
  - Rejeita transações inválidas com erro 422 (Unprocessable Entity).
- **Cálculo de estatísticas**:
  - Retorna soma, média, mínimo, máximo e contagem das transações.
  - Processamento eficiente para respostas rápidas.
- **Tratamento de erros**:
  - Respostas claras e padronizadas para falhas de validação.
  - Uso de exceções personalizadas para maior controle.

## 🔍 Observações

- **Qualidade do código**: O projeto segue padrões de desenvolvimento profissional, com camadas bem definidas e código legível.
- **Extensibilidade**: A estrutura permite adicionar novos endpoints ou funcionalidades sem grandes mudanças.
- **Validações robustas**: Garantem que apenas dados válidos sejam processados.
- **Performance**: Otimizado para lidar com requisições em tempo real.

## 🤝 Contribuições

Este projeto foi criado para um desafio técnico, mas sugestões são bem-vindas! Para contribuir:
1. Faça um fork do repositório.
2. Crie uma branch para sua feature (`git checkout -b feature/nova-funcionalidade`).
3. Commit suas mudanças (`git commit -m "Adiciona nova funcionalidade"`).
4. Envie para o repositório remoto (`git push origin feature/nova-funcionalidade`).
5. Abra um Pull Request.

## 📬 Contato

Desenvolvido por **Pedro Henrique Basílio**.  
LinkedIn: [linkedin.com/in/pedrohenriquebasilio](https://linkedin.com/in/pedrohenriquebasilio)  
E-mail: pedrohenriquebasilio@example.com

## 🙌 Agradecimentos

Agradeço ao Itaú Unibanco pela oportunidade de participar do desafio e aplicar meus conhecimentos em um projeto real!

---
