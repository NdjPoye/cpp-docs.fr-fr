---
title: Classe de CUserException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4613f2ba06ffa697df219172b98a5cf193c1f3b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cuserexception-class"></a>Classe de CUserException
Levée pour arrêter une opération d'utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>Notes  
 Utilisez `CUserException` lorsque vous souhaitez utiliser le mécanisme d’exception throw/catch pour les exceptions spécifiques à l’application. « Utilisateur » dans le nom de classe peut être interprété comme « mon utilisateur a rencontré une erreur exceptionnelles que vous avez besoin gérer. »  
  
 A `CUserException` est généralement levée après l’appel de la fonction globale `AfxMessageBox` pour informer l’utilisateur qui a une opération a échoué. Lorsque vous écrivez un gestionnaire d’exceptions, gérer l’exception spécialement étant donné que l’utilisateur généralement a déjà été notifié de l’échec. Le framework lève cette exception dans certains cas. Pour lever une `CUserException` vous-même, l’utilisateur d’alerte et ensuite appeler la fonction globale `AfxThrowUserException`.  
  
 Dans l’exemple ci-dessous, une fonction contenant des opérations qui peuvent ne pas avertir l’utilisateur et lève un `CUserException`. La fonction appelante intercepte l’exception et il traite :  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 Pour plus d’informations sur l’utilisation de `CUserException`, consultez l’article [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CException, classe](../../mfc/reference/cexception-class.md)
