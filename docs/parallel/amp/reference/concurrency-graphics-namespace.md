---
title: "Concurrency::graphics, espace de noms | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics"
  - "amp_short_vectors/Concurrency::graphics"
dev_langs: 
  - "C++"
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::graphics, espace de noms
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'espace de noms de graphiques fournit des types et des fonctions qui sont conçus pour la programmation graphique.  
  
## Syntaxe  
  
```  
namespace graphics;  
```  
  
## Membres  
  
### Espaces de noms  
  
|Nom|Description|  
|---------|-----------------|  
|[Concurrency::graphics::direct3d, espace de noms](../../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md)|Fournit des fonctions pour l'interopérabilité Direct3D.|  
  
### Typedef  
  
|Nom|Description|  
|---------|-----------------|  
|`uint`|Type d'élément de [uint\_2, classe](../../../parallel/amp/reference/uint-2-class.md), [uint\_3, classe](../../../parallel/amp/reference/uint-3-class.md) et [uint\_4, classe](../../../parallel/amp/reference/uint-4-class.md).  Définie comme `typedef unsigned int uint;`.|  
  
### Énumérations  
  
|Nom|Description|  
|---------|-----------------|  
|[address\_mode, énumération](../Topic/address_mode%20Enumeration.md)|Spécifie les modes d'adresse pris en charge pour l'échantillonnage de texture.|  
|[filter\_mode, énumération](../Topic/filter_mode%20Enumeration.md)|Spécifie les modes de filtre pris en charge pour l'échantillonnage de texture.|  
  
### Classes  
  
|Nom|Description|  
|---------|-----------------|  
|[texture, classe](../../../parallel/amp/reference/texture-class.md)|Une texture est un agrégat de données sur un accelerator\_view dans le champ d'étendue.  Il s'agit d'une collection de variables, une pour chaque élément dans un domaine d'étendue.  Chaque variable contient une valeur correspondant au type primitif C\+\+ \(unsigned int, int, float, double\), ou norme de type scalaire, ou unorm \(défini dans le concurrency::graphics\), ou types de vecteurs courts éligibles définis dans le concurrency::graphics.|  
|[writeonly\_texture\_view, classe](../../../parallel/amp/reference/writeonly-texture-view-class.md)|Un writeonly\_texture\_view permet d'accéder en écriture seule à une texture.|  
|[double\_2, classe](../../../parallel/amp/reference/double-2-class.md)|Représente un vecteur court de 2 valeurs `double`.|  
|[double\_3, classe](../../../parallel/amp/reference/double-3-class.md)|Représente un vecteur court de 3 valeurs `double`.|  
|[double\_4, classe](../../../parallel/amp/reference/double-4-class.md)|Représente un vecteur court de 4 valeurs `double`.|  
|[float\_2, classe](../../../parallel/amp/reference/float-2-class.md)|Représente un vecteur court de 2 valeurs `float`.|  
|[float\_3, classe](../../../parallel/amp/reference/float-3-class.md)|Représente un vecteur court de 3 valeurs `float`.|  
|[float\_4, classe](../../../parallel/amp/reference/float-4-class.md)|Représente un vecteur court de 4 valeurs `float`.|  
|[int\_2, classe](../../../parallel/amp/reference/int-2-class.md)|Représente un vecteur court de 2 valeurs `int`.|  
|[int\_3, classe](../../../parallel/amp/reference/int-3-class.md)|Représente un vecteur court de 3 valeurs `int`.|  
|[int\_4, classe](../../../parallel/amp/reference/int-4-class.md)|Représente un vecteur court de 4 valeurs `int`.|  
|[norm\_2, classe](../../../parallel/amp/reference/norm-2-class.md)|Représente un vecteur court de 2 valeurs `norm`.|  
|[norm\_3, classe](../../../parallel/amp/reference/norm-3-class.md)|Représente un vecteur court de 3 valeurs `norm`.|  
|[norm\_4, classe](../../../parallel/amp/reference/norm-4-class.md)|Représente un vecteur court de 4 valeurs `norm`.|  
|[uint\_2, classe](../../../parallel/amp/reference/uint-2-class.md)|Représente un vecteur court de 2 valeurs `uint`.|  
|[uint\_3, classe](../../../parallel/amp/reference/uint-3-class.md)|Représente un vecteur court de 3 valeurs `uint`.|  
|[uint\_4, classe](../../../parallel/amp/reference/uint-4-class.md)|Représente un vecteur court de 4 valeurs `uint`.|  
|[unorm\_2, classe](../../../parallel/amp/reference/unorm-2-class.md)|Représente un vecteur court de 2 valeurs `unorm`.|  
|[unorm\_3, classe](../../../parallel/amp/reference/unorm-3-class.md)|Représente un vecteur court de 3 valeurs `unorm`.|  
|[unorm\_4, classe](../../../parallel/amp/reference/unorm-4-class.md)|Représente un vecteur court de 4 valeurs `unorm`.|  
|[sampler, classe](../../../parallel/amp/reference/sampler-class.md)|Représente la configuration d'échantillonnage utilisée pour l'échantillonnage de texture.|  
|[short\_vector Structure](../../../parallel/amp/reference/short-vector-structure.md)|Fournit une implémentation de base d'un vecteur court de valeurs.|  
|[short\_vector\_traits Structure](../../../parallel/amp/reference/short-vector-traits-structure.md)|Fournit pour la récupération de la longueur et le type d'un vecteur court.|  
|[texture\_view, classe](../../../parallel/amp/reference/texture-view-class.md)|Fournit un accès en lecture et en écriture à une texture.|  
  
### Fonctions  
  
|Nom|Description|  
|---------|-----------------|  
|[copy, fonction](../Topic/copy%20Function.md)|Surchargé.  Copie le contenu de la texture source dans la mémoire tampon de l'hôte de destination.|  
|[copy\_async, fonction](../Topic/copy_async%20Function.md)|Surchargé.  Copie de façon asynchrone le contenu de la texture source dans la mémoire tampon de l'hôte de destination.|  
  
## Configuration requise  
 **En\-tête :** amp\_graphics.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)