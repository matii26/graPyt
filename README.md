# graPyt

import pygame
pygame.init()

oknoGry = pygame.display.set_mode((400,300))

run = True

zegar = pygame.time.Clock()


x=300
y=100
x_p=20
y_p=20
while run:
    oknoGry.fill("grey")
    rakietka = pygame.Rect((x, y, 10, 20))
    pygame.draw.circle(oknoGry,(255,0,0),(x_p,y_p),10,4)
    pygame.draw.rect(oknoGry,(23,123,233),rakietka)
    for event in pygame.event.get():
        print(event)
        if event.type == pygame.QUIT:
            run = False
        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_a:
                x = x-10
            if event.key == pygame.K_d:
                x = x+10

    x_p+=1
    y_p+=1
    pygame.display.update()
    zegar.tick(60)
