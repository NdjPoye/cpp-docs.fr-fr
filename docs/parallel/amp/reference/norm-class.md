---
title: Norm, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs: C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 785c214ed904d1591c5d532ec9f09d42c93dc2ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="norm-class"></a>norm, classe
Représente un numéro de la norme. Chaque élément est flottante point nombre dans la plage [-1.0f, 1.0f].  
  
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
|Norm::operator-||  
|Norm::operator--||  
|Norm::operator float|Opérateur de conversion. Convertir le numéro de la norme flottante valeur du point.|  
|Norm::operator * =||  
|/ = Norm::operator||  
|Norm::operator ++||  
|Norm::operator +=||  
|Norm::operator =||  
|Norm::operator =||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `norm`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** amp_short_vectors.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="ctor"></a>norme 

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
 [Concurrency::graphics, espace de noms](concurrency-graphics-namespace.md)
