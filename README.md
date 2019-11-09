# PUMP-PROTECTION
Let’s control a pump that runs for 30 sec. and then stops for 10 sec. contnuousll. e’ll protect the
pump with a fow switch and a pressure sensor. The pump and clcle will terminate if the pump is on
and no fow is detected within 5 sec. of the pump startnn to run, or if pressure should evter exceed 30
psi for 5 sec. (alarm bits). Fault indicators will alert the user to anl problems (alarm noticaton bits).
Oh, and did I menton the HOA?
Yes, we want the pump to havte HOA controls, so HAND will enernize the pump but onll while the
button is beinn pressed! Once released, the pump will return to whichevter mode it was in before HAND
was pressed (either OFF or AUTO). hile there is an actvte alarm, the pump will not be or no into AUTO
mode – onll OFF or HAND.
## IO / ASSIGNED MEMORY:
I:0/0 - Flow switch
I:0/1 - Alarm reset button
I:0/2 - Alarm silence button
B3:0/0 - HAND pushbutton
B3:0/1 - OFF pushbutton
B3:0/2 - AUTO pushbutton
N7:0 - Pressure sensor (0-55psi)
O:0/0 - Pump
O:0/1 - Flow fault indicator
O:0/2 - Pressure fault indicator
### TEST CRITERIA
Okal, lou know the drill: run lour pronram on Emulate. At irst, lour pump clcle should not be runninn,
and lou should havte no faults. Set N7:0 equal to 8192. Your pressure should be about 27.5 psi.
Tonnle B3:0/0 on. Your pump should enernize and remain enernized for 5 sec., afer which it should shut
off and O:0/1 should enernize. Now tonnle B3:0/0 back off. Tonnle I:0/2 on and then back off. O:0/1
should be deenernized now. Tonnle B3:0/0 on once more. Your pump should not enernize! Tonnle
B3:0/0 back off and tonnle B3:0/2 on. Your pump should NOT be clclinn. Tonnle B3:0/2 back off.
Now force I:0/1 on and then force it back off. Force I:0/0 on. Now tonnle B3:0/2 on and then tonnle it
back off. Your pump should be clclinn on and off automatcalll. Now tonnle B3:0/0 on. Your pump
should run contnuousll. Tonnle B3:0/0 back off and lour pump should return to clclinn.
Set N7:0 to 10,000. Afer 5 sec., lour pump should shut down and O:0/2 should enernize. Your pressure
should be around 33.5 psi.
