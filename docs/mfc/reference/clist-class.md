---
title: "CList Class | Microsoft Docs"
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
  - "CList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CList class"
  - "listes"
  - "listes, base class for"
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les listes ordonnées d'objets non uniques accessibles de manière séquentielle ou par valeur.  
  
## Syntaxe  
  
```  
template< class TYPE, class ARG_TYPE = const TYPE& >   
class CList : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CList::CList](../Topic/CList::CList.md)|Construit une liste triée vide.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CList::AddHead](../Topic/CList::AddHead.md)|Ajoute un élément \(ou tous les autres éléments de liste\) au début de la liste \(fait une nouvelle tête\).|  
|[CList::AddTail](../Topic/CList::AddTail.md)|Ajoute un élément \(ou tous les autres éléments de liste\) à la fin de la liste \(fait une nouvelle file\).|  
|[CList::Find](../Topic/CList::Find.md)|Obtient la position d'un élément spécifié par valeur de pointeur.|  
|[CList::FindIndex](../Topic/CList::FindIndex.md)|Obtient la position d'un élément spécifié par un index de base zéro.|  
|[CList::GetAt](../Topic/CList::GetAt.md)|Obtient l'élément à une position donnée.|  
|[CList::GetCount](../Topic/CList::GetCount.md)|Retourne le nombre d'éléments de cette liste.|  
|[CList::GetHead](../Topic/CList::GetHead.md)|Retourne l'élément head de la liste \(ne peut pas être vide\).|  
|[CList::GetHeadPosition](../Topic/CList::GetHeadPosition.md)|Retourne la position de l'élément head de la liste.|  
|[CList::GetNext](../Topic/CList::GetNext.md)|Obtient l'élément pour itérer.|  
|[CList::GetPrev](../Topic/CList::GetPrev.md)|Obtient l'élément précédent pour itérer.|  
|[CList::GetSize](../Topic/CList::GetSize.md)|Retourne le nombre d'éléments de cette liste.|  
|[CList::GetTail](../Topic/CList::GetTail.md)|Retourne l'élément de fin de la liste \(ne peut pas être vide\).|  
|[CList::GetTailPosition](../Topic/CList::GetTailPosition.md)|Retourne la position de l'élément de fin de la liste.|  
|[CList::InsertAfter](../Topic/CList::InsertAfter.md)|Insère un nouvel élément après qu'une position donnée.|  
|[CList::InsertBefore](../Topic/CList::InsertBefore.md)|Insère un nouvel élément avant qu'une position donnée.|  
|[CList::IsEmpty](../Topic/CList::IsEmpty.md)|Tests pour l'état vide de liste \(les éléments\).|  
|[CList::RemoveAll](../Topic/CList::RemoveAll.md)|Supprime tous les éléments de cette liste.|  
|[CList::RemoveAt](../Topic/CList::RemoveAt.md)|Supprime un élément de cette liste, spécifiée par position.|  
|[CList::RemoveHead](../Topic/CList::RemoveHead.md)|Supprime l'élément de le début de la liste.|  
|[CList::RemoveTail](../Topic/CList::RemoveTail.md)|Supprime l'élément de la fin de la liste.|  
|[CList::SetAt](../Topic/CList::SetAt.md)|Définit l'élément à une position donnée.|  
  
#### Paramètres  
 `TYPE`  
 Type d'objet stocké dans la liste.  
  
 `ARG` *\_* `TYPE`  
 Tapez utilisé des objets de référence stockés dans la liste.  Peut être une référence.  
  
## Notes  
 Les listes d'`CList` se comportent comme les deux listes liées.  
  
 Une variable de type **position** est une clé de la liste.  Vous pouvez utiliser une variable de **position** comme itérateur pour parcourir une liste séquentielle et comme signet pour stocker un seul emplacement.  Une position n'est pas identique à un index, cependant.  
  
 L'implémentation d'élément est très rapidement au début de liste, à la fin, et à **position**.  Une recherche linéaire est nécessaire de rechercher un élément par valeur ou index.  Cette recherche peut être lente si la liste est longue.  
  
 Si vous avez besoin d'un dump des éléments dans la liste, vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Certaines fonctions membres de cette classe appelle les fonctions d'assistance globales qui doivent être personnalisées pour la plupart des fonctionnalités de la classe d' `CList` .  Consultez [programmes d'assistance de classe de collection](../../mfc/reference/collection-class-helpers.md) dans la section « macros et Globals ».  
  
 Pour plus d'informations sur l'utilisation `CList`, consultez l'article [collections](../../mfc/collections.md).  
  
## Exemple  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/CPP/clist-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## Configuration requise  
 **Header:** afxtempl.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)