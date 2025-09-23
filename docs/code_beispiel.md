```py title="pygame" linenums="1"

import pygame

import random

class Ball:
    def __init__(self):
        self.x = 300
        self.y = 220
        self.radius = 40
        self.color = (255,140,0)
        self.movex = random.randint(-3,3)
        self.movey = random.randint(-3,3)

    def draw(self):
        pygame.draw.ellipse(screen, ball.color, [ball.x, ball.y, ball.radius, ball.radius])



pygame.init()

ball = Ball()
ball2 = Ball()

#Farben

orange = (255, 140, 0)

white = (255, 255, 255)

#spielfeld

fensterbreite = 640

fenstehoehe = 480

#spielfenster

screen = pygame.display.set_mode((fensterbreite, fenstehoehe))
clock = pygame.time.Clock()
pygame.display.set_caption("Götz stinkt nach Maggi")


gameon = True

while gameon:

    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            gameon = False



    ball.x += ball.movex
    ball.y += ball.movey

    if ball.x - ball.radius <= 0 or ball.x + ball.radius >= fensterbreite:
        ball.movex *= -1
    
    if ball.y - ball.radius <= 0 or ball.y + ball.radius >= fenstehoehe:
        ball.movey *= -1
    



    screen.fill(white)
    pygame.draw.ellipse(screen, ball.color, [ball.x, ball.y, ball.radius, ball.radius])

    #Fenster aktualisieren

    pygame.display.flip()

#Refresh-Timer
    clock.tick(60)


pygame.quit()
```