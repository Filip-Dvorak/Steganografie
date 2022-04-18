# Steganografie
Steganografie je vědní disciplína zabývající se utajením komunikace prostřednictvím ukrytí zprávy.
Často se kombinuje se šifrováním.
**Podstatou steganografické zprávy je, že o ní ani nevíme.**

## Historie
- První použití v roce 440 př. n. l. 
- Používáno špiony za 2. světové války
![Neviditelný inkoust](https://i.ytimg.com/vi/-0VCZK9_yao/maxresdefault.jpg)

# Digitální steganografie
## Obrázky
- Ukrytí zprávy pomocí úpravy jednoho pixelu.

![enter image description here](https://cdn.discordapp.com/attachments/821112771763765248/965550512558710844/unknown.png)


![enter image description here](https://media.discordapp.net/attachments/821112771763765248/965550631270088704/unknown.png)

- Ukrytí pomocí nejméně signifikantního bitu
Pokud ukryjeme data do třeba posledních dvou bitů každé barevné složky obrázku, bude výsledný obrázek prakticky totožný s originálem a tajnou zprávu tak nepůjde zpozorovat.
![enter image description here](https://cdn.discordapp.com/attachments/821112771763765248/965552000509026324/unknown.png)

## Zvuk
Zvuk můžeme zobrazit ve spektrogramu a právě do něj můžeme vložit svoji zprávu.

![enter image description here](https://cdn.discordapp.com/attachments/821112771763765248/965552617579241472/unknown.png)
![enter image description here](https://cdn.discordapp.com/attachments/821112771763765248/965552687649259601/unknown.png)
# Setganografické nástroje
### Binwalk
Hledání vložených souborů v binárních souborech

    useros@ubuntu:~/Stego$ binwalk {obrazek-s-tajnymi-soubory.jpg}
    
 Pro extrahování souboru je syntaxe:
 

    useros@ubuntu:~/Stego$ binwalk --extract --dd=".*" {obrazek-s-tajnymi-soubory.jpg}

**Vyzkoušej si to na přiloženém souboru:** [obrazek-pro-binwalk](https://github.com/Filip-Dvorak/Steganografie/blob/main/obrazek-pro-binwalk.jpeg)
   
  ### Exiftool
  Čtení a úprava metadat. Metadata jsou data o datech.
  

     useros@ubuntu:~/Stego$ eexiftool {obrazek-u-ktereho-chceme-zobrazit-metadata.png}

**Vyzkoušej si to na přiloženém souboru:** [obrazek-pro-exiftool](obrazek-pro-exiftool.png)
### Steghide
Nástroj pro schování zprávy do nejméně signifikantních bitů

     useros@ubuntu:~/Stego$ steghide embed -cf {obrazek-pro-ukryti.jpg} -ef {tajna-zprava.txt}
Pro schování je nutné zadat heslo.

     useros@ubuntu:~/Stego$ steghide extract -sf {obrazek-pro-ukryti.jpg}
Pro extrahování tajné zprávy z obrázku je nutné zadat správné heslo.

**Vyzkoušej si to na přiloženém souboru:**[obrazek-pro-steghide](obrazek-pro-steghide.jpg)
*(hint: heslo zjistíš použitím předchozích metod)*
