---
title: CRowset::GetDataHere | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset<TAccessor>::GetDataHere
- CRowset<TAccessor>.GetDataHere
- CRowset.GetDataHere
- GetDataHere
- CRowset::GetDataHere
- ATL::CRowset::GetDataHere
- ATL::CRowset<TAccessor>::GetDataHere
- ATL.CRowset<TAccessor>.GetDataHere
- ATL.CRowset.GetDataHere
dev_langs: C++
helpviewer_keywords: GetDataHere method
ms.assetid: 2fe2a987-1c4c-4299-876e-0591caf63af4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fb5c6cfb07a430de48cb706980c1d8c6eb1b8a61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetgetdatahere"></a>CRowset::GetDataHere
Récupère les données à partir de la ligne actuelle et le place dans la mémoire tampon spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetDataHere(   
   int nAccessor,   
   void* pBuffer    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nAccessor`  
 [in] Le numéro d’index de l’accesseur à utiliser pour accéder aux données.  
  
 `pBuffer`  
 [out] Une mémoire tampon dans laquelle placer les données de l’enregistrement actif.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Remarques  
 Pour obtenir un exemple montrant comment utiliser cette fonction, consultez le [exemple MultiRead](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [CRowset::GetData](../../data/oledb/crowset-getdata.md)