---
title: CCommand::GetNextResult | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs: C++
helpviewer_keywords: GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3bf105f0c85d831d1a8e4bb0048a1385e6275da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
Récupère le résultat suivant définir s’il est disponible.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 *pulRowsAffected*  
 [entrée/sortie] Pointeur vers la mémoire où le nombre de lignes affectées par une commande est retourné.  
  
 `bBind`  
 [in] Spécifie s’il faut lier la commande automatiquement une fois en cours d’exécution. La valeur par défaut est **true**, ce qui entraîne la commande à lier automatiquement. Paramètre `bBind` à **false** empêche la liaison automatique de la commande de sorte que vous pouvez lier manuellement. (Liaison manuelle est particulièrement intéressant pour les utilisateurs OLAP).  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Si un jeu de résultats a été extraite précédemment, cette fonction libère le jeu de résultats précédent et dissocie les colonnes. Si `bBind` est **true**, il lie les nouvelles colonnes.  
  
 Vous devez appeler cette fonction uniquement si vous avez spécifié plusieurs résultats en définissant le `CCommand` paramètre de modèle *TMultiple*=`CMultipleResults`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)