---
title: Norm, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::norm
dev_langs:
- C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
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
ms.openlocfilehash: 8ff5a99136a75d17d914783496205f1dd1eb4a06
ms.lasthandoff: 02/24/2017

---
# <a name="norm-class"></a>norm, classe
Représente un nombre normales. Chaque élément est flottante point nombre dans la plage [-1.0f, 1.0f].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class norm;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Norm, constructeur](#ctor)|Surchargé. Constructeur par défaut. Initialiser à 0.0f.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|Norm::operator-(opérateur)||  
|Norm::operator--(opérateur)||  
|Norm::operator float (opérateur)|Opérateur de conversion. Convertissez le nombre de norme flottante la valeur de point.|  
|Norm::operator * =, opérateur||  
|Norm::operator / =, opérateur||  
|Norm::operator ++ (opérateur)||  
|Norm::operator +=, opérateur||  
|Norm::operator =, opérateur||  
|Norm::operator-= (opérateur)||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `norm`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_short_vectors.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namectora-norm"></a><a name="ctor"></a>norme 

 Constructeur par défaut. Initialiser à 0.0f.  
  
```  
norm(
    void) restrict(amp,
    cpu);

 
explicit norm(
    float _V) restrict(amp,
    cpu);

 
explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit norm(
    int _V) restrict(amp,
    cpu);

 
explicit norm(
    double _V) restrict(amp,
    cpu);

 
norm(
    const norm& _Other) restrict(amp,
    cpu);

 
norm(
    const unorm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_V`  
 La valeur utilisée pour initialiser.  
  
 `_Other`  
 Objet utilisé pour initialiser.  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

