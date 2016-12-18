---
title: "CreateClassFactory, fonction | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::CreateClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateClassFactory (fonction)"
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreateClassFactory, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée une fabrique produisant des instances de la classe spécifiée.  
  
## Syntaxe  
  
```cpp  
  
template<typename Factory>  
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(  
   _In_ unsigned int *flags,   
   _In_ const CreatorMap* entry,   
   REFIID riid,   
   _Outptr_ IUnknown **ppFactory  
) throw();  
  
```  
  
#### Paramètres  
 `flags`  
 Une combinaison d'une ou plusieurs valeurs d'énumération [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
 `entry`  
 Pointeur vers un [CreatorMap](../windows/creatormap-structure.md) contenant les informations d'initialisation et d'enregistrement du paramètre `riid`.  
  
 `riid`  
 Référence à un ID d'interface.  
  
 `ppFactory`  
 Si cette opération est terminée avec succès, un pointeur vers une fabrique de classe.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Remarques  
 Une erreur d'assertion est émise si le paramètre de modèle `Factory` ne dérive pas de l'interface IClassFactory.  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::Details, espace de noms](../windows/microsoft-wrl-wrappers-details-namespace.md)