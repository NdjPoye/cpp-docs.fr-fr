---
title: "WeakRef::CopyTo, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo (méthode)"
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# WeakRef::CopyTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Assigne un pointeur vers une interface, si disponible, à la variable pointeur spécifiée.  
  
## Syntaxe  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<  
   typename U  
>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### Paramètres  
 `U`  
 Pointeur vers une interface IInspectable. Une erreur est générée si `U` n’est pas dérivé d’IInspectable.  
  
 `riid`  
 ID d’interface. Une erreur est générée si `riid` n’est pas dérivé d’**IWeakReference**.  
  
 `ptr`  
 Pointeur doublement indirect vers IInspectable ou IWeakReference.  
  
## Valeur de retour  
 S\_OK en cas de succès. Sinon, valeur HRESULT qui décrit l’erreur. Pour plus d'informations, consultez la section Notes.  
  
## Notes  
 La valeur de retour S\_OK signifie que cette opération a réussi, mais elle n’indique pas si la référence faible a été résolue en une référence forte. Si la valeur S\_OK est retournée, tester que le paramètre `p` est une référence forte ; autrement dit que le paramètre `p` n’est pas égal à `nullptr`.  
  
 À compter du Kit de développement logiciel \(SDK\) Windows 10, cette méthode n’affecte pas la valeur `nullptr` à l’instance WeakRef si la référence faible n’a pas pu être obtenue. Vous devez donc éviter le code de vérification des erreurs qui vérifie si WeakRef est `nullptr`. Vérifiez plutôt le HRESULT retourné pour savoir si la méthode a réussi, ou vérifiez si `ptr` est `nullptr`.  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [WeakRef, classe](../windows/weakref-class.md)