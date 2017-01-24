---
title: "_bstr_t::Attach | Microsoft Docs"
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
  - "_bstr_t::Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach (méthode)"
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Lie un wrapper `_bstr_t` à un `BSTR`.  
  
## Syntaxe  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### Paramètres  
 *s*  
 `BSTR` à associer ou assigné à la variable `_bstr_t`.  
  
## Notes  
 Si `_bstr_t` a été précédemment attaché à un autre `BSTR`, `_bstr_t` nettoie la ressource `BSTR`, si aucune autre variable `_bstr_t` n'utilise `BSTR`.  
  
## Exemple  
 Consultez [\_bstr\_t::Assign](../cpp/bstr-t-assign.md) pour voir un exemple avec **Attacher**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)