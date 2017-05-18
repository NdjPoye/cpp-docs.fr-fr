---
title: Classe de scoped_d3d_access_lock | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs:
- C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fd7f377e1dfe4e99f566da4782be5c2ccfdddbff
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock, classe
Wrapper RAII de verrou sur un objet accelerator_view accès D3D.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
class scoped_d3d_access_lock;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[scoped_d3d_access_lock constructeur](#ctor)|Surchargé. Construit un objet `scoped_d3d_access_lock`. Le verrou est libéré lorsque cet objet est hors de portée.|  
|[~ scoped_d3d_access_lock destructeur](#dtor)|Libère le verrou d’accès D3D sur associé `accelerator_view` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator=](#operator_eq)|Prend possession d’un verrou d’un autre `scoped_d3d_access_lock`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `scoped_d3d_access_lock`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Namespace :** concurrency::direct3d  

##  <a name="ctor"></a>scoped_d3d_access_lock 

 Construit un objet `scoped_d3d_access_lock`. Le verrou est libéré lorsque cet objet est hors de portée.  
 
```  
explicit scoped_d3d_access_lock(// [1] constructor  
    accelerator_view& _Av);

 
explicit scoped_d3d_access_lock(// [2] constructor  
    accelerator_view& _Av,  
    adopt_d3d_access_lock_t _T);

 
scoped_d3d_access_lock(// [3] move constructor  
    scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Av`  
 Le `accelerator_view` d’adopter le verrou.  
  
 `_T`  
 Objet `adopt_d3d_access_lock_t`.  
  
 `_Other`  
 Le `scoped_d3d_access_lock` objet à partir duquel déplacer un verrou existant.  
  
## <a name="construction"></a>Construction  
 [1] constructeur  
 Acquiert un verrou d’accès D3D sur la donnée [accelerator_view](accelerator-view-class.md) objet. Blocs de construction jusqu'à ce que le verrou est acquis.  
  
 [2] constructeur  
 Adopter un verrou d’accès D3D à partir de la donnée [accelerator_view](accelerator-view-class.md) objet.  
  
 [3] constructeur de déplacement  
 Prend un verrou d’accès D3D existant d’une autre `scoped_d3d_access_lock` objet. Construction ne bloque pas.  

  
##  <a name="dtor"></a>~ scoped_d3d_access_lock 

 Libère le verrou d’accès D3D sur associé `accelerator_view` objet.  
  
```  
~scoped_d3d_access_lock();
```  
## <a name="operator_eq"></a>opérateur = 

Prend possession d’un verrou d’accès D3D d’une autre `scoped_d3d_access_lock` objet libérer le verrou précédent.  
 
```  
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Accelerator_view depuis lequel déplacer le verrou d’accès D3D.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `scoped_accelerator_view_lock`.  

## <a name="see-also"></a>Voir aussi  
 [Concurrency::direct3d, espace de noms](concurrency-direct3d-namespace.md)

