---
title: Macros de mappage COM | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs: C++
helpviewer_keywords: COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e97db324dc8e130418419ef435e2665c84eb0b64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="com-map-macros"></a>Macros de mappage COM
Ces macros définissent des tables d’interface COM.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Marque le début des entrées de mappage d’interface COM.|  
|[END_COM_MAP](#end_com_map)|Marque la fin des entrées de mappage d’interface COM.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
   
##  <a name="begin_com_map"></a>BEGIN_COM_MAP  
 Le mappage COM est un mécanisme qui expose des interfaces sur un objet à un client via `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de l’objet de classe que vous exposez des interfaces sur.  
  
### <a name="remarks"></a>Notes  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) renvoie uniquement les pointeurs des interfaces dans le mappage COM. Démarrer votre carte d’interface avec le `BEGIN_COM_MAP` (macro), ajouter des entrées pour chacun de vos interfaces avec la [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) (macro) ou une de ses variantes et effectuer un mappage avec le [END_COM_MAP](#end_com_map) (macro).  

  
### <a name="example"></a>Exemple  
 À partir de la bibliothèque ATL [BEEPER](../../visual-cpp-samples.md) exemple :  
  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>END_COM_MAP  
 Met fin à la définition de votre mappage d’interface COM.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)   
 [Fonctions globales de mappage COM](../../atl/reference/com-map-global-functions.md)
