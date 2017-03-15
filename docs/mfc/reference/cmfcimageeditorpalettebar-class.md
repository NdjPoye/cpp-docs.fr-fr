---
title: Classe de CMFCImageEditorPaletteBar | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorPaletteBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorPaletteBar class
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f6b987a27b43d713835a71dd5c31587020f23f2f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar (classe)
Fournit des fonctionnalités à une image de boîte de dialogue Éditeur de la barre de palette.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|Retourne la hauteur des boutons de barre d’outils. (Substitue [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Détermine si la barre d’outils peut afficher des boutons que vous avez étendu les bordures. (Substitue [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
  
### <a name="remarks"></a>Remarques  
 Cette classe n’est pas destinée à être utilisée directement à partir de votre code.  
  
 L’infrastructure utilise cette classe pour afficher une barre de palette dans une boîte de dialogue Éditeur image. Pour plus d’informations sur la boîte de dialogue Éditeur image, consultez [CMFCImageEditorDialog classe](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afximageeditordialog.h  
  
##  <a name="a-namegetrowheighta--cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a>CMFCImageEditorPaletteBar::GetRowHeight  
 Retourne la hauteur des boutons de barre d’outils.  
  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur de chaque bouton de la barre d’outils.  
  
##  <a name="a-nameisbuttonextrasizeavailablea--cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable  
 Détermine si la barre d’outils peut afficher des boutons que vous avez étendu les bordures.  
  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne `FALSE`.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe de CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

