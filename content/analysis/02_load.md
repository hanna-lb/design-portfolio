---
Title: Laddningstid och användbarhet
Description: Utvärdering av webbplatsers laddningstid och användbarhet 
Template: analysis_single
---

Laddningstid och användbarhet
=======================

I denna rapport presenteras och analyseras webbplatsers laddningstider och användbarhet på datorer och mobiltelefoner hos tre olika webbplatser. I detta fall analyseras tre olika svenska e-handelssidor som säljer produkter inom samma område.

Urval
-----------------------

Urvalet för denna analys är densamme som tidigare färganalys, då det är intressant att se hur tre olika nätbutiker inom gaming står sig i och med att de tre olika hemsidorna erbjuder liknande funktionalitet och har snarlikt syfte. Hemsidorna som därmed analyseras i denna rapport är MaxGaming.se, Webhallen.com och Inet.se.

Metod
-----------------------

I denna rapport mäter vi olika värden för tre undersidor vardera för respektive hemsida. Dessa tre undersidor för samtliga är själva startsidan, en kategori för produkter (i detta fall datortillbehör) samt en sida motsvarande "Om oss".

För att samla mätvärden för de olika hemsidorna används två olika verktyg, nämligen Google PageSpeed Insights och Firefox utvecklingsverktyg där vi kollar i nätverksfliken.

__Google PageSpeed Insights__ är ett verktyg som mäter olika värden dels utifrån mobilbesökares perspektiv och dels utifrån datorer. Den visar mätresultat dels från riktiga användare som använder webbläsaren Chrome samt resultat utifrån en simulerad miljö där diagnostikverktyget kallas för Lighthouse. Den presenterar även olika förbättringsmöjligheter eller åtgärder som webbutvecklaren kan ta för att minska laddtiderna för hemsidan.

__Firefox Devtools__ är inbyggt i webbläsaren Firefox, och det ger oss ett gränssnitt där vi kan se mer vad som händer bakom kulisserna på en webbsida, inklusive vad som skickas över nätverket om vi kollar nätverksfliken. Genom det kan man hämta mycket information, och i mitt fall har jag använt det för att se hur många resurser som det skickas förfrågan för, storleken på laddat hemsideinnehåll samt totala laddtiden för sidan.

Dessa mätvärden sammanställs sedan i ett kalkylark skrivet med __Google Spreadsheet__ som jag sedan embeddar i denna rapport i resultat-delen. Mätvärderna från Goodle PageSpeed Insights är färgkodade i kalkylbladet efter hur de var presenterade på hemsidan. Generellt betyder grönt att det är bra, orange att det hade mått bra av att förbättras och rött är dåligt.

Resultat
-----------------------

Kalkylark med mätvärden för MaxGaming, Webhallen och Inet:
<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSyeiA0YOhyW2MIC2p_hR0xRzUqkg5AI20dapUAiTDbCFcMknj26EfTeSOQJcUSFmJVRHqXVhse1lgT/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false" style="width: 100%; height: 600px; padding-bottom: 1em;"></iframe>

### MaxGaming

![Skärmdump från MaxGaming](%base_url%/image/2_maxgaming.png&w=600)

_Skärmdump från MaxGaming.se tagen 2021-12-05_

På startsidan för MaxGaming möts man högst upp med en menyrad med olika produktkategorier. Nedanför är stora bilder på olika kampanjer och längre ned listas fler produkter med tillhörande bilder.

Enligt data hämtat från faktiska användare på PageSpeed ser vi att MaxGaming har godkänt i test av viktiga webbvärden på datorn och mobilen. 

Kollar vi på datan som hämtats genom den simulerade miljön är det mer problematik. Gemensamt för alla undersidor för MaxGaming är att Largest Contentful Paint (LCP) hade mått bra av att förbättras. LCP är renderingstiden för största bilden eller textblocket som är synligt inom viewporten. Den simulerade mobila enheten lider av problem med hur lång tid det tar innan något händer efter man interagerat med hemsidans innehåll. 

### Webhallen

![Skärmdump från Webhallen](%base_url%/image/2_webhallen.png&w=600)

_Skärmdump från Webhallen.com tagen 2021-12-05_

Går man i på Webhallens startsida ser man en menyrad som är animerad med fallande snöflingor. Det är på denna menyrad man finner alla produktkategorier. Sedan finns bilder i bakgrunden samt i huvudinnehållet för kampanjer. Längre ned är olika produkter listade tillhörande bilder. När jag scrollar ned på sidan laddas bilderna i samband med att de visas på skärmen.

Utifrån användardata ser vi att Webhallen inte har godkänt i de viktiga webbvärden, och detta beror på att de har höga värden inom Cumulative Layout Shift (CLS), vilket hänvisar till hur saker kan hoppa omkring medan sidan laddas. Detta är ett problem både på datorn och mobilen. På mobilen finns även användardata som tyder på att Largest Contentful Paint (LCP) hade behövt förbättras. LCP är renderingstiden för största bilden eller textblocket som är synligt inom viewporten.

### Inet

![Skärmdump från Inet](%base_url%/image/2_inet.png&w=600)

_Skärmdump från Inet.se tagen 2021-12-05_

På startsidan för Inet möts man av en större bild där man kan stega mellan olika bilder som presenterar olika kampanjer. Nedanför börjar produkter med tillhörande bilder listas och det finns även en menylista till vänster.

Enligt data hämtat från faktiska användare på PageSpeed ser vi att Inet har godkänt i test av viktiga webbvärden på datorn, och nästan godkänt i allt för mobil förutom att Largest Contentful Paint (LCP) hade mått bra av att förbättras. LCP är renderingstiden för största bilden eller textblocket som är synligt inom viewporten.

Kikar man i de mätvärden jag antecknade från devtools ser man att inet har lång laddningstid, men jag upplever inte samma laddningstid i verkligheten när jag besöker sidan. Något jag la märke till är att den laddade klart under två sekunder, men sedan efter mer än 10 sekunder laddas en till javascript-resurs in vilket tycks vara för en livechat eller liknande. Bild nedan visar på tidslinje över laddade resurser där vi ser att det inte är något som händer på väldigt länge mellan sista och näst sista laddningen.

![Laddtid för inet](%base_url%/image/2b_inet.png&w=815)

Analys
-----------------------

Alla hemsidor presterade sämre i den simulerade miljön gentemot mätvärderna hämtad från riktig användardata. Det får mig att reflektera över huruvida det finns begränsningar med verktyget som ger det en mindre rättvis bild av dess riktiga prestanda. Information jag kan hitta kring Lighthouse är att den simulerar laddningen från någonstans i Europa med en internethastighet på 10240Kbit/s på dator och motsvarande halvdålig 4G-täckning med den mobila simuleringen, där internethastigheten är satt till 1638,4 Kbit/s. 

På sida 16 i rapporten [10 år med Bredbandskollen – surfhastighet 2008-2017](https://internetstiftelsen.se/docs/Bredbandskollen_Surfhastigheter_2008_2017.pdf#page=16&zoom=auto,-82,637) från Internetstiftelsen ser vi att redan 2017 i Sverige var genomsnittliga hastigheten för 3G/4G på 18 Mbit/s och fast internet desto snabbare, där totala genomsnittshastigheten är på 67 Mbit/s. Då samtliga hemsidor riktar sig mot specifikt kunder i Sverige misstänker jag att skillnaden mellan användardata och testdata beror på att vi i verkligheten har snabbare internetuppkoppling i Sverige än vad testmiljön utgår från.

### Bäst i test

Utifrån testresultaten kan skulle jag rangordna de olika hemsidorna som följande:

1. MaxGaming
2. Inet
3. Webhallen  

MaxGaming tar hem priset då de presterade bra på både dator och mobilnibå utifrån användardata, samt simulerad data för dator. De har även lägst genomsnittsladdtid utifrån data hämtad via devtools. 

Slår man ut genomsnittet över de olika sidorna för prestandapoängen på simulerad mobil skulle jag ändå säga att Inet vinner. Inet ligger inte heller långt efter på övriga håll. Dessutom känns devtools mättiderna missvisande likt presenterat innan, då det tycks vara en fördröjning på en förfrågan då laddtiden annars är under 2 sekunder.

Webhallen hamnar sist då de dels har högre laddtider hämtade via devtools, samt har fått sämre betyg utifrån användar- och simulerad data. Bortser man från deras "Om webhallen"-sida har de dock mindre förbättringsförslag (mätt i tid) via Lighthouse på mobila enheter än exempelvis Inet, vilket visar på att de ändå har mindre rakt uppenbara saker att förbättra för laddtidernas skull.

### Vad är snabb laddningstid?

För mig personligen skulle jag säga att gränsen för snabb laddningstid är kring 2 - 2,5 sekunder, och i verkligheten klarar samtliga testade hemsidor i denna rapport det, då jag skulle vilja påstå att man kan bortse från mätta tiden från Inet då hemsidan känns färdigladdad innan 2 sekunder har gått. Webhallen är mer gränsfall då den dels laddar saktare, dels är bilder inte helt laddade och kommer fram medan man scrollar vilket ger mig intrycket av att det är saktare.

### Förbättringsområden

Rent generellt finns det något som MaxGaming, Webhallen och Inet har gemensamt gällande hur de kan förbättras. Enligt PageSpeed kan de alla minska Javascript som de inte använder sig utav och därmed minska laddtiderna på dator mellan 0,24 - 2,93 sekunder. Framförallt blir det märkbart när man kollar på laddningstiden för mobila enheter. Där kan man spara allt mellan 1,5 - 19,5 sekunder i laddningstid på de olika sidorna. Förbättringsområderna är i övrigt inte särskilt påtagliga på dator, men desto mer märkbara på mobila enheter.

Vad som tycks vara vanliga tidsbovar på mobila enheter är resurser som blockerar renderingen, att bilderna kan skickas i modernare bildformat samt specificeras i storlek. Något som Webhallen bör åtgärda specifikt för användbarhetens skull är Cumulative Layout Shift (CLS) vilket hänvisar till hur saker kan hoppa omkring medan sidan laddas. Det gör innehållet mindre användbart om det man kollar på helt plötsligt hoppar till en annan del av sidan så man tappar bort sig. De är ensamma om att ha fått icke godkända resultat både på dator och mobil.

Referenser
-----------------------

[Google PageSpeed Insights](https://pagespeed.web.dev/)  
[Internetstiftelsen: 10 år med Bredbandskollen – surfhastighet 2008-2017](https://internetstiftelsen.se/docs/Bredbandskollen_Surfhastigheter_2008_2017.pdf)  
[MaxGaming](https://www.maxgaming.se/)  
[Webhallen](https://www.webhallen.com/se/)  
[Inet](https://www.inet.se/)  

Övrigt
-----------------------

Författare: Hanna Björk