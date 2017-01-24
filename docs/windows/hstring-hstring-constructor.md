---
title: "HString::HString, constructeur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::HString"
dev_langs: 
  - "C++"
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::HString, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe HString.  
  
## Syntaxe  
  
```cpp  
  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### Paramètres  
 `hstr`  
 Un handle de HSTRING.  
  
 `other`  
 Un objet HString existant.  
  
## Remarques  
 Le premier constructeur initialise un nouvel objet HString vide.  
  
 Le deuxième constructeur initialise un objet HString à la valeur du paramètre `other` existant, puis détruit le paramètre `other`.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)