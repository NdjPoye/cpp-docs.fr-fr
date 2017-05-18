---
title: CComObjectRoot (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31295a07704e272799398aa82c6a9f0bbac17717
ms.openlocfilehash: 34653d55091a8e872f075010a0ef7cecbb3484c8
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectroot-class"></a>CComObjectRoot (classe)
Ce typedef de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) est mise en modèle sur le modèle du serveur de thread par défaut.  
  
## <a name="syntax"></a>Syntaxe  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Remarques  
 `CComObjectRoot`est un `typedef` de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) mise en modèle sur le modèle du serveur de thread par défaut. Par conséquent [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) fait référence soit [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ou [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx`gère la gestion du nombre de référence objet pour les objets non regroupées en agrégats et agrégées. Il contient le nombre de références d’objet si votre objet n’est pas agrégée et maintient le pointeur vers l’inconnu extérieur si votre objet est en cours d’agrégation. Pour les objets agrégées, `CComObjectRootEx` méthodes peuvent être utilisées en cas d’échec de l’objet interne à construire et à protéger l’objet externe d’une suppression lors de la publication des interfaces internes ou de l’objet interne est supprimé.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
## <a name="see-also"></a>Voir aussi  
 [Membres de CComObjectRootEx (classe)](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx (classe)](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject (classe)](../../atl/reference/ccomaggobject-class.md)   
 [Classe de CComObject](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject (classe)](../../atl/reference/ccompolyobject-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

