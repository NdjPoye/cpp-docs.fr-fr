---
title: "WeakRef::AsIID, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID (méthode)"
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# WeakRef::AsIID, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit le paramètre de pointeur ComPtr spécifié pour qu’il représente l’ID d’interface spécifié.  
  
## Syntaxe  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
#### Paramètres  
 `riid`  
 ID d’interface.  
  
 `ptr`  
 Quand cette opération est terminée, objet qui représente le paramètre `riid`.  
  
## Valeur de retour  
  
-   S\_OK si cette opération réussit ; dans le cas contraire, un HRESULT qui indique la raison pour laquelle l’opération a échoué, et `ptr` prend la valeur `nullptr`.  
  
-   S\_OK si cette opération réussit, mais que l’objet WeakRef actif a déjà été libéré. Le paramètre `ptr` prend la valeur `nullptr`.  
  
-   S\_OK si cette opération réussit, mais que l’objet WeakRef actif n’est pas dérivé du paramètre `riid`. Le paramètre `ptr` prend la valeur `nullptr`. \(Pour plus d’informations, consultez la section Notes.\)  
  
## Notes  
 Une erreur est générée si le paramètre `riid` n’est pas dérivé d’IInspectable. Cette erreur remplace la valeur de retour.  
  
 Le premier modèle est le formulaire que vous devez utiliser dans votre code. Le deuxième modèle \(non illustré ici, mais déclaré dans le fichier d’en\-tête\) est une spécialisation d’assistance interne qui prend en charge les fonctionnalités du langage C\+\+ telles que le mot clé de déduction de type [auto](../cpp/auto-cpp.md).  
  
 À compter du Kit de développement logiciel SDK Windows 10, cette méthode n’affecte pas la valeur `nullptr` à l’instance WeakRef si la référence faible n’a pas pu être obtenue. Vous devez donc éviter le code de vérification des erreurs qui vérifie si WeakRef est `nullptr`. Vérifiez plutôt le HRESULT retourné pour savoir si la méthode a réussi, ou vérifiez si `ptr` est `nullptr`.  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [WeakRef, classe](../windows/weakref-class.md)