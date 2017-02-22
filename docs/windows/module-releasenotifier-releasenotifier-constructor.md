---
title: "Module::ReleaseNotifier::ReleaseNotifier, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseNotifier, constructeur"
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Module::ReleaseNotifier::ReleaseNotifier, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe Module::ReleaseNotifier.  
  
## Syntaxe  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### Paramètres  
 `release`  
 `true` pour supprimer cette instance lorsque la méthode Release est appelée; `false` pour ne pas supprimer cette instance.  
  
## Exceptions  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Module::ReleaseNotifier, classe](../windows/module-releasenotifier-class.md)