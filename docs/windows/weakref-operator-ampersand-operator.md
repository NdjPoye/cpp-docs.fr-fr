---
title: "WeakRef::operator&amp;, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (opérateur)"
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::operator&amp;, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne un objet ComPtrRef représentant l'objet WeakRef actuel.  
  
## Syntaxe  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## Valeur de retour  
 Un objet ComPtrRef représentant l'objet WeakRef actuel.  
  
## Notes  
 Ceci est un opérateur d'assistance interne qui n'est pas destiné à être utilisé dans votre code.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [WeakRef, classe](../windows/weakref-class.md)