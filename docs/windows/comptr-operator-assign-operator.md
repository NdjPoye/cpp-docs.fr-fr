---
title: "ComPtr::operator=, op&#233;rateur | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= (opérateur)"
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator=, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Assigne une valeur au ComPtr actuel.  
  
## Syntaxe  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <  
   typename U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### Paramètres  
 `U`  
 Une classe.  
  
 `other`  
 Un pointeur, une référence, ou une référence rvalue à un type ou un autre ComPtr.  
  
## Valeur de retour  
 Référence au ComPtr actuel.  
  
## Remarques  
 La première version de cet opérateur assigne une valeur vide au ComPtr actuel.  
  
 Dans la deuxième version, si le pointeur d'interface de l'assignation est différent du pointeur d'interface en cours de ComPtr, le deuxième pointeur d'interface est assigné au ComPtr actuel.  
  
 Dans la troisième version, le pointeur d'interface de l'assignation est assigné au ComPtr actuel.  
  
 Dans la quatrième version, si le pointeur d'interface de la valeur d'assignation est différent du pointeur d'interface en cours de ComPtr, le deuxième pointeur d'interface est assigné au ComPtr actuel.  
  
 La cinquième version est un opérateur de copie ; une référence à un ComPtr est assignée au ComPtr actuel.  
  
 La sixième version est un opérateur de copie qui utilise la sémantique de déplacement ; une référence rvalue à un ComPtr si un type est une conversion statique et ensuite assigné au ComPtr actuel.  
  
 La septième version est un opérateur de copie qui utilise la sémantique de déplacement ; une référence rvalue à un ComPtr d'un type `U` est une conversion statique et ensuite assigné au ComPtr actuel.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)