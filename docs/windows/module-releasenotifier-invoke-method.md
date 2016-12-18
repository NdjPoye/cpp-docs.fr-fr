---
title: "Module::ReleaseNotifier::Invoke, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::ReleaseNotifier::Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Invoke (méthode)"
ms.assetid: f62686fe-74bf-482b-a46b-6a3c09b80e7e
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::ReleaseNotifier::Invoke, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En cas d'implémentation, appelle un gestionnaire d'événements lorsque le dernier objet d'un module est libéré.  
  
## Syntaxe  
  
```  
virtual void Invoke() = 0;  
```  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Module::ReleaseNotifier, classe](../windows/module-releasenotifier-class.md)