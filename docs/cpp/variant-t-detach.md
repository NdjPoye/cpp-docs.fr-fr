---
title: "_variant_t::Detach | Microsoft Docs"
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
  - "_variant_t::Detach"
  - "_variant_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach (méthode)"
  - "VARIANT (objet)"
  - "VARIANT (objet), détacher"
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Détache l'objet encapsulé **VARIANT** de cet objet `_variant_t`.  
  
## Syntaxe  
  
```  
  
VARIANT Detach( );  
  
```  
  
## Valeur de retour  
 L'objet **VARIANT**encapsulé.  
  
## Notes  
 Extrait et retourne l'objet **VARIANT**encapsulé, puis efface alors cet objet `_variant_t` sans le détruire.  Cette fonction membre supprime **VARIANT** de l'encapsulation et définit la valeur **VARTYPE** de cet objet `_variant_t` à `VT_EMPTY`.  Il vous appartient de libérer l'objet **VARIANT** retourné en appelant la fonction [VariantClear](http://msdn.microsoft.com/fr-fr/28741d81-8404-4f85-95d3-5c209ec13835).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)