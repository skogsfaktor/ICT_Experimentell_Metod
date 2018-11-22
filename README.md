# ICT_Experimentell_Metod
En central del i ingenjörsvetenskaperna är att vi observerar system och utifrån våra observationer skapar hypoteser eller modeller för egenskaper hos systemen. Experimentell metodik är inte begränsat till fysikaliska system utan kan lika gärna handla om programvarusystem, nätverk, tjänster eller hur användare uppfattar en tjänst. Därför är förmågan att kunna planera och genomföra experiment, samt analysera och presentera resultat från experiment centrala kunskaper för en ingenjör. Detta är också något som ofta efterfrågas av forsknings- och utvecklingsavdelningar på många företag. De upplever ofta att de har problem med:

Forskningsresultat som inte kan reproduceras
Bristande dokumentation
Resultat och påståenden som är dåligt underbyggda
Brister i planering, genomförande och datainsamling
Ostrukturerade arbetsmetoder
Brister i statistisk behandling av resultat och presentation av resultat
Just planeringen är en viktig del i uppgiften. I de flesta kurser du läst så har du oftast kunnat kasta dig rakt in i implementation av de uppgifter/labbar som ingått i kursen. I större problem som du möter i verkligheten eller i dina exjobb fungerar inte det angreppssättet. I exjobben kommer du att möta höga krav på ett metodiskt arbetssätt vilket innebär att du kommer att planera, utreda och dokumentera en hel del innan du ens kan börja tänka på implementationen.

I den här modulen kommer vi tillsammans att reflektera kring metoder för att systematiskt genomföra och analysera experiment kopplade en kvantitativa vetenskaplig metod. Du skall basera ditt arbete på vad du lärt dig i modulerna om att Arbeta i projekt för att göra projektplanering och modulen om Modellering för att designa experimenten, genomföra simuleringar och skriva rapporten. Du behöver använda dina kunskaper från kurserna i Algoritmer och datastrukturer för att implementera och analytiskt analysera algoritmerna. Kunskaper från kursen i Sannolikhetsteori och matematisk statistik behöver du för att kunna analysera och presentera data. 

Experimenten i modulen och rapporten baseras på att du skall göra en utvärderinga av olika prioritetsköer baserade på länkade listor. Kunskaperna från modulen behöver du kunna tillämpa i laborationsrapporten för labb3 i ID2206 Operativsystem.

Modulen examineras genom att du lämnar in dokumentation kring en experimentell utvärdering av ett antal olika implementationer av prioritetsköer.  Uppgifterna får lösas i grupper om maximalt två personer. Gruppen skriver gemensamma dokument som bägge lämnar in i Bilda. De dokument som skall lämnas in i Bilda är:

en sammanfattning av texten om experimentell metodik
experimentplanering
en teknisk rapport som beskriver resultatet av experimenten 
Tänk på följande när du skriver rapporten:

Fokus skall vara på att skriva en teknisk rapport  - inte en labbrapport. Skriv för en läsare som vill förstå hur bra de olika algoritmerna är
Rapporten skall handla om utvärderingen av ett antal algoritmer 
Syftet med uppgiften är att träna er på grunder i vetenskaplig (kvantitativ) metodik - att kunna planera, genomföra och presentera resultat från en experimentell studie - syftet i den här kursen är inte att lära er mer om listor/prioritetsköer (det lär man sig i Algoritm och datastruktur kursen)
Syftet som ni skall beskriva i rapporten är dock inte att ni skall träna rapportskrivning eller skriva en rapport för kursen - skilj på de olika meta-nivåerna
Var noga med att möta alla krav! som att t.ex. utvärdera bästa, värsta och normala prestanda för både exekveringshastighet och minnesförbrukning
Var noga med att argumentera för alla val ni gör av t.ex. experiment
Var noga med hur ni presenterar resultat, hur ni anger tillförlitlighet/felmarginaler i resultaten och hur ni presenterar resultaten så det blir lätt för läsaren att tolka resultaten
Om du skall kunna nå hela vägen fram krävs det att du lägger stor vikt vid planeringen av din experimentella studie. En detaljerad experiimentplan är därför också den första inlämningen i modulen.

Du skall utvärdera och jämföra två implementationer av prioritetsköer. En baserad på länkade listor och en trädbaserad. Prioritetsköer används bland annat för att implementera mängden framtida händelser (eng. pending event set) i händelsestyrda simuleringar och som ready-köer i schemaläggning av processer och trådar.

Utvärderingen skall kunna användas för att ligga till grund för val av prioritetsköimplementation i generella fall. Därför måste din utvärdering omfatta både analytiska och exekveringsmässiga bästa-, värsta- och normalfallsprestanda för de olika datastrukturerna för användningsfall både som shemaläggningskö för processer/trådar med heltalsprioriteter i ett begränsat intervall och för användning som händelselista för händelsestyrd simulering. 

Elementen i listorna skall hållas ordnade efter prioritet. Om flera element i listan har identiskt samma prioritet skall de ordnas i FIFO-ordning - dvs. när de tas ut ur listan skall de tas ut i FIFO-ordning.

För användning som händelselista i en simulering skall prioriteten implementeras som en tidsstämpel av datatypen double. Lågt numeriskt värde betyder hög prioritet (i.e. en händelse som ligger nära i tiden har högre prioritet än en som kommer att inträffa längre fram i tiden). Simuleringen kan modelleras som att man tar ut den händelse som har högst prioritet (lägst tidsstämpel T) ur kön. Detta skall generera 0-N nya händelser med nya tidsstämplar T+increment() där increment() är ett icke-negativt tal genererat från någon form av (stokastisk) distribution (som i sin enklaste form kan returnera ett konstant värde). De nya tidsstämplar som genereras kan naturligtvis vara olika för varje ny händelse som skapas. Skulle två händelser med identiska tidsstämplar genereras så skall de läggas in i kön i den ordning de genererades.

Du skall själv implementera algoritmerna i programmeringsspråket C.

Prioritetsköerna som skall utvärderas är:

En dubbellänkad lista där insättning av ett nytt element sker framifrån om prioriteten på det nya elementet är högre än medelvärdet av prioriteterna på det första och sista elementet i listan. Annars sker insättning från slutet av listan.
Splay tree en prioritetskö baserad på ett självjusterande sökträd föreslagen av Daniel Sleator och Robert Tarjan. 

"The term planning implies the working out of sub-components in some degree of elaborate detail. Broader-brush enunciations of objectives may qualify as metaphorical roadmaps [but does not qualify as a plan]."

En plan måste alltså vara så detaljerad och utförlig att det för den som skall genomföra planen inte får finnas några oklarheter om vad som skall göras eller hur det skall göras. 

Du kan inte förutsätta att det är du själv som skall genomföra planen - dvs. du kan inte anta att den som genomför planen har en massa detaljkunskaper som du sitter på. Allt måste finnas i planen.

Den plan du skapar skall alltså i slutänden vara av sådan kvalitet som beskrivs ovan. Dit kommer du att nå genom en eller ett par iterationer av planen.

Uppgiften utförs i grupper om en eller två personer.

Projektplaneringen skall utgå från Eklunds bok kap. 10 - 11 och första delen av kap. 12. Frågorna nedan skall utredas och beskrivas

Planen lämnas in i Bilda.

Läs laborationsuppgiften
Ställ samman alla krav du hittar  för att uppgiften skall bli godkänd i en kravanalys som lämnas in tillsammans med/som del av experimentplaneringen.
Skriv en plan för och dokumentera den experimentella studie du planerar genomföra. Planen skall vara så utformad att den kan utföras av någon annan person som inte nödvändigtvis har samma detaljkunskap som du. Dvs det du skall arbeta fram är en förhållandevis detaljerad plan till skillnad från en mer översiktlig sk. roadmap.
I din experimentplan skall du ha med/beskriva:

Identifiera resultat- och effektmål
Fråga dig vad syftet med en experimentell utvärdering av ett antal algoritmer kan vara och hur en sådan studie kan användas.
Enkel Förstudie, där du visar att du:
Förstått uppgiften
Förstått systemet som skall studeras 
Vilka parametrar beror systemet av, vilka kan varieras? Hur beror parametrarna av varandra?
Identifiera vilken/vilka typer av metoder studien kommer att baseras på (kvalitativa, kvanitativa, induktiva, deduktiva, mfl.)
Experimentplan
Beskriv vilka experiment som skall utföras och varför? (OBS! detta är en central del och du behöver inte ha detaljkunskap om implementationen av algoritmerna för att kunna planera detta!)
Beskriv vad som skall mätas och hur?
Experimentuppställning
Vad behövs för resurser? (beskriv dem i någorlunda detalj)
Vilka osäkerhets/felkällor finns? Hur stor inverkan kan de ha på resultaten och hur hanterar du det?
Vad behöver implementeras? En plan för implementationen.
Plan för hur du skall verifiera/validera/testa experimentuppställningen?
När har de mål som identifierats nåtts? När är experimenten färdiga?

Det kanske underlättar att förstå vad som krävs av er plan om ni gör tankeexperimentet att ni arbetar utanför KTH. Då är det realistiskt att tänka sig att ni som civilingenjörer inte nödvändigtvis skall göra allt praktiskt arbete själva. För en sådan här studie så skulle man mycket väl kunna tänka sig att ni planerar studien - men någon annan gör själva implementationsjobbet, utför experimenten och levererar resultaten till er. Det kräver betydligt mer av planeringen än det ni antagligen stött på hittills. Men uppgiften är så pass begränsad att ni realtivt enkelt kan (och skall) göra en så detaljerad och tydlig plan att vem som helst kan följa den till punkt och pricka. Det gör också att minst 30-40% av arbetet på projektet måste läggas i planeringen (men det är inte bortkastat då en stor (största) del av det här arbetet direkt kan lyftas in i och användas i slutrapporten). Kvar efter det att ni gjort planen bör vara att implementera köer och testfall/experiment, validera dessa, genomföra experimenten (och ev. om det behövs göra något nytt experiment om resultaten visar att det behövs), samla ihop och analysera resultaten och skriva klart rapporten.

Generellt behöver ni använda kunskaper från flera av de kurser ni skall ha läst för att få in följande i er planering:

Tydliga resultat & effektmål (II1304)
Litteratursökning (både splay tree och det kanske finns andra likande studier ni kan lära er en del av) (LI1012/LI1014)
En analytisk analys av köerna som tydligt beskriver/motiverar för läsaren hur köerna fungerar i olika situationer och vilka parametrar som påverkar prestanda (är det enbart fördelningen av prioriteter på de element som sätts in som styr prestanda eller kan det bero på t.ex. hur insättningar/uttag blandas, antalet element i kön m.m.) Analysen använder ni som en del för att motivera era val av experiment. (ID1020)
Identifiera de parametrar som kan påverka prestanda hos köerna (dvs. det ni skall variera i era experiment)
En utredning av vad ni behöver mäta och i så fall hur ni gör det (tids- och minnesåtgång). Ni behöver utvärdera, testa och välja mätmetoderna redan på det här stadiet för det kommer att påverka hur ni kan utforma era experiment. Till exempel kan noggrannheten i mätmetoden för tidåtgång ha stor påverkan på hur experimenten utformas. (en del eget undersökningsarbete för att hitta mätmetoder och utvärera dessa)
En detaljerad beskrivning av hur era experiment skall utformas (det skall gå att implementera experimenten exakt enligt era specar och också utföra dem) med motivering till varför experimenten är utformade som de är och vad de avser mäta. (ID1018-ID1020)
En testplan som med beskrivning av hur ni skall testa/validera era köimplementationer och era experiment. (om inte de är korrekt implementerade så blir resultaten värdelösa) (ID1018-ID1020, II1304)
Detaljerad beskrivning av vilken utdata och på vilket format utdata från experimenten skall genereras (för att ni skall kunna efterbehandla utdata som underlag för rapporten) (hur skall utdata kunna behandlas statistiskt, SF1901)
Beskrivning av övriga delar i experimentplattformen (t.ex. i detalj vilken hårdvara ni använder, OS, C-kompilator)