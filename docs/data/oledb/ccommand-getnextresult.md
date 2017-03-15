---
title: "CCommand::GetNextResult | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CCommand::GetNextResult"
  - "CCommand::GetNextResult"
  - "GetNextResult"
  - "CCommand.GetNextResult"
  - "ATL.CCommand.GetNextResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetNextResult (méthode)"
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CCommand::GetNextResult
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrait le jeu de résultats suivant le cas échéant.  
  
## Syntaxe  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### Paramètres  
 *pulRowsAffected*  
 \[In\/out\] pointeur vers la mémoire dans lequel le nombre de lignes affectées par une commande est retourné.  
  
 `bBind`  
 \[in\] spécifie s'il faut lier la commande automatiquement après avoir été exécuté.  La valeur par défaut est **true**, ce qui entraîne la commande à être à liée automatiquement.  Mettre le paramètre `bBind` à **faux** pour empêcher la liaison automatique de la commande afin de pouvoir effectuer la liaison manuellement. \(La liaison manuelle présente un intérêt tout particulier aux utilisateurs d'OLAP\).  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Si un jeu de résultats a été extrait, cette fonction renvoie le résultat précédent et délie les colonnes.  Si `bBind` est **true**, il lie les colonnes.  
  
 Vous devez appeler cette fonction uniquement si vous avez spécifié des résultats en définissant le paramètre *TMultiple\=*`CMultipleResults` \= `CCommand`.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)