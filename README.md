# JOGO

Descrição breve do que o projeto faz e seu objetivo.


## Tecnologias Usadas
- Python
- PyGame


## Funcionalidades

- Função 1: mostrar_menu()

**Descrição**:

Essa função exibe o menu inicial na tela, onde o jogador é instruído a pressionar "Enter" para iniciar o jogo. Ela desenha um texto centralizado na tela utilizando uma fonte
predefinida. O menu serve como uma interface de espera até que o jogador esteja pronto para iniciar o jogo.

**Parâmetros**: Nenhum.

**Retorno**: Nenhum.

**Exemplo de uso**:
```python
def mostrar_menu():
    font = pygame.font.Font(None, 74)
    texto = font.render("Pressione Enter para Jogar", True, white)
    screen.blit(texto, (screen_width // 2 - 300, screen_height // 2 - 50))
```

- Função 2: iniciar_jogo()

**Descrição**:  

A função iniciar_jogo() é a responsável por iniciar e controlar a lógica principal do jogo. Ela cria uma instância do personagem jogável e uma lista de inimigos. Dentro de um 
loop infinito, a função escuta eventos, movimenta o personagem com base nas teclas pressionadas, atualiza o desenho do personagem e dos inimigos na tela, e mantém o jogo rodando 
até que o jogador feche a janela.

**Parâmetros**: Nenhum.

**Retorno**: Nenhum.

**Exemplo de uso**:
``python
def iniciar_jogo():
    personagem = Personagem()
    inimigos = [Inimigo() for _ in range(5)]
    
    while True:
        # Lógica do jogo
        pygame.display.flip()
