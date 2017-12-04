---
title: IMetaDataImport::EnumFieldsWithName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumFieldsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f6104f287350a9ac2f0eb5b82c05422a18a48a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="5e885-102">IMetaDataImport::EnumFieldsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="5e885-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="5e885-103">Zählt FieldDef-Token des angegebenen Typs mit dem angegebenen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="5e885-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e885-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e885-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e885-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e885-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5e885-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="5e885-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="5e885-107">[in] Das Token des Typs, dessen Felder aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5e885-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="5e885-108">[in] Der Name des Felds, das den Bereich der Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="5e885-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="5e885-109">[out] Array zum Speichern der FieldDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e885-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5e885-110">[in] Die maximale Größe des `rFields`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="5e885-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5e885-111">[out] Die tatsächliche Anzahl der FieldDef-Token im zurückgegebenen `rFields`.</span><span class="sxs-lookup"><span data-stu-id="5e885-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e885-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e885-112">Remarks</span></span>  
 <span data-ttu-id="5e885-113">Im Gegensatz zu [IMetaDataImport:: EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` verwirft alle Feld-Token, die nicht mit den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="5e885-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e885-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5e885-114">Return Value</span></span>  
  
|<span data-ttu-id="5e885-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e885-115">HRESULT</span></span>|<span data-ttu-id="5e885-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e885-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5e885-117">`EnumFieldsWithName`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5e885-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5e885-118">Es sind keine Felder aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="5e885-118">There are no fields to enumerate.</span></span> <span data-ttu-id="5e885-119">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="5e885-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e885-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e885-120">Requirements</span></span>  
 <span data-ttu-id="5e885-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e885-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e885-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5e885-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e885-123">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5e885-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5e885-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e885-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e885-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e885-125">See Also</span></span>  
 [<span data-ttu-id="5e885-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e885-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5e885-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e885-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)