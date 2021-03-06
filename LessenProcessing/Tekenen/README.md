# Tekenen

 * Door Bo, Lucas, Richel

Processing is een codeer taal waar goed mee getekend kan worden.
maar voordat we daarmee beginnen moeten we eerst een paar basics leren.

```
void setup()
{
  size(600, 400);
}

void draw() 
{
  
}
```

dit stukje code geeft je een scherm om op te tekenen. 
het bestaat uit drie delen:
* `void setup() {}`
  * `setup` is een functie die een keer word uitgevoerd aan het begin van de code. In `setup` wordt vooral het scherm aangeroepen. Ook zou je hier de frame rate van het scherm in kunnen stellen en bestanden vanaf je computer laden. `setup` wordt een keer uitgevoerd.
* `size(x, y)`;
  * dit is een de functie die een scherm maakt er grote can x breed en y hoog.
* `void draw() {}`
  * dit is een speciale omgeving waarin we de code schrijven die wordt getekent. Alles binnen de accolades van `draw` wordt (na `setup`) oneindig herhaald.

### Vragen

 * Welk commando geeft een scherm van 800 bij 800 pixels?
 * Wat als je een scherm van 5 cm bij 3 cm wilt? (1 cm = 37.8 pixels)?
 * Wat als je fullscreen wilt?

Nu als je wilt tekenen moeten we leren werken met coordinaten. net zoals op een kaart hebben we x coordinaten en y coordinaten.
het makkelijkst is om je een ruitjes blad dat gebruikt wordt bij wiskunde voor te stellen. 

![Figuur 1: coordinate grid](Cartesian_coordinates_2D2.png)

je scherm heeft pixels die werkt net als het ruitjes blad. elke pixels is een coordinaat op het ruitjesblad.
de x coordinaten vertellen hoeveel je naar rechts en links wil, de y coordinaten hoeveel je naar boven en beneden wil.
de computer werkt alleen net iets anders op de y-as (naar boven en beneden). Als je naar beneden wilt moet je y coordinaat groter worden. zoals in het plaatje te zien is. coordinaten worden altijd geschreven met de x coordinaat eerst en daarna de y coordinaat (x,y). wanneer coordinaten worden door gegeven aan de computer kunnen we tekenen op het scherm.

![Figuur 2: computer coordinate grid](Computer_coordinates_2D.png)

### Vragen

pak een schrift of blaadje met ruitjes. hierop gaan we coordinaten oefenen.

 * teken een computer grid met een x-as van 15 pixels en een y-as van 15 pixels, zet links bovenin de 0 en tel dan bij elke lijn 1 op tot je 15 pixels hebt.
LETOP! een computer telt inplaats van 1 tot 15 van 0 tot tot 14. als je goed kijkt zie dat er dan nog steeds 15 cijfers zijn. 
 * zet een stip op coordinaat (0,0), (0,14), (14,0), (14,14), (7,7)).
 * zet een stip of coordinaat (7,3)
 * zet een stip of coordinaat (5,1)
 * zet een stip of coordinaat (3,3)
 * zet een stip of coordinaat (7,7)
 * zet een stip of coordinaat (11,3)
 * zet een stip of coordinaat (9,1)
 * verbint nu alle stippen. (als het goed is een hartje)

Er zijn vier simpele functies om mee te tekenen op het computer scherm en ze werken allemaal met x en y coordinaten.
line (lijn),triangle (driehoek),rect (rechthoek),ellipse (cirkel).

`line(x1,y1,x2,y2)`: dit tekent een lijn van punt 1 naar punt 2. de x1 en y1 vertellen waar het eerste punt komt, x2 en y2 waar het tweede punt komt. de computer tekent dan een lijn tussen deze twee punten in.

### Vragen

Nu gaan we tekenen op de computer. 
Hiervoor hebben we een stukje code nodig dat eerder is uitgelegd.

```
void setup()
{
  size(600, 400);
}

void draw() 
{
  // hier zet je alles dat getekent moet worden
}
```
 * teken deze lijnen: `line(200,150,250,100)`,`line(250,100,300,150)`, `line(200,150,300,150)`
 * teken een lijn van coordinaat (200,150) naar (200, 250)
 * teken een lijn van coordinaat (200,250) naar (300, 250)
 * teken een lijn van cordinaat (300,250) naar (300,150)

Je hebt nu een huisje getekent.
Je code moet er nu zo uit zien:

```
void draw()
{
  line(200,150,250,100);
  line(250,100,300,150);
  line(200,150,300,150);
  line(200,150,200,250);
  line(200,250,300,250);
  line(300,250,300,150);
}
```

 * wat gebeurt er als je een lijn tekent van coordinaat (500,200) naar (700,200)
 * wat gebeurt er als je een lijn tekent van coordinaat (100,300) naar (100,500)
 * wat gebeurt er als je een lijn tekent van coordinaat (-100,100) naar (100,100)
 * wat gebeurt er als je een lijn tekent van coordinaat (100,-100) naar (100,100)
 * speel met de `line(x1,y1,x2,y2)` functie todat je hem onder de knie hebt.

Nu heb je onder de knie hoe je lijnen kunt tekenen, 
met lijnen kan je natuurlijk alle figuren maken die je wilt, 
maar er zijn ook al makkelijkere functies gemaakt die je daarbij heel goed kunnen helpen. 
In de oefening heb je een dak getekend voor een huisje. 
Inplaats van drie `line` functies te gebruiken kan je ook een `triangle` functie gebruiken. 
De `triangle` functie kan in een keer driehoeken tekenen:
`triangle(x1,y1,x2,y2,x3,y3)`: de triangle() functie heeft 3 coordinaten nodig en verbint deze dan met lijnen. 
 
### Vragen

 * Teken een driehoek op coordinaten (100,20), (50,50), (150,50)
 * Teken een paar driehoeken, om te oefenen.
 * Vervang de 3 `line` functies uit de vorige opdracthen met een `triangle` functie 

Om een vierkant of cirkel te tekenen krijg je met twee nieuwe termen te maken, hoogte en breedte. om een vierkant te tekenen geef je de (x,y) coordinaten van de linker bovenhoek van het vierkant. daarna vertel je hoe breed en hoog het vierkant moet worden. 
`rect(x,y,breedte,hoogte)`

### Vragen

 * Teken een vierkant op coordinaat (500,100) met een hoogte van 100 en een breedte van 50
 * Teken een vierkant met hoogte 40 en breedte 100
 * Teken een vierkant met breedte 60 en hoogte 60
 * Vervang de 3 overgebleven line() functies van het huisje en vervang het met 1 rect() functie
 * Teken een raampje en een deur in het huisje met de rect()

De ellipse is vergelijkbaar met de rect() fuctie. Een word een coordinaat gegeven met een breedte en een hoogte. bij de ellipse is de coordinaat die gegeven wordt het middelste punt van de cirkel.
`ellipse(x,y,breedte,hoogte)`

### Vragen

 * Teken een cirkel op coordinaat (100, 300) met breedte 50 en hoogte 50
 * Wat gebeurte er als je de hoogte verandert maar de breedte niet
 * Teken een cirkel op coordinaat (100, 300) met breedte 70 en hoogte 30
 * Teken een cirkel op coordinaat (100, 300) met hoogte 70 en breedte 30
 * Teken een paar cirkels om te oefenen
 * Teken een zolderraam in het huisje

Nu weet je de basic functies om mee te tekenen in processing. Er zijn een aantal andere functies om de vier vooreen uitgelegde functies te versterken en flexibeler te maken. eerst moeten we wat leren over het RGB kleuren systeem. RGB is een afkorting van RED GREEN BLUE. met deze drie kleuren kan de computer alle mogelijke kleuren die wij kunnen zien maken. de computer heeft voor elke van de drie kleuren (RED/GREEN/BLUE) een waarde van 0 tot 255 nodig. hoe hoger de waarde hoe feller de kleur, op deze site kan je een beetje spelen met RGB. [RGB rekenmachine](http://www.rapidtables.com/web/color/RGB_Color.html)
Er drie functies die werken met het RGB systeem.
* `background(RED, GREEN, BLUE)` 
  * background() wordt in het begin draw() opgeroepen. background staat voor achtergrond en bepaalt dus de kleur van het scherm zelf. 
* `fill(RED, GREEN, BLUE)`
  * fill() wordt gebruikt om je figuur dat net is getekend in te vullen met een kleur. fill() werkt met ellipse(), triangle() en rect(). 
* `stroke(RED, GREEN, BLUE)`
  * stroke() wordt gebruikt om de lijn van het figuur te kleuren. stroke() werkt met ellipse(), triangle(), rect() en line().

* `noFill()`
  * noFill() is het omgekeerde van fill(), het zorgt ervoor dat er het figuur dat getekent is doorzichtig wordt. noFill() werkt met ellipse(), triangle() en rect(). 
* `noStroke()`
  * noStroke() zorgt ervoor dat de lijnen waarmee je figuur wordt getekent verdwijnen. noStroke() werkt met ellipse(), triangle(), rect() en line().
* `strokeWeight(x)`
  * strokeWeight() bepaalt de dikte van de lijnen die worden getekent. als je een figuur wilt met dikke lijnen gebruikt je de strokeWeight().

Dit zijn allemaal functies om je tekeningen mooier te maken of in te kleuren. TIP: deze functie schrijf je boven het figuur dat je wil tekenen. als je het erna zet werkt het niet.

```
void draw()
{
  background(0,0,0)

  //dit werkt
  fill(0,255,0)
  rect(100,100,50,50)

  //dit niet
  rect(100,100,50,50)
  fill(255,0,0)
}
```

### Vragen

 * geef de tekening een mooie achtegrond kleur die jezelf hebt uitgezocht met de RGB rekenmachine
 * kleur het huisje in
 * geef een figuur dikkere lijnen
 * maak een figuur doorzichtig
 * geef een figuur blauw zonder de zwarte lijnen om het figuur.

Nu weet je hoe je kan tekenen met Processing. 
Dit is het begin om games te maken. 
Als het coördinaten vinden nog lastig gaat, blijf oefenen met tekenen. 
In de volgende hoofdstukken gaan we leren hoe we de tekeningen die we hebben gemaakt kunnen laten bewegen.