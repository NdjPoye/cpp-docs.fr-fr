---
title: "HStringReference::CopyTo, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::CopyTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie l'objet en cours de HStringReference à un objet de HSTRING.  
  
## Syntaxe  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### Paramètres  
 `str`  
 Le HSTRING qui reçoit la copie.  
  
## Notes  
 Cette méthode [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) appelle la fonction.  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HStringReference, classe](../windows/hstringreference-class.md)