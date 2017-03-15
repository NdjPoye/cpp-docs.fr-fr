---
title: "CNoAccessor, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CNoAccessor"
  - "CNoAccessor"
  - "ATL.CNoAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoAccessor (classe)"
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CNoAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Peut être utilisée comme argument TEMPLATE \(`TAccessor`\) pour les classes du modèle, telles que `CCommand` et `CTable`, qui nécessitent un argument de classe d'accesseur.  
  
## Syntaxe  
  
```  
class CNoAccessor  
```  
  
## Notes  
 Utilisez `CNoAccessor` comme argument TEMPLATE lorsque vous ne souhaitez pas que la classe prenne en charge les paramètres ou des colonnes de sortie.  
  
 `CNoAccessor` implémente les méthodes stub suivantes, qui correspondent aux autres méthodes de la classe d'accesseur :  
  
-   **BindColumns** \- colonnes de liaison des accesseurs.  
  
-   `BindParameters` \- lie les paramètres créés aux colonnes.  
  
-   **Liaison** Crée des liaisons.  
  
-   **Fermer** \- Ferme l'accesseur.  
  
-   `ReleaseAccessors` \- versions des accesseurs créés par la classe.  
  
-   `FreeRecordMemory` \- libère toutes les colonnes dans l'enregistrement actif qui doivent être libérées.  
  
-   `GetColumnInfo` \- obtient les informations de colonne de l'ensemble de lignes ouvert.  
  
-   `GetNumAccessors`Récupère le nombre d'accesseurs créés par la classe.  
  
-   `IsAutoAccessor`Retourne true si les données sont récupérées automatiquement pour l'accesseur au cours d'une opération de déplacement.  
  
-   `GetHAccessor`Récupère le handle d'accesseur à partir d'un accesseur spécifié.  
  
-   `GetBuffer`Récupère le pointeur vers la mémoire tampon de signet.  
  
-   **NoBindOnNullRowset** \- elle empêché la liaison de données dans les ensembles de lignes vides.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)