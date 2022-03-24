# kurs-klokke


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
```html
<body>
    <div class="w-full h-full grid content-center bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500">
        
    </div>
</body>  
 
```
 
