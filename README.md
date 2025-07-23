# Simulador de Autenticação FPGA

Um simulador web interativo que reproduz um sistema de autenticação baseado em sequência visual, inspirado na placa FPGA Altera DE2-115.

## 🎯 Sobre o Projeto

Este projeto simula um sistema de autenticação onde o usuário deve observar uma sequência de LEDs piscando e reproduzir a mesma sequência usando botões numerados. É uma representação visual e interativa de como seria implementar tal sistema em uma FPGA real.

## ✨ Características

- **Interface Visual Realística**: Simula a aparência da placa Altera DE2-115
- **Sistema de Desafio-Resposta**: Sequência aleatória de 4 LEDs
- **Tempo Limitado**: 10 segundos para inserir a resposta
- **Feedback Visual**: LEDs, LCD simulado e indicadores de tempo
- **Design Responsivo**: Funciona em diferentes tamanhos de tela

## 🚀 Como Usar

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/seu-usuario/simulador-fpga-auth.git
   cd simulador-fpga-auth
   ```

2. **Execute o simulador**:
   - Abra o arquivo `index.html` em qualquer navegador web moderno
   - Ou use um servidor local:
     ```bash
     python -m http.server 8000
     # Acesse http://localhost:8000
     ```

3. **Interaja com o sistema**:
   - Clique em "Iniciar Autenticação"
   - Observe a sequência de LEDs que piscam
   - Reproduza a sequência clicando nos botões numerados (1-4)
   - Você tem 10 segundos para completar a sequência

## 🎮 Como Funciona

### Fluxo de Autenticação

1. **Geração do Desafio**: Uma sequência aleatória de 4 LEDs é gerada
2. **Apresentação Visual**: Os LEDs piscam em sequência para mostrar o padrão
3. **Entrada do Usuário**: O usuário deve reproduzir a sequência usando os botões
4. **Validação**: O sistema verifica se a sequência está correta
5. **Resultado**: Sucesso (autenticado) ou falha (sequência incorreta/tempo esgotado)

### Estados do Sistema

- **Idle**: Aguardando início da autenticação
- **Gerando**: Criando sequência de desafio
- **Apresentando**: Mostrando sequência nos LEDs
- **Aguardando**: Esperando resposta do usuário
- **Validando**: Verificando resposta
- **Finalizado**: Mostrando resultado (sucesso/falha)

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Estrutura da página
- **CSS3**: Estilização e animações
- **JavaScript (ES6+)**: Lógica do simulador
- **Google Fonts**: Fonte Roboto Mono para aparência técnica

## 🎨 Componentes Simulados

### Hardware da DE2-115
- **LCD Display**: Mostra status e mensagens do sistema
- **LEDs Vermelhos (LEDR)**: 4 LEDs para apresentação da sequência
- **Botões (KEY)**: 4 botões numerados para entrada do usuário
- **Timer**: Contador regressivo de 10 segundos

### Estados Visuais
- LEDs apagados (vermelho escuro)
- LEDs acesos (vermelho brilhante com efeito glow)
- Botões habilitados/desabilitados
- Feedback de cor no display LCD

## 📁 Estrutura do Projeto

```
simulador-fpga-auth/
├── index.html          # Arquivo principal com HTML, CSS e JavaScript
├── README.md          # Este arquivo
└── screenshots/       # Capturas de tela (opcional)
```

## 🔧 Personalização

### Modificar Parâmetros
```javascript
const TAMANHO_DESAFIO = 4;           // Quantidade de LEDs na sequência
const TEMPO_LIMITE_SEGUNDOS = 10;    // Tempo limite em segundos
```

### Alterar Cores
As cores podem ser modificadas nas variáveis CSS:
```css
.simulated-led.on {
    background-color: #FF0000;        /* Cor do LED aceso */
    box-shadow: 0 0 15px #FF0000;     /* Efeito glow */
}
```

## 👥 Autor

[@GabrielRMaciel](https://github.com/GabrielRMaciel)

## 🙏 Agradecimentos

- Inspirado na placa FPGA Altera DE2-115
- Comunidade de desenvolvedores de sistemas embarcados
- Recursos de design da Google Fonts

---

**Nota**: Este é um simulador educacional e não representa uma implementação de segurança real. Para sistemas de autenticação em produção, considere métodos criptográficos adequados.
