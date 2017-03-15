---
title: "RuntimeClass::Release, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "release (méthode)"
ms.assetid: 0bd6f9e2-ad90-4de6-adef-a6286f458cb6
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::Release, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Effectue une opération de livraison COM sur l'objet en cours de RuntimeClass.  
  
## Syntaxe  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Remarques  
 Si le décompte de références est zéro, l'objet de RuntimeClass est supprimé.  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [RuntimeClass, classe](../windows/runtimeclass-class.md)