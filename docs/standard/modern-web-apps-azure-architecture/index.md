---
title: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure
description: Ein Leitfaden, der eine End-to-End-Anleitung zur Erstellung monolithischer Webanwendungen mit ASP.NET Core und Azure bietet.
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: 0d59a07e01897400a53f48799383d1670a468d73
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148105"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure

![Titelbild](./media/cover.png)

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2018 by Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter https://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Mac und macOS sind Marken von Apple Inc.

Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Autor:

> **Steve Smith (@ardalis)**, Software Architecture Advisor, [Ardalis.com](https://ardalis.com)

Editoren:

> **Maira Wenzel**

## <a name="introduction"></a>Einführung

.NET Core und ASP.NET Core bieten mehrere Vorteile gegenüber der traditionellen .NET-Entwicklung. Sie sollten .NET Core für Ihre Serveranwendungen verwenden, wenn einige oder alle der folgenden Punkte für den Erfolg Ihrer Anwendung wichtig sind:

- Plattformübergreifende Unterstützung

- Verwendung von Microservices

- Verwendung von Docker-Containern

- Anforderungen für hohe Leistung und Skalierbarkeit

- Parallele Versionsverwaltung von .NET-Versionen durch Anwendung auf demselben Server

Traditionelle .NET-Anwendungen können und werden diese Anforderungen unterstützen, aber ASP.NET Core und .NET Core wurden optimiert, um eine verbesserte Unterstützung für die oben genannten Szenarien zu bieten.

Immer mehr Unternehmen entscheiden sich dafür, ihre Webanwendungen in der Cloud zu hosten, indem sie Dienste wie Microsoft Azure nutzen. Sie sollten in Erwägung ziehen, Ihre Anwendung in der Cloud zu hosten, wenn die folgenden Punkte für Ihre Anwendung oder Organisation wichtig sind:

- Geringere Investitionen in die Kosten des Datencenters (Hardware, Software, Speicherplatz, Hilfsprogramme usw.)

- Flexible Preisgestaltung (nutzungsbasierte Abrechnung, nicht nach Leerlaufkapazität)

- Extreme Zuverlässigkeit

- Verbesserte App-Mobilität, einfaches Ändern, wo und wie Ihre App bereitgestellt wird

- Flexible Kapazität, Hoch- oder Herunterskalierung basieren auf dem tatsächlichen Bedarf

Das Erstellen von Webanwendungen mit ASP.NET Core (gehostet in Azure) bietet eine Menge Wettbewerbsvorteile gegenüber herkömmlichen Alternativen. ASP.NET Core ist für moderne Webanwendungs-Entwicklungspraktiken und Cloudhostingszenarien optimiert. In diesem Leitfaden erfahren Sie, wie Sie Ihre ASP.NET Core-Anwendungen so gestalten, dass Sie diese Funktionen optimal nutzen können.

## <a name="purpose"></a>Zweck

Dieser Leitfaden bietet eine End-to-End-Anleitung zur Erstellung monolithischer Webanwendungen mit ASP.NET Core und Azure.

Dieser Leitfaden ist eine Ergänzung zum E-Book [„_.NET Microservices. Architektur für .NET-Containeranwendungen_“](../microservices-architecture/index.md), das sich mehr auf Docker, Microservices und die Bereitstellung von Containern zum Hosten von Unternehmensanwendungen konzentriert.

### <a name="net-microservices-architecture-for-containerized-net-applications"></a>.NET-Microservices. .NET-Microservices-Architektur für .NET-Containeranwendungen

- **E-Book**  
  <https://aka.ms/MicroservicesEbook>
- **Beispielanwendung**  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die daran interessiert sind, moderne Webanwendungen mit Microsoft-Technologien und -Diensten in der Cloud zu erstellen.

Eine zweite Zielgruppe sind technische Entscheidungsträger, die bereits mit ASP.NET oder Azure vertraut sind und Informationen dazu suchen, ob ein Upgrade auf ASP.NET Core für neue oder vorhandene Projekte sinnvoll ist.

## <a name="how-you-can-use-this-guide"></a>Wie Sie diesen Leitfaden verwenden können

Dieser Leitfaden wurde in einem relativ kleinen Dokument zusammengefasst, das sich auf die Erstellung von Webanwendungen mit modernen .NET-Technologien und Windows Azure konzentriert. Als solches kann er in seiner Gesamtheit gelesen werden, um eine Grundlage für das Verständnis solcher Anwendungen und ihrer technischen Überlegungen zu schaffen. Der Leitfaden kann zusammen mit seiner Beispielanwendung auch als Ausgangspunkt oder Referenz dienen. Verwenden Sie die zugehörige Beispielanwendung als Vorlage für Ihre eigenen Anwendungen oder um zu sehen, wie Sie die einzelnen Komponenten Ihrer Anwendung organisieren können. Erinnern Sie sich an die Grundsätze des Leitfadens und die Beschreibung von Architektur- und Technologieoptionen und Entscheidungsüberlegungen, wenn Sie diese Entscheidungen für Ihre eigene Anwendung abwägen.

Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten. Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.

## <a name="references"></a>Verweise

- **Wahl zwischen .NET Core und .NET Framework für Server-Apps**  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[Nächste](modern-web-applications-characteristics.md)