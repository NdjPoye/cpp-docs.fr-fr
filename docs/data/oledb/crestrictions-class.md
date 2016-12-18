---
title: "CRestrictions, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CRestrictions"
  - "CRestrictions"
  - "ATL.CRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRestrictions (classe)"
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRestrictions, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe générique qui vous permet de spécifier les restrictions pour les ensembles de lignes de schéma.  
  
## Syntaxe  
  
```  
template <   
   class T,   
   short nRestrictions,   
   const GUID* pguid   
>  
class CRestrictions : public CSchemaRowset <   
   T,   
   nRestrictions   
>  
```  
  
#### Paramètres  
 `T`  
 La classe utilisée pour l'accesseur.  
  
 `nRestrictions`  
 Le nombre de colonnes de restriction pour l'ensemble de lignes de schéma.  
  
 `pguid`  
 Pointeur vers le GUID du schéma.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Ouvrez .](../../data/oledb/crestrictions-open.md)|Retourne un jeu de résultats en fonction des restrictions fournies par l'utilisateur.|  
  
## Configuration requise  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)