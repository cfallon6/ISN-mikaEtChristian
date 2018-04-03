# ISN-mikaEtChristian
#Projet final d'ISN

import pygame


pygame.init()
fenetre = pygame.display.set_mode((1024, 768))
fond = pygame.image.load("Mastermind2.png").convert()
fenetre.blit(fond, (0,0))


blue = (0,0,255)
red = (255,0,0)
green = (0,255,0)
pink = (255,144,210)
purple = (128,0,128)
yellow = (255,255,0)
white = (255,255,255)
orange = (230,126,34)
black = (0,0,0)
grey = (128,128,128)

pygame.draw.rect(fenetre, black, (256,0,512,768))
pygame.draw.rect(fenetre, grey, (297,51,5,660))
pygame.draw.rect(fenetre, grey, (297,51,389,5))
pygame.draw.rect(fenetre, grey, (297,706,430,5))
pygame.draw.rect(fenetre, grey, (681,51,5,660))
pygame.draw.rect(fenetre, grey, (297,111,430,5))
pygame.draw.rect(fenetre, grey, (727,111,5,600))

y=172
for loop in range(9):
    pygame.draw.rect(fenetre, grey, (297,y,430,1))
    y=y+60

redCircle = pygame.draw.circle(fenetre, red, (288,743), 20, 0)
pygame.draw.circle(fenetre, orange, (352,743), 20, 0)
pygame.draw.circle(fenetre, yellow, (416,743), 20, 0)
pygame.draw.circle(fenetre, green, (480,743), 20, 0)
pygame.draw.circle(fenetre, blue, (544,743), 20, 0)
pygame.draw.circle(fenetre, purple, (608,743), 20, 0)
pygame.draw.circle(fenetre, pink, (672,743), 20, 0)
pygame.draw.circle(fenetre, white, (736,743), 20, 0)


height = 682
width = 345
for loop in range(10):
    for loop in range(4):
        x = width
        pygame.draw.circle(fenetre, white, (x,height), 20, 1)
        width = width+97
    height = height-60
    width = width-388

pygame.display.flip()

if pygame.mouse.get_pressed()[0] and redCircle.collidepoint(pygame.mouse.get_pos()):
    pygame.draw.circle(fenetre, red, (345, 682), 20, 0)
    pygame.display.flip


running = True
try:
    while running:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False
    pygame.quit()
except SystemExit:
    pygame.quit()
