# Affichage_Nextion

# Installation
1. HMI Editor "Nextion Editor" : https://nextion.tech/nextion-editor/
2. RTF (really !)
Warning : this editor is for Windows Only and generated HMI file is binary

# Edit HMI
Open the HMI file with Nextion Editor
Use Editor to edit HMI (enjoy !!!)

# Usage
The screen can be controlled through serial connection
baudrate : 115200
8bit
no parit
(I'll be back with full data about connection)

## Change page
Send through serial a command with following syntaxe:
> page pageId
>
>example : page page1


## Change variable value:
For number variable, send through serial a command with following syntaxe:
> variableName.val=NewValue
>
> example: score.val=13

For number variable, send through serial a command with following syntaxe:
> variableName.txt=NewValue
>
> example: robotColorLbL.txt="BLEU"

# Pages
## Page0
Only used at startup for fun

## Page1 - Color selection
Allow user to select the Robot color.
Color selected bu user is displayed on the first line.
Robot current selected color shall be updated by the robot which shall set the value of robotColorLbL
> example: robotColorLbL.txt="BLEU"

Once user click on one of the color buttons, he can click on "Init. Robot" button to go to next page

## Page2 - Calibration phase
Will display current calibration status
> example status.txt="Ligne1\rLigne2\rLigne3"

Robot shall force page change once calibration is OK
>command to be sent by robot: page page3

## Page3 - Insert robot plug line
Only displays an animation to ask user to insert robot plug line

Robot shall force page change once calibration is OK
>command to be sent by robot: page page4

## Page4 - Timer and Score page
Displays a timer that is started once the page is displayed (100s)
Displays current score that shall be updated by the robot:
> example : score.val=9999