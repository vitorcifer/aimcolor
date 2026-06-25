[README.md](https://github.com/user-attachments/files/29355280/README.md)
# exilium Engine - aim color

Este é um programa de auxílio de mira por cor e auregobot desenvolvido em C#, python e assembly que roda nativamente no Windows. Ele oferece alta performance, baixíssima latência (utilizando ponteiros e `LockBits` para escaneamento de tela) e um design moderno premium nas cores **Preto e Vermelho**.

## Como Compilar

Caso faça alterações no código principal (`exilium.cs`), você pode recompilar o executável de duas formas:

1. **Via Script de Build:**
   Dê dois cliques no arquivo `build.bat` presente na pasta. Ele compilará o programa usando o compilador oficial C# do Windows instalado no seu computador.

2. **Via Linha de Comando (PowerShell/CMD):**
   ```cmd
   C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe /target:winexe /unsafe /r:System.dll /r:System.Drawing.dll /r:System.Windows.Forms.dll /out:exilium.exe exilium.cs
   ```

---

## Funcionalidades e Configurações da HUD

O programa é dividido nas seguintes seções:

### 1. Seleção de Cor
- **Cor de Alvo (R/G/B):** Define a cor exata em canais RGB que a mira deve seguir (por padrão, roxo/rosa `250, 100, 250`).
- **Tolerância:** Controla o quanto a cor na tela pode variar da cor alvo (quanto maior o valor, mais tons da cor serão aceitos).
- **Capturar Cor da Tela (F10):** Clique no botão, posicione o mouse sobre a cor que deseja seguir e aperte **F10** para travar a cor. O programa atualizará a prévia visual e as coordenadas de cor automaticamente.

### 2. Área de Busca (FOV) e Suavização
- **Raio de Busca (FOV):** Define o raio (em pixels) do círculo de busca ao redor do centro da sua tela.
- **Grossura Linha FOV:** Ajusta a espessura da linha do círculo de sobreposição na tela (de 1 a 10 pixels).
- **Suavização (Velocidade):** Controla a velocidade de movimento da mira em direção ao alvo (valores mais baixos oferecem movimentos mais naturais).
- **Cor do Círculo FOV:** Escolha a cor do círculo exibido na tela (Vermelho Neon, Verde Neon, Azul Neon, Amarelo Neon, Rosa Neon ou Branco).

### 3. Gatilho e Sistema
- **Tecla de Ativação / Modo do Gatilho:** Define a tecla física e o comportamento (Pressionar/Hold vs Alternar/Toggle) para habilitar a mira.
- **Mostrar FOV:** Exibe um círculo transparente sobreposto na tela representando os limites de busca.
- **Ativar auregobot (Auto-Clique):** Quando ativado, o programa fará um clique esquerdo automático no mouse (`mouse_event`) sempre que o alvo de cor detectado estiver diretamente sobre o centro da sua mira (com um delay de segurança interno de 180ms para simular um comportamento humano).

### 4. Controle Geral e Persistência
- **INICIAR/PARAR MOTOR:** Ativa ou desativa o monitoramento. Ao ativar, o botão pulsa em cor vermelha indicando estado ONLINE.
- **SALVAR CONFIGS:** Grava todas as configurações atuais (cores, fov, velocidade, teclas, estados dos checkboxes) no arquivo `config.txt` local.
- **Carregamento Automático:** Sempre que o programa é aberto, ele carrega automaticamente as configurações salvas em `config.txt`.
- **Salvar ao Sair:** As configurações também são salvas de forma transparente ao fechar a janela.

---

## Observações Importantes

> [!TIP]
> - **Execute como Administrador**: Jogos com sistemas de proteção ou rodando com privilégios elevados bloqueiam o movimento e cliques do mouse sintéticos. Se o programa não estiver movendo ou clicando no seu jogo, feche-o e execute-o clicando com o botão direito e selecionando **"Executar como Administrador"**. A HUD exibirá a tag `(ADMIN)` na barra de título quando o privilégio estiver correto!
