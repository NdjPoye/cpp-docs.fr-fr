---
title: CDynamicAccessor::GetValue | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
dev_langs: C++
helpviewer_keywords: GetValue method
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1599cd82347c4074863f2b649a2c67df894893e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorgetvalue"></a>CDynamicAccessor::GetValue
Récupère les données pour une colonne spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void* GetValue(   
   DBORDINAL nColumn    
) const throw( );  
void* GetValue(  
   const CHAR* pColumnName   
) const throw( );  
void* GetValue(  
   const WCHAR* pColumnName   
) const throw( );  
template < class ctype >  
bool GetValue(  
   DBORDINAL nColumn,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const CHAR* pColumnName,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const WCHAR* pColumnName,  
   ctype* pData   
) const throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ctype`  
 [in] Un paramètre basé sur un modèle qui gère n’importe quel type de données à l’exception des types de chaîne (**CHAR\***, **WCHAR\***), qui nécessitent un traitement particulier. `GetValue`utilise le type de données approprié en fonction de ce que vous spécifiez ici.  
  
 `nColumn`  
 [in] Le numéro de colonne. Les numéros de colonne commencent à 1. La valeur 0 fait référence à la colonne de signet, le cas échéant.  
  
 `pColumnName`  
 [in] Le nom de colonne.  
  
 `pData`  
 [out] Pointeur vers le contenu de la colonne spécifiée.  
  
## <a name="return-value"></a>Valeur de retour  
 Si vous souhaitez passer des données de chaîne, utilisez les versions non de `GetValue`. Les versions non de cette méthode retournent **void\***, qui pointe vers la partie de la mémoire tampon qui contient les données de la colonne spécifiée. Retourne **NULL** si la colonne est introuvable.  
  
 Pour tous les autres types de données, il est plus simple d’utiliser les versions basées sur un modèle de `GetValue`. Les versions basées sur un modèle de retour **true** en cas de réussite ou **false** en cas d’échec.  
  
## <a name="remarks"></a>Notes  
 Utilisez les versions non pour retourner les colonnes qui contiennent des chaînes et les versions basées sur un modèle pour les colonnes qui contiennent d’autres types de données.  
  
 En mode débogage, vous obtiendrez une assertion si la taille de `pData` n’est pas égale à la taille de la colonne vers laquelle il pointe.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)