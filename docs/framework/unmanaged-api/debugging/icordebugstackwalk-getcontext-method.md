---
title: ICorDebugStackWalk::GetContext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.GetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bdd910862e7198d616e79ec732708f708959d26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="54238-102">ICorDebugStackWalk::GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="54238-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="54238-103">Gibt den Kontext für den aktuellen Frame in der [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="54238-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54238-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54238-104">Syntax</span></span>  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54238-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="54238-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="54238-106">[in] Flags, die den angeforderten Inhalt, der den Kontextpuffer (in "Winnt.h" definiert) angeben.</span><span class="sxs-lookup"><span data-stu-id="54238-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="54238-107">[in] Die zugeordnete Größe des Kontextpuffers.</span><span class="sxs-lookup"><span data-stu-id="54238-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="54238-108">[out] Die tatsächliche Größe des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="54238-108">[out] The actual size of the context.</span></span> <span data-ttu-id="54238-109">Dieser Wert muss kleiner als oder gleich der Größe des Kontextpuffers sein.</span><span class="sxs-lookup"><span data-stu-id="54238-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="54238-110">[out] Der Kontextpuffer.</span><span class="sxs-lookup"><span data-stu-id="54238-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54238-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="54238-111">Return Value</span></span>  
 <span data-ttu-id="54238-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="54238-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="54238-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54238-113">HRESULT</span></span>|<span data-ttu-id="54238-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54238-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54238-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="54238-115">S_OK</span></span>|<span data-ttu-id="54238-116">Der Kontext für den aktuellen Frame wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="54238-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="54238-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54238-117">E_FAIL</span></span>|<span data-ttu-id="54238-118">Der Kontext konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="54238-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="54238-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="54238-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="54238-120">Der Kontextpuffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="54238-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="54238-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="54238-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="54238-122">Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="54238-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="54238-123">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="54238-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54238-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54238-124">Remarks</span></span>  
 <span data-ttu-id="54238-125">Da nur eine Teilmenge der Register, z. B. nicht flüchtigen Register, was die Entladung wiederhergestellt werden. möglicherweise der Kontext nicht genau dem registrierungszustand zum Zeitpunkt des Aufrufs überein.</span><span class="sxs-lookup"><span data-stu-id="54238-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54238-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="54238-126">Requirements</span></span>  
 <span data-ttu-id="54238-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54238-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54238-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54238-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54238-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54238-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54238-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54238-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54238-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54238-131">See Also</span></span>  
 [<span data-ttu-id="54238-132">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="54238-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="54238-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="54238-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)