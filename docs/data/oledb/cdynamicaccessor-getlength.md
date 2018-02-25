---
title: CDynamicAccessor::GetLength | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs:
- C++
helpviewer_keywords:
- GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb5f10495e1e57a93cc79f98a234aa1007dadce6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
Récupère la longueur de la colonne spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```
bool GetLength(DBORDINAL nColumn,   
  DBLENGTH* pLength) const throw();  

bool GetLength(const CHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const WCHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nColumn`  
 [in] Le numéro de colonne. Les numéros de colonne commencent à 1. La valeur 0 fait référence à la colonne de signet, le cas échéant.  
  
 `pColumnName`  
 [in] Pointeur vers une chaîne de caractères contenant le nom de colonne.  
  
 `pLength`  
 [out] Pointeur vers l’entier qui contient la longueur de la colonne en octets.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne **true** si la colonne spécifiée est trouvée. Sinon, cette fonction retourne **false**.  
  
## <a name="remarks"></a>Notes  
 La première substitution prend le numéro de colonne, et les remplacements de deuxième et troisième prennent le nom de colonne au format ANSI ou Unicode, respectivement.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicAccessor (classe)](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)