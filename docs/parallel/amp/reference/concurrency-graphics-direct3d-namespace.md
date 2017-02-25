---
title: "Concurrency::graphics::direct3d, espace de noms | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics::direct3d"
  - "amp_short_vectors/Concurrency::graphics::direct3d"
dev_langs: 
  - "C++"
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Concurrency::graphics::direct3d, espace de noms
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Fournit les méthodes [get\_texture](../Topic/get_texture%20Function.md) et [make\_texture](../Topic/make_texture%20Function.md).  
  
## Syntaxe  
  
```  
namespace direct3d;  
```  
  
## Membres  
  
### Fonctions  
  
|Nom|Description|  
|---------|-----------------|  
|[get\_sampler, fonction](../Topic/get_sampler%20Function.md)|Obtenez l'interface d'état d'échantillonnage Direct3D sur la vue d'accélérateur spécifiée qui représente l'objet d'échantillonnage spécifié.|  
|[get\_texture, fonction](../Topic/get_texture%20Function.md)|Obtient l'interface de texture Direct3D sous\-jacente à l'objet [texture](../../../parallel/amp/reference/texture-class.md) spécifié.|  
|[make\_sampler, fonction](../Topic/make_sampler%20Function.md)|Créez un échantillonneur à partir d'un pointeur d'interface de l'état d'échantillonnage Direct3D.|  
|[make\_texture, fonction](../Topic/make_texture%20Function.md)|Crée un objet [texture](../../../parallel/amp/reference/texture-class.md) en utilisant les paramètres spécifiés.|  
|[msad4, fonction](../Topic/msad4%20Function.md)|Compare une valeur de 4 octets et une valeur source de 8 octets et accumule un vecteur de 4 sommes.|  
  
## Configuration requise  
 **En\-tête :** amp\_graphics.h  
  
 **Espace de noms :** Concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)