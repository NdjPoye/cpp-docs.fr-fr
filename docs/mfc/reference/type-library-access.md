---
title: "Type d’accès à la bibliothèque | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbc5ceabe60d7ee15d85495bb1a431955a589849
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="type-library-access"></a>Accès à la bibliothèque de types
Bibliothèques de types exposent les interfaces d’un contrôle OLE à d’autres applications prenant en charge OLE. Chaque contrôle OLE doit avoir une bibliothèque de types si une ou plusieurs interfaces doivent être exposées.  
  
 Les macros suivantes permettent un contrôle OLE fournir l’accès à sa propre bibliothèque de types :  
  
### <a name="type-library-access"></a>Accès à la bibliothèque de types  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Déclare un `GetTypeLib` fonction membre d’un contrôle OLE (doit être utilisé dans la déclaration de classe).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implémente un `GetTypeLib` fonction membre d’un contrôle OLE (doit être utilisé dans l’implémentation de classe).|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 Déclare le `GetTypeLib` fonction membre de classe de votre contrôle.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom de la classe du contrôle lié à la bibliothèque de types.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette macro dans le fichier d’en-tête de classe contrôle.  

### <a name="requirements"></a>Configuration requise  
 **En-tête :** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 Implémente le contrôle `GetTypeLib` fonction membre.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom de la classe du contrôle lié à la bibliothèque de types.  
  
 *tlid*  
 Le numéro d’ID de la bibliothèque de types.  
  
 `wVerMajor`  
 Numéro de version principale de la bibliothèque de types.  
  
 `wVerMinor`  
 Numéro de version mineure de la bibliothèque de types.  
  
### <a name="remarks"></a>Notes  
 Cette macro doit apparaître dans le fichier d’implémentation pour les classes de contrôle qui utilisent le `DECLARE_OLETYPELIB` (macro).  

### <a name="requirements"></a>Configuration requise  
 **En-tête :** afxdisp.h  
   
## <a name="see-also"></a>Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
