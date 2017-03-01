---
title: CTypedPtrMap (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections
- template classes, CTypedPtrMap class
- maps
- CTypedPtrMap class
- pointer maps
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 919d751c6ffe4b10ffad047f1b6be832bf49a1af
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap (classe)
Fournit un « wrapper » de type sécurisé pour les objets des classes de mappage de pointeur `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`et `CMapStringToPtr`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Paramètres  
 `BASE_CLASS`  
 Classe de base de la classe map pointeur typé ; doit être une classe de mappage de pointeur ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, ou `CMapStringToPtr`).  
  
 `KEY`  
 Classe de l’objet utilisé comme clé pour la carte.  
  
 `VALUE`  
 Classe de l’objet stocké dans la table.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Obtient l’élément suivant pour l’itération.|  
|[CTypedPtrMap::Lookup](#lookup)|Retourne un `KEY` basé sur un `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|Supprime un élément spécifié par une clé.|  
|[CTypedPtrMap::SetAt](#setat)|Insère un élément dans la carte ; remplace un élément existant si une clé est trouvée.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[[] CTypedPtrMap::operator](#operator_at)|Insère un élément dans le mappage.|  
  
## <a name="remarks"></a>Remarques  
 Lorsque vous utilisez `CTypedPtrMap`, la fonctionnalité de vérification de type C++ permet d’éliminer les erreurs provoquées par des types pointeur ne correspondent pas.  
  
 Étant donné que tous les `CTypedPtrMap` les fonctions inline, utilisation de ce modèle ne pas affecte de manière significative la taille ou la vitesse de votre code.  
  
 Pour plus d’informations sur l’utilisation de `CTypedPtrMap`, consultez les articles [Collections](../../mfc/collections.md) et [Classes basées sur le modèle](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtempl.h  
  
##  <a name="a-namegetnextassoca--ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc  
 Récupère l’élément de la carte à `rNextPosition`, puis met à jour `rNextPosition` pour faire référence à l’élément suivant dans la carte.  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `rPosition`  
 Spécifie une référence à un **POSITION** valeur retournée par une précédente `GetNextAssoc` ou `BASE_CLASS` **:: GetStartPosition** appeler.  
  
 *CLÉ*  
 Paramètre de modèle qui spécifie le type des clés de la carte.  
  
 `rKey`  
 Spécifie la clé de l’élément récupéré retournée.  
  
 *VALEUR*  
 Paramètre de modèle qui spécifie le type des valeurs de la carte.  
  
 `rValue`  
 Spécifie la valeur retournée de l’élément récupéré.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est particulièrement utile pour itérer tous les éléments dans la carte. Notez que la séquence de position n’est pas nécessairement identique à la séquence de la valeur de clé.  
  
 Si l’élément récupéré est le dernier dans le mappage, puis la nouvelle valeur de `rNextPosition` a **NULL**.  
  
 Cette fonction inline s’appelle `BASE_CLASS` **:: GetNextAssoc**.  
  
##  <a name="a-namelookupa--ctypedptrmaplookup"></a><a name="lookup"></a>CTypedPtrMap::Lookup  
 `Lookup`utilise un algorithme de hachage pour trouver rapidement l’élément de carte avec une clé correspondant exactement.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `BASE_CLASS`  
 Paramètre de modèle spécifiant la classe de base de la classe de cette carte.  
  
 `key`  
 La clé de l’élément à rechercher.  
  
 *VALEUR*  
 Paramètre de modèle qui spécifie le type des valeurs stockées dans ce mappage.  
  
 `rValue`  
 Spécifie la valeur retournée de l’élément récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément a été trouvé ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction inline s’appelle `BASE_CLASS` **:: recherche**.  
  
##  <a name="a-nameoperatorata--ctypedptrmapoperator--"></a><a name="operator_at"></a>[] CTypedPtrMap::operator  
 Cet opérateur peut être utilisé uniquement sur le côté gauche d’une instruction d’assignation (une l-value).  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>Paramètres  
 *VALEUR*  
 Paramètre de modèle qui spécifie le type des valeurs stockées dans ce mappage.  
  
 `BASE_CLASS`  
 Paramètre de modèle spécifiant la classe de base de la classe de cette carte.  
  
 `key`  
 La clé de l’élément recherché ou la création de la carte.  
  
### <a name="remarks"></a>Notes  
 S’il n’existe aucun élément de carte avec la clé spécifiée, un nouvel élément est créé. Aucune (valeur r) « droite » n’est équivalent à cet opérateur, car il est possible qu’une clé peut être introuvable dans la carte. Utilisez le `Lookup` fonction membre pour l’extraction de l’élément.  
  
##  <a name="a-nameremovekeya--ctypedptrmapremovekey"></a><a name="removekey"></a>CTypedPtrMap::RemoveKey  
 Cette fonction membre appelle `BASE_CLASS` **:: RemoveKey**.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>Paramètres  
 *CLÉ*  
 Paramètre de modèle qui spécifie le type des clés de la carte.  
  
 `key`  
 Clé de l’élément à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’entrée a été trouvée et supprimée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Pour plus de notes, consultez [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).  
  
##  <a name="a-namesetata--ctypedptrmapsetat"></a><a name="setat"></a>CTypedPtrMap::SetAt  
 Cette fonction membre appelle `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>Paramètres  
 *CLÉ*  
 Paramètre de modèle qui spécifie le type des clés de la carte.  
  
 `key`  
 Spécifie la valeur de clé de le newValue.  
  
 `newValue`  
 Spécifie le pointeur d’objet qui est la valeur du nouvel élément.  
  
### <a name="remarks"></a>Notes  
 Pour plus de notes, consultez [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC COLLECT](../../visual-cpp-samples.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr (classe)](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord (classe)](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr (classe)](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr (classe)](../../mfc/reference/cmapstringtoptr-class.md)

