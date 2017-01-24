---
title: "_bstr_t::GetBSTR | Microsoft Docs"
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
  - "GetBSTR"
  - "_bstr_t::GetBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBSTR (méthode)"
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::GetBSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Pointe sur le début du `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## Syntaxe  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## Valeur de retour  
 Début du `BSTR` encapsulé par l'objet `_bstr_t`.  
  
## Notes  
 `GetBSTR` affecte tous les objets `_bstr_t` qui partagent un `BSTR`.  Plusieurs objets `_bstr_t` peuvent partager un `BSTR` en utilisant le constructeur de copie et `operator=`.  
  
## Exemple  
 Consultez [\_bstr\_t::Assign](../cpp/bstr-t-assign.md) pour voir un exemple utilisant `GetBSTR`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)