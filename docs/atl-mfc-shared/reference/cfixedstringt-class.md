---
title: CFixedStringT (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f357a70a728b388c3b5d3d26ac4efd0d4c84434a
ms.lasthandoff: 02/24/2017

---
# <a name="cfixedstringt-class"></a>CFixedStringT (classe)
Cette classe représente un objet string avec une mémoire tampon de caractères fixe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>Paramètres  
 `StringType`  
 Utilisé comme classe de base pour l’objet de chaîne fixe et peut être `CStringT`-en fonction du type. Voici quelques exemples : `CString`, `CStringA`, et `CStringW`.  
  
 *t_nChars*  
 Le nombre de caractères stockés dans la mémoire tampon.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Le constructeur de l’objet string.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|Affecte une nouvelle valeur à un `CFixedStringT` objet.|  
  
## <a name="remarks"></a>Notes  
 Cette classe est un exemple d’une classe de chaîne personnalisée basée sur `CStringT`. Bien que très similaire, implémentation diffèrent les deux classes. Principales différences entre `CFixedStringT` et `CStringT` sont :  
  
-   La mémoire tampon de caractère initial est alloué dans le cadre de l’objet et taille *t_nChars*. Cela permet la **CFixedString** objet occupent un bloc contigu de mémoire pour des raisons de performances. Toutefois, si le contenu d’un `CFixedStringT` objet dépasse *t_nChars*, la mémoire tampon est allouée dynamiquement.  
  
-   La mémoire tampon de caractères pour un `CFixedStringT` objet est toujours la même longueur ( *t_nChars*). Il n’existe aucune limitation de taille de mémoire tampon pour `CStringT` objets.  
  
-   Le Gestionnaire de mémoire pour `CFixedStringT` personnalisé tel que le partage d’un [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) objet entre deux ou plusieurs `CFixedStringT` objectsis non autorisé. `CStringT`objets n’ont pas cette limitation.  
  
 Pour plus d’informations sur la personnalisation de `CFixedStringT` et gestion de la mémoire pour les objets string en général, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** cstringt.h  
  
##  <a name="a-namecfixedstringta--cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a>CFixedStringT::CFixedStringT  
 Construit un objet `CFixedStringT`.  
  
```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 Une chaîne terminée par null à copier dans cette `CFixedStringT` objet.  
  
 `str`  
 Existant `CFixedStringT` objet doit être copié dans ce `CFixedStringT` objet.  
  
 `pStringMgr`  
 Un pointeur vers le Gestionnaire de mémoire de le `CFixedStringT` objet. Pour plus d’informations sur `IAtlStringMgr` et gestion de la mémoire pour `CFixedStringT`, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Remarques  
 Étant donné que les constructeurs de copient des données d’entrée dans le nouveau stockage alloué, vous devez être conscient que la mémoire peuvent entraîner des exceptions. Notez que certaines de ces constructeurs agissent comme des fonctions de conversion.  
  
##  <a name="a-nameoperatoreqa--cfixedstringtoperator-"></a><a name="operator__eq"></a>CFixedStringT::operator =  
 Réinitialise un existant `CFixedStringT` objet avec de nouvelles données.  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>Paramètres  
 `str`  
 Une chaîne terminée par null à copier dans cette `CFixedStringT` objet.  
  
 `psz`  
 Existant `CFixedStringT` à copier dans cette `CFixedStringT` objet.  
  
### <a name="remarks"></a>Remarques  
 Vous devez être conscient que les exceptions peuvent se produire lorsque vous utilisez l’opérateur d’assignation, car il est souvent un nouveau stockage est alloué pour contenir résultant de la mémoire `CFixedStringT` objet.  
  
## <a name="see-also"></a>Voir aussi  
 [CStringT (classe)](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)





