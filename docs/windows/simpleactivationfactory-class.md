---
title: "SimpleActivationFactory, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleActivationFactory (classe)"
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SimpleActivationFactory, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit un mécanisme fondamental pour créer une classe de base Windows Runtime ou une classe de base COM classique.  
  
## Syntaxe  
  
```  
template<  
   typename Base  
>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### Paramètres  
 `Base`  
 Une classe de base.  
  
## Remarques  
 La classe de base doit fournir un constructeur par défaut.  
  
 L'extrait de code suivant montre comment utiliser SimpleActivationFactory avec la macro [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md).  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[SimpleActivationFactory::ActivateInstance, méthode](../windows/simpleactivationfactory-activateinstance-method.md)|Crée une instance de l'interface spécifiée.|  
|[SimpleActivationFactory::GetRuntimeClassName, méthode](../windows/simpleactivationfactory-getruntimeclassname-method.md)|Obtient le nom de la classe d'exécution d'une instance de la classe spécifiée par le paramètre de modèle de la classe de `Base`.|  
|[SimpleActivationFactory::GetTrustLevel, méthode](../windows/simpleactivationfactory-gettrustlevel-method.md)|Obtient le niveau de confiance d'une instance de la classe spécifiée par le paramètre de modèle de la classe `Base`.|  
  
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
  
 `ActivationFactory`  
  
 `SimpleActivationFactory`  
  
## Configuration requise  
 **En\-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)