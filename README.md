# fs-product-configurator

### Update Filter:

Op deze branch even een update op de filter functie. Ik ben er nu achter hoe ik deze uit de `method` kan halen. Ik heb hem nu als aparte filterfunctie neergezet:

```
function filterResults(input) {
  const filteredResults = input.products.filter(door => {
    return (
      (input.type === door.type || !input.type) &&
      (input.width < door.width ?? input.type === 0) &&
      (input.height < door.height ?? input.type === 0) &&
      (input.assemblyPosition === door.assemblyPosition ||
        !input.assemblyPosition) &&
      (input.selfHealing === door.selfHealing || !input.selfHealing) &&
      (input.stainlessSteel === door.stainlessSteel || !input.stainlessSteel) &&
      (input.windLoad === door.windLoad || !input.windLoad)
    );
  });
  return filteredResults;
}

```

# Hi Daan en Mike,

Ben benieuwd wat je ervan vindt. Ik moet zeggen dat ik nog steeds op zoek ben naar de juist manier om `data() {}` en methods goed te krijgen. Bij react kun je ook class-based components gebruiken met het this. keyword maar ik geef de voorkeur aan de functional components waarmee je eigenlijk alles als een functie schrijft.

Ik kwam daarom een beetje in de knoop met de filter functie, omdat die gegevens via een `$emit` terug naar de parent component worden gestuurd. Ik denk dat het een stuk beter kan, maar dan moet ik even wat beter naar de structuur van Vue kijken.

Ook heb ik een klein Grid framework geschreven in SCSS om het responsive te krijgen. Ook een beetje rommelig, voor een production app zou dit beter gestructureerd moeten zijn, maar ik hoop dat jullie het idee een beetje krijgen.

# Om hem op jullie machines te krijgen:

```
gh repo clone BleddP/fs-project-configurator
```

```
npm install
```

```
npm run serve
```

En dan draait hij op localhost:8080.

# Tests

Ik heb geen tijd gehad om tests te schrijven.
