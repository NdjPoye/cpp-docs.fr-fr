---
title: "ComPtr::Attach, m&#233;thode | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach (méthode)"
ms.assetid: 5b911f2d-9830-4dc7-b9e3-527abd55d2c8
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::Attach, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Associe ce ComPtr avec le type d'interface spécifié par le paramètre de type de modèle actuel.  
  
## Syntaxe  
  
```  
void Attach(  
   _In_opt_ InterfaceType* other  
);  
```  
  
#### Paramètres  
 `other`  
 Type d'interface.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)