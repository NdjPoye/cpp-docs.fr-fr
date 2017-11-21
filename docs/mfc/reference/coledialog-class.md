---
title: Classe de COleDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
dev_langs: C++
helpviewer_keywords: COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ef2efeb94255631a1d6d66d92a7901ae66cb7ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="coledialog-class"></a>Classe de COleDialog
Fournit les fonctionnalités communes aux boîtes de dialogue pour OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDialog::GetLastError](#getlasterror)|Obtient le code d’erreur retourné par la boîte de dialogue.|  
  
## <a name="remarks"></a>Remarques  
 La bibliothèque Microsoft Foundation Class fournit plusieurs classes dérivées de `COleDialog`:  
  
- [Classe COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)  
  
- [Classe COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)  
  
- [Classe COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)  
  
- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
- [Classe COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)  
  
- [Classe COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)  
  
- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)  
  
- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="getlasterror"></a>COleDialog::GetLastError  
 Appelez le `GetLastError` fonction membre pour obtenir des informations d’erreur supplémentaires lorsque `DoModal` retourne **IDABORT**.  
  
```  
UINT GetLastError() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les codes d’erreur retournés par `GetLastError` dépendent de la boîte de dialogue spécifique affichée.  
  
### <a name="remarks"></a>Remarques  
 Consultez le `DoModal` fonction membre dans les classes dérivées pour plus d’informations sur les messages d’erreur spécifiques.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)



