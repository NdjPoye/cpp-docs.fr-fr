---
title: "Implements::FillArrayWithIid, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid (méthode)"
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Implements::FillArrayWithIid, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Insère l'ID d'interface spécifié par le zérotième paramètre de modèle actuel dans l'élément de tableau spécifié.  
  
## Syntaxe  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### Paramètres  
 `index`  
 Un index de base zéro indiquant le premier élément du tableau pour cette opération.  Lorsque cette opération se termine, `index` est incrémenté de 1.  
  
 `iids`  
 Un tableau de type IID.  
  
## Remarques  
 Fonction d'assistance interne.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Implements, structure](../windows/implements-structure.md)