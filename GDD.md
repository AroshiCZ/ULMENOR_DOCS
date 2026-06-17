# Uživatelská Documentace hry *Kroniky Ulmenoru*

## Obsah : 
- Instalace
- Spuštění hry
- Ukládání hry
- Ovládání


### Instalace :
Instalace hry *Kroniky Ulmenoru* je velicé jednoduchá, a jednosměrná. Testovaná verze byla zprovozněna na linuxu Mint (`Linux Mint 22.1 Cinnamon, with Linux 6.14.0-37-generic`) a běží bez jakýkoliv problémů. Stačí si stáhnout .x86_64 soubor pro linux verzi, či .exe soubor pro windows verzi. Momentálně nebylo provedeno testování na MacOS, ale díky linuxovému jádru tohoto operačního systému by nemněly nastat žádné problémy se spuštěním či hraním této hry.

### Spuštění hry : 
Na hlavní obrazovce se nachází 4 tlačítka. První přesune uživatele rovnou do hry a vybere jako výchozí pozici uložení "Slot 1". Druhé pak umožnuje načíst hru z již uložené pozice 1-3 (Zatím nebylo implementováno ukládání, a hra tedy opět začne po vybrání pozice od začátku). Další tlačítko s textem "Kredity" poté přesune uživatele na obrazovku s kredity ke hře. Poslední tlačítko "Odejít" poté ukončí program.

### Ukládání hry : 
V této verzi hry ještě není implementováno žádné ukládání hry, ale již byl připraven postup k jeho uložení, a v hlavním menu hry se dá vybrat kterou uloženou pozici si hráč chce načíst, z až 3 dostupných pozic. Momentálně se však hra vždy po vybrání pozice zapne od začátku, a hra data nikam neukládá, pouze si uloží která pozice byla vybrána pro pozdější implementaci. Ukládání bude později prováděno automaticky při každém přesunu či sebrání itemu, nebo jiné interakce se světem. Jelikož k ukládání bude použit pouze nešifrovaný JSON soubor, a díky nenáročnosti hry může být použit tento přístup.

### Ovládání :
Celá hra se ovládá pomocí myšy. Pomocí levého tlačítka je možno jak mluvit s NPC (Non-player character - Nehráčské postavy) a zároveň sbírat předměty po mapě. Zároveň, pokuď je levým tlačítkem myši kliknuto na vstup do jiné místnosti, se hráč přesune do dané místnosti. Pravým tlačítkem se poté dají předměty použít na jiné předměty či případně na jiné entity ve hře které zatím nejsou implementovány, ale mohou býti v budoucích verzích, jako například použití předmětu na vstup pro jeho odemčení. Zárověň pokuď není vybrán žádný předmět, tak je pravé tlačítko myši použito pro podívání se na předmět, kdy se zobrazí informace o zvoleném předmětu v levém horním rohu, společně s jeho názvem a ikonou, aby bylo jasné o jaký předmět se jedná, či do jaké místnosti vede vstup na který se hráč podívá. Při kliknutí levým tlačítkem na prázdné místo se poté výběr zruší. Zjednodušené ovládání je také zobrazeno konstantně ve hře pod polem s informacemi o předmětu či vstupu.

### Dialogy :
Dialogy jsou v této verzi velmi minimalizované, každé npc je spíše nápověda co by mněl hráč hledat dále, nebo které předměty zkombinovat, jelikož svět Ulmenoru je velice nepředvídatelný, a hráč který nemá předešlou znalost světa by mněl mnoho problémů hru dohrát bez použitý taktiky používání všeho na vše. Do dialogu se hráč dostane kliknutím levým tlačítkem na NPC, a poté se dialog odehrává v dialogovém boxu pod herní obrazovkou, kde se nachází tlačítko pro pokračování v dialogu. Hra nemá žádný časový limit pro zobrazování dialogu, avšak není možno používat předměty během dialogu.  
