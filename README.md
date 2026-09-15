# Calculadora de IMC

Aplicativo mobile feito em **Flutter** que calcula o Índice de Massa Corporal (IMC) do usuário e exibe a classificação detalhada segundo a OMS — de *Magreza grave* a *Obesidade Grau III*. Projeto leve, sem dependências externas além do SDK do Flutter, ideal como referência de estudo para quem está começando com o framework.

---

## Funcionalidades

- Campos de entrada para peso (kg) e altura (m ou cm)
- Conversão automática de altura: aceita tanto `1.75` quanto `175`
- Tratamento de entrada com vírgula (`75,5` → `75.5`)
- Validação com feedback visual via SnackBar quando os campos estão vazios ou inválidos
- Resultado exibido em AlertDialog com o valor do IMC e a classificação
- Tabela de referência com todas as 8 faixas de classificação integrada na tela principal
- Botão de limpar para resetar os campos

## Classificações do IMC

| Faixa | Classificação |
|---|---|
| < 16 | Magreza grave |
| 16 – 16.9 | Magreza moderada |
| 17 – 18.4 | Magreza leve |
| 18.5 – 24.9 | Saudável |
| 25 – 29.9 | Sobrepeso |
| 30 – 34.9 | Obesidade Grau I |
| 35 – 39.9 | Obesidade Grau II (severa) |
| ≥ 40 | Obesidade Grau III (mórbida) |

## Stack

| Camada | Tecnologia |
|---|---|
| Framework | Flutter (Dart SDK ≥ 3.10.8) |
| UI | Material Design 3 |
| Gerenciamento de estado | `setState` (StatefulWidget) |
| Dependências externas | Nenhuma |

## Estrutura do Projeto

```
lib/
├── main.dart                      # Ponto de entrada, configuração do MaterialApp
└── Screens/
    └── imc_page_widget.dart       # Tela principal: formulário, cálculo, tabela e resultado
```

O projeto segue uma estrutura simples de uma única tela. Toda a lógica de cálculo, validação e classificação está em `imc_page_widget.dart`, que contém o `StatefulWidget` principal e um widget auxiliar `_TabelaRow` para renderizar as linhas da tabela de classificação.

## Pré-requisitos

- **Flutter SDK** 3.10.8 ou superior
- **Dart SDK** 3.10.8 ou superior (incluído no Flutter)
- Um emulador Android/iOS ou dispositivo físico conectado

Para verificar se o ambiente está pronto:

```bash
flutter doctor
```

## Como Executar

```bash
# 1. Clonar o repositório
git clone https://github.com/seu-usuario/calculadora_imc_flutter.git
cd calculadora_imc_flutter

# 2. Instalar dependências
flutter pub get

# 3. Rodar no emulador ou dispositivo conectado
flutter run
```

### Outras plataformas

O projeto inclui os targets padrão do Flutter, então também pode ser executado em web, desktop Linux, Windows e macOS:

```bash
flutter run -d chrome     # Web
flutter run -d windows    # Windows
flutter run -d linux      # Linux
flutter run -d macos      # macOS
```

## Como Funciona

```
Usuário digita peso e altura
        │
        ▼
  Validação dos campos
  (vazios ou ≤ 0 → SnackBar de erro)
        │
        ▼
  Altura > 3? Converte de cm para m
        │
        ▼
  Calcula IMC = peso / (altura²)
        │
        ▼
  Classifica o resultado em 8 faixas
        │
        ▼
  Exibe AlertDialog com IMC e classificação
```

## Possíveis Melhorias

- Histórico de cálculos com persistência local (SharedPreferences ou SQLite)
- Temas claro/escuro
- Gráfico de evolução do IMC ao longo do tempo
- Internacionalização (i18n) para inglês e espanhol
- Testes unitários para a lógica de classificação

## Licença

Este projeto é de uso livre para fins de estudo e aprendizado.
