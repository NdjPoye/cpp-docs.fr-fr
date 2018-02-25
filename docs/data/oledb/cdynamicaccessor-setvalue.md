---
title: CDynamicAccessor::SetValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- SetValue method
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c919c5ec9605f65df9a20bf5ccad03ae2bf2761c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorsetvalue"></a>CDynamicAccessor::SetValue
Stocke les données d’une colonne spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
template <class ctype>
bool SetValue(   
   DBORDINAL nColumn,   
   constctype& data) throw( );  

template <class ctype>    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data) throw( );  

template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ctype`  
 [in] Un paramètre basé sur un modèle qui gère n’importe quel type de données à l’exception des types de chaîne (**CHAR\***, **WCHAR\***), qui nécessitent un traitement particulier. `GetValue` utilise le type de données approprié en fonction de ce que vous spécifiez ici.  
  
 `pColumnName`  
 [in] Pointeur vers une chaîne de caractères contenant le nom de colonne.  
  
 `data`  
 [in] Pointeur vers la mémoire contenant les données.  
  
 `nColumn`  
 [in] Le numéro de colonne. Les numéros de colonne commencent à 1. La valeur 0 fait référence à la colonne de signet, le cas échéant.  
  
## <a name="return-value"></a>Valeur de retour  
 Si vous souhaitez définir les données de chaîne, utilisez les versions non de `GetValue`. Les versions non de cette méthode retournent **void\***, qui pointe vers la partie de la mémoire tampon qui contient les données de la colonne spécifiée. Retourne **NULL** si la colonne est introuvable.  
  
 Pour tous les autres types de données, il est plus simple d’utiliser les versions basées sur un modèle de `GetValue`. Les versions basées sur un modèle de retour **true** en cas de réussite ou **false** en cas d’échec.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)