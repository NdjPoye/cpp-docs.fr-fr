---
title: Classe de CMapWordToPtr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapWordToPtr
dev_langs:
- C++
helpviewer_keywords:
- 16-bit word mapping
- CMapWordToPtr class
ms.assetid: b204d87f-6427-43e1-93e3-a4b1bb41099f
caps.latest.revision: 22
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
ms.openlocfilehash: 982d42b1204d57e2abf76498b90c17864db34fb9
ms.lasthandoff: 02/24/2017

---
# <a name="cmapwordtoptr-class"></a>CMapWordToPtr (classe)
Prend en charge les mappages de pointeurs void indexés par des mots 16 bits.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMapWordToPtr : public CObject  
```  
  
## <a name="members"></a>Membres  
 Les fonctions membres de `CMapWordToPtr` sont similaires aux fonctions membres de classe [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Ainsi, vous pouvez utiliser la documentation de référence de `CMapStringToOb` pour connaître les spécificités des fonctions membres. Chaque fois que vous voyez un `CObject` pointeur comme un paramètre de fonction ou de la valeur de retour, remplacez par un pointeur vers `void`. Chaque fois que vous voyez un `CString` ou **const** pointeur vers `char` en tant que paramètre de fonction ou de valeur de retour, remplacez **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 par exemple, se traduit par  
  
 `BOOL CMapWordToPtr::Lookup( WORD <key>, void*& <rValue> ) const;`  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Retourne le nombre d’éléments dans ce mappage.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Détermine le nombre actuel d’éléments dans la table de hachage.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Obtient l’élément suivant pour l’itération.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Retourne le nombre d’éléments dans ce mappage.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Retourne la position du premier élément.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Calcule la valeur de hachage d’une clé spécifiée.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Initialise la table de hachage.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Vérifie si la condition de mappage vide (aucun élément).|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Recherche un pointeur void en fonction de la clé de pointeur void. La valeur du pointeur, pas l’entité qu’il pointe, est utilisée pour la comparaison de clés.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Retourne une référence à la clé associée à la valeur de clé spécifiée.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Supprime tous les éléments de cette carte.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Supprime un élément spécifié par une clé.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Insère un élément dans la carte ; remplace un élément existant si une clé est trouvée.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[[] CMapStringToOb::operator](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Insère un élément dans le mappage, substitution de l’opérateur pour `SetAt`.|  
  
## <a name="remarks"></a>Notes  
 `CMapWordToPtr`incorpore la `IMPLEMENT_DYNAMIC` macro pour prendre en charge les accès de type au moment de l’exécution et le vidage à un `CDumpContext` objet. Si vous avez besoin d’un vidage des éléments cartographiques individuels, vous devez définir la profondeur du contexte de vidage à 1 ou supérieur.  
  
 Mappages de Word en pointeur ne peuvent pas être sérialisés.  
  
 Lorsqu’un `CMapWordToPtr` objet est supprimé, ou lorsque ses éléments sont supprimés, les mots et les pointeurs sont supprimés. Les entités référencées par les pointeurs ne sont pas supprimées.  
  
 Pour plus d’informations sur `CMapWordToPtr`, consultez l’article [Collections](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToPtr`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcoll.h  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




