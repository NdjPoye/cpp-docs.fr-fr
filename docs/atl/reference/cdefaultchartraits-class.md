---
title: Classe de CDefaultCharTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATL::CDefaultCharTraits<T>
- ATL.CDefaultCharTraits
- ATL.CDefaultCharTraits<T>
- ATL::CDefaultCharTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 12991cfcf1ac96808a0315899d01ce3012324dc6
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits (classe)
Cette classe fournit deux fonctions statiques pour convertir les caractères entre majuscules et minuscules.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(Statique) Appelez cette fonction pour convertir un caractère en majuscules.|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Statique) Appelez cette fonction pour convertir un caractère en minuscule.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit des fonctions qui sont utilisées par la classe [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="a-namechartolowera--cdefaultchartraitschartolower"></a><a name="chartolower"></a>CDefaultCharTraits::CharToLower  
 Appelez cette fonction pour convertir un caractère en minuscule.  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Caractère à convertir en minuscules.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#132;](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="a-namechartouppera--cdefaultchartraitschartoupper"></a><a name="chartoupper"></a>CDefaultCharTraits::CharToUpper  
 Appelez cette fonction pour convertir un caractère en majuscules.  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Caractère à convertir en majuscules.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

