---
title: "Module::MethodReleaseNotifier::MethodReleaseNotifier, constructeur | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MethodReleaseNotifier, constructeur"
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::MethodReleaseNotifier::MethodReleaseNotifier, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe Module::MethodReleaseNotifier.  
  
## Syntaxe  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### Paramètres  
 `object`  
 Un objet dont la fonction membre est un gestionnaire d'événements.  
  
 `method`  
 La fonction membre du paramètre `object` qui est le gestionnaire d'événements.  
  
 `release`  
 Spécifiez `true` pour activer l'appel à la méthod [Module::ReleaseNotifier:: Release\(\)](../windows/module-releasenotifier-release.md) sous\-jacente; sinon, spécifiez `false`.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Module::MethodReleaseNotifier, classe](../windows/module-methodreleasenotifier-class.md)