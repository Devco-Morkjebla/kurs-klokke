![image](https://user-images.githubusercontent.com/71834553/160104224-18424314-2095-470a-a972-07a4002ca4d5.png)


![I dette kurset vil du lære](https://arvidgithubembed.herokuapp.com/skills?languages=javascript,tailwind,html5&backgroundcolor=0D1117&bordercolor=0D1117&title=I%20dette%20kurset%20vil%20du%20lære&titlecolor=ffffff&textcolor=dddddd&boxcolor=0D1117)

# Innhold

[Oppgave1](#Oppgave1)

[Oppgave2](#Oppgave2)

[Oppgave3](#oppgave3)

[Oppgave4](#oppgave4)

[Oppgave5](#oppgave5)

[Oppgave6](#oppgave6)

#oppgave 1

1. Start med å åpne VScode eller en annen editor.

Vis du ikke har VScode så kan du innstallere det her: https://code.visualstudio.com/docs/?dv=win

# 

2. Skriv så inn taggene for å opprette en nettside. 

Pass på at du får med `<html>`, `<body>`, `<head>`, `<style>`, og `<script>` taggen

Filen burde da se noenlunde sånn ut:
```html
<html lang="en">

<head>
  
</head>

<body>

</body>
  

<style>

</style>

<script>
    
</script>

</html>
```

#

Nå kan du legge til tailwindCSS ved å kopiere denne linken `https://cdn.tailwindcss.com` og plassere den inni en egen `<script>` tag. 
Inne i `<script>` taggen kan du spesifisere sourcen til scriptet. Der kan du lime inn linken du nettopp kopierte.
```html
<script src="https://cdn.tailwindcss.com"></script>
```

Denne script taggen kan du da legge under `<html>` taggen på 2. linje

#

`<head>` taggen brukes for å definere metadata. 
Alt av content hører til i `<body>` taggen.
`<script>` taggen brukes for å utføre script. 
og `<style>` taggen brukes til å gi HTML elementene style.

I denne tutorialene kommer vi ikke til å bruke `<style>` taggen i det hele tatt. 
Istedenfor å definere styles manuelt, så lar vi tailwind generere den for oss.

#

3. Du kan så begynne med å lage HTML oppsettet til klokken. 

Inne i `<body>` taggen begynner du med å lage en `<div>`.
En `<div>` fungerer som en kontainer. `<div>` taggen grupperer alt som ligger inni den.
  Så å si alle HTML tagger må bli lukket. Dette kan gjøres ved å skrive `</"navnet på taggen">`  
  
I denne `<div>` taggen kan du gi kontaineren diverse klasser som vil gi kontaineren og dens innhold forskjellig utseende.

![image](https://user-images.githubusercontent.com/71834553/159876711-b5ecd323-7ee5-4c2c-9653-9ae7e8828ded.png)

Her så har vi satt stylingen på kontaineren slik at bredden på den er 100% (w-full) og at høyden på den er 100% (h-full). 
Vi har også satt kontaineren til å være en grid (grid). Dette gir mulighet for å plassere innholdet i kontaineren i midten ved hjelp av `content-center` klassen

# 

I tailwind så kan du gi kontaineren en bakgrunn ved å skrive `bg-` og så din ønskede farge. 
Legg merke til at tailwind har et stort utvalg av farger og fargetoner. 
Her er en liste over fargene som er støttet.
https://tailwindcss.com/docs/background-color

Her så har vi gikk kontaineren en gradient som går mot høyre. Gradienten går fra fargen `indigo-500` (from-indigo-500), har så `purple-500` i midten (via-purple-500) og så `pink-500` i enden (to-pink-500)

##

Inne i `<div>` kontaineren så kan du lage enda en `<div>` kontainer. Denne skal ha klassene `flex`,`flex-row` og `justify-center`
`Flex` klassen sørger for at innholdet tilpasser seg skjermbredden. `flex-row` klassen gjør at elementene inni kontaineren ligger på rad.
`justifiy-center` klassen er ansvarlig for at elementene ligger i midten.

![image](https://user-images.githubusercontent.com/71834553/159911655-ea53c50f-0e7c-455e-b6b5-191cd4ec483a.png)


#

Inne i `<div>` kontaineren du lagde kan du nå lage tre nye `<div>` kontainere. En til å vise Timer, en for minutter og en for sekunder.

![image](https://user-images.githubusercontent.com/71834553/159911830-953ad38f-9756-4759-86f5-e222d9df7f67.png)

#

Siden det ikke er helt optimalt å displaye tekst direkte inne i en kontainer så kan du lage en `<h2>` tag i hver av de tre kontainerene
Siden du senere skal få teksten i `<h2>` taggen til å endre seg i tiden, så må du gi hver av de tre `<h2>` taggene en id. 
IDen må være unik og kan/burde bare brukes en gang i HTML filen. 
Derfor anbefaler **Devco** at du gir den første `<h2>` taggen en id på `hours` eller `timer`, den andre `<h2>` taggen en id på `minutes` osv

I tillegg så kan du gi `<h2>` taggene ett utseende ved å bruke tailwind classer.

`<h2>` taggene burde da se noenlunde slik ut.

![image](https://user-images.githubusercontent.com/71834553/159912039-014f2ab5-3f06-4c80-b9b5-d0f0afcaa15a.png)

#

Nå er du klar til å åpne klokken med Live Server.

Høyreklikk på filen og trykk åpne med Live Server

![image](https://user-images.githubusercontent.com/71834553/160077501-af0f97df-075e-4144-8d4b-3599515aa612.png)

Live Server vil så åpne en live fane i din browser. ALt du trenger å gjøre heretter er å refreshe nettsiden med `CTRL` + `F5` eller `Shift` + `F5` 

#

Du er nå klar til å gi liv til din klokke.

Start med å hoppe ned til `<script>`taggen du lagde tidligere.

Inne i denne `<script>` taggen må/kan du lage en setInterval funksjon.

![image](https://user-images.githubusercontent.com/71834553/159877459-e7894582-f799-4d72-9eb7-51b24c9f738f.png)

En setInterval funksjon kan brukes til å kjøre noe flere ganger, men med en delay. Delayen defineres i millisekund bak den siste `}` bracketen.  
Siden klokken skal oppdateres hvert sekund må du sette delayen til 1000 millisekund.

![image](https://user-images.githubusercontent.com/71834553/159877867-3cc1353f-a1e5-4dba-8a99-94a993db677e.png)

Inne i setInterval funksjonen må du først hente datoen. Dette kan gjøres ved å definere en constant variabel og sette den til **new Date()**

![image](https://user-images.githubusercontent.com/71834553/159878134-c24d1899-fff2-4a56-8077-2b97800a0c4f.png)

Du må også definere en variabel for zero slik at vi kan sette en 0 bak timer, minutt og sekund om de er mindre enn 10

![image](https://user-images.githubusercontent.com/71834553/159907490-cc0cd532-2f67-4e66-9cbe-482fa41a53b5.png)



Deretter må du få ut timer, minutter og sekunder fra variabelen du laget. 
Dette kan du gjøre ved å lage tre nye variabler. 
Variabelen for timer kan du sette til date.getHours()
Variabelen for minutter kan du sette til date.getMinutes()
Variabelen for sekunder kan du sette til date.getSeconds()

![image](https://user-images.githubusercontent.com/71834553/159908159-c0344d07-c510-4db0-8023-1e7e39aa0ab9.png)

Du må så sjekke om timer, minutter og sekunder er mindre enn 10. 
Om den er mindre enn 10 så må du legge til en 0 forran.
Da lager du en if statement for timer, minutter og sekund der du sjekker om verdien er mindre enn 10

![image](https://user-images.githubusercontent.com/71834553/159907580-b44c52a5-acd4-40f5-bb7b-47480e3fe09c.png)
![image](https://user-images.githubusercontent.com/71834553/159907608-4c614e59-334f-46d6-95a6-2fbe1cc75fdb.png)
![image](https://user-images.githubusercontent.com/71834553/159907623-d9fe539e-8ad5-4393-bf85-efd4c8f9f640.png)

Til slutt må du oppdatere `<h2>` taggene for timer, minutter og sekunder.
Da kan du hente inn elementene i javascript ved å skrive:

```javascript
let hourTag = document.getElementById("hours");
let minuteTag = document.getElementById("minutes");
let secondTag = document.getElementById("seconds");
```


JavaScript har en funksjon som heter Template Literals. Dette gir oss muligheten til å skrive variabler rett inn i en string.
For å bruke denne funksjonen så må du sette teksten inn i disse tegnene ``

Så kan du sette inn hvilken som helst variabel ved å sette den inni disse tegnene ${}


Deretter kan du skrive
```javascript
hourTag.innerText = `${zeroHours}${hour}`
minuteTag.innerText = `:${zeroMinutes}${minute}:`
hourTag.innerText = `${zeroSeconds}${second}`
```
Når du setter teksten på minute så kan du legge ":" forran og bak slik at du ender opp med med 00:00:00

Gratulerer! Du er nå ferdig med oppgave 1

#oppgave 2

I denne oppgaven skal du lage en funksjon som skriver datoen under klokken.

Hint: Du kan bruke date variabelen du har definert fra før 

![image](https://user-images.githubusercontent.com/71834553/160081911-72d5d2d2-1dae-4a08-bf19-36e4753336ce.png)


#oppgave 3

Gå og spill en av disse

<a href="https://knightsoftheflexboxtable.com/">Knights Of The Flexbox Table</a>

<a href="https://cssgridgarden.com/">CSS Grid Garden</a>

<a href="https://flexboxfroggy.com/">Flexbox Froggy</a>

#oppgave 4

Lag en smakfull nettside om en av hobbyene/interessene dine ved hjelp av tailwindcss.

## Oppgave 5 (Optional)

Gå og utforsk tailwind
https://play.tailwindcss.com/

#oppgave 6

Gå og svar på <a href="https://forms.office.com/r/vR9SF1WRat">Formsen</a>

