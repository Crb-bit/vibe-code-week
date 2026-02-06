1. Tech Stack

Frontend
    HTML, CSS, JavaScript
    Canvas of simpele DOM-based UI
    (Optioneel) Phaser.js voor 2D game-logica
Backend / Logica
    JavaScript (client-side)
    Random number generation via JavaScript

Tools
    VS Code
    Git / GitHub
    Browser (Chrome / Firefox) voor testing

2. Globale Architectuur

UI Layer
    Toont twee paden
    Laat kansen en mogelijke materialen zien
    Geeft feedback na een keuze
    Game Logic Layer
    Genereert willekeurige kansen per ronde
    Berekent welk materiaal de speler krijgt
    Verwerkt winst of verlies
    Data Layer
    Materialen (naam, waarde, kans)
    Score of totale opbrengst van de speler
    Alles draait lokaal in de browser zonder externe server.

3. Belangrijke Keuzes

Kansen zichtbaar maken
    Spelers zien de percentages zodat keuzes gebaseerd zijn op inzicht, niet alleen geluk.

Random maar gebalanceerd
    Waardevolle materialen hebben altijd lagere kansen om het risico eerlijk te houden.

Simpel scope
    Geen accounts, geen multiplayer, geen echte valuta — focus op de kern: keuzes maken.

Twee paden per ronde
    Houdt het spel overzichtelijk en voorkomt keuzestress.

4. Bekende Risico’s

Balancing probleem
    Als kansen niet goed zijn afgestemd, voelt het spel te makkelijk of juist oneerlijk.

Herhalend gameplay-gevoel
    Zonder extra variatie kan het spel na verloop van tijd saai worden.

Ethiek rondom gokken
    Het spel kan gokken stimuleren; daarom geen echte geldbeloningen of microtransacties.

Te veel randomness
    Als spelers het gevoel hebben dat keuzes er niet toe doen, haken ze af.

dag 4:
    wat heb ik aangepast?:
        de code language, heb alleen html gebruikt, voor de rest is alles hetzelfde.