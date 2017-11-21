---
title: Classe de CSplitterWndEx | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs: C++
helpviewer_keywords: CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e45a136941ccaf34108085a14ddefb64bcdb3fa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="csplitterwndex-class"></a>Classe de CSplitterWndEx



Représente une fenêtre fractionnée personnalisée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|Constructeur par défaut.|  
|`CSplitterWndEx::~CSplitterWndEx`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Appelé par l’infrastructure pour dessiner une fenêtre fractionnée. (Substitue [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|  
  
## <a name="remarks"></a>Remarques  
 Remplacer la `OnDrawSplitter` méthode pour personnaliser l’apparence des composants de graphiques d’une fenêtre fractionnée.  
  
 Le `CSplitterWndEx` classe est utilisée conjointement avec la [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), et [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) , ces méthodes sont implémentée par un gestionnaire visuel. Pour qu’un gestionnaire visuel dessiner une fenêtre fractionnée dans votre application, remplacez les déclarations de la `CSplitterWnd` classe avec la `CSplitterWndEx` classe. Pour les applications de fenêtre frame, la classe de fenêtre fractionnée est déclarée dans la classe CMainFrame qui se trouve dans mainfrm.h. Pour obtenir un exemple, consultez le `OutlookDemo` présenté dans le répertoire Samples.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter  
 Appelé par l’infrastructure pour dessiner une fenêtre fractionnée.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers le contexte de périphérique. Si ce paramètre est `NULL`, le framework redessine la fenêtre active.  
  
 [in] `nType`  
 Parmi les `CSplitterWnd::ESplitType` des valeurs d’énumération qui spécifie l’élément de la fenêtre fractionnée à dessiner. Les valeurs valides sont `splitBox`, `splitBar`, `splitIntersection` et `splitBorder`.  
  
 [in] `rect`  
 Un rectangle englobant qui spécifie les dimensions et l’emplacement pour dessiner l’élément de fenêtre de fractionnement spécifiée.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../hierarchy-chart.md)   
 [Classes](mfc-classes.md)   
 [Classe de CSplitterWnd](csplitterwnd-class.md)   
 [CMFCVisualManager, classe](cmfcvisualmanager-class.md)