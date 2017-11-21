---
title: Classe de CComObjectRoot | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs: C++
helpviewer_keywords: CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c2dc617eeb58594262ea272a0a4ef7da2865b73f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot (classe)
Ce typedef de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) est mise en modèle sur la valeur par défaut, le modèle du serveur de thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Remarques  
 `CComObjectRoot`est un `typedef` de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) transformer en modèle sur la valeur par défaut, le modèle du serveur de thread. Par conséquent, [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) fait référence soit [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ou [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx`gère la gestion du nombre de référence objet pour les objets brutes et non agrégées et agrégées. Il conserve le décompte de références d’objet si votre objet n’est pas agrégée et maintient le pointeur vers l’inconnu extérieur si votre objet est en cours d’agrégation. Pour les objets agrégées, `CComObjectRootEx` méthodes peuvent être utilisées pour gérer l’échec de l’objet interne pour construire et à protéger l’objet externe d’une suppression lors de la publication des interfaces internes ou de l’objet interne est supprimé.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
## <a name="see-also"></a>Voir aussi  
 [Membres de CComObjectRootEx (classe)](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx (classe)](../../atl/reference/ccomobjectrootex-class.md)   
 [Classe de CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Classe de CComObject](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject (classe)](../../atl/reference/ccompolyobject-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
