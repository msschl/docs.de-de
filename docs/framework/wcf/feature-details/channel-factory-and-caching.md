---
title: Kanalfactory und Zwischenspeichern
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: fa333d3ffa0063e226405eb8e715f9ee99f68432
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151329"
---
# <a name="channel-factory-and-caching"></a>Kanalfactory und Zwischenspeichern
WCF-Clientanwendungen verwenden die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um einen Kommunikationskanal mit einem WCF-Dienst zu erstellen.  Die Erstellung von <xref:System.ServiceModel.ChannelFactory%601>-Instanzen verursacht einigen Mehraufwand, da sie die folgenden Vorgänge umfasst:  
  
-   Erstellen der <xref:System.ServiceModel.Description.ContractDescription>-Struktur  
  
-   Reflektieren aller erforderlichen CLR-Typen  
  
-   Erstellen des Kanalstapels  
  
-   Freigeben von Ressourcen  
  
 Um den Mehraufwand zu minimieren, kann WCF Kanalfactorys zwischenspeichern, wenn Sie einen WCF-Clientproxy verwenden.  
  
> [!TIP]
>  Sie können die Erstellung von Kanalfactorys direkt steuern, wenn Sie die <xref:System.ServiceModel.ChannelFactory%601>-Klasse direkt verwenden.  
  
 Mit generierten WCF-Clientproxys [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) davon abgeleitet sind <xref:System.ServiceModel.ClientBase%601>. <xref:System.ServiceModel.ClientBase%601> definiert eine statische <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>-Eigenschaft, die das Cachingverhalten der Kanalfactory definiert. Cacheeinstellungen gelten für einen bestimmten Typ. Beispiel: Wenn `ClientBase<ITest>.CacheSettings` auf einen der unten definierten Werte wirken sich nur die Proxy/ClientBase vom Typ `ITest`. Die Cacheeinstellung für eine bestimmte <xref:System.ServiceModel.ClientBase%601> ist unveränderlich, sobald die erste Proxy/ClientBase-Instanz erstellt wurde.  
  
## <a name="specifying-caching-behavior"></a>Angeben des Cachingverhaltens  
 Das Cachingverhalten wird angegeben, indem die <xref:System.ServiceModel.ClientBase%601.CacheSetting>-Eigenschaft auf einen der folgenden Werte festgelegt wird.  
  
|Wert der Cacheeinstellung|Beschreibung|  
|-------------------------|-----------------|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|Alle Instanzen von <xref:System.ServiceModel.ClientBase%601> in der Anwendungsdomäne können am Caching teilnehmen. Der Entwickler hat bestimmt, dass die Sicherheit des Cachings nicht gefährdet wird. Caching wird nicht deaktiviert werden auch, wenn "sicherheitsrelevante" Eigenschaften <xref:System.ServiceModel.ClientBase%601> zugegriffen werden. Die Eigenschaften "sicherheitsrelevante" <xref:System.ServiceModel.ClientBase%601> sind <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> und <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.|  
|<xref:System.ServiceModel.CacheSetting.Default>|Nur Instanzen von <xref:System.ServiceModel.ClientBase%601>, die aus in den Konfigurationsdateien definierten Endpunkten erstellt wurden, nehmen am Caching innerhalb der Anwendungsdomäne teil. Alle Instanzen von <xref:System.ServiceModel.ClientBase%601>, die innerhalb dieser Anwendungsdomäne programmgesteuert erstellt wurden, nehmen nicht am Caching teil. Darüber hinaus Zwischenspeicherung deaktiviert für eine Instanz von <xref:System.ServiceModel.ClientBase%601> , sobald eine der Eigenschaften "sicherheitsrelevante" zugegriffen wird.|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|Das Caching wird für alle <xref:System.ServiceModel.ClientBase%601>-Instanzen eines bestimmten Typs innerhalb der betreffenden Anwendungsdomäne deaktiviert.|  
  
 In den folgenden Codeausschnitten wird die Verwendung der <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>-Eigenschaft veranschaulicht.  
  
```csharp  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase<ITest>.CacheSettings = CacheSettings.AlwaysOn;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient (new BasicHttpBinding(), new EndpointAddress(address)))   
         {   
            // ...  
            proxy.Test(msg);   
            // ...  
         }   
      }   
   }   
}  
// Generated by SvcUtil.exe     
public partial class TestClient : System.ServiceModel.ClientBase, ITest { }  
```  
  
 Im obigen Code verwenden alle Instanzen von `TestClient` die gleiche Kanalfactory.  
  
```csharp  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase.CacheSettings = CacheSettings.Default;   
      int i = 1;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))   
         {   
            if (i == 4)   
            {   
               ServiceEndpoint endpoint = proxy.Endpoint;   
               ... // use endpoint in some way   
            }   
            proxy.Test(msg);   
         }   
         i++;   
   }   
}   
  
// Generated by SvcUtil.exe     
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}  
```  
  
 Im obigen Beispiel verwenden alle Instanzen von `TestClient` die gleiche Kanalfactory, mit Ausnahme von #4. Instanz #4 verwendet eine Kanalfactory, die speziell für diesen Zweck erstellt wird. Diese Einstellung eignet sich für Szenarien, in denen ein bestimmter Endpunkt unterschiedliche Sicherheitseinstellungen anderer Endpunkte desselben Kanalfactorytyps (in diesem Fall `ITest`) benötigt.  
  
```csharp  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase.CacheSettings = CacheSettings.AlwaysOff;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))   
         {   
            proxy.Test(msg);   
         }           
      }   
   }  
}  
  
// Generated by SvcUtil.exe   
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}  
```  
  
 Im obigen Beispiel verwenden alle Instanzen von `TestClient` verschiedene Kanalfactorys. Dies ist nützlich, wenn jeder Endpunkt verschiedene Sicherheitsanforderungen hat und das Caching keinen Sinn macht.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ClientBase%601>  
 [Erstellen von Clients](../../../../docs/framework/wcf/building-clients.md)  
 [Clients](../../../../docs/framework/wcf/feature-details/clients.md)  
 [Zugreifen auf Dienste mithilfe eines WCF-Clients](../../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)  
 [So wird es gemacht: Verwenden von ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
