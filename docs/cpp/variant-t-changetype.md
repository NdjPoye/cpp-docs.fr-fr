---
title: "_variant_t::ChangeType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::ChangeType"
  - "_variant_t.ChangeType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChangeType (méthode)"
  - "VARIANT (objet)"
  - "VARIANT (objet), ChangeType"
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t::ChangeType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Change le type de l'objet `_variant_t` en **VARTYPE** indiqué.  
  
## Syntaxe  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### Paramètres  
 `vartype`  
 Valeur **VARTYPE** de cet objet `_variant_t`.  
  
 `pSrc`  
 Pointeur vers l'objet `_variant_t` à convertir.  Si cette valeur est **NULL**, la conversion s'effectue sur place.  
  
## Notes  
 Cette fonction membre convertit un objet `_variant_t` en **VARTYPE** indiqué.  Si `pSrc` est **NULL**, la conversion s'effectue sur place, sinon cet objet `_variant_t` est copié depuis `pSrc`, puis converti.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)