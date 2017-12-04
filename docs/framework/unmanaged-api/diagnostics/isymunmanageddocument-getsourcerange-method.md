---
title: ISymUnmanagedDocument::GetSourceRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6c47f1f491b184e9abe9d56d0729100b0d9b36a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="e550e-102">ISymUnmanagedDocument::GetSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="e550e-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="e550e-103">Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="e550e-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="e550e-104">Der Puffer muss groß genug für die Quelle sein.</span><span class="sxs-lookup"><span data-stu-id="e550e-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e550e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e550e-105">Syntax</span></span>  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e550e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e550e-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="e550e-107">[in] Die Anfangszeile im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="e550e-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="e550e-108">[in] Die Anfangsspalte im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="e550e-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="e550e-109">[in] Die letzte Zeile im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="e550e-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="e550e-110">[in] Die letzte Spalte im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="e550e-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="e550e-111">[in] Die Größe der Quelle, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e550e-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="e550e-112">[out] Ein Zeiger auf eine Variable, die Größe der Quelle empfängt.</span><span class="sxs-lookup"><span data-stu-id="e550e-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="e550e-113">[out] Die Größe und die Länge des angegebenen Bereichs des Quelldokuments, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e550e-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e550e-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e550e-114">Return Value</span></span>  
 <span data-ttu-id="e550e-115">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="e550e-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e550e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e550e-116">See Also</span></span>  
 [<span data-ttu-id="e550e-117">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e550e-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)