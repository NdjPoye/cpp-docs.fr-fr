---
title: "SimpleClassFactory, classe | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleClassFactory (classe)"
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleClassFactory, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit un mécanisme fondamental pour créer une classe de base.  
  
## Syntaxe  
  
```  
template<  
   typename Base  
>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### Paramètres  
 `Base`  
 Une classe de base.  
  
## Remarques  
 La classe de base doit fournir un constructeur par défaut.  
  
 L'extrait de code suivant montre comment utiliser SimpleClassFactory avec la macro [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md).  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[SimpleClassFactory::CreateInstance, méthode](../windows/simpleclassfactory-createinstance-method.md)|Crée une instance de l'interface spécifiée.|  
  
## Hiérarchie d'héritage  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## Configuration requise  
 **En\-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)