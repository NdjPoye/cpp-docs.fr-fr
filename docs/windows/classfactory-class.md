---
title: "ClassFactory, classe | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ClassFactory (classe)"
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ClassFactory, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités de base de l'interface IClassFactory.  
  
## Syntaxe  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### Paramètres  
 `I0`  
 La zérotième interface.  
  
 `I1`  
 La première interface.  
  
 `I2`  
 La deuxième interface.  
  
## Remarques  
 Utilisez `ClassFactory` pour fournir une implémentation de fabrique définie par utilisateur.  
  
 Le modèle de programmation suivant démontre comment utiliser la structure [Implémentations](../windows/implements-structure.md) pour spécifier plus de trois interfaces sur une fabrique de classe.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ClassFactory::ClassFactory, constructeur](../windows/classfactory-classfactory-constructor.md)||  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ClassFactory::AddRef, méthode](../windows/classfactory-addref-method.md)|Incrémente le décompte de références de l'objet ClassFactory actuel.|  
|[ClassFactory::LockServer, méthode](../windows/classfactory-lockserver-method.md)|Incrémente ou décrémente le nombre d'objets sous\-jacents suivis par l'objet ClassFactory actuel.|  
|[ClassFactory::QueryInterface, méthode](../windows/classfactory-queryinterface-method.md)|Récupère un pointeur vers l'interface spécifiée par paramètre.|  
|[ClassFactory::Release, méthode](../windows/classfactory-release-method.md)|Décrémente le décompte de références de l'objet ClassFactory actuel.|  
  
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
  
## Configuration requise  
 **En\-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType, énumération](../windows/runtimeclasstype-enumeration.md)