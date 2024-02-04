import pygame
import sys

# Inicializar Pygame
pygame.init()

# Configuración de la pantalla
width, height = 300, 600
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Tetris")

# Colores
black = (0, 0, 0)
white = (255, 255, 255)
blue = (0, 0, 255)

# Definir la cuadrícula del juego
grid = [[0] * 10 for _ in range(20)]

# Definir pieza de Tetris
piece = [[1, 1, 1, 1]]

# Función para dibujar la cuadrícula
def draw_grid():
    for row in range(20):
        for col in range(10):
            color = white if grid[row][col] == 0 else blue
            pygame.draw.rect(screen, color, [col * 30, row * 30, 30, 30], 0)

# Función principal del juego
def main():
    clock = pygame.time.Clock()

    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        # Lógica del juego

        # Dibujar la cuadrícula y la pieza
        screen.fill(black)
        draw_grid()

        pygame.display.flip()
        clock.tick(30)

if _name_ == "_main_":
    main()
