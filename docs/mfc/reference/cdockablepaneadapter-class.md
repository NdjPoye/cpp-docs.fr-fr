---
title: Classe de CDockablePaneAdapter | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter class
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
caps.latest.revision: 22
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
ms.openlocfilehash: 05d34e3ec84db48e50328b99c38abf1ef73747b4
ms.lasthandoff: 02/24/2017

---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter (classe)
Fournit la prise en charge de l'ancrage pour les volets dérivés de `CWnd`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Retourne la fenêtre incluse dans un wrapper.|  
|[CDockablePaneAdapter::LoadState](#loadstate)|(Substitue [CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917).)|  
|[CDockablePaneAdapter::SaveState](#savestate)|(Substitue [CDockablePane::SaveState](http://msdn.microsoft.com/en-us/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).)|  
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||  
  
## <a name="remarks"></a>Remarques  
 En règle générale, le framework instancie les objets de cette classe lorsque vous utilisez la [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) ou [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) méthodes.  
  
 Si vous souhaitez personnaliser le `CDockablePaneAdapter` comportement, simplement dériver une nouvelle classe à partir de celui-ci et définir les informations de classe d’exécution dans une fenêtre à onglets à l’aide de [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxDockablePaneAdapter.h  
  
##  <a name="a-namegetwrappedwnda--cdockablepaneadaptergetwrappedwnd"></a><a name="getwrappedwnd"></a>CDockablePaneAdapter::GetWrappedWnd  
 Retourne la fenêtre sous-jacente de l’adaptateur de volet Ancrable.  
  
```  
virtual CWnd* GetWrappedWnd() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la fenêtre encapsulée.  
  
### <a name="remarks"></a>Notes  
 Cette fonction permet d’accéder à la fenêtre encapsulée.  
  
##  <a name="a-nameloadstatea--cdockablepaneadapterloadstate"></a><a name="loadstate"></a>CDockablePaneAdapter::LoadState  
 Charge l’état du volet à partir du Registre.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Nom du profil.  
  
 [in] `nIndex`  
 L’index du profil.  
  
 [in] `uiID`  
 L’ID du volet.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesavestatea--cdockablepaneadaptersavestate"></a><a name="savestate"></a>CDockablePaneAdapter::SaveState  
 Enregistre l’état du volet dans le Registre.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Nom du profil.  
  
 [in] `nIndex`  
 L’index de profil (l’ID de contrôle de la fenêtre par défaut).  
  
 [in] `uiID`  
 L’ID du volet.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetwrappedwnda--cdockablepaneadaptersetwrappedwnd"></a><a name="setwrappedwnd"></a>CDockablePaneAdapter::SetWrappedWnd  
 Définit la fenêtre sous-jacente de l’adaptateur de volet Ancrable.  
  
```  
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Pointeur vers la fenêtre de l’adaptateur de volet à encapsuler.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockablePane (classe)](../../mfc/reference/cdockablepane-class.md)

