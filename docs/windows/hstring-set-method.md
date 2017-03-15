---
title: "HString::Set, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::Set"
dev_langs: 
  - "C++"
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# HString::Set, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la valeur de l'objet HString actuel à une chaîne à caractères larges ou au paramètre HString spécifié.  
  
## Syntaxe  
  
```  
  
HRESULT Set(  
          const wchar_t* str) throw();  
HRESULT Set(   
          const wchar_t* str,   
          unsigned int len  
           ) throw();  
HRESULT Set(  
          const HSTRING& hstr  
           ) throw();  
```  
  
#### Paramètres  
 `str`  
 Une chaîne à caractères larges.  
  
 `len`  
 La longueur maximale du paramètre `str` assigné à l'objet HString actuel.  
  
 `hstr`  
 Un objet HString existant.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)