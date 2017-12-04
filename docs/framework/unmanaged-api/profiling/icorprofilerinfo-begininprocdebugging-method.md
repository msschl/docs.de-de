---
title: ICorProfilerInfo::BeginInprocDebugging-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.BeginInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c7c0b3c0a20c98b9ca2e5dd5ea51053008e415a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="04d48-102">ICorProfilerInfo::BeginInprocDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="04d48-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="04d48-103">Initialisiert in-Process-debugging-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="04d48-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="04d48-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="04d48-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d48-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="04d48-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04d48-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="04d48-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="04d48-107">[in] Legen Sie diesen Wert auf `true` Debuggingunterstützung für nur den aktuellen Thread initialisiert werden, legen Sie es auf `false` Debugunterstützung für alle Threads zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="04d48-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="04d48-108">[out] Der Zeiger auf ein zurückgegebener Wert, der die Debugsitzung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="04d48-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04d48-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04d48-109">Remarks</span></span>  
 <span data-ttu-id="04d48-110">Die CLR-Debugdiensten unterstützt beschränkt prozessinternes Debuggen in .NET Framework, Version 1.0 und 1.1.</span><span class="sxs-lookup"><span data-stu-id="04d48-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="04d48-111">Prozessinternes Debuggen aktiviert einen Profiler an die Inspektionsteile der Debug-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="04d48-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="04d48-112">Jedoch aufgrund von Kundenfeedback wurde prozessinternes Debuggen von .NET Framework Version 2.0 entfernt, und durch eine Reihe von Funktionen, die mehrere im Einklang mit den die profilerstellungs-API ersetzt.</span><span class="sxs-lookup"><span data-stu-id="04d48-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04d48-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04d48-113">Requirements</span></span>  
 <span data-ttu-id="04d48-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04d48-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d48-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04d48-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04d48-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04d48-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04d48-117">**.NET Framework-Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="04d48-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d48-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04d48-118">See Also</span></span>  
 [<span data-ttu-id="04d48-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04d48-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)