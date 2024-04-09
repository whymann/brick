# brick
import pygame
pygame.init()
pygame.display.set_caption("top down grid game") # set the window title
screen = pygame.display.set_mode((500,500)) # creats a game screen
clock = pygame.time.Clock() #set up clock
gameover = False # variable to run our game loop

map = [[2,2,2,2,2,2,2,2,2,2],
       [2,3,3,3,3,2,2,3,3,2],
       [2,3,1,3,3,2,2,3,3,2],
       [2,0,0,2,2,2,2,3,3,2],
       [2,3,3,3,3,3,1,3,0,2],
       [2,0,1,3,3,3,3,3,0,2],
       [2,0,2,3,3,3,1,1,3,2],
       [2,3,2,0,3,3,1,3,1,2],
       [2,2,2,2,2,2,2,2,2,2],
       [2,2,2,2,2,2,2,2,2,2]]


brick = pygame.image.load('brick.jpg')
dirt = pygame.image.load('wa wa.jpg')
rat  = pygame.image.load('rat.png')


while not gameover:# GAME LOOP==================================================
    clock.tick(60) #FPS
    #input section---------------------------------------------------------------
    for event in pygame.event.get(): # quit game if x is pressed in the top corner
        if event.type == pygame.QUIT:
            gameover = True
            
            
    # physics section--------------------------------------------------------------
    
    
    #Render section--------------------------------------------------------------------
    
    screen.fill((0,0,0)) # wipe screen so it doesn't smear
    #draw map
    for i in range(len(map)):
        for j in range(len(map[i])):
           if map[i][j] == 1:
              screen.blit(dirt, (j * 50, i * 50), (0, 0, 50, 50))
           if map[i][j] ==2:
              screen.blit(brick, (j * 50, i * 50), (0, 0, 50, 50))
           if map[i][j] ==3:
              screen.blit(rat, (j * 50, i * 50), (0, 0, 50, 50))
                
    pygame.display.flip() # this actually puts the pixles on the screen
    
# end game loop=====================================================================
pygame.quit() 
