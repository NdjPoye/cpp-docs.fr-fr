---
title: "_bstr_t::GetAddress | Microsoft Docs"
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
  - "_bstr_t::GetAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddress (méthode)"
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::GetAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Libère toute chaîne existante et retourne l'adresse d'une chaîne nouvellement allouée.  
  
## Syntaxe  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## Valeur de retour  
 Pointeur désignant le `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## Notes  
 `GetAddress` affecte tous les objets `_bstr_t` qui partagent un `BSTR`.  Plusieurs objets `_bstr_t` peuvent partager un `BSTR` en utilisant le constructeur de copie et `operator=`.  
  
## Exemple  
 Consultez [\_bstr\_t::Assign](../cpp/bstr-t-assign.md) pour voir un exemple utilisant `GetAddress`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)