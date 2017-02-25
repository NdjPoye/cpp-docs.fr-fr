---
title: "ActivationFactory, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactory (classe)"
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ActivationFactory, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Permet à une ou plusieurs classes d'être activées par le Windows Runtime.  
  
## Syntaxe  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### Paramètres  
 `I0`  
 La zérotième interface.  
  
 `I1`  
 La première interface.  
  
 `I2`  
 La deuxième interface.  
  
## Remarques  
 ActivationFactory fournit des méthodes d'inscription et les fonctionnalités de base de l'interface IActivationFactory.  ActivationFactory vous permet également de fournir une implémentation de fabrique personnalisée.  
  
 Le fragment de code suivant montre symboliquement comment utiliser ActivationFactory.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 Le fragment de code suivant montre comment utiliser la structure [Implements](../windows/implements-structure.md) pour spécifier plus de trois IDs d'interface.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ActivationFactory::ActivationFactory, constructeur](../windows/activationfactory-activationfactory-constructor.md)|Initialise la classe ActivationFactory.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ActivationFactory::AddRef, méthode](../windows/activationfactory-addref-method.md)|Incrémente le décompte de références de l'objet ActivationFactory actuel.|  
|[ActivationFactory::GetIids, méthode](../windows/activationfactory-getiids-method.md)|Récupère un tableau d'IDs d'interface implémentés.|  
|[ActivationFactory::GetRuntimeClassName, méthode](../windows/activationfactory-getruntimeclassname-method.md)|Obtient le nom de la classe d'exécution de l'objet que l'ActivationFactory actuel instancie.|  
|[ActivationFactory::GetTrustLevel, méthode](../windows/activationfactory-gettrustlevel-method.md)|Obtient le niveau de confiance de l'objet qu'instancie l'ActivationFactory actuelle.|  
|[ActivationFactory::QueryInterface, méthode](../windows/activationfactory-queryinterface-method.md)|Récupère un pointeur vers l'interface spécifiée.|  
|[ActivationFactory::Release, méthode](../windows/activationfactory-release-method.md)|Décrémente le décompte de références de l'objet ActivationFactory actuel.|  
  
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
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL, espace de noms  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)