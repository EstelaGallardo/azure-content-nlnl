<properties 
    pageTitle="Application Insights Telemetry in Visual Studio CodeLens | Microsoft Azure" 
    description="Krijg snel toegang tot uw Application Insights-aanvraag en uitzonderingstelemetrie met CodeLens in Visual Studio." 
    services="application-insights" 
    documentationCenter=".net"
    authors="numberbycolors" 
    manager="douge"/>

<tags 
    ms.service="application-insights" 
    ms.workload="tbd" 
    ms.tgt_pltfrm="ibiza" 
    ms.devlang="na" 
    ms.topic="get-started-article" 
    ms.date="08/30/2016" 
    ms.author="daviste"/>
    

# Application Insights Telemetry in Visual Studio CodeLens

De methoden in de code van uw webtoepassing kunnen worden voorzien van aantekeningen met telemetrie over runtime-uitzonderingen en reactietijden voor aanvragen. Als u [Visual Studio Application Insights](app-insights-overview.md) installeert in uw toepassing, wordt de telemetrie weergegeven in Visual Studio [CodeLens](https://msdn.microsoft.com/library/dn269218.aspx): het opmerkingengedeelte boven aan elke functie, waar u normaal handige informatie ziet, zoals vanaf hoeveel plaatsen wordt verwezen naar de functie en wie de toepassing voor het laatst heeft bewerkt.

![CodeLens](./media/app-insights-visual-studio-codelens/codelens-overview.png)

> [AZURE.NOTE] Application Insights in CodeLens is beschikbaar in Visual Studio 2015 Update 3 en hoger of via de nieuwste versie van de [Developer Analytics Tools-extensie](https://visualstudiogallery.msdn.microsoft.com/82367b81-3f97-4de1-bbf1-eaf52ddc635a). CodeLens is beschikbaar via de edities Enterprise en Professional van Visual Studio.

## Waar vind ik Application Insights-gegevens?

Zoek naar Application Insights Telemetry in de CodeLens-indicatoren van de openbare aanvraagmethoden van uw webtoepassing. De CodeLens-indicatoren worden boven de methode en andere verklaringen weergegeven in C#- en Visual Basic-code. Als er Application Insights-gegevens beschikbaar zijn voor een methode, ziet u indicatoren voor aanvragen en uitzonderingen, zoals '100 aanvragen, 1% is mislukt' of '10 uitzonderingen'. Klik op een CodeLens-indicator voor meer informatie. 

> [AZURE.TIP] Wanneer de CodeLens-indicatoren worden weergegeven, kan het enkele seconden langer duren voordat de Application Insights-aanvraag- en uitzonderingsindicatoren worden weergegeven.

## Uitzonderingen in CodeLens

![NOG TE BEPALEN](./media/app-insights-visual-studio-codelens/codelens-exceptions.png)

De CodeLens-uitzonderingsindicator geeft aan hoeveel uitzonderingen er zijn opgetreden in de afgelopen 24 uur. U ziet de 15 uitzonderingen die het meest zijn optreden in uw toepassing gedurende die periode tijdens het verwerken van de aanvraag van de methode.

Voor meer informatie klikt u op de CodeLens-uitzonderingsindicator:

* Het wijzigingspercentage in het aantal uitzonderingen in de afgelopen 24 uur ten opzichte van de voorafgaande 24 uur
* Kies **Go to code** om te navigeren naar de broncode te van de functie die de uitzondering veroorzaakt
* Kies **Search** om een query uit te voeren voor alle keren dat de uitzondering in de afgelopen 24 uur is opgetreden
* Kies **Trend** om een trendvisualisatie weer te geven voor alle keren dat de uitzondering de afgelopen 24 uur is opgetreden
* Kies **View all exceptions in this app** om een query uit te voeren voor alle uitzonderingen die in de afgelopen 24 uur zijn opgetreden
* Kies **Explore exception trends** een trendvisualisatie weer te geven voor alle uitzonderingen die de afgelopen 24 zijn opgetreden. 

> [AZURE.TIP] Als u '0 exceptions' ziet in CodeLens, maar u weet dat er wel uitzonderingen zouden moeten zijn, controleert u of u wel de juiste Application Insights-resource hebt geselecteerd in CodeLens. Als u een andere resource wilt selecteren, klikt u met de rechtermuisknop op uw project in Solution Explorer en kiest u **Application Insights > Choose Telemetry Source**. CodeLens toont alleen de 15 uitzonderingen die de afgelopen 24 uur het vaakst zijn opgetreden in uw toepassing. Als een uitzondering op plaats 16 of lager staat, ziet u '0 exceptions'. Uitzonderingen als gevolg van ASP.NET-weergaven worden mogelijk niet weergegeven bij de controllermethoden op basis waarvan de weergaven zijn gegenereerd.

> [AZURE.TIP] Als u '? exceptions' ziet in CodeLens, moet u uw Azure-account koppelen aan Visual Studio. Het kan dan ook zijn dat uw Azure-accountreferenties zijn verlopen. In beide gevallen klikt u op '? exceptions' en kiest u **Add an account...** om uw referenties in te voeren.

## Aanvragen in CodeLens

![NOG TE BEPALEN](./media/app-insights-visual-studio-codelens/codelens-requests.png)

De CodeLens-aanvraagindicator toont het aantal HTTP-aanvragen dat de afgelopen 24 uur is verwerkt door een methode, plus het percentage van deze aanvragen dat is mislukt.

Voor meer informatie klikt u op de CodeLens-aanvraagindicator:

* De absolute en procentuele wijzigingen in het aantal aanvragen, mislukte aanvragen en gemiddelde reactietijden in de afgelopen 24 uur vergeleken met de voorafgaande 24 uur
* De betrouwbaarheid van de methode, berekend als het percentage aanvragen dat niet is mislukt in de afgelopen 24 uur
* Kies **Search** voor (mislukte) aanvragen om een query uit te voeren voor alle (mislukte) aanvragen die in de afgelopen 24 uur zijn gedaan
* Kies **Trend** om een trendvisualisatie weer te geven voor aanvragen, mislukte aanvragen en de gemiddelde reactietijden in de afgelopen 24 uur.
* Kies de naam van de Application Insights-resource in de linkerbovenhoek van de CodeLens-detailweergave om te wijzigen welke resource als bron wordt gebruikt voor de CodeLens-gegevens.

## <a name="next"></a>Volgende stappen

||
|---|---
|**[Met Application Insights werken in Visual Studio](app-insights-visual-studio.md)**<br/>Telemetrie zoeken, data in CodeLens bekijken en configureren van Application Insights. Allen vanuit Visual Studio. |![Klik met de rechtermuisknop op het project en kies Application Insights > Zoeken.](./media/app-insights-visual-studio-trends/34.png)
|**[Meer gegevens toevoegen](app-insights-asp-net-more.md)**<br/>Bewaak het gebruik, de beschikbaarheid, de afhankelijkheden en de uitzonderingen. Integreer bijgehouden informatie uit frameworks voor logboekregistratie. Schrijf aangepaste telemetrie. | ![Visual Studio](./media/app-insights-visual-studio-trends/64.png)
|**[Werken met de Application Insights-portal](app-insights-dashboards.md)**<br/>Dashboards, krachtige hulpprogramma's voor diagnose en analyse, waarschuwingen, een live afhankelijkheidskaart van uw toepassing en exportmogelijkheden voor telemetrie. |![Visual Studio](./media/app-insights-visual-studio-trends/62.png)



<!--HONumber=Sep16_HO3-->


