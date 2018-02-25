---
title: CBookmark, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
dev_langs:
- C++
helpviewer_keywords:
- CBookmark class
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b5c0f5f7a2af7c5b744fcad31ae6901988e92b9e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cbookmark-class"></a>CBookmark, classe
Contient une valeur de signet dans sa mémoire tampon.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase
  
template <>  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nSize`  
 La taille de la mémoire tampon du signet en octets. Lorsque `nSize` est égal à zéro, la mémoire tampon de signet sera créée dynamiquement au moment de l’exécution.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|Le constructeur|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|Récupère le pointeur vers la mémoire tampon.|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|Récupère la taille de la mémoire tampon en octets.|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|Définit la valeur du signet.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator =](../../data/oledb/cbookmark-operator-equal.md)|Assigne un `CBookmark` classe vers un autre.|  
  
## <a name="remarks"></a>Notes  
 **CBookmark\<0 >** est une spécialisation de modèle de `CBookmark`; sa mémoire tampon est créé dynamiquement au moment de l’exécution.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)