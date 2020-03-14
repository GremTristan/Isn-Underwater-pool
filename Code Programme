import time
import random
import pygame
pygame.init()


## load ressource (personnage , bateau , background )

blue = (113,122,255)
white =(255,255,255)
fenetreW = 1000
fenetreH = 720
turtelW = 50
turtelH = 10
NavirW = 100
NavirH = 200
Navir = pygame.image.load('img/NAVIRE.png')
bg = pygame.image.load('img/background.jpg')
hugo= pygame.image.load('img/turtel.png')
bateau = pygame.transform.scale(Navir,(220,190))
tortue = pygame.transform.scale(hugo, (50, 30))
fenetre = pygame.display.set_mode((fenetreW,fenetreH))
horloge = pygame.time.Clock()

pygame.display.set_caption("Underwater")









## Fonction pour quitter ou pour rejouer

def rejouOuQuitte ():
    for event in pygame.event.get ([pygame.KEYDOWN, pygame.KEYUP, pygame.QUIT]):
        if event.type == pygame.QUIT:
            pygame.quit()
        elif event.type == pygame.KEYUP:
            continue
        return event.key










## Fontion qui parametre le texte police et texte

def creaTextObjet (texte , police):
    texteSurface = police.render(texte,True,white)
    return texteSurface, texteSurface.get_rect()








##Fontion qui crée les texte de game over et (appuyer pour rejouer ) indiquer la police et la taille , et crée l'apparition du message

def message (texte):
    GTexte = pygame.font.Font('font/Second.ttf',150)
    Ptexte = pygame.font.Font('font/Second.ttf ', 100)


    GtexteSurf,GTexteRect = creaTextObjet (texte, GTexte)
    GTexteRect.center = fenetreW/2 , ((fenetreH/2)-50)
    fenetre.blit(GtexteSurf, GTexteRect)
    PtexteSurf,PtexteRect = creaTextObjet("appuyer sur une touche pour continuer",Ptexte)
    PtexteRect.center = fenetreW / 2 , ((fenetreH / 2) + 50)
    fenetre.blit ( PtexteSurf, PtexteRect )

    pygame.display.update()
    time.sleep(2)
    while rejouOuQuitte() == None:
        horloge.tick()
        corps_game()











## Fonction lorsque l'on perd on appele la fonction message crée au dessus

def game0ver ():
    message("Perdu!!!")










## Fonction du personnage principal du jeux
def perso (x,y,image):
    fenetre.blit(image, (x, y))











## Fonction principale du jeux qui permet de mettre en lien les autres fonction et de parametrer les touches ect

def corps_game ():


    perso_x = 150
    perso_y = 400                  ## initie les coordonnées au seron afficher les images qui sont les personnages du jeux
    mvt_y = 0
    mvt_x = 0
    Navir_x =200
    Navir_y = 150


    fin_game = False

    while not  fin_game :
        fenetre.blit(bg , (0, 10))
        pygame.display.flip()                         ## boucle du jeux ( tant que la valeur de fin_game ne passe pas en True alors afficher les fonctions
        perso ( perso_x, perso_y ,tortue )
        fenetre.blit(bateau,(Navir_x,Navir_y))



        if perso_y > fenetreH -110 or perso_y < -500:
            game0ver()                                              ## condition qui dit que lorsque on atteint une hauteur superieur a 100 pixel on execute la fonction gameover  ou si le personnage et à 70 pixel




        for event in pygame.event.get():
            if event.type == pygame.QUIT:
               fin_game = True

            if event.type == pygame.KEYDOWN :
                if event.key == pygame.K_UP:
                    mvt_y = -2
                if event.key == pygame.K_DOWN :
                    mvt_y = +2
                if event.key == pygame.K_RIGHT :
                    mvt_x = +2
                if event.key == pygame.K_LEFT :
                    mvt_x = -2
        perso_x+= mvt_x
        perso_y+= mvt_y



        pygame.display.update()

    pygame.quit()
corps_game()

quit()
