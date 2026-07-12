'''''
Ramiz Mert and Christopher Bueno
04/21/2026
Elemon
Using elements as pokemons to fight
'''''
import math

endScreen = Group(
    Rect(0, 0, 400, 400, fill="white"),
    Label("you won. the end.", 200, 200, size=20)
    )
app.attackDone = False
app.gameScreen = "MainMenu"
app.subScreen = "NONE"
app.turn = 0
app.timer1 = 0
app.timerStart1 = False

background = Image("cmu://1156096/46271999/ElemonBGNight2.png", 0, 0)
background.width = 400
background.height = 400

app.count = 0

app.moveButtonAnimeDone1 = False


app.currentAttack = "None"

app.selectedAttack = "None"

elementsInfo = ["Hydrogen", "H", "cmu://1156096/46193690/Hydrogen.png",
"Oxygen", "O", "cmu://1156096/46196080/Oxygen.png", "Neptunium", "Np",
"cmu://1156096/46201884/Neptunium.png", "Tantalum", "Ta", "cmu://1156096/46204943/Tantalum.png",
"Americium", "Am", "cmu://1156096/46213599/Americium.png", "Plutonium", "Pu",
"cmu://1156096/46215052/Plutonium.png", "Sulfur", "S", "cmu://1156096/46215622/Sulfur.png",
"Gold", "Au", "cmu://1156096/46413158/Gold.png", "Uranium", "U",
"cmu://1156086/46508566/pixil-frame-0+(1).png", "Tungsten", "W", "cmu://1156096/46271341/Tung+Tung.png"]

elementAttacks = ["-Hydrogen-", "Recover", "Combust", "Slow Start",
"Condense", "-Oxygen-", "Oxidize", "Combust", "Condense",
"Ozone Shield", "-Neptunium-", "Elemental Pulse", "Nuclear Drain", "Acid Rain", "Decay Shield",
"-Tantalum-", "Iron Wall", "Elemental Pulse", "Decay Shield", "Nuclear Drain",
"-Americium-", "Alpha Strike", "Acid Rain", "Nuclear Blast", "Decay Shield",
"-Plutonium-", "Acid Rain", "Chain Reaction", "Meltdown", "Alpha Strike",
"-Sulfur-", "Condense", "Acid Rain", "Elemental Pulse", "Stench Wave", "-Gold-",
"Elemental Pulse", "Heavy Slam", "Iron Wall", "Recover", "-Uranium-",
"Nuclear Blast", "Acid Rain", "Nuclear Drain", "Meltdown", "-Tungsten-",
"Heavy Slam", "Sharpen", "Iron Wall", "Heavy Swing"]

# Format: Element, HP, Physical Attack, Physical Defense, Chemical Attack, Chemical Defense, Weight
elementStats = ["Hydrogen", 60, 120, 20, 120, 20, 95, "Oxygen", 70, 65, 60, 80, 70, 75,
"Neptunium", 80, 70, 65, 95, 85, 40, "Tantalum", 90, 60, 110, 50, 95, 30, "Americium",
75, 45, 75, 110, 90, 50, "Plutonium", 85, 95, 75, 90, 85, 35, "Sulfur", 65, 70, 44, 85, 60, 90,
"Gold", 130, 20, 140, 20, 130, 15, "Uranium", 80, 90, 85, 130, 95, 20, "Tungsten",
90, 150, 80, 20, 30, 10]

#attack name, description, category, damage, accuracy, atk+, spatk+, def+, spdef+, speed+, priority+

attackInfo=[
"Condense", "The user trades their speed for defense", "Unknown", 0, 100, 1, 1, 2, 1, 0.5, 1, 1, 1, 1, 1, 1,
"Fusion Burst", "The user unleashes a powerful blast", "Special", 120, 75, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1,
"Slow Start", "User moves last but delivers a devasating hit", "Special", 280, 100, 1, 1, 1, 1, 1, -1,
"Oxidize", "The user deals damage and increases their Attack slightly", "Physical", 40, 100, 1.33, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1,
"Combust", "The user explodes", "Physical", 275, 100, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
"Ozone Shield", "The user increases its defense", "Unknown", 0,100,1,1,1.5,1,1, 0,1, 1, 1, 1, 1,
"Nuclear Drain", "The user absorbs energy, restoring HP equal to half damage dealt", "Special", 70,90,1,1,1,1,1, 0,1, 1, 1, 1, 1,
"Elemental Pulse","The user shoots its pure power", "Special", 100,95,1,1,1,1,1, 0,1, 1, 1, 1, 1,
"Alpha Strike","The user releases a radioactive attack", "Physical", 100,90,1,1,1,1,1,0,1, 1, 1, 1, 1,
"Decay Shield","The user surrounds itself with radiation that may harm attackers", "Unknown", 0,100,1,1,1,1,1,3,1, 1, 1, 1, 1,
"Chain Reaction","The user repeatedly bursts and hits multiple times", "Physical", 25,95,1,1,1,1,1, 0,1, 1, 1, 1, 1,
"Meltdown","The user uses up its strength in an attack","Special", 200,90,0.67,0.67,0.67,0.67,0.67, 0,1, 1, 1, 1, 1,
"Acid Rain","The user brings rain that damages opponents each turn", "Unknown", 15,95,1,1,1,1,1, 0,1, 1, 1, 1, 1,
"Stench Wave", "Its stench attacks the target, may flinch the target", "Physical", 40, 80,1,1,1,1,1, 0,1, 1, 1, 1, 1,
"Recover","The user restores its HP, goes last","Special", 20,100,1,1,1,1,1,-1,1, 1, 1, 1, 1,
"Nuclear Blast","The user unleashes a huge but unreliable blast", "Special", 150, 80,1,1,1,1,1,0,1, 1, 1, 1, 1,
"Critical Mass","The user build power, sharply boosting attack", "Unknown,", 0,100,2,1,1,1,1,1, 0,1, 1, 1, 1, 1,
"Heavy Slam","The user slams into the target using its defense", "Physical", 80, 90,1,1,1,1,1, 0,1, 1, 1, 1, 1,
"Sharpen","Increases the users Attack","Unknown", 0,100,1.5,1,1,1,1,0,1, 1, 1, 1, 1,
"Iron Wall","The user raises both its defenses.", "Unknown", 0, 100,1,1,1.5,1.5,1,0,1, 1, 1, 1, 1,
"Upside Down", "Flips the order of speed, including priority", "Unknown", 0, 100, 1, 1, 1, 1, 1,1, 1, 1, 1, 1,
"Heavy Swing", "User swings their bat with upmost force, raises attack", "Physical", 80, 95,1.5,1,1,1,1, -1,1, 1, 1, 1, 1,
]

#Breath of Life(heal the user),     Radioactive Pulse(Poisons the target),   decay field(damages target every turn),      Nuclear Drain(absorbs the damage dealt),    Decay Shield(damages the attacker),      Fission Blast(the user takes recoild damage),      chain reaction(user hits multtiple times),      Radiation Leak(poisons the opponent),      acid rain(summons acidic rain that damages targets for each turn),        sulfur burst(burn the target),    Stench wave(flinch the target),      Royal Heal(restores HP),      nuclear bladt(recoild damage),   Acid Rain(damages foes every turn),    Half-Life Drain(drains targets HP each turn),      Molten strike(burns the target)

print("Total Element Count: " + str(len(elementsInfo)/3))
#Clears the teams.
opponentTeam=[]
opponentTeamStatus=[]
playerTeam=[]
playerTeamStatus=[]

backH=Polygon(0,380,80,380,80,400,0,400)
backHT=Label("Back",40,390,fill='white')
attackBack = Group(
    backH,
    backHT
    )
backH.width= 50
attackBack.right = 180
attackBack.top = 365


randPlayer = elementsInfo[randrange(0, len(elementsInfo), 3)]
randOpponent = elementsInfo[randrange(0, len(elementsInfo), 3)]

# Randomly sets the team of both sides.
for i in range(5):
   
    while randPlayer in playerTeam:
        randPlayer = elementsInfo[randrange(0, len(elementsInfo), 3)]
    playerTeam.append(randPlayer)
   
    playerTeamStatus.append(playerTeam[i])
    playerTeamStatus.append(1)
    playerTeamStatus.append(1)
    playerTeamStatus.append(1)
    playerTeamStatus.append(1)
    playerTeamStatus.append(1)
    playerTeamStatus.append(elementStats[elementStats.index(playerTeam[i])+1])
    while randOpponent in opponentTeam:
        randOpponent = elementsInfo[randrange(0, len(elementsInfo), 3)]
    opponentTeam.append(randOpponent)
    opponentTeamStatus.append(opponentTeam[i])
    opponentTeamStatus.append(1)
    opponentTeamStatus.append(1)
    opponentTeamStatus.append(1)
    opponentTeamStatus.append(1)
    opponentTeamStatus.append(1)
    opponentTeamStatus.append(elementStats[elementStats.index(opponentTeam[i])+1])
   
opponentTeamStatus[1] = 1.5
opponentTeamStatus[2] = 1.5
opponentTeamStatus[3] = 1.5
opponentTeamStatus[4] = 1.5
opponentTeamStatus[5] = 1.5

# For testing purposes to see if it works
print("Player Team: " + str(playerTeam))
print("Player Team Buffs: " + str(playerTeamStatus))
print("Enemy Team: " + str(opponentTeam))
if "Tungsten" in playerTeam:
    print("You got Triple T!")

# Sets the current team member for both sides
opponentSelected = 0
playerSelected = 0

opponentElement = opponentTeam[opponentSelected]
# opponentTeam[opponentSelected]
playerElement = playerTeam[playerSelected]
# playerTeam[playerSelected]




buttonAttack = Group(
    Rect(190,320,80,40,fill='black', visible=False),
    Label("Attack",230,340,fill='white',visible=False,size=20)
    )
buttonSwitch = Group(
    Rect(310,320,80,40,fill='black', visible=False),
    Label("Switch",350,340,fill='white',size=20,visible=False)
    )
playerHPBarBG=Rect(200,280,160,20)
oppponentHPBG=Rect(40,40,160,20)
playerHPBar = Rect(playerHPBarBG.centerX, playerHPBarBG.centerY, playerHPBarBG.width*0.95, playerHPBarBG.height*0.5, align="center", fill="limeGreen")
opponentHPBar = Rect(oppponentHPBG.centerX, oppponentHPBG.centerY, oppponentHPBG.width*0.95, oppponentHPBG.height*0.5, align="center", fill="limeGreen")
app.playerHP = elementStats[elementStats.index(playerElement)+1]
app.opponentHP = elementStats[elementStats.index(opponentElement)+1]


print("playerHPBar's Left: " + str(playerHPBar.left))
print("playerHPBar's Width: " + str(playerHPBar.width))
print("opponentHPBar's Left: " + str(opponentHPBar.left))
print("opponentHPBar's Width: " + str(opponentHPBar.width))

attack1Button = Rect(230,330,80,20, align="center")
attack1Name = Label(elementAttacks[elementAttacks.index("-" + playerElement + "-")+1], 230, 330, fill="white", size=144/(len(elementAttacks[elementAttacks.index("-" + playerElement + "-")+1])*1.2), bold=True)
attack1=Group(
    attack1Button,
    attack1Name
    )
attack2Button = Rect(230,370,80,20, align="center")
attack2Name = Label(elementAttacks[elementAttacks.index("-" + playerElement + "-")+2], 230, 370, fill="white", size=144/(len(elementAttacks[elementAttacks.index("-" + playerElement + "-")+2])*1.2), bold=True)
attack2=Group(
    attack2Button,
    attack2Name
    )
attack3Button = Rect(350,330,80,20, align="center")
attack3Name = Label(elementAttacks[elementAttacks.index("-" + playerElement + "-")+3], 350, 330, fill="white", size=144/(len(elementAttacks[elementAttacks.index("-" + playerElement + "-")+3])*1.2), bold=True)
attack3=Group(
    attack3Button,
    attack3Name
    )
attack4Button = Rect(350,370,80,20, align="center")
attack4Name = Label(elementAttacks[elementAttacks.index("-" + playerElement + "-")+4], 350, 370, fill="white", size=144/(len(elementAttacks[elementAttacks.index("-" + playerElement + "-")+4])*1.2), bold=True)
attack4=Group(
    attack4Button,
    attack4Name
    )
attacks = Group(
    attack1,
    attack2,
    attack3,
    attack4
    )

attackDescLine1 = Label(elementAttacks[elementAttacks.index("-" + playerElement + "-")+1], 230, 330, fill="white", size = 144/(len(elementAttacks[elementAttacks.index("-" + playerElement + "-")+1])), align = "left", bold=True)
attackDescD= Label(elementAttacks[elementAttacks.index("-" + playerElement + "-")+2], 200, 360, fill="white", size = 10, align = "left", bold=True)

attacks.visible = False

switchBG = Group(
    Rect(200, 200, 410, 410, fill=rgb(80, 120, 210), align="center", border="white", borderWidth=5),
    Rect(200, 200, 375, 375, fill=rgb(80, 120, 210), align="center", border="white", borderWidth=5)
    )


switchScreen=Group()

switchScreen.add(switchBG)

switch1HPBar = Rect(110, 102.5, 112, 7, fill="limeGreen", align="center")
switch1= Group(
    Rect(40, 40, 150, 80, fill=rgb(40, 80, 160), border="white", borderWidth=5),
    Rect(50, 95, 120, 15),
    switch1HPBar
    )
   
switch2HPBar = Rect(110, 192.5, 112, 7, fill="limeGreen", align="center")
switch2= Group(
    Rect(40, 130, 150, 80, fill=rgb(40, 80, 160), border="white", borderWidth=5),
    Rect(50, 185, 120, 15),
    switch2HPBar
    )

switch3HPBar = Rect(290, 102.5, 112, 7, fill="limeGreen", align="center")
switch3=Group(
    Rect(220, 40, 150, 80, fill=rgb(40, 80, 160), border="white", borderWidth=5),
    Rect(230, 95, 120, 15),
    switch3HPBar
    )

switch4HPBar = Rect(290, 192.5, 112, 7, fill="limeGreen", align="center")
switch4=Group(
    Rect(220, 130, 150, 80, fill=rgb(40, 80, 160), border="white", borderWidth=5),
    Rect(230, 185, 120, 15),
    switch4HPBar
    )
   
switch5HPBar = Rect(290, 282.5, 112, 7, fill="limeGreen", align="center")
switch5=Group(
    Rect(220, 220, 150, 80, fill=rgb(40, 80, 160), border="white", borderWidth=5),
    Rect(230, 275, 120, 15),
    switch5HPBar
    )

switchBack=Polygon(40,320,160,320,160,360,40,360)

switchScreen.add(switch1)
switchScreen.add(switch2)
switchScreen.add(switch3)
switchScreen.add(switch4)
switchScreen.add(switch5)
switchScreen.add(switchBack)




### When attacked onces it gets stuck in the attack section, the user can't switch (idk how to fix it)

###  When the oppent dies he doesn't switch (idk how to do that eaither)

###Can you do something here so the sprites of the right element is showing
switchSprite1 = Image(elementsInfo[elementsInfo.index(playerTeam[0])+2], 50, 50)
switchSprite1.width=40
switchSprite1.height=40

#switchName1=Label(name of the elemnt)

switchSprite2 = Image(elementsInfo[elementsInfo.index(playerTeam[1])+2], 50, 140)
switchSprite2.width=40
switchSprite2.height=40

#switchName2=Label(name of the element)

switchSprite3 = Image(elementsInfo[elementsInfo.index(playerTeam[2])+2], 230, 50)
switchSprite3.width=40
switchSprite3.height=40

#switchName3=Label(name of the element)

switchSprite4 = Image(elementsInfo[elementsInfo.index(playerTeam[3])+2], 230, 140)
switchSprite4.width=40
switchSprite4.height=40

#switchName4=Label(name of the element)

switchSprite5 = Image(elementsInfo[elementsInfo.index(playerTeam[4])+2], 230, 230)
switchSprite5.width=40
switchSprite5.height=40

#switchName5=Label(name of the element)

switchBackLB=Label("Back",100,340,fill='white',size=20)

switchScreen.add(switchSprite1)
switchScreen.add(switchSprite2)
switchScreen.add(switchSprite3)
switchScreen.add(switchSprite4)
switchScreen.add(switchSprite5)
switchScreen.add(switchBackLB)


switchScreen.visible=False

app.switch=False

print(opponentElement)
print(playerElement)

def percentOf(percent, base):
  return(base*(percent/100))

app.background = rgb(248, 243, 247)



opponentSprite = Image(elementsInfo[elementsInfo.index(opponentElement)+2], 200, 200)
opponentSprite.width = 150
opponentSprite.height = 150
   
   
   
playerSprite1 = Image(elementsInfo[elementsInfo.index(playerTeam[0])+2], 200, 200)
playerSprite1.width = 150
playerSprite1.height = 150
   
playerSprite2 = Image(elementsInfo[elementsInfo.index(playerTeam[1])+2], 200, 200)
playerSprite2.width = 150
playerSprite2.height = 150

playerSprite3 = Image(elementsInfo[elementsInfo.index(playerTeam[2])+2], 200, 200)
playerSprite3.width = 150
playerSprite3.height = 150
   
playerSprite4 = Image(elementsInfo[elementsInfo.index(playerTeam[3])+2], 200, 200)
playerSprite4.width = 150
playerSprite4.height = 150
   
playerSprite5 = Image(elementsInfo[elementsInfo.index(playerTeam[4])+2], 200, 200)
playerSprite5.width = 150
playerSprite5.height = 150




opponentSprite.centerY = 200

opponentSprite.size = 85


if opponentElement != "Tungsten":
    opponentSprite.mainY = 150
else:
    opponentSprite.mainY = 120
opponentSprite.mainX = 300

opponentSprite.centerY = opponentSprite.mainY
opponentSprite.centerX = opponentSprite.mainX

playerSprite1.centerY = 200

playerSprite1.size = 85


playerSprite1.mainY = 362 - playerSprite1.height/2
playerSprite1.mainX = 400 - 300

playerSprite1.centerY = playerSprite1.mainY
playerSprite1.centerX = playerSprite1.mainX

playerSprite2.centerY = playerSprite1.mainY
playerSprite2.centerX = playerSprite1.mainX

playerSprite3.centerY = playerSprite1.mainY
playerSprite3.centerX = playerSprite1.mainX

playerSprite4.centerY = playerSprite1.mainY
playerSprite4.centerX = playerSprite1.mainX

playerSprite5.centerY = playerSprite1.mainY
playerSprite5.centerX = playerSprite1.mainX



darkness = Rect(0, 0, 400, 400)
attack1Button.height += (35 - attack1Button.height)/3

menuBG = Image("cmu://1156096/46380877/pixil-frame-0+(10).png", 0, 0, width=400, height=400)
title = Image("cmu://1156096/46382433/pixil-frame-0+(11).png", 0, 0, width=400, height=80)
title.bottom = 0
title.trueY = title.centerY
mainMenu = Image("cmu://1156096/46379729/pixil-frame-0+(8).png", 0, 500, width=350, height=175)
mainMenu.centerX = 200

startButton = Image("cmu://1156096/46398234/pixil-frame-0+(12).png", 500, 0)
startButton.width = 150
startButton.height = 75
app.stepNumber = 0
startButton.toFront()
app.mouseX = 0
app.mouseY = 0
def onMousePress(x, y):
    global playerElement
    app.mouseX = x
    app.mouseY = y
    if startButton.contains(app.mouseX, app.mouseY):
        app.gameScreen = "TransToBattle"
    if buttonSwitch.hits(app.mouseX, app.mouseY) and buttonSwitch.visible and app.switch!=True:
        switchScreen.visible=True
        app.switch=True
        switchScreen.centerX = (400+(switchScreen.width/2))
    if (switch1.contains(app.mouseX,app.mouseY))and(app.switch==True):
        ###can Put something so swithing works
        switchScreen.visible=True
        app.switch=False
        switchScreen.centerX=200
        playerTeamStatus[playerTeam.index(playerElement)+6] = app.playerHP
        playerElement = playerTeam[0]
        app.playerHP = playerTeamStatus[playerTeam.index(playerElement)+6]
       
    if (switch2.contains(app.mouseX,app.mouseY))and(app.switch==True):
        ###can Put something so swithing works  
        switchScreen.visible=True
        app.switch=False
        switchScreen.centerX=200
        playerTeamStatus[playerTeamStatus.index(playerElement)+6] = app.playerHP
        playerElement = playerTeam[1]
        app.playerHP = playerTeamStatus[playerTeamStatus.index(playerElement)+6]
       
    if (switch3.contains(app.mouseX,app.mouseY))and(app.switch==True):
        ###can Put something so swithing works
        switchScreen.visible=True
        app.switch=False
        switchScreen.centerX=200
        playerTeamStatus[playerTeamStatus.index(playerElement)+6] = app.playerHP
        playerElement = playerTeam[2]
        app.playerHP = playerTeamStatus[playerTeamStatus.index(playerElement)+6]
       
    if (switch4.contains(app.mouseX,app.mouseY))and(app.switch==True):
        ###can Put something so swithing works
        switchScreen.visible=True
        app.switch=False
        switchScreen.centerX=200
        playerTeamStatus[playerTeamStatus.index(playerElement)+6] = app.playerHP
        playerElement = playerTeam[3]
        app.playerHP = playerTeamStatus[playerTeamStatus.index(playerElement)+6]
       
    if (switch5.contains(app.mouseX,app.mouseY))and(app.switch==True):
        ###can Put something so swithing works
        switchScreen.visible=True
        app.switch=False
        switchScreen.centerX=200
        playerTeamStatus[playerTeamStatus.index(playerElement)+6] = app.playerHP
        playerElement = playerTeam[4]
        app.playerHP = playerTeamStatus[playerTeamStatus.index(playerElement)+6]
       
    if (switchBack.contains(app.mouseX,app.mouseY))and(app.switch==True):
        switchScreen.visible=True
        app.switch=False
        switchScreen.centerX=200
    if buttonAttack.contains(app.mouseX, app.mouseY) and buttonAttack.visible:
        attacks.visible=True
        buttonAttack.visible=False
        buttonSwitch.visible=False
        app.subScreen = "Attack"
    if app.timerStart1 == False:
        if attack1.contains(app.mouseX, app.mouseY):
            app.currentAttack = app.selectedAttack
            app.subScreen = "None"
            app.attackDone = True
            app.moveButtonAnimeDone1 = False
        if attack2.contains(app.mouseX, app.mouseY):
            app.currentAttack = app.selectedAttack
            app.subScreen = "None"
            app.attackDone = True
            app.moveButtonAnimeDone1 = False
        if attack3.contains(app.mouseX, app.mouseY):
            app.currentAttack = app.selectedAttack
            app.subScreen = "None"
            app.attackDone = True
            app.moveButtonAnimeDone1 = False
        if attack4.contains(app.mouseX, app.mouseY):
            app.currentAttack = app.selectedAttack
            app.subScreen = "None"
            app.attackDone = True
            app.moveButtonAnimeDone1 = False
        if attackBack.contains(app.mouseX, app.mouseY) and attackBack.visible:
            app.subScreen = "NONE"
            attacks.visible = False
            app.moveButtonAnimeDone1 = False
     

    if app.selectedAttack != "None":
        app.timer1 = 0
        app.timerStart1 = True
        app.count = 0
       
    if playerHPBar==0:
        app.switch=True
       
   
       
app.opponentSelectedAttack = "None"
   
def playerAttack():
    print("Your " + playerElement + " used " + app.currentAttack + "! " + attackInfo[attackInfo.index(app.selectedAttack)+1])
    if attackInfo[(attackInfo.index(app.selectedAttack)+3)] != 0:
        if randrange(0, 101) <= attackInfo[(attackInfo.index(app.selectedAttack)+4)]:
            if app.opponentSelectedAttack != "Decay Shield":
                if app.selectedAttack == "Nuclear Drain":
                    app.opponentHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.selectedAttack)+3)] * ((((elementStats[elementStats.index(playerElement)+2]) * playerTeamStatus[playerTeamStatus.index(playerElement)+1]))/(elementStats[elementStats.index(opponentElement)+3] * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3]))/50)+2
                    app.playerHP += (((10 + 2) * attackInfo[(attackInfo.index(app.selectedAttack)+3)] * ((((elementStats[elementStats.index(playerElement)+2]) * playerTeamStatus[playerTeamStatus.index(playerElement)+1]))/(elementStats[elementStats.index(opponentElement)+3] * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3]))/50)+2)/2
                elif app.selectedAttack == "Combust":
                    app.opponentHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.selectedAttack)+3)] * ((((elementStats[elementStats.index(playerElement)+2]) * playerTeamStatus[playerTeamStatus.index(playerElement)+1]))/(elementStats[elementStats.index(opponentElement)+3] * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3]))/50)+2
                    app.playerHP = 0
                elif app.selectedAttack == "Heavy Slam":
                    app.opponentHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.selectedAttack)+3)] * ((((elementStats[elementStats.index(playerElement)+2]) * playerTeamStatus[playerTeamStatus.index(playerElement)+3]))/(elementStats[elementStats.index(opponentElement)+3] * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3]))/50)+2
                elif app.selectedAttack == "Recover":
                    app.playerHP += attackInfo[(attackInfo.index(app.selectedAttack)+3)]
                else:
                    if attackInfo[attackInfo.index(app.selectedAttack)+2] == "Physical":
                        app.opponentHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.selectedAttack)+3)] * ((((elementStats[elementStats.index(playerElement)+2]) * playerTeamStatus[playerTeamStatus.index(playerElement)+1]))/(elementStats[elementStats.index(opponentElement)+3] * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3]))/50)+2
                    elif attackInfo[attackInfo.index(app.selectedAttack)+2] == "Special":
                        app.opponentHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.selectedAttack)+3)] * ((((elementStats[elementStats.index(playerElement)+4]) * playerTeamStatus[playerTeamStatus.index(playerElement)+2]))/(elementStats[elementStats.index(opponentElement)+5] * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+4]))/50)+2
            else:
                if attackInfo[attackInfo.index(app.selectedAttack)+2] == "Physical":
                    app.playerHP -= elementStats[elementStats.index(playerElement)+1]/4
                print("But it protected itself!")
        else:
            print("But it missed!")
   
    playerTeamStatus[playerTeamStatus.index(playerElement)+1] = playerTeamStatus[playerTeamStatus.index(playerElement)+1] * attackInfo[(attackInfo.index(app.selectedAttack)+5)]
    playerTeamStatus[playerTeamStatus.index(playerElement)+2] = playerTeamStatus[playerTeamStatus.index(playerElement)+2] * attackInfo[(attackInfo.index(app.selectedAttack)+6)]
    playerTeamStatus[playerTeamStatus.index(playerElement)+3] = playerTeamStatus[playerTeamStatus.index(playerElement)+3] * attackInfo[(attackInfo.index(app.selectedAttack)+7)]
    playerTeamStatus[playerTeamStatus.index(playerElement)+4] = playerTeamStatus[playerTeamStatus.index(playerElement)+4] * attackInfo[(attackInfo.index(app.selectedAttack)+8)]
    playerTeamStatus[playerTeamStatus.index(playerElement)+5] = playerTeamStatus[playerTeamStatus.index(playerElement)+5] * attackInfo[(attackInfo.index(app.selectedAttack)+9)]
    print("Attack Power: " + str(playerTeamStatus[playerTeamStatus.index(playerElement)+1]))

def opponentAttack():
    print("Opponent's " + opponentElement + " used " + app.opponentSelectedAttack + "! " + attackInfo[attackInfo.index(app.opponentSelectedAttack)+1])
    if app.opponentSelectedAttack != "None" and attackInfo[(attackInfo.index(app.opponentSelectedAttack)+3)] != 0:
        if randrange(0, 101) <= attackInfo[(attackInfo.index(app.opponentSelectedAttack)+4)]:
            if app.selectedAttack != "Decay Shield":
                if app.opponentSelectedAttack == "Nuclear Drain":
                    app.playerHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+3)] * ((((elementStats[elementStats.index(opponentElement)+2]) * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+1]))/(elementStats[elementStats.index(playerElement)+3] * playerTeamStatus[playerTeamStatus.index(playerElement)+3]))/50)+2
                    app.opponentHP += (((10 + 2) * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+3)] * ((((elementStats[elementStats.index(opponentElement)+2]) * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+1]))/(elementStats[elementStats.index(playerElement)+3] * playerTeamStatus[playerTeamStatus.index(playerElement)+3]))/50)+2)/2
                elif app.opponentSelectedAttack == "Combust":
                    app.playerHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+3)] * ((((elementStats[elementStats.index(opponentElement)+2]) * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+1]))/(elementStats[elementStats.index(playerElement)+3] * playerTeamStatus[playerTeamStatus.index(playerElement)+3]))/50)+2
                    app.opponentHP = 0
                elif app.opponentSelectedAttack == "Heavy Slam":
                    app.playerHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+3)] * ((((elementStats[elementStats.index(opponentElement)+2]) * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3]))/(elementStats[elementStats.index(playerElement)+3] * playerTeamStatus[playerTeamStatus.index(playerElement)+3]))/50)+2
                elif app.opponentSelectedAttack == "Recover":
                    app.opponentHP += attackInfo[(attackInfo.index(app.opponentSelectedAttack)+3)]
                else:
                    app.playerHP -= ((10 + 2) * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+3)] * ((((elementStats[elementStats.index(opponentElement)+2]) * opponentTeamStatus[opponentTeamStatus.index(opponentElement)+1]))/(elementStats[elementStats.index(playerElement)+3] * playerTeamStatus[playerTeamStatus.index(playerElement)+3]))/50)+2
            elif attackInfo[attackInfo.index(app.opponentSelectedAttack)+2] == "Physical":
                app.opponentHP -= elementStats[elementStats.index(opponentElement)+1]/4
            if app.selectedAttack == "Decay Shield":
                print("But you protected yourself!")
                   
        else:
            print("But it missed!")
           
    opponentTeamStatus[opponentTeamStatus.index(opponentElement)+1] = opponentTeamStatus[opponentTeamStatus.index(opponentElement)+1] * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+5)]
    opponentTeamStatus[opponentTeamStatus.index(opponentElement)+2] = opponentTeamStatus[opponentTeamStatus.index(opponentElement)+2] * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+6)]
    opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3] = opponentTeamStatus[opponentTeamStatus.index(opponentElement)+3] * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+7)]
    opponentTeamStatus[opponentTeamStatus.index(opponentElement)+4] = opponentTeamStatus[opponentTeamStatus.index(opponentElement)+4] * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+8)]
    opponentTeamStatus[opponentTeamStatus.index(opponentElement)+5] = opponentTeamStatus[opponentTeamStatus.index(opponentElement)+5] * attackInfo[(attackInfo.index(app.opponentSelectedAttack)+9)]
   
       
print("Opponent's HP: " + str(elementStats[elementStats.index(opponentElement)+1]))
print("Opponent's Defense; " + str(elementStats[elementStats.index(opponentElement)+3]))

def priorityLogic(x):
    return(x*1000)
   
credits = Image("cmu://1156096/46398772/pixil-frame-0+(13).png", 200 - 27, 20, width = 54, height=5)
def onStep():
   
    attack1Name.value = elementAttacks[elementAttacks.index("-" + playerElement + "-")+1]
       
    attack2Name.value = elementAttacks[elementAttacks.index("-" + playerElement + "-")+2]
       
    attack3Name.value = elementAttacks[elementAttacks.index("-" + playerElement + "-")+3]
       
    attack4Name.value = elementAttacks[elementAttacks.index("-" + playerElement + "-")+4]
       
       
       
    if app.opponentHP < 0.01:
        app.opponentHP = 0.01
    if app.playerHP < 0.01:
        app.playerHP = 0.01
       
    if app.opponentHP > elementStats[elementStats.index(opponentElement)+1]:
        app.opponentHP = elementStats[elementStats.index(opponentElement)+1]
    if app.playerHP > elementStats[elementStats.index(playerElement)+1]:
        app.playerHP = elementStats[elementStats.index(playerElement)+1]
       
       
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6] < 0:
        playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6] = 0
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6] > elementStats[elementStats.index(playerTeam[0])+1]:
        playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6] = elementStats[elementStats.index(playerTeam[0])+1]
       
       
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[1])+6] < 0:
        playerTeamStatus[playerTeamStatus.index(playerTeam[1])+6] = 0
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[1])+6] > elementStats[elementStats.index(playerTeam[1])+1]:
        playerTeamStatus[playerTeamStatus.index(playerTeam[1])+6] = elementStats[elementStats.index(playerTeam[1])+1]
       
       
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[2])+6] < 0:
        playerTeamStatus[playerTeamStatus.index(playerTeam[2])+6] = 0
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[2])+6] > elementStats[elementStats.index(playerTeam[2])+1]:
        playerTeamStatus[playerTeamStatus.index(playerTeam[2])+6] = elementStats[elementStats.index(playerTeam[2])+1]
       
       
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[3])+6] < 0:
        playerTeamStatus[playerTeamStatus.index(playerTeam[3])+6] = 0
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[3])+6] > elementStats[elementStats.index(playerTeam[3])+1]:
        playerTeamStatus[playerTeamStatus.index(playerTeam[3])+6] = elementStats[elementStats.index(playerTeam[3])+1]
       
       
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[4])+6] < 0:
        playerTeamStatus[playerTeamStatus.index(playerTeam[4])+6] = 0
       
    if playerTeamStatus[playerTeamStatus.index(playerTeam[4])+6] > elementStats[elementStats.index(playerTeam[4])+1]:
        playerTeamStatus[playerTeamStatus.index(playerTeam[4])+6] = elementStats[elementStats.index(playerTeam[4])+1]
       
    #  ((playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6])/(elementStats[elementStats.index(playerTeam[0])+1]))*255
    switch1HPBar.width = 112*((int(playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6])/int(elementStats[elementStats.index(playerTeam[0])+1]))+0.01)
    switch1HPBar.left = 54 + switchScreen.centerX - 200
    switch1HPBar.fill=rgb(255 - ((playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6])/(elementStats[elementStats.index(playerTeam[0])+1]))*255, ((playerTeamStatus[playerTeamStatus.index(playerTeam[0])+6])/(elementStats[elementStats.index(playerTeam[0])+1]))*255, 0)
   
    switch2HPBar.width = 112*((int(playerTeamStatus[playerTeamStatus.index(playerTeam[1])+6])/int(elementStats[elementStats.index(playerTeam[1])+1]))+0.01)
    switch2HPBar.left = 54 + switchScreen.centerX - 200
    switch2HPBar.fill=rgb(255 - ((playerTeamStatus[playerTeamStatus.index(playerTeam[1])+6])/(elementStats[elementStats.index(playerTeam[1])+1]))*255, ((playerTeamStatus[playerTeamStatus.index(playerTeam[1])+6])/(elementStats[elementStats.index(playerTeam[1])+1]))*255, 0)
   
    switch3HPBar.width = 112*((int(playerTeamStatus[playerTeamStatus.index(playerTeam[2])+6])/int(elementStats[elementStats.index(playerTeam[2])+1]))+0.01)
    switch3HPBar.left = 234 + switchScreen.centerX - 200
    switch3HPBar.fill=rgb(255 - ((playerTeamStatus[playerTeamStatus.index(playerTeam[2])+6])/(elementStats[elementStats.index(playerTeam[2])+1]))*255, ((playerTeamStatus[playerTeamStatus.index(playerTeam[2])+6])/(elementStats[elementStats.index(playerTeam[2])+1]))*255, 0)
   
    switch4HPBar.width = 112*((int(playerTeamStatus[playerTeamStatus.index(playerTeam[3])+6])/int(elementStats[elementStats.index(playerTeam[3])+1]))+0.01)
    switch4HPBar.left = 234 + switchScreen.centerX - 200
    switch4HPBar.fill=rgb(255 - ((playerTeamStatus[playerTeamStatus.index(playerTeam[3])+6])/(elementStats[elementStats.index(playerTeam[3])+1]))*255, ((playerTeamStatus[playerTeamStatus.index(playerTeam[3])+6])/(elementStats[elementStats.index(playerTeam[3])+1]))*255, 0)
   
    switch5HPBar.width = 112*((int(playerTeamStatus[playerTeamStatus.index(playerTeam[4])+6])/int(elementStats[elementStats.index(playerTeam[4])+1]))+0.01)
    switch5HPBar.left = 234 + switchScreen.centerX - 200
    switch5HPBar.fill=rgb(255 - ((playerTeamStatus[playerTeamStatus.index(playerTeam[4])+6])/(elementStats[elementStats.index(playerTeam[4])+1]))*255, ((playerTeamStatus[playerTeamStatus.index(playerTeam[4])+6])/(elementStats[elementStats.index(playerTeam[4])+1]))*255, 0)
       
    if app.gameScreen == "MainMenu":
        mainMenu.centerY += (290 - mainMenu.centerY)/5
        startButton.centerY = mainMenu.centerY - 32
        startButton.centerX = mainMenu.centerX + 82
        title.trueY += (100 - title.trueY)/5
        title.centerX = (math.sin(app.stepNumber/10)*2) + 200
        title.centerY = (math.cos(app.stepNumber/10)*2) + title.trueY
        title.rotateAngle = math.cos(app.stepNumber/10)
    elif app.gameScreen == "TransToBattle":
        if darkness.opacity > 0:
            darkness.opacity -= 5
        else:
            app.gameScreen = "Battle"
        if startButton.visible:
            startButton.visible = False
        if title.bottom >= 0:
            title.centerY += (-100 - title.centerY)/5
        if mainMenu.top <= 400:
            mainMenu.top += (500 - mainMenu.top)/5
        if menuBG.bottom >= 0:
            menuBG.bottom += (-100 - menuBG.bottom)/8
       
    else:
        playerHPBar.width += (((app.playerHP/elementStats[elementStats.index(playerElement)+1]) * 152) - playerHPBar.width)/4
        playerHPBar.left = 204
        playerHPBar.fill=rgb(255 - (app.playerHP/elementStats[elementStats.index(playerElement)+1])*255, (app.playerHP/elementStats[elementStats.index(playerElement)+1])*255, 0)
       
        opponentHPBar.width += (((app.opponentHP/elementStats[elementStats.index(opponentElement)+1]) * 152) - opponentHPBar.width)/4
        opponentHPBar.left = 44
        opponentHPBar.fill=rgb(255 - (app.opponentHP/elementStats[elementStats.index(opponentElement)+1])*255, (app.opponentHP/elementStats[elementStats.index(opponentElement)+1])*255, 0)
       
        if app.stepNumber/10 == rounded(app.stepNumber/10):
            if opponentSprite.centerY == opponentSprite.mainY:
                opponentSprite.centerY += 5*(opponentSprite.size/100)
            else:
                opponentSprite.centerY -= 5*(opponentSprite.size/100)
        if app.stepNumber/10 == rounded(app.stepNumber/10):
            if playerSprite1.centerY == playerSprite1.mainY:
                playerSprite1.centerY += 5*(playerSprite1.size/100)
                playerSprite2.centerY += 5*(playerSprite1.size/100)
                playerSprite3.centerY += 5*(playerSprite1.size/100)
                playerSprite4.centerY += 5*(playerSprite1.size/100)
                playerSprite5.centerY += 5*(playerSprite1.size/100)
            else:
                playerSprite1.centerY -= 5*(playerSprite1.size/100)
                playerSprite2.centerY -= 5*(playerSprite1.size/100)
                playerSprite3.centerY -= 5*(playerSprite1.size/100)
                playerSprite4.centerY -= 5*(playerSprite1.size/100)
                playerSprite5.centerY -= 5*(playerSprite1.size/100)
    if app.subScreen != "Attack":
        if attacks.top != 400:
            attacks.top += 400 - (attacks.top)/3
            if (app.gameScreen != "MainMenu")and(app.switch==False) and (app.attackDone == False):
                if rounded(app.playerHP) != 0:
                    buttonAttack.visible=True
                buttonSwitch.visible=True
            else:
                buttonAttack.visible=False
                buttonSwitch.visible=False
    if app.subScreen == "Attack":
        attacks.centerY += (345 - attacks.centerY)/3
        if rounded(attacks.centerY) == 345:
            app.moveButtonAnimeDone1 = True



   
    app.stepNumber += 1
    if app.stepNumber >= 360:
        app.stepNumber = 0
    if app.timerStart1:
        app.count += 1
        if app.count % app.stepsPerSecond == 0 or app.count % (app.stepsPerSecond/2) == 0:
            app.timer1 += 0.5
        if app.selectedAttack != "Chain Reaction":
            if app.count % app.stepsPerSecond == 0 and app.timer1 == 1:
                app.opponentSelectedAttack = elementAttacks[elementAttacks.index("-"+opponentElement+"-") + randrange(1, 5)]
                app.turn += 1
                print("Turn " + str(app.turn) + ":")
                if elementStats[elementStats.index(playerElement)+6] + priorityLogic(attackInfo[(attackInfo.index(app.selectedAttack)+10)]) >= elementStats[elementStats.index(opponentElement)+6] + priorityLogic(attackInfo[(attackInfo.index(app.opponentSelectedAttack)+10)]):
                    playerAttack()
                else:
                    opponentAttack()
            if app.count % app.stepsPerSecond == 0 and app.timer1 == 2:
                if elementStats[elementStats.index(playerElement)+6] + priorityLogic(attackInfo[(attackInfo.index(app.selectedAttack)+10)]) >= elementStats[elementStats.index(opponentElement)+6] + priorityLogic(attackInfo[(attackInfo.index(app.opponentSelectedAttack)+10)]):
                    app.opponentSelectedAttack = elementAttacks[elementAttacks.index("-"+opponentElement+"-") + randrange(1, 5)]
                    if app.playerHP != 0:
                        opponentAttack()
                else:
                    if app.opponentHP != 0:
                        playerAttack()
                app.opponentSelectedAttack = "None"
                app.timerStart1 = False
                app.attackDone = False
            playerTeamStatus[playerTeamStatus.index(playerElement)+6] = app.playerHP
            opponentTeamStatus[opponentTeamStatus.index(opponentElement)+6] = app.opponentHP
               

    # Entire Section to animate attack buttons
    if not(attack2.contains(app.mouseX, app.mouseY) or attack3.contains(app.mouseX, app.mouseY) or attack1.contains(app.mouseX, app.mouseY) or attack4.contains(app.mouseX, app.mouseY) or app.timerStart1):
        if not app.timerStart1:
            app.selectedAttack = "None"
       
        if app.moveButtonAnimeDone1:
            attack1Button.height += (20 - attack1Button.height)/3
            attack1Button.width += (80 - attack1Button.width)/3
           
       
            attack2Button.height += (20 - attack2Button.height)/3
            attack2Button.width += (80 - attack2Button.width)/3
            attack2.bottom = 375
           
            attack3Button.height += (20 - attack3Button.height)/3
            attack3Button.width += (80 - attack3Button.width)/3
            attack3.right = 390
           
            attack4Button.height += (20 - attack4Button.height)/3
            attack4Button.width += (80 - attack4Button.width)/3
            attack4.right = 390
            attack4.bottom = 375
           
    elif app.moveButtonAnimeDone1:
        if attack1.contains(app.mouseX, app.mouseY) and not(attack2.contains(app.mouseX, app.mouseY) or attack3.contains(app.mouseX, app.mouseY) or attack4.contains(app.mouseX, app.mouseY)):
            attack1Button.height += (60 - attack1Button.height)/3
            attack1Button.width += (200 - attack1Button.width)/3
            attack1.toFront()
            app.selectedAttack = elementAttacks[elementAttacks.index("-" + playerElement + "-")+1]
        else:
            attack1Button.height += (20 - attack1Button.height)/3
            attack1Button.width += (80 - attack1Button.width)/3
        if attack2.contains(app.mouseX, app.mouseY) and not(attack1.contains(app.mouseX, app.mouseY) or attack3.contains(app.mouseX, app.mouseY) or attack4.contains(app.mouseX, app.mouseY)):
            attack2Button.height += (60 - attack2Button.height)/3
            attack2Button.width += (200 - attack2Button.width)/3
            attack2.toFront()
            attack2.bottom = 375
            app.selectedAttack = elementAttacks[elementAttacks.index("-" + playerElement + "-")+2]
        else:
            attack2Button.height += (20 - attack2Button.height)/3
            attack2Button.width += (80 - attack2Button.width)/3
            attack2.bottom = 375
        if attack3.contains(app.mouseX, app.mouseY) and not(attack2.contains(app.mouseX, app.mouseY) or attack1.contains(app.mouseX, app.mouseY) or attack4.contains(app.mouseX, app.mouseY)):
            attack3Button.height += (60 - attack3Button.height)/3
            attack3Button.width += (200 - attack3Button.width)/3
            attack3.toFront()
            attack3.right = 390
            app.selectedAttack = elementAttacks[elementAttacks.index("-" + playerElement + "-")+3]
        else:
            attack3Button.height += (20 - attack3Button.height)/3
            attack3Button.width += (80 - attack3Button.width)/3
            attack3.right = 390
        if attack4.contains(app.mouseX, app.mouseY) and not(attack2.contains(app.mouseX, app.mouseY) or attack3.contains(app.mouseX, app.mouseY) or attack1.contains(app.mouseX, app.mouseY)):
            attack4Button.height += (60 - attack4Button.height)/3
            attack4Button.width += (200 - attack4Button.width)/3
            attack4.toFront()
            attack4.right = 390
            attack4.bottom = 375
            app.selectedAttack = elementAttacks[elementAttacks.index("-" + playerElement + "-")+4]
        else:
            attack4Button.height += (20 - attack4Button.height)/3
            attack4Button.width += (80 - attack4Button.width)/3
            attack4.right = 390
            attack4.bottom = 375
           
    if app.selectedAttack != "None":
        attackDescLine1.visible=True
        attackDescLine1.value = attackInfo[attackInfo.index(app.selectedAttack)+1]
        attackDescLine1.size=(144*2.5)/(len(attackDescLine1.value)+1)
        attackDescLine1.left=195
        attackDescLine1.top=335
        attackDescD.visible=True
        attackDescD.value="Power: " + str(attackInfo[attackInfo.index(app.selectedAttack)+3]) + "  Accuracy: " + str(attackInfo[attackInfo.index(app.selectedAttack)+4]) + "    " + attackInfo[attackInfo.index(app.selectedAttack)+2]
        attackDescD.left=195
        attackDescD.top=350
        if app.timerStart1:
            attackDescLine1.visible=False
            attackDescD.visible=False
           
    else:
        attackDescLine1.visible=False
        attackDescD.visible=False
   
    attack1Name.size=0.75
    attack1Name.size = (80*0.60)/attack1Name.width
    if attack1Name.height > 20*0.75:
        attack1Name.size = 20 * 0.75
       
    attack2Name.size=0.75
    attack2Name.size = (80*0.60)/attack2Name.width
    if attack2Name.height > 20*0.75:
        attack2Name.size = 20 * 0.75
       
    attack3Name.size=0.75
    attack3Name.size = (80*0.60)/attack3Name.width
    if attack3Name.height > 20*0.75:
        attack3Name.size = 20 * 0.75
       
    attack4Name.size=0.75
    attack4Name.size = (80*0.60)/attack4Name.width
    if attack4Name.height > 20*0.75:
        attack4Name.size = 20 * 0.75
    if not app.switch:
        if playerTeam[0] == playerElement:
            playerSprite1.visible = True
            playerSprite2.visible = False
            playerSprite3.visible = False
            playerSprite4.visible = False
            playerSprite5.visible = False
        elif playerTeam[1] == playerElement:
            playerSprite1.visible = False
            playerSprite2.visible = True
            playerSprite3.visible = False
            playerSprite4.visible = False
            playerSprite5.visible = False
        elif playerTeam[2] == playerElement:
            playerSprite1.visible = False
            playerSprite2.visible = False
            playerSprite3.visible = True
            playerSprite4.visible = False
            playerSprite5.visible = False
        elif playerTeam[3] == playerElement:
            playerSprite1.visible = False
            playerSprite2.visible = False
            playerSprite3.visible = False
            playerSprite4.visible = True
            playerSprite5.visible = False
        elif playerTeam[4] == playerElement:
            playerSprite1.visible = False
            playerSprite2.visible = False
            playerSprite3.visible = False
            playerSprite4.visible = False
            playerSprite5.visible = True
       
    if app.switch:
        switchScreen.toFront()
        switchScreen.centerX += (200 - switchScreen.centerX)/4
    else:
        switchScreen.toFront()
        switchScreen.left += (400 - switchScreen.left)/4
    if app.opponentHP <= 0:
        endScreen.visible = True
        endScreen.toFront()
        app.stop()
    if not attacks.visible or attacks.top >= 400:
        attackBack.visible = False
    else:
        attackBack.visible = True
       
   
def onKeyPress(key):
    if app.opponentHP < 0:
        app.opponentHP = 0
       

       
def onMouseMove(x, y):
    app.mouseX = x
    app.mouseY = y
