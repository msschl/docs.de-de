---
title: ICorDebugArrayValue::GetElement-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetElement
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5fc9671365a866c04671bca965ed43d83533f07f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="a1269-102">ICorDebugArrayValue::GetElement-Methode</span><span class="sxs-lookup"><span data-stu-id="a1269-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="a1269-103">Ruft den Wert des angegebenen Arrayelements ab.</span><span class="sxs-lookup"><span data-stu-id="a1269-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1269-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1269-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1269-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1269-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="a1269-106">[in] Die Anzahl der Dimensionen dieses `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a1269-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="a1269-107">Dieser Wert ist auch die Größe der `indices` Arrays, da seine Größe gleich der Anzahl der Dimensionen des ist die `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a1269-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="a1269-108">[in] Ein Array von Indexwerten, von denen jeder eine Position innerhalb einer Dimension gibt den `ICorDebugArrayValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a1269-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="a1269-109">Dieser Wert darf nicht null sein.</span><span class="sxs-lookup"><span data-stu-id="a1269-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a1269-110">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert des angegebenen Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="a1269-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1269-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1269-111">Requirements</span></span>  
 <span data-ttu-id="a1269-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1269-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1269-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1269-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1269-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1269-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1269-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1269-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>