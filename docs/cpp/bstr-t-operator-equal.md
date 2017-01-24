---
title: "_bstr_t::operator = | Microsoft Docs"
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
  - "_bstr_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= (opérateur), avec des objets Visual C++ spécifiques"
  - "= (opérateur), bstr"
  - "= (opérateur), bstr"
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Assigne une nouvelle valeur à un objet `_bstr_t` existant.  
  
## Syntaxe  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### Paramètres  
 *s1*  
 Objet `_bstr_t` à assigner à un objet `_bstr_t` existant.  
  
 *s2*  
 Chaîne multioctets à assigner à un objet `_bstr_t` existant.  
  
 `s3`  
 Chaîne Unicode à assigner à un objet `_bstr_t` existant.  
  
 `var`  
 Objet `_variant_t` à assigner à un objet `_bstr_t` existant.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Exemple  
 Pour obtenir un exemple d'utilisation d'`operator=`, consultez [\_bstr\_t::Assign](../cpp/bstr-t-assign.md).  
  
## Voir aussi  
 [\_bstr\_t, classe](../cpp/bstr-t-class.md)