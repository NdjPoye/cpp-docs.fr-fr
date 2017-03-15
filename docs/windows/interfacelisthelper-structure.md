---
title: "InterfaceListHelper, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceListHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceListHelper (structure)"
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceListHelper, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
template <  
   typename T0,  
   typename T1 = Nil,  
   typename T2 = Nil,  
   typename T3 = Nil,  
   typename T4 = Nil,  
   typename T5 = Nil,  
   typename T6 = Nil,  
   typename T7 = Nil,  
   typename T8 = Nil,  
   typename T9 = Nil  
>  
struct InterfaceListHelper;  
  
template <  
   typename T0  
>  
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;  
```  
  
#### Paramètres  
 `T0`  
 Paramètre de modèle 0, qui est requis.  
  
 `T1`  
 Paramètre de modèle 1, qui par défaut n'est pas spécifié.  
  
 `T2`  
 Paramètre de modèle 2, qui par défaut n'est pas spécifié. Le troisième paramètre de modèle.  
  
 `T3`  
 Paramètre de modèle 3, qui par défaut n'est pas spécifié.  
  
 `T4`  
 Paramètre de modèle 4, qui par défaut n'est pas spécifié.  
  
 `T5`  
 Paramètre de modèle 5, qui par défaut n'est pas spécifié.  
  
 `T6`  
 Paramètre de modèle 6, qui par défaut n'est pas spécifié.  
  
 `T7`  
 Paramètre de modèle 7, qui par défaut n'est pas spécifié.  
  
 `T8`  
 Paramètre de modèle 8, qui par défaut n'est pas spécifié.  
  
 `T9`  
 Paramètre de modèle 9, qui par défaut n'est pas spécifié.  
  
## Remarques  
 Génère un type InterfaceList en appliquant de manière récursive les arguments de paramètres de modèle spécifiés.  
  
 Le modèle InterfaceListHelper utilise le paramètre de modèle `T0` pour définir la première donnée membre dans une structure InterfaceList, puis applique de manière récursive le modèle InterfaceListHelper à tous paramètres restants de modèle.  InterfaceListHelper s'arrête lorsqu'il n'y a aucun paramètre de modèle restant.  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`TypeT`|Un synonyme du type InterfaceList.|  
  
## Hiérarchie d'héritage  
 `InterfaceListHelper`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)