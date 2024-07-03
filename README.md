# Turma: 6CLDR

# Disciplina: ORQUESTRAÇÃO KUBERNETES E CONTAINERS

# Professor: KLEBER SANTOS DE CARVALHO

# Estudo de Caso: Modernização de Aplicação Monolítica para Kubernetes

A modernização de uma aplicação monolítica para o Kubernetes pode ser um processo significativo que envolve a reestruturação da aplicação para tirar proveito das capacidades de orquestração de contêineres, melhorando a escalabilidade, a disponibilidade e a gestão de recursos. Com isso, considerando o conteúdo transmitido até a última aula, realize uma proposta de modernização para a seguinte aplicação.

## Aplicação Monolítica: Sistema de E-commerce

O cenário As-Is contempla um sistema de e-commerce clássico que opera como uma aplicação monolítica. Esta aplicação inclui várias funcionalidades principais, como:

- **Interface de usuário (frontend)**
- **Gerenciamento de produtos**
- **Processamento de pedidos**
- **Gestão de clientes**
- **Sistema de pagamento**
- **Administração do site**

Todos esses componentes são empacotados em uma única base de código e executadas como um único serviço. Isso facilita o desenvolvimento, a implantação e a gestão inicial, mas rapidamente se torna um gargalo à medida que a aplicação cresce em complexidade e uso.

## Modernização para Kubernetes

A modernização dessa aplicação para o Kubernetes envolve a decomposição da monolítica em microsserviços. Cada funcionalidade principal da aplicação é transformada em um serviço independente, permitindo que sejam desenvolvidos, implantados e escalados de forma independente. Para tanto, elabore uma abordagem passo a passo para a modernização conforme roteiro abaixo, considerando como cada recurso ou característica do Kubernetes pode ser aplicada em fase, ou seja, cada Fase descrita abaixo representa um “o quê” é necessário para realizar uma modernização para este estudo de caso, portanto, é esperado que o aluno preencha o “como” baseado na oferta de recursos que o Kubernetes dispõe:

## Fase 1

Análise e Planejamento: Avalie a aplicação monolítica para identificar componentes que podem ser separados em microsserviços. Este passo envolve a compreensão profunda da aplicação e de suas dependências internas. Com base nos recursos que o Kubernetes dispões, qual seria sua proposta para tratar esse caso?

## Fase 2

Definição de Microsserviços: Defina os limites dos microsserviços com base nas funcionalidades da aplicação. Por exemplo, você pode ter serviços separados para "Gerenciamento de Produtos", "Processamento de Pedidos", "Gestão de Clientes", etc. Com base nos recursos que o Kubernetes dispões, qual seria sua proposta para tratar esse caso?

## Fase 3

Criação de Containers: Cada microsserviço é conteinerizado, ou seja, é empacotado com todas as suas dependências em um contêiner. Isso garante a consistência e a portabilidade em diferentes ambientes de execução. Com base nos recursos que o Kubernetes dispões, qual seria sua proposta para tratar esse caso?

## Fase 4

Orquestração com Kubernetes: Utilize o Kubernetes para gerenciar o deployment, a escalabilidade e a operação dos contêineres dos microsserviços. O Kubernetes permite definir como os serviços interagem, como são expostos para o mundo externo, e como os recursos são alocados. Com base nos recursos que o Kubernetes dispões, qual seria sua proposta para tratar esse caso ?

## Proposta de Modernização

### Objetivos da Modernização

1. **Melhorar a Escalabilidade:** A capacidade de escalar componentes individuais da aplicação conforme a demanda.
2. **Aumentar a Disponibilidade:** Garantir alta disponibilidade através de uma arquitetura resiliente.
3. **Otimizar a Gestão de Recursos:** Utilização eficiente dos recursos de computação.

### Estrutura Recomendada

A modernização envolve a divisão da aplicação monolítica em microserviços independentes, cada um gerenciado pelo Kubernetes. A seguir está uma proposta de arquitetura para a nova aplicação:

#### Microserviços

1. **User Interface (Frontend) Service**

   - Gerencia a interface de usuário.
   - Escala conforme o tráfego de usuários.

2. **Product Management Service**

   - Lida com o catálogo de produtos.
   - Pode ser escalado conforme o número de consultas e atualizações de produtos.

3. **Order Processing Service**

   - Processa e gerencia os pedidos.
   - Escalável de acordo com o volume de pedidos.

4. **Customer Management Service**

   - Gerencia informações dos clientes.
   - Escalável conforme a base de clientes cresce.

5. **Payment Processing Service**

   - Processa transações de pagamento.
   - Garantia de alta disponibilidade e segurança.

6. **Admin Interface (Site Administration) Service**

   - Interface e lógica administrativa.
   - Escalável conforme necessário.

7. **Authentication and Authorization Service**

   - Gerencia a autenticação e autorização dos usuários.
   - Escalável para garantir segurança e acesso apropriado.

8. **Notification Service**

   - Lida com notificações para usuários e administradores.
   - Escalável para suportar vários canais de notificação (e-mail, SMS, push notifications).

9. **Inventory Management Service**

   - Gerencia o estoque de produtos.
   - Escalável para atualizar e monitorar o inventário em tempo real.

10. **Shipping and Logistics Service**
    - Gerencia o envio e logística dos pedidos.
    - Escalável para otimizar rotas e acompanhar entregas.

### Kubernetes Components

- **Pods:** Cada microserviço será implementado em um ou mais pods.
- **Services:** Serviços do Kubernetes para gerenciar a descoberta e balanceamento de carga entre os pods.
- **Deployments:** Gerenciamento das atualizações de versão dos microserviços.
- **Ingress Controller:** Gerenciamento de acesso externo aos microserviços.
- **ConfigMaps e Secrets:** Armazenamento de configurações e informações sensíveis.
