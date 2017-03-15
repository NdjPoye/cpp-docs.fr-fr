---
title: Classe de CSize | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSize
dev_langs:
- C++
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
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
ms.openlocfilehash: 96905d916dfde8f8a7bf8131a280ae7ccfe511d8
ms.lasthandoff: 02/24/2017

---
# <a name="csize-class"></a>CSize (classe)
Semblable à la structure [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) Windows, qui implémente une coordonnée ou une position relative.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSize::CSize](#csize)|Construit un objet `CSize`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|Soustrait deux tailles.|  
|[CSize::operator ! =](#operator_neq)|Vérifie l’inégalité entre `CSize` et une taille.|  
|[CSize::operator +](#operator_add)|Ajoute deux tailles.|  
|[CSize::operator +=](#operator_add_eq)|Ajoute une taille à `CSize`.|  
|[CSize::operator =](#operator_-_eq)|Soustrait une taille de `CSize`.|  
|[CSize::operator ==](#operator_eq_eq)|Vérifie l’égalité entre `CSize` et une taille.|  
  
## <a name="remarks"></a>Notes  
 Cette classe est dérivée de la **taille** structure. Cela signifie que vous pouvez passer un `CSize` dans un paramètre qui appelle un **taille** et que les membres de données de la **taille** structure sont les membres de données accessibles de `CSize`.  
  
 Le **cx** et **cy** membres de **taille** (et `CSize`) sont publics. En outre, `CSize` implémente les fonctions de membre pour manipuler le **taille** structure.  
  
> [!NOTE]
>  Pour plus d’informations sur partagé classes d’utilitaire (comme `CSize`), consultez [Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltypes.h  
  
##  <a name="a-namecsizea--csizecsize"></a><a name="csize"></a>CSize::CSize  
 Construit un objet `CSize`.  
  
```  
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 *initCX*  
 Définit les **cx** membre pour le `CSize`.  
  
 *initCY*  
 Définit les **cy** membre pour le `CSize`.  
  
 `initSize`  
 [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure ou `CSize` objet utilisé pour initialiser `CSize`.  
  
 `initPt`  
 [POINT de](../../mfc/reference/point-structure1.md) structure ou `CPoint` objet utilisé pour initialiser `CSize`.  
  
 `dwSize`  
 `DWORD`utilisé pour initialiser `CSize`. Le mot de poids faible est le **cx** membre et le mot de poids fort est le **cy** membre.  
  
### <a name="remarks"></a>Remarques  
 Si aucun argument n’est fourni, **cx** et **cy** sont initialisés à zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#97;](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="a-nameoperatoreqeqa--csizeoperator-"></a><a name="operator_eq_eq"></a>CSize::operator ==  
 Vérifie l’égalité entre deux tailles.  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Remarques  
 Retourne zéro si les tailles sont égales, otherwize 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#98;](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="a-nameoperatorneqa--csizeoperator-"></a><a name="operator_neq"></a>CSize::operator ! =  
 Vérifie l’inégalité entre deux tailles.  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Notes  
 Retourne zéro si la taille n’est pas égale, sinon 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#99;](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="a-nameoperatoraddeqa--csizeoperator-"></a><a name="operator_add_eq"></a>CSize::operator +=  
 Ajoute une taille à ce `CSize`.  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[100 NVC_ATLMFC_Utilities](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="a-nameoperator-eqa--csizeoperator--"></a><a name="operator_-_eq"></a>CSize::operator =  
 Soustrait une taille à partir de ce `CSize`.  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#101;](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="a-nameoperatoradda--csizeoperator-"></a><a name="operator_add"></a>CSize::operator +  
 Ces opérateurs ajouter `CSize` valeur à la valeur du paramètre.  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>Remarques  
 Consultez les descriptions de chacun des opérateurs suivantes :  
  
- **opérateur + (** `size` **)**cette opération ajoute deux `CSize` valeurs.  
  
- **opérateur + (** `point` **)**cette opération offsets (déplace) un [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) (ou [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) valeur par ce `CSize` valeur. Le **cx** et **cy** membres de ce `CSize` valeur sont ajoutés à la **x** et **y** les membres de données de la **POINT** valeur. Elle est analogue à la version de [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) qui accepte un [taille](http://msdn.microsoft.com/library/windows/desktop/dd145106) paramètre.  
  
- **opérateur + (** `lpRect` **)**cette opération offsets (déplace) un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (ou [CRect](../../atl-mfc-shared/reference/crect-class.md)) valeur par ce `CSize` valeur. Le **cx** et **cy** membres de ce `CSize` valeur sont ajoutés à la **gauche**, **haut**, **droit**, et **bas** les membres de données de la `RECT` valeur. Elle est analogue à la version de [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) qui accepte un [taille](http://msdn.microsoft.com/library/windows/desktop/dd145106) paramètre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#102;](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="a-nameoperator-a--csizeoperator--"></a><a name="operator_-"></a>CSize::operator-  
 Les trois premiers de ces opérateurs soustraire ce `CSize` valeur à la valeur du paramètre.  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>Notes  
 L’opérateur unaire moins, quatrième modifie le signe de la `CSize` valeur. Consultez les descriptions de chacun des opérateurs suivantes :  
  
- **opérateur-(** `size` **)**cette opération Soustrait deux `CSize` valeurs.  
  
- **opérateur-(** `point` **)**cette opération offsets (déplace) un [POINT](http://msdn.microsoft.com/library/windows/desktop/dd162805) ou [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) valeur par l’inverse additif de ce `CSize` valeur. Le **cx** et **cy** de ce `CSize` valeur sont soustraites de la **x** et **y** les membres de données de la **POINT** valeur. Elle est analogue à la version de [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) qui accepte un [taille](http://msdn.microsoft.com/library/windows/desktop/dd145106) paramètre.  
  
- **opérateur-(** `lpRect` **)**cette opération offsets (déplace) un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) ou [CRect](../../atl-mfc-shared/reference/crect-class.md) valeur par l’inverse additif de ce `CSize` valeur. Le **cx** et **cy** membres de ce `CSize` valeur sont soustraites de la **gauche**, **haut**, **droit**, et **bas** membres de données de la `RECT` valeur. Elle est analogue à la version de [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) qui accepte un [taille](http://msdn.microsoft.com/library/windows/desktop/dd145106) paramètre.  
  
- **opérateur-()**cette opération retourne l’inverse additif de ce `CSize` valeur.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#103;](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MDI](../../visual-cpp-samples.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRect (classe)](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint (classe)](../../atl-mfc-shared/reference/cpoint-class.md)


