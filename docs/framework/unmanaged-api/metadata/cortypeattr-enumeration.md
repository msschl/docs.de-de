---
title: CorTypeAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTypeAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTypeAttr
helpviewer_keywords: CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab9ce555406dfeb16f99601e6b88af2395c91ae0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="6c787-102">CorTypeAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6c787-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="6c787-103">Enthält Werte, die Typmetadaten angeben.</span><span class="sxs-lookup"><span data-stu-id="6c787-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c787-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c787-104">Syntax</span></span>  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="6c787-105">Member</span><span class="sxs-lookup"><span data-stu-id="6c787-105">Members</span></span>  
  
|<span data-ttu-id="6c787-106">Member</span><span class="sxs-lookup"><span data-stu-id="6c787-106">Member</span></span>|<span data-ttu-id="6c787-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c787-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="6c787-108">Für Informationen zur Sichtbarkeit des Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c787-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="6c787-109">Gibt an, dass der Typ nicht im öffentlichen Bereich befindet.</span><span class="sxs-lookup"><span data-stu-id="6c787-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="6c787-110">Gibt an, dass der Typ im öffentlichen Bereich befindet.</span><span class="sxs-lookup"><span data-stu-id="6c787-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="6c787-111">Gibt an, dass der Typ mit öffentlicher Sichtbarkeit geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="6c787-112">Gibt an, dass der Typ mit privater Sichtbarkeit geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="6c787-113">Gibt an, dass der Typ mit familiensichtbarkeit geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="6c787-114">Gibt an, dass der Typ mit Assemblysichtbarkeit geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="6c787-115">Gibt an, dass der Typ mit Family und Assembly Sichtbarkeit geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="6c787-116">Gibt an, dass der Typ mit Family oder Assembly Sichtbarkeit geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="6c787-117">Ruft Layoutinformationen für den Typ ab.</span><span class="sxs-lookup"><span data-stu-id="6c787-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="6c787-118">Gibt an, dass die Felder dieses Typs automatisch angelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6c787-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="6c787-119">Gibt an, dass die Felder dieses Typs sequenziell angelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6c787-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="6c787-120">Gibt an, dass diese Feldlayouts explizit angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6c787-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="6c787-121">Ruft die semantischen Informationen über den Typ ab.</span><span class="sxs-lookup"><span data-stu-id="6c787-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="6c787-122">Gibt an, dass der Typ eine Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="6c787-123">Gibt an, dass der Typ eine Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="6c787-124">Gibt an, dass der Typ abstrakt ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="6c787-125">Gibt an, dass der Typ nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="6c787-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="6c787-126">Gibt an, dass der Name der Klasse spezielle.</span><span class="sxs-lookup"><span data-stu-id="6c787-126">Specifies that the class name is special.</span></span> <span data-ttu-id="6c787-127">Der Name beschreibt wie.</span><span class="sxs-lookup"><span data-stu-id="6c787-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="6c787-128">Gibt an, dass der Typ importiert wird.</span><span class="sxs-lookup"><span data-stu-id="6c787-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="6c787-129">Gibt an, dass der Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="6c787-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="6c787-130">Gibt an, dass dieser Typ ist ein [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typ.</span><span class="sxs-lookup"><span data-stu-id="6c787-130">Specifies that this type is a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="6c787-131">Ruft Informationen darüber, wie Zeichenfolgen codiert und formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="6c787-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="6c787-132">Gibt an, dass dieser Typ eine LPTSTR als ANSI interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6c787-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="6c787-133">Gibt an, dass dieser Typ eine LPTSTR als Unicode interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6c787-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="6c787-134">Gibt an, dass dieser Typ eine LPTSTR automatisch interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6c787-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="6c787-135">Gibt an, dass der Typ verfügt über eine nicht standardmäßige Codierung gemäß `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="6c787-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="6c787-136">Verwenden Sie diese Maske, um nicht standardkonforme Codierungsinformationen für systemeigenes Interop abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6c787-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="6c787-137">Die Bedeutung der Werte dieser zwei Bits ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="6c787-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="6c787-138">Gibt an, dass der Typ muss vor dem ersten Versuch, ein statisches Feld initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6c787-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="6c787-139">Gibt an, dass der Typ exportiert wird, und eine typweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="6c787-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="6c787-140">Dieses Flag und die folgenden Flags werden intern von der common Language Runtime verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c787-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="6c787-141">Gibt an, dass die common Language Runtime die Codierung von Namen überprüfen soll.</span><span class="sxs-lookup"><span data-stu-id="6c787-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="6c787-142">Gibt an, dass der Typ Sicherheit zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6c787-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c787-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c787-143">Requirements</span></span>  
 <span data-ttu-id="6c787-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c787-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c787-145">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6c787-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6c787-146">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c787-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c787-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c787-147">See Also</span></span>  
 [<span data-ttu-id="6c787-148">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="6c787-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)