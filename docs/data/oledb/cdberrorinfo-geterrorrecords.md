---
title: CDBErrorInfo::GetErrorRecords | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- GetErrorRecords method
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5187de6c9150ead2c01c770e09cb1a7e64c48004
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdberrorinfogeterrorrecords"></a>CDBErrorInfo::GetErrorRecords
Obtient les enregistrements d’erreur pour l’objet spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords) throw();  


HRESULT GetErrorRecords(ULONG* pcRecords) throw();  
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
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)