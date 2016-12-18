---
title: "MakeAllocator, classe | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::MakeAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MakeAllocator (classe)"
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MakeAllocator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,   
   T)> , T)> class MakeAllocator;  
  
template<  
   typename T  
>  
class MakeAllocator<T, false>;  
  
template<  
   typename T  
>  
class MakeAllocator<T, true>;  
```  
  
#### Paramètres  
 `T`  
 Un nom de type.  
  
 `hasWeakReferenceSupport`  
 `true` pour allouer de la mémoire pour un objet prenant en charge les références faibles; `false` pour allouer de la mémoire pour un objet ne prenant pas en charge les références faibles.  
  
## Remarques  
 Alloue de la mémoire pour une classe activabel, avec ou sans la prise en charge de références faibles.  
  
 Redéfinissez la classe MakeAllocator pour implémenter un modèle d'allocation de mémoire défini par utilisateur.  
  
 MakeAllocator est généralement utilisé pour éviter les fuites mémoire si un objet lève pendant la construction.  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[MakeAllocator::MakeAllocator, constructeur](../windows/makeallocator-makeallocator-constructor.md)|Initialise une nouvelle instance de la classe MakeAllocator.|  
|[MakeAllocator::~MakeAllocator, destructeur](../windows/makeallocator-tilde-makeallocator-destructor.md)|Libère l'instance actuelle de la classe MakeAllocator.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[MakeAllocator::Allocate, méthode](../windows/makeallocator-allocate-method.md)|Alloue de la mémoire et l'associe à l'objet MakeAllocator actuel.|  
|[MakeAllocator::Detach, méthode](../windows/makeallocator-detach-method.md)|Dissocie la mémoire allouée par la méthode [Allocate](../windows/makeallocator-allocate-method.md) de l'objet MakeAllocator actuel.|  
  
## Hiérarchie d'héritage  
 `MakeAllocator`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)