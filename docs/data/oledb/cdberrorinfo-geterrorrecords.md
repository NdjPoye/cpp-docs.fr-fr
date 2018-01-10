---
title: CDBErrorInfo::GetErrorRecords | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs: C++
helpviewer_keywords: GetErrorRecords method
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 560477035eee06e80b56b428e3c11d8c91f2b749
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfogeterrorrecords"></a>CDBErrorInfo::GetErrorRecords
Obtient les enregistrements d’erreur pour l’objet spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetErrorRecords(   
   IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords    
) throw( );  
HRESULT GetErrorRecords(   
   ULONG* pcRecords    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 *pUnk*  
 [in] Interface à l’objet pour lequel obtenir les enregistrements d’erreur.  
  
 `iid`  
 [in] IID de l’interface associée à l’erreur.  
  
 *pcRecords*  
 [out] Pointeur vers le nombre (base 1) des enregistrements d’erreur.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Utiliser la première forme de la fonction si vous souhaitez vérifier quelle interface pour obtenir les informations d’erreur à partir de. Sinon, utilisez la deuxième forme.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)