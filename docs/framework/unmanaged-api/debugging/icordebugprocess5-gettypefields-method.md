---
title: ICorDebugProcess5::GetTypeFields-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 214fc97e41d8d220547a5f8bd28117ff411fa89b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418404"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields-Methode
Enthält Informationen zu den Feldern, die zu einem Typ gehören.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.  
  
 `celt`  
 [in] Die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekte, deren Feldinformationen abgerufen werden sollen.  
  
 `fields`  
 [out] Ein Array von [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekte, die Informationen über die Felder enthalten, die in den Typ gehören.  
  
 `pceltNeeded`  
 [out] Ein Zeiger auf die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekttypen `fields`.  
  
## <a name="remarks"></a>Hinweise  
 Die `celt` -Parameter, der die Anzahl der Felder angibt, dessen Feldinformationen die Methode zum Auffüllen verwendet `fields`, sollte auf den Wert der entsprechen den `COR_TYPE_LAYOUT::numFields` Feld.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
