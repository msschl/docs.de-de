---
title: ICorDebugILFrame::GetArgument-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetArgument
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 592354f11faac1fb4d5b050a096f4eab04643c0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="3fd60-102">ICorDebugILFrame::GetArgument-Methode</span><span class="sxs-lookup"><span data-stu-id="3fd60-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="3fd60-103">Ruft den Wert des angegebenen Arguments in Microsoft intermediate Language (MSIL)-Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="3fd60-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fd60-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fd60-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3fd60-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="3fd60-106">[in] Der Index des Arguments in diesem MSIL-Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="3fd60-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3fd60-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="3fd60-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fd60-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fd60-108">Remarks</span></span>  
 <span data-ttu-id="3fd60-109">Die `GetArgument` Methode kann verwendet werden, in einem Stapelrahmen des MSIL oder in einem Just-in-Time (JIT) kompilierten Frame.</span><span class="sxs-lookup"><span data-stu-id="3fd60-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fd60-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fd60-110">Requirements</span></span>  
 <span data-ttu-id="3fd60-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fd60-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fd60-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fd60-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fd60-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fd60-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fd60-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>