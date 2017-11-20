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
ms.openlocfilehash: 99bd7cb23f34192f3fd634856193f6616a58af0c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cnoaccessor-class"></a>CNoAccessor, classe
Peut être utilisé comme argument de modèle (`TAccessor`) pour les classes de modèle, telles que `CCommand` et `CTable`, qui nécessitent un argument de classe d’accesseur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CNoAccessor  
```  
  
## <a name="remarks"></a>Remarques  
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
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)