---
title: "HString::CopyTo, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HString::CopyTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie l'objet HString actuel dans un objet HSTRING.  
  
## Syntaxe  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### Paramètres  
 `str`  
 HSTRING qui reçoit la copie.  
  
## Notes  
 Cette méthode appelle la fonction [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx).  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)