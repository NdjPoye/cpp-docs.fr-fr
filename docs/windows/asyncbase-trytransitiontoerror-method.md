---
title: "AsyncBase::TryTransitionToError, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToError"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToError (méthode)"
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::TryTransitionToError, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si le code d'erreur spécifié peut modifier l'état d'erreur interne.  
  
## Syntaxe  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### Paramètres  
 `error`  
 Un HRESULT d'erreur.  
  
## Valeur de retour  
 `true` si l'état d'erreur interne a été modifié; sinon, `false`.  
  
## Remarques  
 Cette opération modifie l'état d'erreur uniquement si celui\-ci est déjà défini à S\_OK.  Cette opération n'a aucun effet si l'état d'erreur est déjà erreur, annulé, effectué, ou fermé.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)