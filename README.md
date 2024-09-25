# Nome do Projeto

Descrição breve do que o projeto faz e seu objetivo.


## Tecnologias Usadas
- Python
- PyGame


## Funcionalidades

- Função 1: iniciar_jogo()

**Descrição**:  
A função iniciar_jogo() é responsável por inicializar os componentes principais do jogo, como a tela e as variáveis de controle. Ela configura a tela onde o jogo será exibido, 
define os parâmetros iniciais (como a posição do jogador, o fundo e os elementos da interface) e dá início ao loop principal de execução. Essa função prepara o ambiente do jogo 
antes que a ação comece.

**Parâmetros**: Nenhum.

**Retorno**: Nenhum.

**Exemplo de uso**:
def iniciar_jogo():
    pygame.init()
    tela = pygame.display.set_mode((largura, altura))
    # Outras configurações iniciais do jogo

- Função 2: desenhar_menu()

**Descrição**: A função desenhar_menu() é responsável por exibir o menu principal do jogo na tela. O menu pode incluir opções como "Iniciar Jogo", "Configurações", e "Sair". Essa
função desenha todos os elementos gráficos do menu e também trata as entradas do usuário para navegar entre as opções disponíveis. Ela será chamada sempre que o jogador estiver no
estado de menu.

**Parâmetros**: Nenhum.

**Retorno**: Nenhum.

**Exemplo de uso**:
def desenhar_menu():
    # Desenhar fundo e opções de menu
    tela.blit(fundo, (0, 0))
    # Lógica de interação com o menu


- Função 3: 'verificar_colisoes()'

**Descrição**:  A função verificar_colisoes() é responsável por detectar colisões entre os elementos do jogo, como o jogador e os inimigos ou obstáculos. Ela verifica se os objetos 
colidem durante o jogo e executa ações apropriadas, como diminuir a vida do jogador, finalizar o jogo ou remover um inimigo da tela. Essa função é fundamental para o funcionamento 
da mecânica do jogo.

**Parâmetros**: 
- `jogador`: objeto representando o jogador.
- `inimigos`: lista de objetos representando os inimigos.

**Retorno**:  
- Retorna `True` se houver uma colisão, ou `False` caso contrário.

**Exemplo de uso**:
def verificar_colisoes(jogador, inimigos):
    for inimigo in inimigos:
        if jogador.rect.colliderect(inimigo.rect):
            return True
    return False


## Como Instalar

Instruções para instalar as dependências do projeto:

pip install pygame


Como Jogar
Instruções sobre como iniciar o jogo e controles:

Pressione Enter para começar.
Use as teclas de seta para mover o personagem.


## Código do Jogo
O código do jogo está disponível no arquivo [jogo.py](jogo.py).

