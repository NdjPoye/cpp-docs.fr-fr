---
title: "WeakRef::As, m&#233;thode | Microsoft Docs"
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
  - "client/Microsoft::WRL::WeakRef::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As (méthode)"
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
caps.latest.revision: 6
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::As, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit le paramètre de pointeur ComPtr spécifié pour qu’il représente l’interface spécifiée.  
  
## Syntaxe  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### Paramètres  
 `U`  
 ID d’interface.  
  
 `ptr`  
 Quand cette opération est terminée, objet qui représente le paramètre `U`.  
  
## Valeur de retour  
  
-   S\_OK si cette opération réussit ; dans le cas contraire, un HRESULT qui indique la raison pour laquelle l’opération a échoué, et `ptr` prend la valeur `nullptr`.  
  
-   S\_OK si cette opération réussit, mais que l’objet WeakRef actif a déjà été libéré. Le paramètre `ptr` prend la valeur `nullptr`.  
  
-   S\_OK si cette opération réussit, mais que l’objet WeakRef actif n’est pas dérivé du paramètre `U`. Le paramètre `ptr` prend la valeur `nullptr`.  
  
## Notes  
 Une erreur est générée si le paramètre `U` est IWeakReference ou s’il n’est pas dérivé d’IInspectable.  
  
 Le premier modèle est le formulaire que vous devez utiliser dans votre code. Le deuxième modèle est une spécialisation d’assistance interne qui prend en charge les fonctionnalités du langage C\+\+ telles que le mot clé de déduction de type [auto](../cpp/auto-cpp.md).  
  
 À compter du Kit de développement logiciel SDK Windows 10, cette méthode n’affecte pas la valeur `nullptr` à l’instance WeakRef si la référence faible n’a pas pu être obtenue. Vous devez donc éviter le code de vérification des erreurs qui vérifie si WeakRef est `nullptr`. Vérifiez plutôt le HRESULT retourné pour savoir si la méthode a réussi, ou vérifiez si `ptr` est `nullptr`.  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [WeakRef, classe](../windows/weakref-class.md)