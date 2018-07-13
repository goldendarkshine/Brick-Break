# Brick-Break
def setup():
    size(1000,1000)
    background(0)
    global ellipse_x, speedX, ellipse_y, speedY, counter
    global brick1, brick2, brick3, brick4, brick5
    brick1= True
    brick2= True
    brick3= True
    brick4= True
    brick5= True
    ellipse_x = 100
    ellipse_y = 500
    speedX = 5
    speedY = 5
    counter = 0 
def draw():
    ball()
    paddle()
    bricks()
    textSize(40)
    text("Score: " + str(counter), 400, 500)
    
    if not brick1 and not brick2 and not brick3 and not brick4 and not brick5:
     background(255,255,0)
     fill(0)
     textSize(50)
     text("You win!", 400, 500)
     textSize(40)
     text("Score: " + str(counter), 400, 600)
    
def paddle():
    global ellipse_x, speedX, ellipse_y, speedY
    if mouseX <= 1000:
     rect(mouseX,900,100,20)
     if ellipse_x >= mouseX - 80 and ellipse_x <= mouseX + 80 and ellipse_y == 900:    
      speedY = -speedY 
     
     
def ball():
    global ellipse_x, speedX, ellipse_y, speedY
    background(0)
    ellipse(ellipse_x, ellipse_y, 20, 20)
    ellipse_x = ellipse_x + speedX
    if ellipse_x >= 1000 or ellipse_x <= 0:
        speedX = -speedX
    ellipse_y = ellipse_y + speedY
    if ellipse_y <= 0:
          speedY = -speedY
    if ellipse_y == 1000:
     ellipse_x = 100
     ellipse_y = 500
            
def bricks():
    global ellipse_x, speedX, ellipse_y, speedY, counter
    global brick1, brick2, brick3, brick4, brick5

    
    if brick1:
        rect(0,0,200,50)
    if brick2:
        rect(200,0,200,50)
    if brick3:
        rect(400,0,200,50)
    if brick4:
        rect(600,0,200,50)
    if brick5:
        rect(800,0,200,50)
        
    if ellipse_x > 0 and ellipse_x <= 200 and ellipse_y  <= 50 and brick1:   
        brick1= False
        speedY= -speedY 
        counter+=1
    elif ellipse_x > 0 and ellipse_x <= 400 and ellipse_y  <= 50 and brick2:   
         brick2= False
         speedY= -speedY
         counter+=1
    elif ellipse_x > 0 and ellipse_x <= 600 and ellipse_y  <= 50 and brick3: 
         brick3= False
         speedY= -speedY
         counter+=1
    elif ellipse_x > 0 and ellipse_x <= 800 and ellipse_y  <= 50 and brick4: 
         brick4= False
         speedY= -speedY
         counter+= 1
    elif ellipse_x > 0 and ellipse_x <= 1000 and ellipse_y  <= 50 and brick5: 
         brick5= False
         speedY= -speedY
         counter+= 1
    if not brick1 and not brick2 and not brick3 and not brick4 and not brick5:
         background(255,255,0)
