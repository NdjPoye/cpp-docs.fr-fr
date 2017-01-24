---
title: "CStringList Class | Microsoft Docs"
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
  - "CStringList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringList class"
  - "listes, de type chaîne"
  - "chaînes (C++), collections"
  - "chaînes (C++), listes"
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Listes de support d'objets d' `CString` .  
  
## Syntaxe  
  
```  
class CStringList : public CObject  
```  
  
## Membres  
 Les fonctions membres d' `CStringList` sont semblables aux fonctions membres de la classe [CObList](../../mfc/reference/coblist-class.md).  En raison de cette ressemblance, vous pouvez utiliser la documentation de référence des `CObList` pour les détails de la fonction membre.  Partout où vous consultez un pointeur d' `CObject` comme valeur de retour, substituez `CString` \(pas un pointeur d' `CString` \).  Partout où vous consultez un pointeur d' `CObject` comme paramètre de fonction, substituez `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 par exemple, traduit la valeur  
  
 `CString& CStringList::GetHead() const;`  
  
 et  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 convertit la valeur  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|Construit une liste vide.|  
  
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
 Toutes les comparaisons sont effectuées par la valeur, ce qui signifie que les caractères dans la chaîne sont comparés à la place des adresses des chaînes.  
  
 `CStringList` incorpore la macro d' `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et faire un dump de ses éléments.  Si une liste d'objets d' `CString` est stockée à une archive, avec un opérateur surchargé d'insertion ou avec la fonction membre d' `Serialize` , chaque élément d' `CString` est sérialisé après.  
  
 Si vous avez besoin d'un dump des éléments d' `CString` , vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Pour plus d'informations sur l'utilisation `CStringList`, consultez l'article [collections](../../mfc/collections.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)