---
title: 'Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f4cc450b04fd05d390a1f41f3d14c19f4b23be29
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155144"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft
Dieses Thema enthält Anleitungen, um sicherzustellen, dass neue ASP.NET-Webdienste auch zusammen mit WCF-Anwendungen funktionieren, wenn Sie heute ASP.NET verwenden und erwarten, in der Zukunft mithilfe von WCF.  
  
## <a name="general-recommendations"></a>Allgemeine Empfehlungen  
 Übernehmen Sie ASP.NET 2.0 auch für neue Dienste. Dadurch stellen Sie den Zugriff auf die Verbesserungen und Erweiterungen der neuen Version bereit. Allerdings können sie auch die Möglichkeit der Verwendung von ASP.NET 2.0-Komponenten zusammen mit den WCF-Komponenten in der gleichen Anwendung.  
  
## <a name="protocols"></a>Protokolle  
 Verwenden Sie die neue Funktion von ASP.NET 2.0 zum Überprüfen der Konformität mit WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 ASP.NET Web Services, die mit WS-I Basic Profile 1.1 mithilfe von WCF, vordefinierte Bindung wird mit WCF-Clients interoperabel werden <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Dienstentwicklung  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des SOAPAction HTTP-Headers an Methoden weiterzuleiten. WCF verwendet den SOAPAction-HTTP-Header zum Weiterleiten von Nachrichten an.  
  
## <a name="data-representation"></a>Datendarstellung  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Wenn Sie einen Datentyp für die Verwendung mit ASP.NET Web Services in der Erwartung von einführen WCF, die in der Zukunft zu definieren, führen Sie folgende Schritte aus:  
  
1.  Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
2.  Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um zu steuern, wie die .NET Framework-Klasse in XML übersetzt wird.  
  
 Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die von ASP.NET-Webdiensten verwendeten Typen werden können als Datenverträge verarbeitet werden, die von WCF-Anwendungen, zurückgegeben, a. eine bessere Leistung für WCF-Anwendungen.  
  
## <a name="security"></a>Sicherheit  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. WCF-Clients unterstützen sie nicht. Wenn ein Dienst gesichert werden muss, verwenden Sie die Optionen, WCF, bereitgestellt werden, da diese Optionen leistungsstärker sind und auf Standardprotokollen basieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
