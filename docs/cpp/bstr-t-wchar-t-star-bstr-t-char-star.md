---
title: "_bstr_t::wchar_t*, _bstr_t::char* | Microsoft Docs"
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
  - "_bstr_t::wchar_t*"
  - "_bstr_t::char*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char* (opérateur)"
  - "wchar_t* (opérateur)"
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::wchar_t*, _bstr_t::char*
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Retourne les caractères BSTR sous la forme d'un tableau de caractères étroits ou larges.  
  
## Syntaxe  
  
```  
  
      operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## Notes  
 Ces opérateurs peuvent être utilisés pour extraire les données de type caractère encapsulées par l'objet `BSTR`.  L'assignation d'une nouvelle valeur au pointeur retourné ne modifie pas les données BSTR d'origine.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)