---
title: IMetaDataImport::GetMethodProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4037ca42c5a66f075e949cd2035c1e7db510bb8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448907"
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps-Methode
Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mb`  
 [in] Das MethodDef-Token, das die Methode zum Zurückgeben von Metadaten für darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf ein TypeDef-Token, das den Typ darstellt, der die Methode implementiert.  
  
 `szMethod`  
 [out] Ein Zeiger auf einen Puffer, der den Namen der Methode.  
  
 `cchMethod`  
 [in] Die angeforderte Größe des `szMethod`.  
  
 `pchMethod`  
 [out] Ein Zeiger auf die Größe in Breitzeichen `szMethod`, oder im Falle von abschneiden, die tatsächliche Anzahl von Breitzeichen in den Methodennamen.  
  
 `pdwAttr`  
 [out] Ein Zeiger auf die Attribute der Methode zugeordnet.  
  
 `ppvSigBlob`  
 [out] Ein Zeiger auf die binäre Metadatensignatur der Methode.  
  
 `pcbSigBlob`  
 [out] Ein Zeiger auf die Größe in Bytes des `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse der Methode.  
  
 `pdwImplFlags`  
 [out] Ein Zeiger auf die Implementierungsflags für die Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
