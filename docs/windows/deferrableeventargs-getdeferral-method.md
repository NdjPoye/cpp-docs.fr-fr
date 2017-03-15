---
title: "DeferrableEventArgs::GetDeferral (m&#233;thode) | Microsoft Docs"
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
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DeferrableEventArgs::GetDeferral (m&#233;thode)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient une référence à l'objet [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) qui représente un événement différé.  
  
## Syntaxe  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### Paramètres  
 `result`  
 Pointeur qui référence l'objet [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) à la fin de l'appel.  
  
## Valeur de retour  
 S\_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.  
  
## Notes  
 Pour obtenir un exemple de code, voir [DeferrableEventArgs, classe](../windows/deferrableeventargs-class.md).  
  
## Configuration requise  
 **En\-tête** : event.h  
  
 **Espace de noms** : Microsoft::WRL  
  
## Voir aussi  
 [DeferrableEventArgs, classe](../windows/deferrableeventargs-class.md)