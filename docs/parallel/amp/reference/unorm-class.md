---
title: unorm, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm
- amp/Concurrency::graphics::unorm
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: aae5de80bed3b2d3d5c15285c2d12f2f6771a251
ms.lasthandoff: 02/24/2017

---
# <a name="unorm-class"></a>unorm, classe
Représente un nombre unorm. Chaque élément est flottante point nombre dans la plage [0.0f, 1.0f].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class unorm;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[unorm, constructeur](#ctor)|Surchargé. Constructeur par défaut. Initialiser à 0.0f.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|unorm::operator--(opérateur)||  
|unorm::operator float (opérateur)|Opérateur de conversion. Convertissez le nombre d’unorm flottante la valeur de point.|  
|unorm::operator * =, opérateur||  
|unorm::operator / =, opérateur||  
|unorm::operator ++ (opérateur)||  
|unorm::operator +=, opérateur||  
|unorm::operator =, opérateur||  
|unorm::operator-= (opérateur)||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `unorm`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_short_vectors.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namectora-unorm"></a><a name="ctor"></a>unorm 

 Constructeur par défaut. Initialiser à 0.0f.  
  
```  
unorm(
    void) restrict(amp,
    cpu);

 
explicit unorm(
    float _V) restrict(amp,
    cpu);

 
explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit unorm(
    int _V) restrict(amp,
    cpu);

 
explicit unorm(
    double _V) restrict(amp,
    cpu);

 
unorm(
    const unorm& _Other) restrict(amp,
    cpu);

 
inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_V`  
 La valeur utilisée pour initialiser.  
  
 `_Other`  
 L’objet de la norme utilisée pour initialiser.  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

