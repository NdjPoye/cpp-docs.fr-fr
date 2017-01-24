---
title: "CObList Class | Microsoft Docs"
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
  - "CObList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObList class"
  - "listes, objet"
  - "objets (C++), lists of"
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les listes ordonnées de pointeurs non uniques d' `CObject` accessibles de manière séquentielle ou par valeur de pointeur.  
  
## Syntaxe  
  
```  
class CObList : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|Construit une liste vide pour les pointeurs d' `CObject` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CObList::AddHead](../Topic/CObList::AddHead.md)|Ajoute un élément \(ou tous les autres éléments de liste\) au début de la liste \(fait une nouvelle tête\).|  
|[CObList::AddTail](../Topic/CObList::AddTail.md)|Ajoute un élément \(ou tous les autres éléments de liste\) à la fin de la liste \(fait une nouvelle file\).|  
|[CObList::Find](../Topic/CObList::Find.md)|Obtient la position d'un élément spécifié par valeur de pointeur.|  
|[CObList::FindIndex](../Topic/CObList::FindIndex.md)|Obtient la position d'un élément spécifié par un index de base zéro.|  
|[CObList::GetAt](../Topic/CObList::GetAt.md)|Obtient l'élément à une position donnée.|  
|[CObList::GetCount](../Topic/CObList::GetCount.md)|Retourne le nombre d'éléments de cette liste.|  
|[CObList::GetHead](../Topic/CObList::GetHead.md)|Retourne l'élément head de la liste \(ne peut pas être vide\).|  
|[CObList::GetHeadPosition](../Topic/CObList::GetHeadPosition.md)|Retourne la position de l'élément head de la liste.|  
|[CObList::GetNext](../Topic/CObList::GetNext.md)|Obtient l'élément pour itérer.|  
|[CObList::GetPrev](../Topic/CObList::GetPrev.md)|Obtient l'élément précédent pour itérer.|  
|[CObList::GetSize](../Topic/CObList::GetSize.md)|Retourne le nombre d'éléments de cette liste.|  
|[CObList::GetTail](../Topic/CObList::GetTail.md)|Retourne l'élément de fin de la liste \(ne peut pas être vide\).|  
|[CObList::GetTailPosition](../Topic/CObList::GetTailPosition.md)|Retourne la position de l'élément de fin de la liste.|  
|[CObList::InsertAfter](../Topic/CObList::InsertAfter.md)|Insère un nouvel élément après qu'une position donnée.|  
|[CObList::InsertBefore](../Topic/CObList::InsertBefore.md)|Insère un nouvel élément avant qu'une position donnée.|  
|[CObList::IsEmpty](../Topic/CObList::IsEmpty.md)|Tests pour l'état vide de liste \(les éléments\).|  
|[CObList::RemoveAll](../Topic/CObList::RemoveAll.md)|Supprime tous les éléments de cette liste.|  
|[CObList::RemoveAt](../Topic/CObList::RemoveAt.md)|Supprime un élément de cette liste, spécifiée par position.|  
|[CObList::RemoveHead](../Topic/CObList::RemoveHead.md)|Supprime l'élément de le début de la liste.|  
|[CObList::RemoveTail](../Topic/CObList::RemoveTail.md)|Supprime l'élément de la fin de la liste.|  
|[CObList::SetAt](../Topic/CObList::SetAt.md)|Définit l'élément à une position donnée.|  
  
## Notes  
 Les listes d'`CObList` se comportent comme les deux listes liées.  
  
 Une variable de type **position** est une clé de la liste.  Vous pouvez utiliser une variable de **position** comme itérateur pour parcourir une liste séquentielle et comme signet pour stocker un seul emplacement.  Une position n'est pas identique à un index, cependant.  
  
 L'implémentation d'élément est très rapidement au début de liste, à la fin, et à **position**.  Une recherche linéaire est nécessaire de rechercher un élément par valeur ou index.  Cette recherche peut être lente si la liste est longue.  
  
 `CObList` incorpore la macro d' `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et faire un dump de ses éléments.  Si une liste des pointeurs d' `CObject` est stockée à une archive, avec un opérateur surchargé d'insertion ou avec la fonction membre d' `Serialize` , chaque élément d' `CObject` est sérialisé après.  
  
 Si vous avez besoin d'un dump des éléments d' `CObject` dans la liste, vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Lorsqu'un objet d' `CObList` est supprimé, ou lorsque ses éléments sont supprimés, seuls les pointeurs d' `CObject` sont supprimés, pas les objets qu'ils référencent.  
  
 Vous pouvez dériver vos propres classes d' `CObList`.  Votre nouvelle classe de liste, conçue pour contenir les pointeurs vers des objets dérivés d' `CObject`, ajoute de nouvelles données membres et nouvelles fonctions membres.  Notez que la liste résultante n'est pas strictement type sécurisé, car elle permet l'implémentation de n'importe quel pointeur d' `CObject` .  
  
> [!NOTE]
>  Vous devez utiliser la macro d' [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) dans l'implémentation de votre classe dérivée si vous avez l'intention de sérialiser la liste.  
  
 Pour plus d'informations sur l'utilisation `CObList`, consultez l'article [collections](../../mfc/collections.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CStringList Class](../../mfc/reference/cstringlist-class.md)   
 [CPtrList Class](../../mfc/reference/cptrlist-class.md)