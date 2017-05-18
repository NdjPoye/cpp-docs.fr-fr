---
title: "Accès à la bibliothèque de type | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries, accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8a3fbcf66036ef3df3bd34b5182dac8af3dfccef
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="type-library-access"></a>Accès à la bibliothèque de types
Bibliothèques de types exposent les interfaces d’un contrôle OLE à d’autres applications prenant en charge OLE. Chaque contrôle OLE doit avoir une bibliothèque de types si une ou plusieurs interfaces doivent être exposées.  
  
 Les macros suivantes permettent un contrôle OLE fournir l’accès à sa propre bibliothèque de types :  
  
### <a name="type-library-access"></a>Accès à la bibliothèque de types  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Déclare un `GetTypeLib` fonction membre d’un contrôle OLE (doit être utilisé dans la déclaration de classe).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implémente une `GetTypeLib` fonction membre d’un contrôle OLE (doit être utilisé dans l’implémentation de classe).|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 Déclare le `GetTypeLib` fonction membre de classe de votre contrôle.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom de la classe de contrôle relatives à la bibliothèque de types.  
  
### <a name="remarks"></a>Notes  
 Utilisez la macro dans le fichier d’en-tête (classe).  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 Implémente le contrôle `GetTypeLib` fonction membre.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>Paramètres  
 *CLASS_NAME*  
 Le nom de la classe de contrôle relatives à la bibliothèque de types.  
  
 *tlid*  
 Le numéro d’ID de la bibliothèque de types.  
  
 `wVerMajor`  
 Le numéro de version principale de bibliothèque de types.  
  
 `wVerMinor`  
 Le numéro de version secondaire de bibliothèque de types.  
  
### <a name="remarks"></a>Remarques  
 Cette macro doit apparaître dans le fichier d’implémentation pour les classes de contrôle qui utilisent le `DECLARE_OLETYPELIB` (macro).  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  
   
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

