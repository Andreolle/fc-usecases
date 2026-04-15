# Clean Architecture: Use Cases para a Entidade Product

Implementação dos casos de uso (CRUD) para a entidade **Product** seguindo os princípios de Clean Architecture, com testes de unidade e integração.

## Pré-requisitos

- [Node.js](https://nodejs.org/) v18 ou superior
- npm v8 ou superior

## Instalação

```bash
npm install
```

## Rodando os testes

### Todos os testes

```bash
npm test
```

### Apenas testes de unidade e integração (sem type-check)

```bash
npx jest
```

### Testes com cobertura

```bash
npm run test:coverage
```

### Testes de um Use Case específico

```bash
# Create
npx jest src/usecase/product/create/ --no-coverage

# Find
npx jest src/usecase/product/find/ --no-coverage

# List
npx jest src/usecase/product/list/ --no-coverage

# Update
npx jest src/usecase/product/update/ --no-coverage
```

## Use Cases implementados

| Use Case | Descrição | Unit Test | Integration Test |
|----------|-----------|-----------|-----------------|
| Create | Criação de um produto | `create.product.unit.spec.ts` | `create.product.integration.spec.ts` |
| Find | Busca de um produto por ID | `find.product.unit.spec.ts` | `find.product.integration.spec.ts` |
| List | Listagem de todos os produtos | `list.product.unit.spec.ts` | `list.product.integration.spec.ts` |
| Update | Atualização dos dados de um produto | `update.product.unit.spec.ts` | `update.product.integration.spec.ts` |

## Estrutura do projeto

```
src/
├── domain/
│   └── product/
│       ├── entity/
│       │   ├── product.interface.ts
│       │   ├── product.ts
│       │   └── product-b.ts
│       ├── factory/
│       │   └── product.factory.ts
│       └── repository/
│           └── product-repository.interface.ts
├── infrastructure/
│   └── product/
│       └── repository/
│           └── sequelize/
│               ├── product.model.ts
│               └── product.repository.ts
└── usecase/
    └── product/
        ├── create/
        ├── find/
        ├── list/
        └── update/
```
