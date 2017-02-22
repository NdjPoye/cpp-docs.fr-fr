---
title: "Module::GenericReleaseNotifier::GenericReleaseNotifier, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GenericReleaseNotifier, constructeur"
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Module::GenericReleaseNotifier::GenericReleaseNotifier, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe Module::GenericReleaseNotifier.  
  
## Syntaxe  
  
```  
GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### Paramètres  
 `callback`  
 Un lambda, un functor, ou un gestionnaire d'événements de pointeur\-vers\-fonction qui peut être appelé avec l'opérateur de fonction parenthèses \(`()`\).  
  
 `release`  
 Spécifiez `true` pour activer l'appel à la méthod [Module::ReleaseNotifier:: Release\(\)](../windows/module-releasenotifier-release.md) sous\-jacente; sinon, spécifiez `false`.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Module::GenericReleaseNotifier, classe](../windows/module-genericreleasenotifier-class.md)