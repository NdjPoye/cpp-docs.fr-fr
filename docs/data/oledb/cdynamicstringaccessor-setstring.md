---
title: CDynamicStringAccessor::SetString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 43956a0bb9ce673e96c4a8c06194a6ef48a56495
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicstringaccessorsetstring"></a>CDynamicStringAccessor::SetString
Définit les données de la colonne spécifiée sous forme de chaîne.  
  
## <a name="syntax"></a>Syntaxe  
  
```
HRESULT SetString(DBORDINAL nColumn,  
  BaseType* data) throw();  


HRESULT SetString(const CHAR* pColumnName,  
   BaseType* data) throw();  


HRESULT SetString(const WCHAR* pColumnName,  
   BaseType* data) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nColumn`  
 [in] Le numéro de colonne. Les numéros de colonne commencent à 1. La valeur spéciale 0 fait référence à la colonne de signet, le cas échéant.  
  
 `pColumnName`  
 [in] Pointeur vers une chaîne de caractères qui contient le nom de colonne.  
  
 `data`  
 [in] Pointeur vers les données de chaîne à écrire dans la colonne spécifiée.  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers la valeur de chaîne pour lequel définir la colonne spécifiée. La valeur est de type `BaseType`, qui sera `CHAR` ou `WCHAR` selon que `_UNICODE` est défini ou non.  
  
## <a name="remarks"></a>Notes  
 La seconde substituer formulaire prend le nom de colonne sous forme de chaîne ANSI ainsi le troisième formulaire prend le nom de colonne sous forme de chaîne Unicode.  
  
 Si `_SECURE_ATL` est défini pour avoir une valeur différente de zéro, un échec d’assertion runtime sera généré si l’entrée `data` chaîne est plus longue que la longueur maximale autorisée de la colonne de données référencée. Sinon, la chaîne d’entrée sera être tronquée si elle est supérieure à la longueur maximale autorisée.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)