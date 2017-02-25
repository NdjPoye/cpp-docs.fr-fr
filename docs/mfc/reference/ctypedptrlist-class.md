---
title: "CTypedPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTypedPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrList class"
  - "linked lists [C++]"
  - "lists [C++]"
  - "pointer lists"
  - "template classes, CTypedPtrList class"
  - "type-safe collections"
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CTypedPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit un wrapper de type sécurisé pour les objets de classe `CPtrList`.  
  
## Syntaxe  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### Paramètres  
 `BASE_CLASS`  
 Classe de base de la classe typée de liste de pointeur ; doit être une classe de liste de pointeur \(`CObList` ou `CPtrList`\).  
  
 `TYPE`  
 Type des éléments stockés dans la liste de classes de base.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTypedPtrList::AddHead](../Topic/CTypedPtrList::AddHead.md)|Ajoute un élément \(ou tous les autres éléments de liste\) au début de la liste \(fait une nouvelle tête\).|  
|[CTypedPtrList::AddTail](../Topic/CTypedPtrList::AddTail.md)|Ajoute un élément \(ou tous les autres éléments de liste\) à la fin de la liste \(fait une nouvelle file\).|  
|[CTypedPtrList::GetAt](../Topic/CTypedPtrList::GetAt.md)|Obtient l'élément à une position donnée.|  
|[CTypedPtrList::GetHead](../Topic/CTypedPtrList::GetHead.md)|Retourne l'élément head de la liste \(ne peut pas être vide\).|  
|[CTypedPtrList::GetNext](../Topic/CTypedPtrList::GetNext.md)|Obtient l'élément pour itérer.|  
|[CTypedPtrList::GetPrev](../Topic/CTypedPtrList::GetPrev.md)|Obtient l'élément précédent pour itérer.|  
|[CTypedPtrList::GetTail](../Topic/CTypedPtrList::GetTail.md)|Retourne l'élément de fin de la liste \(ne peut pas être vide\).|  
|[CTypedPtrList::RemoveHead](../Topic/CTypedPtrList::RemoveHead.md)|Supprime l'élément de le début de la liste.|  
|[CTypedPtrList::RemoveTail](../Topic/CTypedPtrList::RemoveTail.md)|Supprime l'élément de la fin de la liste.|  
|[CTypedPtrList::SetAt](../Topic/CTypedPtrList::SetAt.md)|Définit l'élément à une position donnée.|  
  
## Notes  
 Lorsque vous utilisez `CTypedPtrList` plutôt qu' `CObList` ou `CPtrList`, les aide de la fonctionnalité de vérification de type C\+\+ éliminent des erreurs provoquées par les types pointeur incompatibles.  
  
 En outre, le wrapper d' `CTypedPtrList` effectue une grande partie du cast qui est nécessaire si vous avez utilisé `CObList` ou `CPtrList`.  
  
 Étant donné que toutes fonctions d' `CTypedPtrList` sont inline, l'utilisation de ce modèle n'affecte pas considérablement la taille ou la vitesse de votre code.  
  
 Les listes dérivées d' `CObList` peuvent être sérialisées, mais celles dérivées d' `CPtrList` ne peuvent pas.  
  
 Lorsqu'un objet d' `CTypedPtrList` est supprimé, ou lorsque ses éléments sont supprimés, seuls les pointeurs sont supprimés, pas les entités qu'ils référencent.  
  
 Pour plus d'informations sur l'utilisation `CTypedPtrList`, consultez les articles [collections](../../mfc/collections.md) et [Classes basée sur les rôles](../../mfc/template-based-classes.md).  
  
## Exemple  
 Cet exemple crée une instance d' `CTypedPtrList`, ajoute un objet, sérialise la liste sur le disque, puis supprime l'objet :  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/CPP/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/CPP/ctypedptrlist-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## Configuration requise  
 **Header:** afxtempl.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPtrList Class](../../mfc/reference/cptrlist-class.md)   
 [CObList Class](../../mfc/reference/coblist-class.md)