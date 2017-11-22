---
title: "Les API ANSI déconseillées | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC, ANSI deprecated methods
ms.assetid: c7c5a6fd-95e4-4bee-b3d5-d3826c30947d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 185ed8c530f6d18e22fddadaa668e37af66351b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="deprecated-ansi-apis"></a>API ANSI déconseillées
Migration de la bibliothèque Microsoft Foundation classes (MFC) vers les classes et méthodes qui sont basées sur le jeu de caractères Unicode. Par conséquent, les versions ANSI de plusieurs méthodes MFC sont déconseillées. Utilisez les versions Unicode de ces méthodes dans vos applications futures.  
  
 En commençant par les contrôles communs Windows version 6.1, qui est fourni avec [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)], les méthodes ANSI suivantes sont déconseillées.  
  
## <a name="cbutton-class"></a>Classe de CButton  
  
```  
AFX_ANSI_DEPRECATED BOOL GetIdealSize(LPSIZE psize) const;

 
AFX_ANSI_DEPRECATED BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist) const;

 
AFX_ANSI_DEPRECATED BOOL GetTextMargin(LPRECT pmargin) const;

 
AFX_ANSI_DEPRECATED BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);

AFX_ANSI_DEPRECATED BOOL SetTextMargin(LPRECT pmargin);
```  
  
## <a name="ccomboboxex-class"></a>CComboBoxEx (classe)  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="cedit-class"></a>Classe CEdit  
  
```  
AFX_ANSI_DEPRECATED BOOL GetCueBanner(LPWSTR lpszText,
    int cchText) const;

 
AFX_ANSI_DEPRECATED BOOL SetCueBanner(LPCWSTR lpszText,
    BOOL fDrawIfFocused = FALSE);
```  
  
## <a name="clinkctrl-class"></a>Classe de CLinkCtrl  
 L’ensemble de la classe est déconseillée.  
  
## <a name="clistctrl-class"></a>CListCtrl (classe)  
  
```  
AFX_ANSI_DEPRECATED void CancelEditLabel();

AFX_ANSI_DEPRECATED int EnableGroupView(BOOL fEnable);

AFX_ANSI_DEPRECATED int GetGroupInfo(int iGroupId,
    PLVGROUP pgrp) const;

 
AFX_ANSI_DEPRECATED void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;

 
AFX_ANSI_DEPRECATED BOOL GetInsertMark(LPLVINSERTMARK lvim) const;

 
AFX_ANSI_DEPRECATED COLORREF GetInsertMarkColor() const;

 
AFX_ANSI_DEPRECATED int GetInsertMarkRect(LPRECT pRect) const;

 
AFX_ANSI_DEPRECATED COLORREF GetOutlineColor() const;

 
AFX_ANSI_DEPRECATED UINT GetSelectedColumn() const;

 
AFX_ANSI_DEPRECATED BOOL GetTileInfo(PLVTILEINFO pti) const;

 
AFX_ANSI_DEPRECATED BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;

 
AFX_ANSI_DEPRECATED DWORD GetView() const;

 
AFX_ANSI_DEPRECATED BOOL HasGroup(int iGroupId) const;

 
AFX_ANSI_DEPRECATED int InsertGroup(int index,
    PLVGROUP pgrp);

AFX_ANSI_DEPRECATED void InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);

AFX_ANSI_DEPRECATED int InsertMarkHitTest(LPPOINT pPoint,
    LPLVINSERTMARK lvim) const;

 
AFX_ANSI_DEPRECATED BOOL IsGroupViewEnabled() const;

 
AFX_ANSI_DEPRECATED void MoveGroup(int iGroupId,
    int toIndex);

AFX_ANSI_DEPRECATED void MoveItemToGroup(int idItemFrom,
    int idGroupTo);

AFX_ANSI_DEPRECATED void RemoveAllGroups();

AFX_ANSI_DEPRECATED int RemoveGroup(int iGroupId);

AFX_ANSI_DEPRECATED BOOL SetGroupInfo(int iGroupId,
    PLVGROUP pGroup);

AFX_ANSI_DEPRECATED void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);

AFX_ANSI_DEPRECATED BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);

AFX_ANSI_DEPRECATED BOOL SetInsertMark(LPLVINSERTMARK lvim);

AFX_ANSI_DEPRECATED COLORREF SetInsertMarkColor(COLORREF color);

AFX_ANSI_DEPRECATED COLORREF SetOutlineColor(COLORREF color);

AFX_ANSI_DEPRECATED void SetSelectedColumn(int iCol);

AFX_ANSI_DEPRECATED BOOL SetTileInfo(PLVTILEINFO pti);

AFX_ANSI_DEPRECATED BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);

AFX_ANSI_DEPRECATED DWORD SetView(int iView);

AFX_ANSI_DEPRECATED BOOL SortGroups(PFNLVGROUPCOMPARE _pfnGroupCompare,
    LPVOID _plv);
```  
  
## <a name="crebarctrl-class"></a>CReBarCtrl (classe)  
  
```  
AFX_ANSI_DEPRECATED void GetBandMargins(PMARGINS pMargins) const;

 
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="ctoolbarctrl-class"></a>CToolBarCtrl (classe)  
  
```  
AFX_ANSI_DEPRECATED void GetMetrics(LPTBMETRICS ptbm) const;

 
AFX_ANSI_DEPRECATED void SetMetrics(LPTBMETRICS ptbm);

AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="ctooltipctrl-class"></a>CToolTipCtrl (classe)  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
## <a name="see-also"></a>Voir aussi  
 [Configuration requise pour les contrôles communs Windows Vista](../mfc/build-requirements-for-windows-vista-common-controls.md)
