---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: 2e2e36486c3788cd714ffd0ed545fbb14f831476
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197040"
---
# <a name="reliablesessionbindingelement"></a>ReliableSessionBindingElement
ReliableSessionBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Mit der ReliableSessionBindingElement-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die ReliableSessionBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="acknowledgementinterval"></a>AcknowledgementInterval  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das Zeitintervall, in dem ein Ziel wartet, bevor eine Bestätigung an die Nachrichtenquelle in zuverlässigen Kanälen gesendet wird, die von der Factory erstellt werden.  
  
### <a name="flowcontrolenabled"></a>FlowControlEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob die Flusssteuerung aktiviert ist.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die maximale Dauer an, die der Kanal dem anderen Kommunikationsteilnehmer für das ausbleibende Senden von Nachrichten zugesteht, bevor im Kanal ein Fehler ausgelöst wird.  
  
### <a name="maxpendingchannels"></a>MaxPendingChannels  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Anzahl von Kanälen, die auf dem Listener akzeptiert werden sollen.  
  
### <a name="maxretrycount"></a>MaxRetryCount  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Maximale Anzahl der Versuche eines zuverlässigen Kanals, eine Nachricht, für die keine Bestätigung empfangen wurde, erneut zu übertragen (durch Aufrufen von `Send` im zugrunde liegenden Kanal).  
  
### <a name="maxtransferwindowsize"></a>MaxTransferWindowSize  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Übertragungsfenstergröße für die zuverlässige Sitzung.  
  
### <a name="ordered"></a>Testreihe  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob Nachrichten auf jeden Fall in der Reihenfolge ihres Versands eintreffen.  
  
### <a name="reliablemessagingversion"></a>ReliableMessagingVersion  
 Datentyp: Ganzzahl  
  
 Zugriffstyp: Schreibgeschützt  
  
 Eine ganze Zahl, die die in der zuverlässigen Sitzung verwendete WS-ReliableMessaging Protokollversion angibt.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
