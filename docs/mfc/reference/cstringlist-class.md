---
title: Classe de CStringList | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], lists
- lists, string
- CStringList class
- strings [C++], collections
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0b67104e330890ffe8f67bac0dd3b129c7742a29
ms.lasthandoff: 02/24/2017

---
# <a name="cstringlist-class"></a>CStringList (classe)
Prend en charge des listes d'objets `CString` .  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>Membres  
 Les fonctions membres de `CStringList` sont similaires aux fonctions membres de classe [CObList](../../mfc/reference/coblist-class.md). Ainsi, vous pouvez utiliser la documentation de référence de `CObList` pour connaître les spécificités des fonctions membres. Chaque fois que vous voyez un `CObject` pointeur en tant que valeur de retour, remplacez un `CString` (pas un `CString` pointeur). Chaque fois que vous voyez un `CObject` pointeur en tant que paramètre de fonction, remplacez un `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 par exemple, se traduit par  
  
 `CString& CStringList::GetHead() const;`  
  
 et  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 se traduit par  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Construit une liste vide.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Ajoute un élément (ou tous les éléments dans une autre liste) au début de la liste (fait une nouvelle tête).|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Ajoute un élément (ou tous les éléments dans une autre liste) à la fin de la liste (fait une nouvelle fin).|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|Obtient la position d’un élément spécifié par la valeur du pointeur.|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Obtient la position d’un élément spécifié par un index de base zéro.|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Obtient l’élément à une position donnée.|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Renvoie le nombre d’éléments dans cette liste.|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|Retourne l’élément head de la liste (ne peut pas être vide).|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Retourne la position de l’élément head de la liste.|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Obtient l’élément suivant pour l’itération.|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Obtient l’élément précédent pour l’itération.|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Renvoie le nombre d’éléments dans cette liste.|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|Retourne l’élément de fin de la liste (ne peut pas être vide).|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Retourne la position de l’élément de fin de la liste.|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Insère un nouvel élément après une position donnée.|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Insère un élément avant une position donnée.|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Vérifie si la condition de la liste vide (aucun élément).|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Supprime tous les éléments de cette liste.|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Supprime un élément de cette liste, spécifiée par position.|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Supprime l’élément au début de la liste.|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Supprime l’élément de la fin de la liste.|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Définit l’élément à une position donnée.|  
  
## <a name="remarks"></a>Remarques  
 Toutes les comparaisons sont effectuées par valeur, ce qui signifie que les caractères de la chaîne sont comparés au lieu des adresses des chaînes.  
  
 `CStringList` incorpore la macro `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et le vidage de ses éléments. Si une liste de `CString` objets est stocké dans une archive, avec un opérateur d’insertion surchargés ou les `Serialize` fonction membre, chaque `CString` élément est sérialisé à son tour.  
  
 Si vous avez besoin d’une image de chaque `CString` éléments, vous devez définir la profondeur du contexte de vidage à 1 ou supérieur.  
  
 Pour plus d’informations sur l’utilisation de `CStringList`, consultez l’article [Collections](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcoll.h  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC COLLECT](../../visual-cpp-samples.md)   
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




