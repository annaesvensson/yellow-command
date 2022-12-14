<p align="right"><a href="README-de.md">Deutsch</a> &nbsp; <a href="README.md">English</a> &nbsp; <a href="README-sv.md">Svenska</a></p>

# Command 0.8.45

Webbplatsens kommandorad.

<p align="center"><img src="command-screenshot.png?raw=true" alt="Skärmdump"></p>

## Hur man installerar ett tillägg

[Ladda ner ZIP-filen](https://github.com/annaesvensson/yellow-command/archive/main.zip) och kopiera den till din `system/extensions` mapp. [Läs mer om tillägg](https://github.com/annaesvensson/yellow-update/tree/main/README-sv.md).

## Hur man visar tillgängliga kommandon

Du kan köra kommandon från kommandoraden. Detta ger dig möjlighet att bygga en statisk webbplats och göra andra saker. Öppna ett terminalfönster. Gå till installationsmappen där filen `yellow.php` finns. Skriv `php yellow.php` för att visa tillgängliga kommandona. De tillgängliga kommandona beror på installerade tillägg.

## Hur man bygger en statisk webbplats

Du kan bygga en statisk webbplats på kommandoraden. Den static-site-generator bygger hella webbsidan i förväg, istället för att vänta på att en fil ska begäras. Öppna ett terminalfönster. Gå till installationsmappen där filen `yellow.php` finns. Skriv `php yellow.php build`, du kan valfritt ange en mapp och en plats. Detta kommer att bygga en statisk webbplats i `public` mappen. Ladda upp den statiska webbplatsen till din webbserver och bygg en ny när det behövs. För att söka efter trasiga länkar skriv: `php yellow.php check`. För att rengöra statiska webbplatsen skriv: `php yellow.php clean`.

Om du inte vill att en sida ska byggas, ställ in `Build: exclude` i [sidinställningar](https://github.com/annaesvensson/yellow-core/tree/main/README-sv.md#inställningar-page) högst upp på en sida.

## Hur man bygger en statisk cache

Du kan skapa en statisk cache på kommandoraden. Den statiska cachen stöder en vanlig webbplats genom att bygga några filer i förväg och lagra dem i filsystemet. Du kan också tänka på det som att kombinera funktionerna hos en statisk webbplats och funktionerna hos en vanlig webbplats. Öppna ett terminalfönster. Gå till installationsmappen där filen `yellow.php` finns. Skriv `php yellow.php build system/cache`. Detta kommer att bygga en cache i `system/cache` mappen. Skapa en ny cache vid behov. För att rensa cachen skriv: `php yellow.php clean system/cache`.

Om du inte vill att en sida ska byggas, ställ in `Build: exclude` i [sidinställningar](https://github.com/annaesvensson/yellow-core/tree/main/README-sv.md#inställningar-page) högst upp på en sida.

## Exempel

Innehållsfil med alternativ för att bygga en statisk webbplats:

    ---
    Title: Exempelsida
    Build: exclude
    ---
    Den här sidan ingår inte i en statisk webbplats.

Översikt över tillgängliga kommandon:

`php yellow.php about` = Visa tillägg, [kräver update-tillägg](https://github.com/annaesvensson/yellow-update/tree/main/README-sv.md)  
`php yellow.php build` = Bygg statisk webbplats, kräver command-tillägg  
`php yellow.php check` = Kontrollera statisk webbplats, kräver command-tillägg  
`php yellow.php clean` = Rengör statisk webbplats, kräver command-tillägg  
`php yellow.php install` = Installera tillägg, [kräver update-tillägg](https://github.com/annaesvensson/yellow-update/tree/main/README-sv.md)  
`php yellow.php publish` = Publicera tillägg, [kräver publish-tillägg](https://github.com/annaesvensson/yellow-publish/tree/main/README-sv.md)  
`php yellow.php serve` = Starta inbyggda webbservern, [kräver serve-tillägg](https://github.com/annaesvensson/yellow-serve/tree/main/README-sv.md)  
`php yellow.php traffic` = Skapa trafikanalyser, [kräver traffic-tillägg](https://github.com/annaesvensson/yellow-traffic/tree/main/README-sv.md)  
`php yellow.php uninstall` = Avinstallera tillägg, [kräver update-tillägg](https://github.com/annaesvensson/yellow-update/tree/main/README-sv.md)  
`php yellow.php update` = Uppdatera webbplats, [kräver update-tillägg](https://github.com/annaesvensson/yellow-update/tree/main/README-sv.md)  
`php yellow.php user` = Skapa användarkonton, [kräver edit-tillägg](https://github.com/annaesvensson/yellow-edit/tree/main/README-sv.md)  

Visa tillgängliga kommandon på kommandoraden:

`php yellow.php`

Bygg statisk webbplats på kommandoraden: 

`php yellow.php build`  

Kontrollera statisk webbplats för trasiga länkar på kommandoraden:

`php yellow.php check`  

Rengör statisk webbplats och andra filer på kommandoraden:

`php yellow.php clean`  

## Inställningar

Följande inställningar kan konfigureras i filen `system/extensions/yellow-system.ini`:

`CommandStaticUrl` = webbplatsens URL när man använder kommandoraden  
`CommandStaticDirectory ` = map för statiskt genererade filer  
`CommandStaticDefaultFile` = standardfil för statisk webbplats  
`CommandStaticErrorFile` = felfil för statisk webbplats  

## Utvecklare

Anna Svensson. [Få hjälp](https://datenstrom.se/sv/yellow/help/).
