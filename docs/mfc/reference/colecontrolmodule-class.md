---
title: Classe de COleControlModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules
- MFC ActiveX controls, OLE control modules
- COleControlModule class
- control modules
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
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
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2e77c386875d25f47f0cc07eb3b7d315f1678c56
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolmodule-class"></a>Classe de COleControlModule
Classe de base à partir de laquelle vous dérivez un objet de module de contrôle OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit des fonctions membres pour initialiser le module de votre contrôle. Chaque module de contrôle OLE qui utilise les classes Microsoft Foundation ne peut contenir un objet dérivé de `COleControlModule`. Cet objet est construit lorsque les autres objets globaux C++ sont construites. Déclarez votre dérivée `COleControlModule` objet au niveau global.  
  
 Pour plus d’informations sur l’utilisation de la `COleControlModule` de classe, consultez la [CWinApp](../../mfc/reference/cwinapp-class.md) classe et l’article [contrôles ActiveX](../../mfc/mfc-activex-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxctl.h  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC TESTHELP](../../visual-cpp-samples.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




