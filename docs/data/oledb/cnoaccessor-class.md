---
title: Cnoaccessor, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs: C++
helpviewer_keywords: CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 799fe151b22748da25901139a5aefe67460b2484
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cnoaccessor-class"></a>CNoAccessor, classe
Peut être utilisé comme argument de modèle (`TAccessor`) pour les classes de modèle, telles que `CCommand` et `CTable`, qui nécessitent un argument de classe d’accesseur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CNoAccessor  
```  
  
## <a name="remarks"></a>Notes  
 Utilisez `CNoAccessor` comme argument de modèle lorsque vous ne souhaitez pas la classe pour prendre en charge des paramètres ou des colonnes de sortie.  
  
 `CNoAccessor`implémente les méthodes stub suivantes, chacune d’elles correspondent aux autres méthodes d’accesseur de classe :  
  
-   **BindColumns** -lie les colonnes aux accesseurs.  
  
-   `BindParameters`-Lie les paramètres aux colonnes.  
  
-   **Lier** -crée des liaisons.  
  
-   **Fermer** -ferme l’accesseur.  
  
-   `ReleaseAccessors`-Libère les accesseurs créés par la classe.  
  
-   `FreeRecordMemory`-Permet de libérer toutes les colonnes dans l’enregistrement actif qui doivent être libérées.  
  
-   `GetColumnInfo`-Obtient les informations de colonne à partir de l’ensemble de lignes ouvert.  
  
-   `GetNumAccessors`-Récupère le nombre d’accesseurs créé par la classe.  
  
-   `IsAutoAccessor`-Retourne la valeur true si les données sont récupérées automatiquement pour l’accesseur pendant une opération de déplacement.  
  
-   `GetHAccessor`-Récupère le handle d’accesseur d’un accesseur spécifié.  
  
-   `GetBuffer`-Récupère le pointeur vers la mémoire tampon de signet.  
  
-   **NoBindOnNullRowset** -empêche la liaison de données sur des ensembles de lignes vide.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)