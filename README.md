# kurs-klokke
Oppgave 1

1. Start med å åpne VScode eller en annen editor.

Skriv så inn taggene for å opprette en nettside. 

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
Du kan så begynne med å lage HTML oppsettet til klokken. 

Inne i `<body>` taggen begynner du med å lage en `<div>`.
En `<div>` fungerer som en kontainer. `<div>` taggen grupperer alt som ligger inni den.
  Så å si alle HTML tagger må bli lukket. Dette kan gjøres ved å skrive `</"navnet på taggen">`  
  
I denne `<div>` taggen kan du gi kontaineren diverse klasser som vil gi kontaineren og dens innhold forskjellig utseende.

![image](https://user-images.githubusercontent.com/71834553/159876711-b5ecd323-7ee5-4c2c-9653-9ae7e8828ded.png)



#

Inne i `<div>` kontaineren du lagde kan du nå lage tre nye `<div>` kontainere. En til å vise Timer, en for minutter og en for sekunder.

#

Siden det ikke er helt optimalt å displaye tekst direkte inne i en kontainer så kan du lage en `<h2>` tag i hver av de tre kontainerene
Siden du senere skal få teksten i `<h2>` taggen til å endre seg i tiden, så må du gi hver av de tre `<h2>` taggene en id. 
IDen må være unik og kan/burde bare brukes en gang i HTML filen. 
Derfor anbefaler **Devco** at du gir den første `<h2>` taggen en id på `hours` eller `timer`, den andre `<h2>` taggen en id på `minutes` osv

I tillegg så kan du gi `<h2>` taggene ett utseende ved å bruke tailwind classer.

`<h2>` taggene burde da se noenlunde slik ut.

![image](https://user-images.githubusercontent.com/71834553/159876582-19f9e9d7-582a-4bfc-b3db-e974f3c7469d.png)

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

Du må så sjekke om timer, minutter og sekund er mindre enn 10. 
Om den er mindre enn 10 så må du legge til en 0 forran.
Da lager du en if statement for timer, minutter og sekund der du sjekker om verdien er mindre enn 10

![image](https://user-images.githubusercontent.com/71834553/159907580-b44c52a5-acd4-40f5-bb7b-47480e3fe09c.png)
![image](https://user-images.githubusercontent.com/71834553/159907608-4c614e59-334f-46d6-95a6-2fbe1cc75fdb.png)
![image](https://user-images.githubusercontent.com/71834553/159907623-d9fe539e-8ad5-4393-bf85-efd4c8f9f640.png)

Til slutt må du oppdatere `<h2>` taggene for timer, minutter og sekunder.
Da kan du hente inn elementene i javascript ved å skrive:

`let hourTag = document.getElementById("hours")`
`let minuteTag = document.getElementById("minutes")`
`let secondTag = document.getElementById("seconds")`

JavaScript har en funksjon som heter Template Literals. Dette gir oss muligheten til å skrive variabler rett inn i en string.
For å bruke denne funksjonen så må kan du sette teksten inn i disse tegnene ``

Så kan du sette inn hvilken som helst variabel ved å sette den inni disse tegnene ${}


Deretter kan du skrive
```javascript
hourTag.innerText = `${zeroHours}${hour}`
minuteTag.innerText = `:${zeroMinutes}${minute}:`
hourTag.innerText = `${zeroSeconds}${second}`
```
Når du setter teksten på minute så kan du legge ":" forran og bak slik at du ender opp med med 00:00:00
