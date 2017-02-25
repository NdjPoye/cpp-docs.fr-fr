---
title: "CSimpleMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleMap"
  - "ATL.CSimpleMap"
  - "CSimpleMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMap class"
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CSimpleMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit la prise en charge d'un tableau de mappage simple.  
  
## Syntaxe  
  
```  
  
      template <   
   class TKey,  
   class TVal,  
   class TEqual = CSimpleMapEqualHelper< TKey, TVal >   
>   
class CSimpleMap  
```  
  
#### Paramètres  
 `TKey`  
 Le type d'élément clé.  
  
 `TVal`  
 Le type d'élément de valeur.  
  
 `TEqual`  
 Un objet de fonctionnalités, en définissant le test d'égalité pour les éléments de type `T`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleMap::\_ArrayElementType](../Topic/CSimpleMap::_ArrayElementType.md)|Typedef pour le type valeur.|  
|[CSimpleMap::\_ArrayKeyType](../Topic/CSimpleMap::_ArrayKeyType.md)|Typedef pour le type de clé.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleMap::CSimpleMap](../Topic/CSimpleMap::CSimpleMap.md)|Constructeur.|  
|[CSimpleMap::~CSimpleMap](../Topic/CSimpleMap::~CSimpleMap.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleMap::Add](../Topic/CSimpleMap::Add.md)|Ajoute une clé et une valeur associée au tableau de mappage.|  
|[CSimpleMap::FindKey](../Topic/CSimpleMap::FindKey.md)|Recherche une clé spécifique.|  
|[CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md)|Recherche une valeur spécifique.|  
|[CSimpleMap::GetKeyAt](../Topic/CSimpleMap::GetKeyAt.md)|Extrait la clé spécifiée.|  
|[CSimpleMap::GetSize](../Topic/CSimpleMap::GetSize.md)|Retourne le nombre d'entrées dans la table de mappage.|  
|[CSimpleMap::GetValueAt](../Topic/CSimpleMap::GetValueAt.md)|Extrait la valeur spécifiée.|  
|[CSimpleMap::Lookup](../Topic/CSimpleMap::Lookup.md)|Retourne la valeur associée à la clé spécifiée.|  
|[CSimpleMap::Remove](../Topic/CSimpleMap::Remove.md)|Supprime une clé et une valeur de correspondance.|  
|[CSimpleMap::RemoveAll](../Topic/CSimpleMap::RemoveAll.md)|Supprime toutes les clés et valeurs.|  
|[CSimpleMap::RemoveAt](../Topic/CSimpleMap::RemoveAt.md)|Supprime une clé et une valeur spécifiques de correspondance.|  
|[CSimpleMap::ReverseLookup](../Topic/CSimpleMap::ReverseLookup.md)|Retourne la clé associée à la valeur donnée.|  
|[CSimpleMap::SetAt](../Topic/CSimpleMap::SetAt.md)|Définit la valeur associée à la clé spécifiée.|  
|[CSimpleMap::SetAtIndex](../Topic/CSimpleMap::SetAtIndex.md)|Définit la clé et la valeur spécifiques.|  
  
## Notes  
 `CSimpleMap` fournit la prise en charge d'un tableau de mappage simple de n'importe quel type donné `T`, la gestion d'un tableau non ordonné d'éléments clés et leurs valeurs associées.  
  
 Le paramètre `TEqual` offre un moyen de définir une fonction d'égalité de deux éléments de type `T`.  En créant une classe semblable à [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), il est possible de modifier le comportement du test d'égalité pour toute tableau donné.  Par exemple, lors d'un tableau de pointeurs, il peut être utile de définir l'égalité en fonction de les valeurs des pointeurs de référence.  L'implémentation par défaut utilise **operator\=\=\(\)**.  
  
 `CSimpleMap` et [CSimpleArray](../../atl/reference/csimplearray-class.md) sont fournis pour la compatibilité avec les versions précédentes ATL, les implémentations et plus complètes et plus efficace de collection sont fournies par [CAtlArray](../../atl/reference/catlarray-class.md) et [CAtlMap](../../atl/reference/catlmap-class.md).  
  
 Contrairement à d'autres collections de cartes de ATL et MFC, cette classe est implémentée avec un tableau simple, et la recherche de correspondance nécessitent une recherche linéaire.  `CAtlMap` doit être utilisé lorsque le tableau contient un grand nombre d'éléments.  
  
## Configuration requise  
 **Header:** atlsimpcoll.h  
  
## Exemple  
 [!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/CPP/csimplemap-class_1.cpp)]  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)