---
title: "BEGIN_ACCESSOR | Microsoft Docs"
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
  - "BEGIN_ACCESSOR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR (macro)"
  - "BEGIN_ACCESSOR (macro), syntaxe"
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_ACCESSOR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque le début d'une entrée d'accesseur.  
  
## Syntaxe  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### Paramètres  
 *num*  
 \[in\] nombre de décalage à zéro pour l'accesseur de la carte d'accesseur.  
  
 *bAuto*  
 \[in\] spécifie si l'accesseur est un accesseur automatique ou un accesseur manuel.  Si **true**, l'accesseur est automatique ; si **false**, l'accesseur est manuel.  Des données des méthodes d'accesseur sont extraites automatiquement sur les opérations de déplacement.  
  
## Notes  
 Dans le cas de plusieurs accesseurs sur un ensemble de lignes, vous devez spécifier `BEGIN_ACCESSOR_MAP` au début et à la macro `BEGIN_ACCESSOR` pour chaque accesseur individuel.  La macro `BEGIN_ACCESSOR` est complétée par la macro `END_ACCESSOR`.  La macro `BEGIN_ACCESSOR_MAP` est complétée par la macro `END_ACCESSOR_MAP`.  
  
## Exemple  
 Consultez [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)