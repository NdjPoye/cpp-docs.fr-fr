---
title: "Op&#233;rateurs relationnels&#160;_bstr_t | Microsoft Docs"
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
  - "_bstr_t::operator>"
  - "_bstr_t::operator=="
  - "_bstr_t::operator>="
  - "_bstr_t::operator!="
  - "_bstr_t::operator<"
  - "_bstr_t::operator<="
  - "_bstr_t::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= (opérateur)"
  - "< (opérateur), comparer des objets spécifiques"
  - "<= (opérateur), avec des objets spécifiques"
  - "== (opérateur), avec des objets Visual C++ spécifiques"
  - "> (opérateur), comparer des objets spécifiques"
  - ">= (opérateur), comparer des objets spécifiques"
  - "!= (opérateur), opérateurs relationnels"
  - "< (opérateur), bstr"
  - "<= (opérateur), bstr"
  - "== (opérateur), bstr"
  - "> (opérateur), bstr"
  - ">= (opérateur), bstr"
  - "!= (opérateur), opérateurs relationnels"
  - "< (opérateur), bstr"
  - "<= (opérateur), bstr"
  - "== (opérateur), bstr"
  - ">= (opérateur), bstr"
  - "opérateurs relationnels, _bstr_t (classe)"
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs relationnels&#160;_bstr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Compare deux objets `_bstr_t`.  
  
## Syntaxe  
  
```  
  
      bool operator!( ) const throw( );   
bool operator==(  
   const _bstr_t& str   
) const throw( );  
bool operator!=(  
   const _bstr_t& str   
) const throw( );  
bool operator<(  
   const _bstr_t& str   
) const throw( );  
bool operator>(  
   const _bstr_t& str   
) const throw( );  
bool operator<=(  
   const _bstr_t& str   
) const throw( );  
bool operator>=(  
   const _bstr_t& str   
) const throw( );  
```  
  
## Notes  
 Ces opérateurs comparent deux objets `_bstr_t` du point de vue lexicographique.  Les opérateurs retournent **true** si les comparaisons sont positives et **false** dans le cas contraire.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)