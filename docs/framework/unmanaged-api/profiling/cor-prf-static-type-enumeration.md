---
title: COR_PRF_STATIC_TYPE-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_STATIC_TYPE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_STATIC_TYPE
helpviewer_keywords: COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 446967cc157962a1ec4a87193bbf84b1a356efa6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="a5dd4-102">COR_PRF_STATIC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a5dd4-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="a5dd4-103">Zeigt an, ob ein Feld statisch ist und, falls dies der Fall ist, ob die statische Qualität für das Feld gilt.</span><span class="sxs-lookup"><span data-stu-id="a5dd4-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="a5dd4-104">Diese Werte können kombiniert werden, verwenden die bitweise OR-Operation, um anzugeben, dass das Feld mehrere verschiedene statische Qualitäten.</span><span class="sxs-lookup"><span data-stu-id="a5dd4-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5dd4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5dd4-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a5dd4-106">Member</span><span class="sxs-lookup"><span data-stu-id="a5dd4-106">Members</span></span>  
  
|<span data-ttu-id="a5dd4-107">Member</span><span class="sxs-lookup"><span data-stu-id="a5dd4-107">Member</span></span>|<span data-ttu-id="a5dd4-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5dd4-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="a5dd4-109">Das Feld ist nicht statisch.</span><span class="sxs-lookup"><span data-stu-id="a5dd4-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="a5dd4-110">Das Feld ist Anwendung statische Domäne.</span><span class="sxs-lookup"><span data-stu-id="a5dd4-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="a5dd4-111">Das Feld ist threadstatische.</span><span class="sxs-lookup"><span data-stu-id="a5dd4-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="a5dd4-112">Das Feld ist statischen Kontext.</span><span class="sxs-lookup"><span data-stu-id="a5dd4-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="a5dd4-113">Das Feld wird die relative virtuelle Adresse (RVA)-statisch.</span><span class="sxs-lookup"><span data-stu-id="a5dd4-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5dd4-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5dd4-114">Requirements</span></span>  
 <span data-ttu-id="a5dd4-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5dd4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5dd4-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5dd4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5dd4-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5dd4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5dd4-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5dd4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dd4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5dd4-119">See Also</span></span>  
 [<span data-ttu-id="a5dd4-120">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="a5dd4-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)