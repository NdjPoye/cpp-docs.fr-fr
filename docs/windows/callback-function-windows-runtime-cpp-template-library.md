---
title: "Callback, fonction (biblioth&#232;que de mod&#232;les Windows Runtime C++) | Microsoft Docs"
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
  - "event/Microsoft::WRL::Callback"
dev_langs: 
  - "C++"
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Callback, fonction (biblioth&#232;que de mod&#232;les Windows Runtime C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un objet dont la fonction membre est une méthode de rappel.  
  
## Syntaxe  
  
```  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
ComPtr<TDelegateInterface> Callback(  
   TCallbackcallback  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)()  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6,  
   TArg7)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6,  
   TArg7,  
   TArg8)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6,  
   TArg7,  
   TArg8,  
   TArg9)  
);  
```  
  
#### Paramètres  
 `TDelegateInterface`  
 Paramètre de modèle qui spécifie l'interface du délégué à appeler lorsqu'un événement se produit.  
  
 `TCallback`  
 Paramètre de modèle qui spécifie le type d'un objet qui représente un objet et sa fonction membre de rappel.  
  
 `TCallbackObject`  
 Paramètre de modèle qui spécifie l'objet dont la fonction membre est la méthode à appeler lorsqu'un événement se produit.  
  
 `TArg1`  
 Paramètre de modèle qui spécifie le type du premier argument de la méthode de rappel.  
  
 `TArg2`  
 Paramètre de modèle qui spécifie le type du second argument de la méthode de rappel.  
  
 `TArg3`  
 Paramètre de modèle qui spécifie le type du troisième argument de la méthode de rappel.  
  
 `TArg4`  
 Paramètre de modèle qui spécifie le type du quatrième argument de la méthode de rappel.  
  
 `TArg5`  
 Paramètre de modèle qui spécifie le type du cinquième argument de la méthode de rappel.  
  
 `TArg6`  
 Paramètre de modèle qui spécifie le type du sixième argument de la méthode de rappel.  
  
 `TArg7`  
 Paramètre de modèle qui spécifie le type du septième argument de la méthode de rappel.  
  
 `TArg8`  
 Paramètre de modèle qui spécifie le type du huitième argument de la méthode de rappel.  
  
 `TArg9`  
 Paramètre de modèle qui spécifie le type du neuvième argument de la méthode de rappel.  
  
 `callback`  
 Objet qui représente l'objet de rappel et sa fonction membre.  
  
 `object`  
 Objet dont la fonction membre est appelée lorsqu'un événement se produit.  
  
 `method`  
 Fonction membre à appeler lorsqu'un événement se produit.  
  
## Valeur de retour  
 Objet dont la fonction membre est la méthode de rappel spécifiée.  
  
## Notes  
 La base d'un objet délégué doit être IUnknown, et non IInspectable.  
  
## Configuration requise  
 **En\-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)