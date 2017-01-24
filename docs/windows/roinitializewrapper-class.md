---
title: "RoInitializeWrapper, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RoInitializeWrapper, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
class RoInitializeWrapper  
```  
  
## Remarques  
 RoInitializeWrapper est une pratique qui initialise le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et retourne un HRESULT indiquant si l'opération a réussi.  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper, constructeur](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Initialise une nouvelle instance de la classe RoInitializeWrapper.|  
|[RoInitializeWrapper::~RoInitializeWrapper, destructeur](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Détruit l'instance actuelle de la classe RoInitializeWrapper.|  
  
### Opérateurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT\(\), opérateur](../windows/roinitializewrapper-hresult-parens-operator.md)|Récupère le HRESULT produit par le constructeur de RoInitializeWrapper.|  
  
## Hiérarchie d'héritage  
 `RoInitializeWrapper`  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers, espace de noms](../windows/microsoft-wrl-wrappers-namespace.md)