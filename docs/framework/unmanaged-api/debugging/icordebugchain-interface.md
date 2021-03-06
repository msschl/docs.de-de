---
title: ICorDebugChain Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32889a8e8867fc42b48413463095dda423f26b85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409840"
---
# <a name="icordebugchain-interface1"></a>ICorDebugChain Schnittstelle1
Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateFrames-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Ruft ein Enumerator, der alle verwalteten Stapelrahmen in der Kette enthält, beginnend mit den aktuellsten Frame ab.|  
|[GetActiveFrame-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Ruft den aktiven (d. h. die letzte) Frame in der Kette.|  
|[GetCallee-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Ruft die Kette, die durch diese Kette aufgerufen wurde.|  
|[GetCaller-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Ruft die Kette, die diese Kette aufgerufen.|  
|[GetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Nicht implementiert.|  
|[GetNext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Ruft die nächste Kette von Frames für den Thread an.|  
|[GetPrevious-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Ruft die vorherige Kette von Frames für den Thread an.|  
|[GetReason-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Ruft den Grund für die Entstehung dieser Aufrufkette ab.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Ruft den Registersatz für den aktiven Teil dieser Kette ab.|  
|[GetStackRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Ruft den Adressbereich des Stapelsegments für diese Kette ab.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Ruft den physischen Thread, den diese Aufrufkette wird Teil ab.|  
|[IsManaged-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Ruft einen Wert, der angibt, ob diese Kette verwalteten Code ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Stapelrahmen in einer Kette zusammenhängenden Stapelspeicherplatz belegen und Freigeben von dem gleichen Thread und Kontext. Eine Kette kann entweder Codeketten verwalteten oder nicht verwalteten darstellen. Ein leeres `ICorDebugChain` Instanz darstellt, eine Kette von nicht verwaltetem Code.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
