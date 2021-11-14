---
Title: Om sidan
Description: Om teknikerna bakom sidan
---

Tekniker och språk som används på sidan
==========================

I detta portfolio används flera kodspråk. I grunden används HTML och CSS, men det har använts flertalet tekniker för att generera dessa åt oss.

Själva hemsidans innehåll genereras med hjälp av Pico, som är ett filbaserat innehållshanteringssystem. De olika sidornas innehåll genereras utifrån markdown-filer, där dokumentation går för Pico går att hitta under "Docs".
Jag använder mig också utav Twig, vilket är en mallmotor för PHP och är vad som styr strukturen av sidan.
För att generera CSS-koden för stilsättningen av sidan används SASS (Syntactically Awesome Style Sheets), vilket är en extension av CSS-språket. Den ger oss möjligheten att skriva stilsättningen på ett sätt som kan vara mer läsbart, användning av existerande funktioner utöver det vanliga (operatorer, variabler, arv, nästlade regler) med mera.

Fonter hämtar vi från Google Fonts. Ikoner från Font Awesome. Vi använder oss även av normalize.css, vilket är en färdigkonstruerad css-fil vars syfte är att standardisera css så det skiljer sig så lite som möjligt mellan olika webbläsare.  