---
title: Implémentation de CComObjectRootEx | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CComObjectRootEx
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ae8b8266aca2c9d6099455ddcb7618206dbe8c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-ccomobjectrootex"></a>Implémentation de CComObjectRootEx
[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) est essentiel ; tous les objets ATL doivent avoir une instance du `CComObjectRootEx` ou [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) dans leur héritage. `CComObjectRootEx` fournit le mécanisme `QueryInterface` par défaut en fonction des entrées de la mappe COM.  
  
 Via sa mappe COM, les interfaces d'un objet sont exposées à un client quand celui-ci émet une requête pour une interface. La requête est effectuée via `CComObjectRootEx::InternalQueryInterface`. `InternalQueryInterface` gère seulement des interfaces dans le tableau de mappage COM.  
  
 Vous pouvez entrer des interfaces dans la table de mappage COM avec le [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) (macro) ou une de ses variantes. Par exemple, le code suivant entre les interfaces `IDispatch`, `IBeeper` et `ISupportErrorInfo` dans le tableau de mappage COM :  
  
 [!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Notions de base des objets ATL COM](../atl/fundamentals-of-atl-com-objects.md)   
 [Macros de mappage COM](../atl/reference/com-map-macros.md)

