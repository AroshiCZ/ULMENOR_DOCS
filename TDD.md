# Technická Dokumentace hry *Kroniky Ulmenoru*


>Tento dokument se bude zabírat technickou stránkou hry "*Kroniky Ulmenoru*".
>
>Jedná se o velice jednoduchou a primitivní *Point & Click* Adventure hru, která se ovládá pouze pomocí dvou tlačítek na myši a kurzorem. 
>
> ---
>
>Základem hry bylo (ne příliš štastně) vybrán herní engine Unity. Byl využit jeho základní template pro 2D hru, avšak celá hra se ve výsledku odehrává v jediném *Canvas* gameObjectku, který je upravován podle potřeby.
<br>
<br>


> ## Základ fungování
> Hra využívá hlavního Canvasu **MainUICanvas** ve kterém se nachází následující pod objekty:
> 
> - `Image` - slouží jako background celého UI kde není žádné jiné pole nebo herní objekt.
> - `BackgroundImage` - Herní pole ve kterém se nachází prvky hry, se kterýmy hráč interaguje během průběhu hry, jako například sebratelné předměty a jiné.
> - `Inventory` - Inventář hráče, ve kterém lze kombinovat a prohlížet předměty.
> - `InventoryTextHolder` - Pouze pole s textem "*Inventář*"
> - `RoomName` - Nachází se na horní části obrazovky, a ukazuje název aktuální místnosti/polohy hráče.
> - `ActiveItemPanel` - Zobrazuje ikonu, název a popis zvoleného předmětu. Zároveň umí zobrazit popis vstupu do jiné lokace.
> - `Hints` - Obsahuje pomoc pro uživatele jak ovládat hru.
> - `DialogPanel` - Obsahuje tlačítko s textem "*Další*", sloužící pro posun v konverzacích, a textový blok pro zobrazení textu konverzace.
> 