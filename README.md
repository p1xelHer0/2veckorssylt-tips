# p1xelHer0s spelsyltstips!

## Tips och tricks inför [Kodsnacks Tvåveckorssylt](https://itch.io/jam/kodsnacks-2veckorssylt)

Detta är en liten snabbguide med tips och tricks när du utvecklar ditt spel. Jag har tidigare lekt lite med LÖVE och Lua och tänkte därför dela med mig lite av mina erfarenheter (främst bibliotek som kan underlätta utvecklandet).

* [Läs mer om LÖVE](https://love2d.org/)
* [Läs mer om Lua 5.1](https://www.lua.org/manual/5.1/)

---

## Mitt Projekt
Här är en länk till mitt nuvarande spel som jag tänkt återuppliva och vidareutveckla under spelsylten: [love2d-platformer](https://github.com/p1xelHer0/love2d-platformer)

---


**Table of Contents**

* [Installera bibliotek](#Intallera)
* [Awesome-lista](#Awesome-lista)
* [Nice2Have](#Nice2Have)
* [Annat](#Annat)

---
### Installera bibliotek 🛠

Jag själv kommer från JavaScript-världen och är van att installera saker via [npm](https://www.npmjs.com/). Lua har något liknande vid namn [LuaRocks](https://luarocks.org/) men jag har själv inte använt det.

Oftast står det i readme:n för biblioteket hur det ska installeras. Jag brukar oftast skapa en mapp i rooten av projeket vid namn `lib`. Där brukar jag sen antingen direkt kopiera `lua`-filen. Om inte det duger så brukar jag använda mig av [Git Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules). 

En tl;dr av Submodules, jag vill installera paketet `https://github.com/fake/paket` till min mapp `lib`:
```
git submodule add https://github.com/fake/paket/ lib/
```

Nu ligger paketet i mappen `lib` under namnet `paket`. Du kan då importera paketet genom följade i din `main.lua`:

```lua
local paket = require('lib.paket')
```

> Notera: paketet i fråga kan exportera andra moduler, då får själv kolla pathen du ska ange i `require(...)`!

---

### Awesome-lista 😎

Ni alla har nog sätt liknande i andra ämnen, en "awesome-lista". Här hittar man det mesta, om inte mina förslag duger, titta här!

- [Awesome LÖVE](https://github.com/love2d-community/awesome-love2d)

---

## Förslag à la p1xelHer0

### Nice2Have 💆‍♀️

Generalla bibliotek som underlättar utvecklande! (Det verkar som att allt [rxi](https://github.com/rxi/) gör är fantastiskt!)

- [Lovebird](https://github.com/rxi/lovebird) - Browser-baserad debugkonsol.
- [Lume](https://github.com/rxi/lume) - massvis med små hjälpfunktioner som underlättar spelutveckling.
- [Lurker](https://github.com/rxi/lurker) - "hotswap":a Lua-filer när dom sparas. _Behöver Lume för att fungera!_
- [hump](https://hump.readthedocs.io/en/latest/index.html) - Hjälpklasser för spelutveckling, tänk `vector`, `timer`, `camera` med mera. Jag har själv använt `hump.vector` och `hump.timer`.

### Fysik 🤼‍♀️

Bibliotek för att lägga till fysik i ditt spel, tänk er kollisionshantering.

- [bump.lua](https://github.com/kikito/bump.lua) - Kollisionsbibliotek för AABB (axis-aligned bounding box), delvis endast för rektanglar! Föredra detta om du endast jobbar med just rektanglar.
- [Hadron Collider](https://hc.readthedocs.io/en/latest/) - Kollisionbibliotek för punkter, cirklar och polygoner. Komplexare än [bump.lua](#bump.lua).
- [love.physics](https://love2d.org/wiki/love.physics) - Medflöljer i LÖVE, bindings till [Box2D](http://box2d.org/).

### Skapa banor 🗺

Verktyg som hjälper dig att skapa banor till ditt spel

- [Tiled](https://www.mapeditor.org) - Program utanför spelet som hjälper dig att skapa så kallade Tilemaps, banor indelade i kvadrater. Perfekt för att snabbt kunna iterera.
- [STI](https://github.com/karai17/Simple-Tiled-Implementation) - Bibliotek för att skapa banor i LÖVE utfrån exporter ifrån [Tiled](#Tiled).

### Annat 🤷‍♀️

* [scrale.lua](https://github.com/MartyMaro/scrale) - Litet bibliotek för att hantera skalning av pixelart till olika skärmar.

### Overkill, men kul, Entity Component System 🔥

Bibliotek som får dig att slösa tid på att skriva kod istället för att göra spel, men vill man lära sig om ECS, som kanske främst användes i större spel skriva i typade språk kan det vara roligt...! Jag har själv använt HooECS i mitt projekt.

Biblioteken skiljer sig lite, men konceptet ECS är desamma!

* [HooECS](https://github.com/Hooodini/HooECS)
* [tiny-ecs](https://github.com/bakpakin/tiny-ecs/)
