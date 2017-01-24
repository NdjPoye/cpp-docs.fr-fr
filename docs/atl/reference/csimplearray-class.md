---
title: "CSimpleArray Class | Microsoft Docs"
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
  - "ATL.CSimpleArray"
  - "ATL::CSimpleArray"
  - "CSimpleArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArray class"
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour gérer un tableau simple.  
  
## Syntaxe  
  
```  
  
      template <  
   class T,  
   class TEqual = CSimpleArrayEqualHelper< T >  
>   
class CSimpleArray  
```  
  
#### Paramètres  
 `T`  
 Le type de données à stocker dans le tableau.  
  
 `TEqual`  
 Un objet de fonctionnalités, en définissant le test d'égalité pour les éléments de type `T`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleArray::CSimpleArray](../Topic/CSimpleArray::CSimpleArray.md)|Le constructeur de tableau simple.|  
|[CSimpleArray::~CSimpleArray](../Topic/CSimpleArray::~CSimpleArray.md)|Le destructeur de tableau simple.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleArray::Add](../Topic/CSimpleArray::Add.md)|Ajoute un nouvel élément au tableau.|  
|[CSimpleArray::Find](../Topic/CSimpleArray::Find.md)|Recherche un élément du tableau.|  
|[CSimpleArray::GetData](../Topic/CSimpleArray::GetData.md)|Retourne un pointeur vers les données stockées dans le tableau.|  
|[CSimpleArray::GetSize](../Topic/CSimpleArray::GetSize.md)|Retourne le nombre d'éléments stockés dans le tableau.|  
|[CSimpleArray::Remove](../Topic/CSimpleArray::Remove.md)|Supprime un élément donné de tableau.|  
|[CSimpleArray::RemoveAll](../Topic/CSimpleArray::RemoveAll.md)|Supprime tous les éléments du tableau.|  
|[CSimpleArray::RemoveAt](../Topic/CSimpleArray::RemoveAt.md)|Supprime l'élément spécifié du tableau.|  
|[CSimpleArray::SetAtIndex](../Topic/CSimpleArray::SetAtIndex.md)|Définit l'élément spécifié dans le tableau.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleArray::operator](../Topic/CSimpleArray::operator.md)|Extrait un élément de tableau.|  
|[CSimpleArray::operator \=](../Topic/CSimpleArray::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 `CSimpleArray` fournit des méthodes pour créer et gérer un tableau simple, de n'importe quel type donné `T`.  
  
 Le paramètre `TEqual` offre un moyen de définir une fonction d'égalité de deux éléments de type `T`.  En créant une classe semblable à [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), il est possible de modifier le comportement du test d'égalité pour toute tableau donné.  Par exemple, lors d'un tableau de pointeurs, il peut être utile de définir l'égalité en fonction de les valeurs des pointeurs de référence.  L'implémentation par défaut utilise **operator\=\(\)**.  
  
 `CSimpleArray` et [CSimpleMap](../../atl/reference/csimplemap-class.md) sont conçus pour un petit nombre d'éléments.  [CAtlArray](../../atl/reference/catlarray-class.md) et [CAtlMap](../../atl/reference/catlmap-class.md) doivent être utilisés lorsque le tableau contient un grand nombre d'éléments.  
  
## Configuration requise  
 **Header:** atlsimpcoll.h  
  
## Exemple  
 [!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/CPP/csimplearray-class_1.cpp)]  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)