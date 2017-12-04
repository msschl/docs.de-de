---
title: Merkmale der modernen Webanwendungen
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Merkmale der modernen Webanwendungen
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 9ff9380b318457a842dec4e41b9b74dcddcda3d3
ms.sourcegitcommit: 882e02b086d7cb9c75f748494cf7a8d3377c5874
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="characteristics-of-modern-web-applications"></a><span data-ttu-id="87f71-103">Merkmale der modernen Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="87f71-103">Characteristics of Modern Web Applications</span></span>

> <span data-ttu-id="87f71-104">"…</span><span class="sxs-lookup"><span data-stu-id="87f71-104">"…</span></span> <span data-ttu-id="87f71-105">ordnungsgemäßen entwerfen die im Lieferumfang der Funktionen zu zweit.</span><span class="sxs-lookup"><span data-stu-id="87f71-105">with proper design, the features come cheaply.</span></span> <span data-ttu-id="87f71-106">Dieser Ansatz ist damit den mühseligen, jedoch weiterhin erfolgreich ausgeführt werden."</span><span class="sxs-lookup"><span data-stu-id="87f71-106">This approach is arduous, but continues to succeed."</span></span>  
> <span data-ttu-id="87f71-107">_\-Dennis Ritchie_</span><span class="sxs-lookup"><span data-stu-id="87f71-107">_\- Dennis Ritchie_</span></span>

## <a name="summary"></a><span data-ttu-id="87f71-108">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="87f71-108">Summary</span></span>

<span data-ttu-id="87f71-109">Innovative Webanwendungen verfügen über höhere Erwartungen der Benutzer und mehr Anforderungen als jemals zuvor.</span><span class="sxs-lookup"><span data-stu-id="87f71-109">Modern web applications have higher user expectations and greater demands than ever before.</span></span> <span data-ttu-id="87f71-110">Heute Web-apps werden verfügbare 24/7 von an einer beliebigen Stelle in der ganzen Welt und von praktisch jedem Gerät verwendet werden kann oder Displaygröße erwartet.</span><span class="sxs-lookup"><span data-stu-id="87f71-110">Today's web apps are expected to be available 24/7 from anywhere in the world, and usable from virtually any device or screen size.</span></span> <span data-ttu-id="87f71-111">Webanwendungen muss sichere, flexible und skalierbare, um Spitzen in der Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="87f71-111">Web applications must be secure, flexible, and scalable to meet spikes in demand.</span></span> <span data-ttu-id="87f71-112">Zunehmend sollten komplexe Szenarien durch umfangreiche Benutzeroberflächen, die auf dem Client mithilfe von JavaScript und effiziente Kommunikation über Web-APIs erstellt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="87f71-112">Increasingly, complex scenarios should be handled by rich user experiences built on the client using JavaScript, and communicating efficiently through web APIs.</span></span>

<span data-ttu-id="87f71-113">ASP.NET Core ist für die modernen Webanwendungen und Cloud-basierten Hostingszenarien optimiert.</span><span class="sxs-lookup"><span data-stu-id="87f71-113">ASP.NET Core is optimized for modern web applications and cloud-based hosting scenarios.</span></span> <span data-ttu-id="87f71-114">Der modularen Aufbau ermöglicht Anwendungen nur die Funktionen abhängig, die sie tatsächlich verwenden, Verbessern der Sicherheit der Anwendung und die Leistung beim hosting ressourcenanforderungen reduziert.</span><span class="sxs-lookup"><span data-stu-id="87f71-114">Its modular design enables applications to depend on only those features they actually use, improving application security and performance while reducing hosting resource requirements.</span></span>

## <a name="reference-application-eshoponweb"></a><span data-ttu-id="87f71-115">Verweisen auf die Anwendung: eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="87f71-115">Reference Application: eShopOnWeb</span></span>

<span data-ttu-id="87f71-116">Dieser Leitfaden enthält eine Referenz-Anwendung, *eShopOnWeb*, veranschaulicht, dass einige der Prinzipien und Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="87f71-116">This guidance includes a reference application, *eShopOnWeb*, that demonstrates some of the principles and recommendations.</span></span> <span data-ttu-id="87f71-117">Die Anwendung ist eine einfache Onlineshop unterstützt einen Katalog von Hemden Kaffeetassen und andere marketing Elemente durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="87f71-117">The application is a simple online store which supports browsing through a catalog of shirts, coffee mugs, and other marketing items.</span></span> <span data-ttu-id="87f71-118">Die Verweis-Anwendung ist absichtlich einfach gehalten, um ihn leichter nachvollziehen können.</span><span class="sxs-lookup"><span data-stu-id="87f71-118">The reference application is deliberately simple in order to make it easy to understand.</span></span>

<span data-ttu-id="87f71-119">**Abbildung 2-1.**</span><span class="sxs-lookup"><span data-stu-id="87f71-119">**Figure 2-1.**</span></span> <span data-ttu-id="87f71-120">eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="87f71-120">eShopOnWeb</span></span>

![](./media/image2-1.png)

> ### <a name="reference-application"></a><span data-ttu-id="87f71-121">Referenz-Anwendung</span><span class="sxs-lookup"><span data-stu-id="87f71-121">Reference Application</span></span>
> - <span data-ttu-id="87f71-122">**eShopOnWeb**</span><span class="sxs-lookup"><span data-stu-id="87f71-122">**eShopOnWeb**</span></span>  
> <span data-ttu-id="87f71-123"><https://github.com/dotnet/eShopOnWeb></span><span class="sxs-lookup"><span data-stu-id="87f71-123"><https://github.com/dotnet/eShopOnWeb></span></span>

## <a name="cloud-hosted-and-scalable"></a><span data-ttu-id="87f71-124">Cloudgehosteten und skalierbare</span><span class="sxs-lookup"><span data-stu-id="87f71-124">Cloud-Hosted and Scalable</span></span>

<span data-ttu-id="87f71-125">ASP.NET Core ist für die Cloud (öffentliche Cloud, private Cloud, keiner Cloud) optimiert, da es sich um Arbeitsspeicherstatus niedrig zu halten und hohem Durchsatz handelt.</span><span class="sxs-lookup"><span data-stu-id="87f71-125">ASP.NET Core is optimized for the cloud (public cloud, private cloud, any cloud) because it is low-memory and high-throughput.</span></span> <span data-ttu-id="87f71-126">Die kleinere Ressourcenbedarf des ASP.NET Core Anwendungen bedeutet, dass können mehrere dieser Header auf derselben Hardware gehostet und Sie weniger Ressourcen bezahlen, wenn unter Verwendung der Pay-als wechseln Sie zum Hosten von Diensten.</span><span class="sxs-lookup"><span data-stu-id="87f71-126">The smaller footprint of ASP.NET Core applications means you can host more of them on the same hardware, and you pay for fewer resources when using pay-as-you go cloud hosting services.</span></span> <span data-ttu-id="87f71-127">Die Durchsätze bedeutet, dass Sie mehr Kunden aus einer Anwendung erhält die gleiche Hardware weiter mindert die Notwendigkeit, die bei Servern und hosting-Infrastruktur zu investieren dienen können.</span><span class="sxs-lookup"><span data-stu-id="87f71-127">The higher-throughput means you can serve more customers from an application given the same hardware, further reducing the need to invest in servers and hosting infrastructure.</span></span>

## <a name="cross-platform"></a><span data-ttu-id="87f71-128">Plattformübergreifend</span><span class="sxs-lookup"><span data-stu-id="87f71-128">Cross Platform</span></span>

<span data-ttu-id="87f71-129">ASP.NET Core plattformübergreifende ist und auf Linux und MacOS sowie Windows ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="87f71-129">ASP.NET Core is cross-platform, and can run on Linux and MacOS as well as Windows.</span></span> <span data-ttu-id="87f71-130">Viele neue Optionen für Entwicklung und Bereitstellung von apps mit ASP.NET Core wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="87f71-130">This opens up many new options for both development and deployment of apps built with ASP.NET Core.</span></span> <span data-ttu-id="87f71-131">Docker-Container, der in der Regel Linux derzeit ausgeführt wird, können als host für ASP.NET Core-Anwendungen, sodass sie die Vorteile nutzen [Container und Microservices](../microservices-architecture).</span><span class="sxs-lookup"><span data-stu-id="87f71-131">Docker containers, which typically run Linux today, can host ASP.NET Core applications, allowing them to take advantage of the benefits of [containers and microservices](../microservices-architecture).</span></span>

## <a name="modular-and-loosely-coupled"></a><span data-ttu-id="87f71-132">Modulare und lose</span><span class="sxs-lookup"><span data-stu-id="87f71-132">Modular and Loosely Coupled</span></span>

<span data-ttu-id="87f71-133">NuGet-Pakete sind hohem Maße für Webdaten in .NET Core und ASP.NET Core apps bestehen viele Bibliotheken über NuGet.</span><span class="sxs-lookup"><span data-stu-id="87f71-133">NuGet packages are first-class citizens in .NET Core, and ASP.NET Core apps are composed of many libraries through NuGet.</span></span> <span data-ttu-id="87f71-134">Dieser Granularität Funktionen trägt dazu bei apps nur abhängig und Funktionalität, die sie tatsächlich ihre Platzbedarf und Sicherheit Sicherheitsrisiko Oberfläche verringert benötigen, bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="87f71-134">This granularity of functionality helps ensure apps only depend on and deploy functionality they actually require, reducing their footprint and security vulnerability surface area.</span></span>

<span data-ttu-id="87f71-135">ASP.NET Core unterstützt auch vollständig Abhängigkeitsinjektion, intern sowohl auf Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="87f71-135">ASP.NET Core also fully supports dependency injection, both internally and at the application level.</span></span> <span data-ttu-id="87f71-136">Schnittstellen können mehrere Implementierungen aufweisen, die ausgelagert werden können nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="87f71-136">Interfaces can have multiple implementations that can be swapped out as needed.</span></span> <span data-ttu-id="87f71-137">Abhängigkeitsinjektion kann apps für lose miteinander verknüpfen, die diese Schnittstellen, sodass sie einfacher zu erweitern, zu verwalten und zu testen.</span><span class="sxs-lookup"><span data-stu-id="87f71-137">Dependency injection allows apps to loosely couple to those interfaces, making them easier to extend, maintain, and test.</span></span>

## <a name="easily-tested-with-automated-tests"></a><span data-ttu-id="87f71-138">Problemlos mit automatisierten Tests getestet.</span><span class="sxs-lookup"><span data-stu-id="87f71-138">Easily Tested with Automated Tests</span></span>

<span data-ttu-id="87f71-139">ASP.NET Core-Anwendungen unterstützen Komponententests und ihre Anzahl lose verbundener Einzelsysteme und Unterstützung für Abhängigkeit einfügungen erleichtert Aspekte, die Infrastruktur gefälschte Implementierungen für Testzwecke austauschen.</span><span class="sxs-lookup"><span data-stu-id="87f71-139">ASP.NET Core applications support unit testing, and their loose coupling and support for dependency injections makes it easy to swap infrastructure concerns with fake implementations for test purposes.</span></span> <span data-ttu-id="87f71-140">ASP.NET Core umfasst auch einen TestServer, die als Host-apps im Arbeitsspeicher verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="87f71-140">ASP.NET Core also ships a TestServer that can be used to host apps in memory.</span></span> <span data-ttu-id="87f71-141">Funktionstests können anschließend Anfragen an in-Memory-Server, den vollständigen Anwendungszugriff Stapel (einschließlich Middleware, routing, modellbindung, Filter usw.)-Code und Empfangen einer Antwort in einem Bruchteil der Zeit würde es dauern zum Hosten der Anwendung auf einem echten server und stellen Sie Anforderungen über die Ebene des Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="87f71-141">Functional tests can then make requests to this in-memory server, exercising the full application stack (including middleware, routing, model binding, filters, etc.) and receiving a response, all in a fraction of the time it would take to host the app on a real server and make requests through the network layer.</span></span> <span data-ttu-id="87f71-142">Diese Tests sind besonders leicht zu schreiben und wertvolle für APIs, die zunehmend wichtig sind in modernen Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="87f71-142">These tests are especially easy to write, and valuable, for APIs, which are increasingly important in modern web applications.</span></span>

## <a name="traditional-and-spa-behaviors-supported"></a><span data-ttu-id="87f71-143">Herkömmliche und unterstützt SPA-Verhalten</span><span class="sxs-lookup"><span data-stu-id="87f71-143">Traditional and SPA Behaviors Supported</span></span>

<span data-ttu-id="87f71-144">Herkömmliche Webanwendungen haben wenig clientseitige Verhalten beteiligt, aber stattdessen verlassen haben, auf dem Server für alle Navigation, Abfragen und Updates, die von die app vorgenommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="87f71-144">Traditional web applications have involved little client-side behavior, but instead have relied on the server for all navigation, queries, and updates the app might need to make.</span></span> <span data-ttu-id="87f71-145">Jede neue Operation, die vom Benutzer vorgenommene würde in eine neue webanforderung mit dem Ergebnis wird eine vollständige Seite neu laden im Browser des Benutzers, der das Ende übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="87f71-145">Each new operation made by the user would be translated into a new web request, with the result being a full page reload in the end user's browser.</span></span> <span data-ttu-id="87f71-146">Klassische Model-View-Controller (MVC)-Frameworks folgen dieser Ansatz in der Regel mit der jede neue Anforderung für eine andere Controlleraktion, die wiederum würde und Arbeiten mit einem Modell eine Ansicht zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="87f71-146">Classic Model-View-Controller (MVC) frameworks typically follow this approach, with each new request corresponding to a different controller action, which in turn would work with a model and return a view.</span></span> <span data-ttu-id="87f71-147">Einige einzelne Vorgänge in einer gegebenen Seite möglicherweise mit AJAX (Asynchronous JavaScript and XML)-Funktionen erweitert werden, aber der Gesamtarchitektur der app verwendet werden, viele verschiedene MVC-Ansichten und URL-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="87f71-147">Some individual operations on a given page might be enhanced with AJAX (Asynchronous JavaScript and XML) functionality, but the overall architecture of the app used many different MVC views and URL endpoints.</span></span>

<span data-ttu-id="87f71-148">Single Page Applications (SPAs), umfassen, im Gegensatz dazu nur sehr wenige Laden von dynamisch generierten serverseitige-Seite (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="87f71-148">Single Page Applications (SPAs), by contrast, involve very few dynamically generated server-side page loads (if any).</span></span> <span data-ttu-id="87f71-149">Viele SPAs werden in statische HTML-Datei initialisiert, die die erforderlichen JavaScript-Bibliotheken zum Starten und Ausführen der app lädt.</span><span class="sxs-lookup"><span data-stu-id="87f71-149">Many SPAs are initialized within a static HTML file which loads the necessary JavaScript libraries to start and run the app.</span></span> <span data-ttu-id="87f71-150">Diese apps stellen beanspruchter Web-APIs für ihren Anforderungen hinsichtlich der Daten, und stellen viel umfangreichere Benutzer bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="87f71-150">These apps make heavy usage of web APIs for their data needs, and can provide much richer user experiences.</span></span>

<span data-ttu-id="87f71-151">Viele Webanwendungen erfordern eine Kombination des Verhalten der herkömmlichen Web-Anwendung (in der Regel für Inhalt) und SPAs (für Interaktivität).</span><span class="sxs-lookup"><span data-stu-id="87f71-151">Many web applications involve a combination of traditional web application behavior (typically for content) and SPAs (for interactivity).</span></span> <span data-ttu-id="87f71-152">ASP.NET Core unterstützt MVC und Web-APIs in der gleichen Anwendung verwenden den gleichen Satz von Tools und zugrunde liegende Framework-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="87f71-152">ASP.NET Core supports both MVC and web APIs in the same application, using the same set of tools and underlying framework libraries.</span></span>

## <a name="simple-development-and-deployment"></a><span data-ttu-id="87f71-153">Einfache Entwicklung und Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="87f71-153">Simple Development and Deployment</span></span>

<span data-ttu-id="87f71-154">ASP.NET Core-Anwendungen können mithilfe von einfachen Text-Editoren und Befehlszeilenschnittstellen oder voll ausgestatteten entwicklungsumgebungen wie Visual Studio geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="87f71-154">ASP.NET Core applications can be written using simple text editors and command line interfaces, or full-featured development environments like Visual Studio.</span></span> <span data-ttu-id="87f71-155">Aufgrund eines monolithischen Anwendungen werden in der Regel einen einzelnen Endpunkt bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="87f71-155">Monolithic applications are typically deployed to a single endpoint.</span></span> <span data-ttu-id="87f71-156">Bereitstellungen können leicht automatisiert werden, um Sie als Teil einer continuous Integration (CI) und die Pipeline für fortlaufende Übermittlung (CD) auftreten.</span><span class="sxs-lookup"><span data-stu-id="87f71-156">Deployments can easily be automated to occur as part of a continuous integration (CI) and continuous delivery (CD) pipeline.</span></span> <span data-ttu-id="87f71-157">Zusätzlich zu den herkömmlichen CI-CD-Tools Windows Azure verfügt über eine integrierte Unterstützung für Git-Repositorys und Updates können automatisch bereitgestellt werden, wenn sie an einem angegebenen Git Verzweigung oder Tag beziehen.</span><span class="sxs-lookup"><span data-stu-id="87f71-157">In addition to traditional CI/CD tools, Windows Azure has integrated support for git repositories and can automatically deploy updates as they are made to a specified git branch or tag.</span></span>

## <a name="traditional-aspnet-and-web-forms"></a><span data-ttu-id="87f71-158">Herkömmliche ASP.NET und WebForms</span><span class="sxs-lookup"><span data-stu-id="87f71-158">Traditional ASP.NET and Web Forms</span></span>

<span data-ttu-id="87f71-159">Zusätzlich zu ASP.NET Core, herkömmlichen ASP.NET 4.x weiterhin eine robuste und zuverlässige Plattform zum Erstellen von Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="87f71-159">In addition to ASP.NET Core, traditional ASP.NET 4.x continues to be a robust and reliable platform for building web applications.</span></span> <span data-ttu-id="87f71-160">ASP.NET unterstützt MVC und Web-API Entwicklungsmodellen sowie Web Forms, die sich gut für umfassende seitenbasierte Anwendungsentwicklung und verfügt über eine umfangreiche Drittanbieter-Komponente-Ökosystem.</span><span class="sxs-lookup"><span data-stu-id="87f71-160">ASP.NET supports MVC and Web API development models, as well as Web Forms, which is well-suited to rich page-based application development and features a rich third-party component ecosystem.</span></span> <span data-ttu-id="87f71-161">Windows Azure bietet hervorragende befolgter Unterstützung für ASP.NET 4.x-Anwendungen, und viele Entwickler mit dieser Plattform vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="87f71-161">Windows Azure has great longstanding support for ASP.NET 4.x applications, and many developers are familiar with this platform.</span></span>

> ### <a name="references--modern-web-applications"></a><span data-ttu-id="87f71-162">Verweise – moderner Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="87f71-162">References – Modern Web Applications</span></span>
> - <span data-ttu-id="87f71-163">**Einführung in ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="87f71-163">**Introduction to ASP.NET Core**</span></span>  
> <span data-ttu-id="87f71-164"><https://docs.Microsoft.com/ASPNET/Core/></span><span class="sxs-lookup"><span data-stu-id="87f71-164"><https://docs.microsoft.com/aspnet/core/></span></span>
> - <span data-ttu-id="87f71-165">**Sechs Schlüssel Vorteile von ASP.NET Core, die anders und besser zu vereinfachen**</span><span class="sxs-lookup"><span data-stu-id="87f71-165">**Six Key Benefits of ASP.NET Core which make it Different and Better**</span></span>  
> <span data-ttu-id="87f71-166"><https://Blog.trigent.com/Six-Key-Benefits-of-ASP-NET-Core-1-0-Which-Make-IT-different-Better/></span><span class="sxs-lookup"><span data-stu-id="87f71-166"><https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/></span></span>
> - <span data-ttu-id="87f71-167">**Testen in ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="87f71-167">**Testing in ASP.NET Core**</span></span>  
> <span data-ttu-id="87f71-168"><https://docs.Microsoft.com/ASPNET/Core/Testing/></span><span class="sxs-lookup"><span data-stu-id="87f71-168"><https://docs.microsoft.com/aspnet/core/testing/></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="87f71-169">[Vorherigen] (index.md) [weiter] (Choose-between-traditional-web-and-single-page-apps.md)</span><span class="sxs-lookup"><span data-stu-id="87f71-169">[Previous] (index.md) [Next] (choose-between-traditional-web-and-single-page-apps.md)</span></span>