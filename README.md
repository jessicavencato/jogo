import pygame
import sys
import random

# Inicializa o PyGame
pygame.init()

# Configurações da tela
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Jogo de Aventura")

# Cores
black = (0, 0, 0)
white = (255, 255, 255)
red = (255, 0, 0)

# Classe Personagem
class Personagem:
    def __init__(self):
        self.x = screen_width // 2
        self.y = screen_height // 2
        self.size = 50

    def mover(self, dx, dy):
        self.x += dx
        self.y += dy

    def desenhar(self):
        pygame.draw.rect(screen, white, (self.x, self.y, self.size, self.size))

# Classe Inimigo
class Inimigo:
    def __init__(self):
        self.x = random.randint(0, screen_width)
        self.y = random.randint(0, screen_height)
        self.size = 50

    def desenhar(self):
        pygame.draw.rect(screen, red, (self.x, self.y, self.size, self.size))

# Função para mostrar o menu
def mostrar_menu():
    font = pygame.font.Font(None, 74)
    texto = font.render("Pressione Enter para Jogar", True, white)
    screen.blit(texto, (screen_width // 2 - 300, screen_height // 2 - 50))

# Função para iniciar o jogo
def iniciar_jogo():
    personagem = Personagem()
    inimigos = [Inimigo() for _ in range(5)]

    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        # Movimentação do personagem
        keys = pygame.key.get_pressed()
        if keys[pygame.K_LEFT]:
            personagem.mover(-5, 0)
        if keys[pygame.K_RIGHT]:
            personagem.mover(5, 0)
        if keys[pygame.K_UP]:
            personagem.mover(0, -5)
        if keys[pygame.K_DOWN]:
            personagem.mover(0, 5)

        # Atualiza a tela
        screen.fill(black)
        personagem.desenhar()
        for inimigo in inimigos:
            inimigo.desenhar()

        pygame.display.flip()

# Função principal
def main():
    while True:
        mostrar_menu()
        pygame.display.flip()

        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()
            if event.type == pygame.KEYDOWN:
                if event.key == pygame.K_RETURN:  # Inicia o jogo ao pressionar Enter
                    iniciar_jogo()

# Executa a função principal
if __name__ == "__main__":
    main()
