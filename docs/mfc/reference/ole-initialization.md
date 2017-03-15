---
title: "Initialisation d’OLE | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 5c2d8a1552b8cd546b7e22683fe9f73bbc54df5c
ms.lasthandoff: 02/24/2017

---
# <a name="ole-initialization"></a>Initialisation d'OLE
Qu’une application puisse utiliser les services du système OLE, il doit initialiser les DLL système OLE et vérifiez que les DLL sont la version correcte. Le **AfxOleInit** fonction initialise les DLL système OLE.  
  
### <a name="ole-initialization"></a>Initialisation d'OLE  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|Initialise les bibliothèques OLE.|  
  
##  <a name="a-nameafxoleinita--afxoleinit"></a><a name="afxoleinit"></a>AfxOleInit  
 Initialise la prise en charge OLE pour l’application.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 si l’initialisation échoue, probablement parce que les versions incorrectes des DLL système OLE sont installées.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour initialiser la prise en charge OLE pour une application MFC. Lorsque cette fonction est appelée, les actions suivantes se produisent :  
  
-   Initialise la bibliothèque COM sur le cloisonnement actuel de l’application appelante. Pour plus d’informations, consultez [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Crée un objet de filtre de message, l’implémentation de la [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) interface. Ce filtre de messages est accessible par un appel à [AfxOleGetMessageFilter](http://msdn.microsoft.com/library/36cca011-4775-4086-b471-5557a87b266c).  
  
> [!NOTE]
>  Si **AfxOleInit** est appelée à partir d’une DLL MFC, l’appel échoue. La défaillance se produit car la fonction suppose que, si elle est appelée à partir d’une DLL, le système OLE a été précédemment initialisé par l’application appelante.  
  
> [!NOTE]
>  Les applications MFC doivent être initialisées en tant que thread unique cloisonné (STA). Si vous appelez [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) dans votre `InitInstance` de remplacement, spécifiez `COINIT_APARTMENTTHREADED` (au lieu de `COINIT_MULTITHREADED`). Pour plus d’informations, consultez PRB : Application MFC cesse de répondre lors de l’initialisation de l’Application comme un multithread cloisonné (828643) à [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h

## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

