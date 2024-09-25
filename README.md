# JOGO

Descrição breve do que o projeto faz e seu objetivo.


## Tecnologias Usadas
- Python
- PyGame


## Funcionalidades

- Função 1: mostrar_menu()

Descrição:
Essa função exibe o menu inicial na tela, onde o jogador é instruído a pressionar "Enter" para iniciar o jogo. Ela desenha um texto centralizado na tela utilizando uma fonte
predefinida. O menu serve como uma interface de espera até que o jogador esteja pronto para iniciar o jogo.

Parâmetros: Nenhum.

Retorno: Nenhum.

Exemplo de uso:

def mostrar_menu():
    font = pygame.font.Font(None, 74)
    texto = font.render("Pressione Enter para Jogar", True, white)
    screen.blit(texto, (screen_width // 2 - 300, screen_height // 2 - 50))


- Função 2: iniciar_jogo()

**Descrição**:  

A função iniciar_jogo() é a responsável por iniciar e controlar a lógica principal do jogo. Ela cria uma instância do personagem jogável e uma lista de inimigos. Dentro de um 
loop infinito, a função escuta eventos, movimenta o personagem com base nas teclas pressionadas, atualiza o desenho do personagem e dos inimigos na tela, e mantém o jogo rodando 
até que o jogador feche a janela.

**Parâmetros**: Nenhum.

**Retorno**: Nenhum.

**Exemplo de uso**:
def iniciar_jogo():
    personagem = Personagem()
    inimigos = [Inimigo() for _ in range(5)]
    
    while True:
        # Lógica do jogo
        pygame.display.flip()


- Função 3: main()

**Descrição**:  

A função main() é o ponto de entrada principal do jogo. Ela exibe o menu inicial chamando a função mostrar_menu(), e aguarda que o jogador pressione a tecla "Enter" para
iniciar o jogo, momento em que a função `iniciar_jogo()` é chamada. Também verifica se o jogador deseja fechar o jogo, tratando o evento de saída do PyGame.

**Parâmetros**: Nenhum.

**Retorno**: Nenhum.

**Exemplo de uso**:
def main():
    while True:
        mostrar_menu()
        pygame.display.flip()
        
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()
            if event.type == pygame.KEYDOWN:
                if event.key == pygame.K_RETURN:
                    iniciar_jogo()

Essas três funções desempenham papéis essenciais no controle do fluxo do jogo e da interface do usuário. O main() é responsável pelo loop inicial, enquanto iniciar_jogo() gerencia 
a lógica principal do jogo. A função mostrar_menu() apresenta a interface para começar o jogo.


## Como Instalar

Instruções para instalar as dependências do projeto:

pip install pygame


## Como Jogar

Instruções sobre como iniciar o jogo e controles:

Pressione Enter para começar.
Use as teclas de seta para mover o personagem.


## Código do Jogo
O código do jogo está disponível no arquivo [jogo.py](jogo.py).

