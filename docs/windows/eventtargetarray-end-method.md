---
title: "EventTargetArray::End, m&#233;thode | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::EventTargetArray::End"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "End (méthode)"
ms.assetid: 20c491b8-f355-4d8f-ad14-8f46121d9af6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray::End, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
ComPtr<IUnknown>* End();  
```  
  
## Valeur de retour  
 L'adresse du dernier élément du tableau interne de gestionnaires d'événements.  
  
## Notes  
 Obtient l'adresse du dernier élément du tableau interne de gestionnaires d'événements.  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [EventTargetArray, classe](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)