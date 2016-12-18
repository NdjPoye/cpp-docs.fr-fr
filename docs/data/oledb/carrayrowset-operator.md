---
title: "CArrayRowset::operator | Microsoft Docs"
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
  - "CArrayRowset::operator[]"
  - "CArrayRowset.operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur [], tableaux"
  - "[], opérateur"
  - "operator[], tableaux"
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArrayRowset::operator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une syntaxe similaire aux tables pour accéder à une ligne de l'ensemble de lignes.  
  
## Syntaxe  
  
```  
  
      TAccessor  
      & operator[](int nRow);  
```  
  
#### Paramètres  
 `TAccessor`  
 Un paramètre basé sur des modèles qui spécifie le type d'accesseur stocké dans l'ensemble de lignes.  
  
 `nRow`  
 \[in\] nombre de la ligne \(élément de tableau\) auquel vous souhaitez accéder.  
  
## Valeur de retour  
 Le contenu de la ligne demandée.  
  
## Notes  
 Si `nRow` dépasse le nombre de lignes dans l'ensemble de lignes, une exception est levée.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CArrayRowset, classe](../../data/oledb/carrayrowset-class.md)