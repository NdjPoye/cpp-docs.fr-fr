---
title: "_variant_t::SetString | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::SetString"
  - "_variant_t.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString (méthode)"
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::SetString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Assigne une chaîne à cet objet `_variant_t`.  
  
## Syntaxe  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### Paramètres  
 `pSrc`  
 Pointeur vers la chaîne de caractères.  
  
## Notes  
 Convertit une chaîne de caractères ANSI en chaîne Unicode `BSTR` et l'assigne à cet objet `_variant_t`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)