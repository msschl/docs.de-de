---
title: ICLRTaskManager::SetUILocale-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28ecba8b88ceadaf743f5c65bc6f257f7ef8cd60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="d3e71-102">ICLRTaskManager::SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e71-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="d3e71-103">Benachrichtigt auf die gerade ausgeführte Aufgabe die common Language Runtime (CLR), dass der Host das Gebietsschema der Benutzeroberfläche (UI) oder Kultur geändert hat.</span><span class="sxs-lookup"><span data-stu-id="d3e71-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3e71-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3e71-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3e71-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3e71-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="d3e71-106">[in] Der Wert der Gebietsschema-Bezeichner, der das neu zugeordnete geografische Kultur und die Sprache für die Benutzeroberfläche zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d3e71-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3e71-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d3e71-107">Return Value</span></span>  
  
|<span data-ttu-id="d3e71-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3e71-108">HRESULT</span></span>|<span data-ttu-id="d3e71-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3e71-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3e71-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3e71-110">S_OK</span></span>|<span data-ttu-id="d3e71-111">`SetUILocale`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d3e71-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="d3e71-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="d3e71-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3e71-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d3e71-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3e71-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3e71-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3e71-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d3e71-115">The call timed out.</span></span>|  
|<span data-ttu-id="d3e71-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3e71-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3e71-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d3e71-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3e71-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3e71-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3e71-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d3e71-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3e71-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3e71-120">E_FAIL</span></span>|<span data-ttu-id="d3e71-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d3e71-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3e71-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="d3e71-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3e71-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d3e71-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3e71-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3e71-124">Remarks</span></span>  
 <span data-ttu-id="d3e71-125">`SetUILocale`bietet die Möglichkeit für den Host Mechanismen, die sie möglicherweise für die Synchronisierung von Gebietsschemas auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d3e71-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3e71-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3e71-126">Requirements</span></span>  
 <span data-ttu-id="d3e71-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3e71-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3e71-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3e71-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3e71-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d3e71-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3e71-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3e71-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e71-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3e71-131">See Also</span></span>  
 [<span data-ttu-id="d3e71-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3e71-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d3e71-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3e71-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d3e71-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3e71-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d3e71-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3e71-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)