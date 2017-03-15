---
title: "_variant_t::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::Attach"
  - "_variant_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach (méthode)"
  - "VARIANT (objet)"
  - "VARIANT (objet), attacher"
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Attache un objet **VARIANT** dans l'objet `_variant_t`.  
  
## Syntaxe  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### Paramètres  
 *varSrc*  
 Objet **VARIANT** à attacher à cet objet `_variant_t`.  
  
## Notes  
 Prend possession de l'objet **VARIANT** en l'encapsulant.  Cette fonction membre libère tout objet **VARIANT**encapsulé existant, puis copie l'objet **VARIANT** fourni, et affecte à son **VARTYPE** la valeur `VT_EMPTY` pour garantir que ses ressources pourront être libérées uniquement par le destructeur `_variant_t`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)