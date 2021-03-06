---
title: Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit
description: Entdecken Sie die Optionen zum Orchestrieren von Microservices und Anwendungen mit mehreren Containern, um hohe Skalierbarkeit und Verfügbarkeit zu erzielen, sowie die Möglichkeiten von Azure Dev Spaces für die Entwicklung des Lebenszyklus von Kubernetes-Anwendungen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/20/2018
ms.openlocfilehash: c3a40d5a9229ec754f5a5c2e2637af964f25ba08
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152719"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit

Falls Ihre Anwendung auf Microservices beruht oder über mehrere Container verteilt ist, ist die Nutzung von Orchestratoren für Anwendungen auf Produktionsniveau von entscheidender Bedeutung. Wie bereits in einem vorherigen Artikel erwähnt, ist jeder Microservice Besitzer seines Modells und seiner Daten, damit er von der Entwicklung und Bereitstellung unabhängig ist. Auch wenn Sie eine herkömmliche Anwendung aus mehreren Diensten besitzen (z.B. eine SOA-Anwendung), besteht eine einzelne Geschäftsanwendung aus mehreren Containern oder Diensten, die als verteiltes System bereitgestellt werden müssen. Derartige Systeme lassen sich nur schwer horizontal hochskalieren und verwalten. Wenn Sie also eine skalierbare Anwendung mit mehreren Containern auf Produktionsniveau bereitstellen möchten, ist die Nutzung eines Orchestrators unumgänglich.

Abbildung 4-23 veranschaulicht die Bereitstellung einer aus mehreren Microservices (Containern) bestehenden Anwendung in einem Cluster.

![Zusammengesetzte Docker-Anwendungen in einem Cluster: Sie verwenden einen Container für jede Dienstinstanz. Docker-Container sind Bereitstellungseinheiten, und ein Container ist eine Instanz eines Dockers. Ein Host verarbeitet viele Container.](./media/image23.png)

**Abbildung 4-23.** Ein Cluster mit Containern

Dieser Ansatz mag logisch erscheinen. Nicht offensichtlich ist aber, wie der Lastenausgleich, das Routing und die Orchestrierung dieser zusammengesetzten Anwendungen erfolgen soll.

Mit der einfachen Docker-Engine können Instanzen mit nur einem Image auf einem einzelnen Docker-Host leicht verwaltet werden. Die einfache Docker-Engine ist allerdings unzureichend, wenn mehrere Container, die auf mehreren Hosts bereitgestellt werden, für komplexere verteilte Anwendungen verwaltet werden sollen. In den meisten Fällen wird eine Verwaltungsplattform benötigt, die Container automatisch startet, Container mit mehreren Instanzen pro Image horizontal hochskaliert, diese bei Bedarf anhält oder beendet und idealerweise auch steuert, wie Container auf Ressourcen wie Netzwerke oder Datenspeicher zugreifen.

Um anstelle von einzelnen Containern oder einfach zusammengesetzten Anwendungen größere Unternehmensanwendungen mit Microservices verwalten zu können, ist eine Orchestrierung und ein Clustering von Plattformen notwendig.

Wenn Sie große, auf Microservices basierende Unternehmensanwendungen erstellen möchten, sollten Sie sich hinsichtlich der Architektur und Entwicklung mit den folgenden Plattformen und Produkten vertraut machen, die für komplexere Szenarios geeignet sind:

**Cluster und Orchestratoren**. Wenn es erforderlich ist, Anwendungen für mehrere Docker-Hosts oder große, auf Microservices basierende Anwendungen horizontal hochzuskalieren, müssen sich sämtliche Hosts als einzelner Cluster verwalten lassen, was durch die Abstraktion der Komplexität der zugrunde liegenden Plattform erreicht wird. Dafür sorgen die Containercluster und Orchestratoren. Azure Service Fabric und Kubernetes sind Beispiele für Orchestratoren. Kubernetes ist in Azure über den Azure Kubernetes Service verfügbar.

**Planer**. Durch *Planung* können Administratoren Container so in einem Cluster starten, dass sie auch eine Benutzeroberfläche bereitstellen. Ein Clusterplaner ist für mehrere Aufgaben zuständig: Neben der effizienten Verwaltung von Ressourcen müssen auch die vom Benutzer vorgegebenen Einschränkungen festgelegt und der Lastenausgleich wirksam für Container für unterschiedliche Knoten oder Hosts vorgenommen werden. Zusätzlich muss der Cluster auch bei Fehlern stabil sein und gleichzeitig Hochverfügbarkeit gewährleisten.

Das Clusterkonzept ist eng mit dem Konzept eines Planers verbunden. Produkte von unterschiedlichen Anbietern stellen daher oft beide Funktionen zur Verfügung. Die folgende Liste enthält die wichtigsten Plattformen und Softwareprodukte für Cluster und Planer. Diese Orchestratoren werden häufig in öffentlichen Clouds wie Azure zur Verfügung gestellt.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Softwareplattformen für Containerclustering, Orchestrierung und Planung

### <a name="kubernetes"></a>Kubernetes

![Kubernetes-Logo](./media/image24.png)

> [*Kubernetes*](https://kubernetes.io/) ist ein Open Source-Produkt, das unterschiedliche Funktionen bereitstellt, von der Bereitstellung einer Clusterinfrastruktur über die Containerplanung bis hin zur Orchestrierung. Mit dieser Plattform können Sie die Bereitstellung, die Skalierung und die Vorgänge von Anwendungscontainern für Hostcluster automatisieren.
>
> *Kubernetes* stellt eine auf Container ausgerichtete Infrastruktur bereit, die Anwendungscontainer so in logischen Einheiten gruppiert, dass diese leicht verwaltet und ermittelt werden können.
>
> *Kubernetes* ist unter Linux ausgereifter als unter Windows.

### <a name="azure-kubernetes-service-aks"></a>Azure Kubernetes Service (AKS)

![Azure Kubernetes Service-Logo](./media/image41.png)

> [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/) ist ein verwalteter Dienst für die Kubernetes-Containerorchestrierung in Azure, der Verwaltung, Bereitstellung und Vorgänge für Kubernetes-Cluster vereinfacht.

### <a name="azure-service-fabric"></a>Azure Service Fabric

![Azure Service Fabric-Logo](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) ist eine Microsoft-Microservicesplattform zum Erstellen von Anwendungen. Es handelt sich um einen [Dienstorchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction), der Computercluster erstellt. Service Fabric kann Dienste als Container oder einfache Prozesse bereitstellen. Innerhalb derselben Anwendung und desselben Clusters können darüber hinaus Dienste in Prozessen mit Diensten in Containern kombiniert werden.
>
> *Service Fabric*-Cluster können in Azure, lokal oder in einer beliebigen Cloud bereitgestellt werden. Die Bereitstellung in Azure wird durch einen verwalteten Ansatz vereinfacht.
>
> Zusätzlich stellt *Service Fabric* optional normative [Service Fabric-Programmiermodelle](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) wie [zustandsbehaftete Dienste](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) und [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction) zur Verfügung.
>
> *Service Fabric* ist nach vielen Jahren der Entwicklung unter Windows ausgereifter als unter Linux.
>
> Seit 2017 werden in Service Fabric sowohl Linux- als auch Windows-Container unterstützt.

### <a name="azure-service-fabric-mesh"></a>Azure Service Fabric Mesh

![Azure Service Fabric Mesh-Logo](./media/image35.png)

> [*Azure Service Fabric Mesh*](https://docs.microsoft.com/azure/service-fabric-mesh/service-fabric-mesh-overview) bietet die gleiche Zuverlässigkeit, unternehmenskritische Leistung und Skalierbarkeit wie Service Fabric, ist jedoch eine vollständig verwaltete, serverlose Plattform. Sie müssen weder Cluster noch virtuelle Computer, Speicher oder Netzwerkkonfiguration verwalten. Stattdessen konzentrieren Sie sich einfach auf die Entwicklung Ihrer Anwendung.
>
> *Service Fabric Mesh* unterstützt sowie Windows- als auch Linux-Container, sodass Sie Ihre Anwendungen mit jeder Programmiersprache und jedem Framework Ihrer Wahl entwickeln können.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Verwenden von containerbasierten Orchestratoren in Microsoft Azure

Mehrere Cloudanbieter wie Microsoft Azure, Amazon EC2 Container Service und Google Container Engine unterstützen Docker-Container, Docker-Cluster und Orchestrierung. Microsoft Azure stellt Unterstützung für Docker-Cluster und -Orchestratoren über Azure Kubernetes Service (AKS) und Azure Service Fabric sowie Azure Service Fabric Mesh bereit.

## <a name="using-azure-kubernetes-service"></a>Verwenden von Azure Kubernetes Service

Ein Kubernetes-Cluster fasst mehrere Docker-Hosts in einem Pool zusammen und macht sie als einen einzelnen virtuellen Docker-Host verfügbar, sodass Sie mehrere Container im Cluster bereitstellen und auf eine beliebige Anzahl von Containerinstanzen horizontal skalieren können. Der Cluster übernimmt komplexe Verwaltungsaufgaben und gewährleistet dabei z.B. Skalierbarkeit und Integrität.

AKS vereinfacht die Erstellung, Konfiguration und Verwaltung eines Clusters mit virtuellen Computern in Azure, die zur Ausführung von Containeranwendungen vorkonfiguriert werden. Mit einer optimierten Konfiguration für Open Source-Planungs- und -Orchestrierungstools unterstützt AKS Sie dabei, Ihr eigenes Know-how anzuwenden oder auf das Fachwissen einer wachsenden Community zuzugreifen, damit Sie containerbasierte Anwendungen in Microsoft Azure bereitstellen und verwalten können.

Azure Kubernetes Service optimiert die Azure-spezifische Konfiguration bekannter Open Source-Clusteringtools und -technologien von Docker. Dadurch erhalten Sie eine offene Lösung, die die Portabilität der Container und der Anwendungskonfiguration garantiert. Sie müssen nur die Größe, die Anzahl von Hosts und die Orchestratortools auswählen. Alles Weitere erledigt AKS.

![Kubernetes-Clusterstruktur: Es gibt einen Masterknoten, der DNS, Planer, Proxy usw. verarbeitet, sowie mehrere Workerknoten zum Hosten der Container.](media/image36.png)

**Abbildung 4-24.** Vereinfachte Struktur und Topologie von Kubernetes-Clustern

In Abbildung 4-24 sehen Sie die Struktur eines Kubernetes-Clusters, in dem ein Masterknoten (virtueller Computer) den größten Teil der Koordinierung des Clusters steuert. Sie können Container auf den verbleibenden Knoten bereitstellen, die aus Sicht der Anwendung als ein einziger Pool verwaltet werden und Ihnen die Skalierung auf Tausende oder sogar Zehntausende von Containern ermöglichen.

## <a name="development-environment-for-kubernetes"></a>Entwicklungsumgebung für Kubernetes

In der Entwicklungsumgebung [kündigte Docker im Juli 2018 an](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/), dass Kubernetes auch auf einem einzelnen Entwicklungscomputer (Windows 10 oder macOS) ausgeführt werden kann, indem Sie einfach [Docker Desktop](https://docs.docker.com/install/) installieren. Sie können die Bereitstellung später in die Cloud (AKS) ausweiten, um weitere Integrationstests auszuführen, wie in Abbildung 4-25 gezeigt.

![Docker kündigte im Juli 2018 mit Docker Desktop Unterstützung für Entwicklungscomputer für Kubernetes-Cluster an.](media/image37.png) 

**Abbildung 4-25.** Ausführen von Kubernetes auf einem Entwicklungscomputer und in der Cloud

## <a name="getting-started-with-azure-kubernetes-service-aks"></a>Erste Schritte mit Azure Kubernetes Service (AKS) 

Um mit der Nutzung von AKS zu beginnen, stellen Sie über das Azure-Portal oder mithilfe der CLI einen AKS-Cluster bereit. Weitere Informationen zum Bereitstellen eines Azure Container Service-Clusters finden Sie unter [Bereitstellen eines Azure Kubernetes Service-Clusters (AKS)](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

Für die durch AKS standardmäßig installierte Software fallen keine Gebühren an. Alle Standardoptionen werden mit Open Source-Software implementiert. AKS ist für viele virtuelle Computer in Azure verfügbar. Sie zahlen nur für die von Ihnen ausgewählten Compute-Instanzen und den Verbrauch von Ressourcen der zugrunde liegenden Infrastruktur, wie z.B. Netzwerkfunktionen und Speicher. Für AKS selbst fallen keine zusätzlichen Gebühren an.

Weitere Implementierungsinformationen zur Bereitstellung in Kubernetes basierend auf kubectl und Original-YAML-Dateien finden Sie im Beitrag unter [Setting eShopOnContainers up in AKS (Azure Kubernetes Service)](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.-Setting-the-solution-up-in-AKS-(Azure-Kubernetes-Service)) (Einrichten von eShopOnContainers in AKS).

## <a name="deploying-with-helm-charts-into-kubernetes-clusters"></a>Bereitstellen von Helm-Charts in Kubernetes-Clustern

Wenn Sie eine Anwendung in einem Kubernetes-Cluster bereitstellen, können Sie das Original-CLI-Tool „kubectl.exe“ mit Bereitstellungsdateien verwenden, die auf dem nativen Format (YAML-Dateien) basieren, wie bereits im vorherigen Abschnitt erwähnt. Für komplexere Kubernetes-Anwendungen, z.B. die Bereitstellung komplexer microservicebasierter Anwendungen, empfiehlt sich die Verwendung von [Helm](https://helm.sh/).

Mit Helm-Charts können Sie auch hochkomplexe Kubernetes-Anwendungen definieren, versionieren, installieren, freigeben oder Upgrades oder Rollbacks durchführen.

Darüber hinaus wird die Verwendung von Helm empfohlen, weil zusätzliche Kubernetes-Umgebungen in Azure wie etwa [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) ebenfalls auf Helm-Charts basieren.

Helm wird von der [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) in Zusammenarbeit mit Microsoft, Google, Bitnami und der Helm-Community verwaltet.

Weitere Informationen zur Implementierung in Helm-Charts und Kubernetes finden Sie im Beitrag unter [Using Helm Charts to deploy eShopOnContainers to AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.1-Deploying-to-AKS-using-Helm-Charts) (Verwenden von Helm-Charts zum Bereitstellen von eShopOnContainers in AKS).

## <a name="use-azure-dev-spaces-for-your-kubernetes-application-lifecycle"></a>Verwenden von Azure Dev Spaces für den Lebenszyklus Ihrer Kubernetes-Anwendungen

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) stellt eine schnelle, iterative Kubernetes-Entwicklungsoberfläche für Teams bereit. Mit einem minimalen Setup der Entwicklungscomputer können Sie Container direkt in Azure Kubernetes Service (AKS) iterativ ausführen und debuggen. Führen Sie Ihre Entwicklungsaufgaben unter Windows, Mac oder Linux mit bekannten Tools wie Visual Studio, Visual Studio Code oder der Befehlszeile aus.

Wie bereits erwähnt, verwendet Azure Dev Spaces Helm-Charts bei der Bereitstellung der containerbasierten Anwendungen.

Azure Dev Spaces hilft Entwicklungsteams dabei, in Kubernetes produktiver zu arbeiten, da es ihnen ermöglicht, Code schnell direkt in einem globalen Kubernetes-Cluster in Azure zu durchlaufen und zu debuggen, indem sie ganz einfach Visual Studio 2017 oder Visual Studio Code verwenden. Dieser Kubernetes-Cluster in Azure ist ein freigegebener verwalteter Kubernetes-Cluster, sodass Ihr Team nahtlos zusammenarbeiten kann. Sie können Ihren Code isoliert entwickeln und dann im globalen Cluster bereitstellen und End-to-End-Tests mit anderen Komponenten durchführen, ohne Abhängigkeiten replizieren oder imitieren zu müssen.

Wie in Abbildung 4-26 gezeigt, ist das bemerkenswerteste Feature in Azure Dev Spaces die Möglichkeit, „Bereiche“ zu erstellen, die integriert in den Rest der globalen Bereitstellung im Cluster ausgeführt werden.

![Azure Dev Spaces kann Produktionsmicroservices transparent mit Entwicklungscontainerinstanzen kombinieren, um das Testen neuer Versionen zu erleichtern.](media/image38.png)

**Abbildung 4-26.** Verwenden mehrerer Bereiche in Azure Dev Spaces

Sie können einen freigegebenen Entwicklungsbereich in Azure einrichten. Jeder Entwickler kann sich auf seinen Teil der Anwendung konzentrieren und Code vor dem Committen in einem Entwicklungsbereich iterativ entwickeln, der bereits alle anderen Dienste und Cloudressourcen enthält, die ihre Szenarios benötigen. Abhängigkeiten sind immer aktuell, und die Entwickler arbeiten auf eine Weise, die die Produktion spiegelt.

Azure Dev Spaces stellt das Konzept eines Bereichs bereit, das Ihnen ermöglicht, isoliert zu arbeiten, ohne die Arbeit Ihrer Teammitglieder zu beeinträchtigen. Dieses Feature basiert auf URL-Präfixen. Wenn Sie also ein Präfix für einen Entwicklungsbereich in der URL angeben, wird für die Anforderungen jedes Containers eine bestimmte Version des Containers für den Bereich ausgeführt, in dem dieser vorhanden ist. Andernfalls wird die globale/konsolidierte Version ausgeführt.

Auf der [Wiki-Seite für eShopOnContainers in Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.2-Using-Azure-Dev-Spaces-and-AKS) finden Sie eine praktische Ansicht eines konkreten Beispiels.

Weitere Informationen finden Sie im Artikel zur [Teamentwicklung mit Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Erste Schritte mit Azure Kubernetes Service (AKS)** \
  [*https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal*](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)

- **Azure Dev Spaces** \
  [*https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces*](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces)

- **Kubernetes** (offizielle Website). \
  [*https://kubernetes.io/*](https://kubernetes.io/)

>[!div class="step-by-step"]
>[Zurück](resilient-high-availability-microservices.md)
>[Weiter](using-azure-service-fabric.md)