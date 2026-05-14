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


> ## Funkce Itemů
> Všechny itemy jsou řešené pomocí `ScriptableObject` class. která umožňuje vytvoření templatu pro všechny itemy, a zároveň tak vytvořit základ pro novou hru, při které dojde k načtení všech instancí pomocí těchto ScriptableObjectů místo dat uložených v hráčově datech. Tato data jsou poté přepsána (Toto se stane pouze pokuď si hráč vybere vytvořit nový savefile).
> Itemy podporují následující funkce :
>  - `PointerEventData.InputButton.Left` - Sebere item ze země a přidá ho do inventáře. Sebrané itemy nelze již odstranit z inventáře, pouze s nimi kombinovat jiné itemy. Pokuď je tato funkce použitá znovu na item v inventáři, tak se item přesune na konec inventáře, efektivně slouží jako organizace inventáře.
> - `PointerEventData.InputButton.Right` - Slouží pro podívání se na předmět, a zobrazení jeho názvu a podrobností o něm. Pokuď je funkce zavolaná ve chvíli kdy se hráč dívá na jiný předmět, tak se hra pokusí předměty spojit. Při úspěšném spojení dojde k vytvoření nového itemu, při nepodařeném se nic nestane.
>
> Dále itemy používají script `ItemRuntimeState.cs` který umožnuje interakci s itemem během runtimu bez nutnosti upravování původního ScriptableObjectu, a má následující funkce :
> - `public void PickUp()` - Nastaví hodnotu `IsUsed` na true, tato hodnota rozhoduje zda je předmět v inventáří, či je na mapě stále.
> - `public void Use()` - Nastaví hodnotu `IsUsed` na true.
> - `public void ResetToTemplate()` - Resetuje všechny hodnoty itemu na základní hodnoty nacházející se ve ScriptableObjectu daného itemu.
> - `public int GetItemID()` - Vrací ID daného itemu, použito při kombinování itemů pro vytvoření nového.
> - `public int GetCollectionID()` - Vrátí ID kolekce do které item spadá. Kolekce jsou určené k rozhodování jaké itemy jdou spojit, a jak mají být spojeny.
> - `public string GetItemName()` - Vrací název itemu.
> - `public string GetItemDescription()` - Vrací podrobnosti o itemu.
> - `public int bool IsConsumable()` - Nevyužitá funkce pro budou podporu Consumable itemu, které se použijí a přímo sami spustí nějakou událost ve hře.
> - `public Sprite GetItemIcon()` - Vrací sprite itemu, použito při vykreslování itemu na mapě či inventáři.


> K itemům také patří `InventoryControler.cs` který se stará o funkčnost inventáře a zobrazování itemů, a podporuje následující funkce :
> - `SetActive(GameObject item)` - Nastaví zobrazení podrobností o itemu v příslušném okně, a zároveň ho označí jako aktivní.
> - `ResetActive()` - Odstraní data o zobrazovaném itemu, a odstraní jeho uznačení jako aktivní.
> - `AddItem(GameObject item)` - přidá daný item do inventáře.