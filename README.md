# PacifistaBot
Robot hau, [OPRobots](https://github.com/OPRobots)-ek diseinatutakoa da, informazio guztia github-ean zintzilikatu dute edozeinek eraikitzeko edota gehiago garatzeko. [ionhsFP](https://github.com/ionhsFP)-en githubeko informazioaren bitartez egin da proiektu hau.

Lehenengo robot bat eraikitzeko hasteko, hau aproposena da. Ikusten denez robot guztia 3D-ko piezas osaturikoa da,gainera, piezak pertsonalizatu ahal dira, robotak nahi den itxura izan dezan. Arduino NANO baten bidez kontrolatzen da, beraz programatzeko Arduino IDE erabiltzen da. PCB plaka soldatzeko erraza da, lekua duelako soldadorea errez mugitzeko.


Robot hau, jatorriz, Bluetooth bidez diseinatu zen, baina, garapenekin, wifi bidez kontrolatzea lortu da. Gure kasuan jatorrizko diseinuarekin geratu gara hau da, bluetooh bidez kontrolatzeko. 

<p align="center">
  <img width="370" height="550" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/IMG_20210203_115501.jpg">
</p>


**ERABILITAKO KOMUNIKAZIOA:**
- Kable mini USB
- Bluetooth

**SOFTWARE**
- Programazioa: [Arduino IDE](https://www.arduino.cc/en/software)
- Komunikazioa: [Arduino IDE](https://www.arduino.cc/)
- APP Androind: [Bluetooth Elektronics](https://www.keuwl.com/apps/bluetoothelectronics/)



# PacifistaBot-aren muntaketa eta kalibrazioa

## 1.Pausua: 3D-ko piezak inprimatu.

Github-ean STL fitxeroak inprimatzen hasi.

<p align="center">
  <img width="460" height="300" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/1610709638869.jpg">
</p>

## 2.Pausua: Muntaia
Atal honetan 2 zatitan bananduta daude, alde batetik muntai mekanikoa eta bestetik muntai elektronikoa. Bideo onetan [OPRobots](https://github.com/OPRobots) sortutakoa da.
[![Botón de video de montaje](https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/pacifista_tutorial_preview_img.jpg)](https://drive.google.com/file/d/10EezfLya-EukxTjCjV9P1Jr0ghWxqBgg/view)


Dena muntatzerakoan,servoak konektatu gabe, zihurtatu artikulazio guztiak ondo mugitzen diren ala ez, bestela, desmontatu eta berriro muntatu edo berriz pieza inprimitu egingo da.

 <p align="center"> Besoa luzatuta                                                      


<p align="center">
  <img width="360" height="200" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/1611818640201.jpg">
</p>

<p align="center"> Besoa jasota

<p align="center">
  <img width="360" height="200" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/1611818640196.jpg">
</p>
 

## 3.Pausua: Robotaren eskema elektrikoa eta bloke diagrama

Hona hemen, robotaren [Bloke diagrama](https://github.com/xabieroiarbide/PacifistaBot/blob/main/Muntaia/Muntai%20elektronikoa/Bloke%20diagrama.png) eta [eskema elektrikoa](https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/eskema.PNG).
<p align="center">
  <img width="360" height="200" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/eskema.PNG">
</p>

<p align="center">
  <img width="360" height="200" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Muntaia/Muntai%20elektronikoa/Bloke%20diagrama.png">
</p>


## 4.Pausua: Kalibrazioa

Muntaia eta artikulazioak ondo daudenean, Bluetooth modulua configuratu beharko da, eta [Servoen kalibrazio program-arekin](https://github.com/xabieroiarbide/PacifistaBot/blob/main/Arduino/Servoen%20Kalibrazioa/Servoen%20kalibrazio%20program) (GOGORATU! servoak kalibratzeko banaka kalibratu egin behar dira) guk nahi dugun artikulazio limiteak jarri ahalko dira. Bestalde, mugikorrarekin aginduak emango diogu robotari [Bluetooth Elektronics](https://www.keuwl.com/apps/bluetoothelectronics/) (Play Store-an dago ere) App-aren bidez.

<p align="center">
  <img width="360" height="200" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/Servo1_bluetooth.jpg">
</p>

Argazki honetan ikusten dugunez, LiFe bateria PCB plakari elikatuta dagoela eta A0 pin-ean konektatuta dagoela.


<p align="center">
  <img width="360" height="200" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/Movil_app_1servo.png">
</p>

Gohiko irudian mugikorran App-ean panel bat sortu eta kalibratzen dugu.


## 5.Pausua: Servomotoreak konektatu
Pausu honetan 12 servomotoreak plakara konektatzen dugu argazkietan bezala.
 
<p align="center">
  <img width="360" height="350" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/ServosRobot.png">
</p>

<p align="center">
  <img width="360" height="350" src="https://github.com/xabieroiarbide/PacifistaBot/blob/main/Argazkiak/PinerServosPCB.png">
</p>


## 6.Pasua: Programa nagusia 

Programa honetan 3 liburutegi izan behar ditu ([Octosnake](https://github.com/xabieroiarbide/PacifistaBot/tree/main/Arduino/Programa%20printzipala/lib), Wire y Servo) Arduino programan. [Programa orokorrean](https://github.com/xabieroiarbide/PacifistaBot/tree/main/Arduino/Programa%20printzipala/src) 5 azpi programa daude (Main, Comunicaciones, Init, Movimientos eta Servocontrol) Main kargatzerakoan irikiko dira. Irikitzerakoan Init azpiprogramara joango gara eta hor 12 servoko posizioak jarriko ditugu lehen ateratako (kalibrazio programan) servo bakoitzeko 3 egoerak.

Ondoren Movimientos azpiprogramara joango gara, eta robotare hasierako posizioa jarriko dugu, eta posicion_hombros eta switch/Case funtzioetan servoak sorbalda aurrera eta atzera definitzeko balio dute.


Beste mugimendu bat, makurtuta, Movimientos azpiprograman posicion_agachado funtzioan 8 arrays dude nun 8 servo hoiek definitu behar diran nola egongo diren makurtuta mugimnedua egin ondoren. Servo hoiek komeni da gure robotaren artikulazioen arabera definitzea hankak ondo tolesteko eta ondo makurtzeko. 
