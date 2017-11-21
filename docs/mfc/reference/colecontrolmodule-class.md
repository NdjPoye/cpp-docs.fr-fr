---
title: Classe de COleControlModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: OleControlModule
dev_langs: C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0153adbae458d0f4ab432c2c7cb8c71621d76418
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="colecontrolmodule-class"></a>Classe de COleControlModule
Classe de base à partir de laquelle vous dérivez un objet de module de contrôle OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit des fonctions membres pour l’initialisation du module de votre contrôle. Chaque module de contrôle OLE qui utilise les classes Microsoft Foundation ne peut contenir un objet dérivé de `COleControlModule`. Cet objet est construit lors de l’établissement d’autres objets globaux de C++. Déclarez votre dérivée `COleControlModule` objet au niveau global.  
  
 Pour plus d’informations sur l’utilisation de la `COleControlModule` de classe, consultez la [CWinApp](../../mfc/reference/cwinapp-class.md) classe et l’article [contrôles ActiveX](../../mfc/mfc-activex-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxctl.h  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC TESTHELP](../../visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)



