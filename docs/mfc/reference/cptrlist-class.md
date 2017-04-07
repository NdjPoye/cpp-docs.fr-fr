---
title: Classe de CPtrList | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPtrList
dev_langs:
- C++
helpviewer_keywords:
- lists, generic
- CPtrList class
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 23
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 8158e0acce04ee78ea07da26332f53613489653f
ms.lasthandoff: 03/17/2017

---
# <a name="cptrlist-class"></a>CPtrList (classe)
Prend en charge des listes de pointeurs void.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>Membres  
 Les fonctions membres de `CPtrList` sont similaires aux fonctions membres de classe [CObList](../../mfc/reference/coblist-class.md). Ainsi, vous pouvez utiliser la documentation de référence de `CObList` pour connaître les spécificités des fonctions membres. Chaque fois que vous voyez un `CObject` pointeur comme un paramètre de fonction ou de la valeur de retour, remplacez par un pointeur vers `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 par exemple, se traduit par  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>Remarques  
 `CPtrList`incorpore la `IMPLEMENT_DYNAMIC` macro pour prendre en charge les accès de type au moment de l’exécution et le vidage à un `CDumpContext` objet. Si vous avez besoin de vider des éléments de liste individuels de pointeur, vous devez définir la profondeur du contexte de vidage à 1 ou supérieur.  
  
 Listes de pointeur ne peut pas être sérialisés.  
  
 Lorsqu’un `CPtrList` objet est supprimé, ou lorsque ses éléments sont supprimés, seuls les pointeurs sont supprimées, pas les entités qu’ils référencent.  
  
 Pour plus d’informations sur l’utilisation de `CPtrList`, consultez l’article [Collections](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcoll.h  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CObList, classe](../../mfc/reference/coblist-class.md)

