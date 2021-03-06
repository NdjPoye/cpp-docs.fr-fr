---
title: Classe de CMFCRibbonStatusBar | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0257370e69c5304c4d945087f2a8c5694da4aa03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribbonstatusbar-class"></a>Classe de CMFCRibbonStatusBar
La `CMFCRibbonStatusBar` classe implémente un contrôle de barre d’état qui peut afficher les éléments de ruban.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|Ajoute un élément dynamique à la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::AddElement](#addelement)|Ajoute un nouvel élément de ruban à la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Ajoute un élément de ruban à la zone étendue de la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Ajoute un séparateur à la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::Create](#create)|Crée une barre d’état du ruban.|  
|[CMFCRibbonStatusBar::CreateEx](#createex)|Crée une barre d’état du ruban avec un style étendu.|  
|[CMFCRibbonStatusBar::FindByID](#findbyid)||  
|[CMFCRibbonStatusBar::FindElement](#findelement)|Retourne un pointeur vers l’élément qui possède l’ID de commande spécifiée.|  
|[CMFCRibbonStatusBar::GetCount](#getcount)|Retourne le nombre d’éléments qui se trouvent dans la zone principale de la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::GetElement](#getelement)|Retourne un pointeur vers l’élément qui se trouve à l’index spécifié.|  
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Retourne le nombre d’éléments qui se trouvent dans la zone étendue de la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Retourne un pointeur vers l'élément situé à l'index spécifié dans la zone étendue de la barre d'état du ruban.|  
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCRibbonStatusBar::GetSpace](#getspace)||  
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||  
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||  
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|Détermine si le mode d’informations est activé pour la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Substitue [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|  
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Supprime tous les éléments de la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Supprime l’élément qui a un ID de commande spécifié à partir de la barre d’état du ruban.|  
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Active ou désactive le mode d’informations pour la barre d’état du ruban.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Affiche la chaîne d’informations qui s’affiche sur l’état de ruban barre lorsque le mode d’informations est activé.|  
  
## <a name="remarks"></a>Notes  
 Les utilisateurs peuvent modifier la visibilité des éléments de ruban dans une barre d’état de ruban à l’aide du menu contextuel intégré pour la barre d’état du ruban. Vous pouvez ajouter ou supprimer des éléments de façon dynamique.  
  
 Une barre d’état du ruban comporte deux zones : une zone principale et une zone étendue. La zone étendue s’affiche sur le côté droit de la barre d’état de ruban et s’affiche dans une couleur différente de la zone principale fait.  
  
 En règle générale, la zone principale de la barre d’état affiche les notifications d’état et la zone étendue affiche les contrôles de la vue. La zone étendue reste visible aussi longtemps que possible lorsque l’utilisateur redimensionne la barre d’état du ruban.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes de la `CMFCRibbonStatusBar` classe. L’exemple montre comment ajouter un nouvel élément de ruban à la barre d’état du ruban, ajoutez un élément de ruban à la zone étendue de la barre d’état du ruban, ajoutez un séparateur et activer le mode normal pour la barre d’état du ruban.  
  
 [!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribbonstatusbar.h  
  
##  <a name="adddynamicelement"></a>  CMFCRibbonStatusBar::AddDynamicElement  
 Ajoute un élément dynamique à la barre d’état du ruban.  
  
```  
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pElement`  
 Pointeur vers un élément dynamique.  
  
### <a name="remarks"></a>Notes  
 Contrairement aux éléments régulières, éléments dynamiques ne sont pas personnalisables et le menu de personnaliser la barre d’état n’affiche pas les.  
  
##  <a name="addelement"></a>  CMFCRibbonStatusBar::AddElement  
 Ajoute un nouvel élément de ruban à la barre d’état du ruban.  
  
```  
void AddElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pElement`  
 Pointeur vers l’élément ajouté.  
  
 [in] `lpszLabel`  
 Une étiquette de texte de l’élément.  
  
 [in] `bIsVisible`  
 `TRUE` Si vous souhaitez ajouter l’élément comme visible, `FALSE` si vous souhaitez ajouter l’élément est masqué.  
  
##  <a name="addextendedelement"></a>  CMFCRibbonStatusBar::AddExtendedElement  
 Ajoute un élément de ruban à la zone étendue de la barre d’état du ruban.  
  
```  
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pElement`  
 Pointeur vers l’élément ajouté.  
  
 [in] `lpszLabel`  
 L’étiquette de texte de l’élément.  
  
 [in] `bIsVisible`  
 `TRUE` Si vous souhaitez ajouter l’élément comme visible, `FALSE` si vous souhaitez ajouter l’élément est masqué.  
  
### <a name="remarks"></a>Notes  
 La zone étendue se trouve sur le côté droit du contrôle de barre d'état.  
  
##  <a name="addseparator"></a>  CMFCRibbonStatusBar::AddSeparator  
 Ajoute un séparateur à la barre d’état du ruban.  
  
```  
void AddSeparator();
```  
  
### <a name="remarks"></a>Notes  
 Le framework ajoute un séparateur d’après la méthode [CMFCRibbonStatusBar::AddElement](#addelement). Insère le dernier élément.  
  
##  <a name="create"></a>  CMFCRibbonStatusBar::Create  
 Crée une barre d’état du ruban.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParentWnd`  
 Pointeur vers la fenêtre parente.  
  
 [in] `dwStyle`  
 Combinaison OR logique de styles de contrôle.  
  
 [in] `nID`  
 L’ID de contrôle de la barre d’état.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` Si la barre d’état est créée avec succès, `FALSE` dans le cas contraire.  
  
##  <a name="createex"></a>  CMFCRibbonStatusBar::CreateEx  
 Crée une barre d’état de ruban qui a un style étendu.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle=0,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers la fenêtre parente.  
  
 `dwCtrlStyle`  
 Combinaison OR logique des styles supplémentaires pour la création de l’objet de barre d’état.  
  
 `dwStyle`  
 Le style du contrôle de la barre d’état.  
  
 `nID`  
 L’ID de contrôle de la barre d’état.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` Si la barre d’état est créée avec succès, `FALSE` dans le cas contraire.  
  
##  <a name="findbyid"></a>  CMFCRibbonStatusBar::FindByID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 [in] `BOOL`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="findelement"></a>  CMFCRibbonStatusBar::FindElement  
 Retourne un pointeur vers l’élément qui possède l’ID de commande spécifiée.  
  
```  
CMFCRibbonBaseElement* FindElement(UINT uiID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiID`  
 L’ID de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément qui possède l’ID de commande spécifiée. `NULL` s’il n’existe aucun élément.  
  
##  <a name="getcount"></a>  CMFCRibbonStatusBar::GetCount  
 Retourne le nombre d’éléments qui se trouvent dans la zone principale de la barre d’état du ruban.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments qui se trouvent dans la zone principale de la barre d’état du ruban.  
  
##  <a name="getelement"></a>  CMFCRibbonStatusBar::GetElement  
 Retourne un pointeur vers l’élément qui se trouve à l’index spécifié.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie un index de base zéro d’un élément qui se trouve dans la zone principale du contrôle de barre d’état.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’élément qui se trouve à l’index spécifié. `NULL` Si l’index est un nombre négatif ou est supérieur au nombre d’éléments dans la barre d’état.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getexcount"></a>  CMFCRibbonStatusBar::GetExCount  
 Retourne le nombre d’éléments qui se trouvent dans la zone étendue de la barre d’état du ruban.  
  
```  
int GetExCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments qui se trouvent dans la zone étendue de la barre d’état du ruban.  
  
##  <a name="getexelement"></a>  CMFCRibbonStatusBar::GetExElement  
 Retourne un pointeur vers l'élément situé à l'index spécifié dans la zone étendue de la barre d'état du ruban. La zone étendue se trouve sur le côté droit du contrôle de barre d'état.  
  
```  
CMFCRibbonBaseElement* GetExElement(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l'index de base zéro d'un élément qui se trouve dans la zone étendue du contrôle de barre d'état.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l'élément situé à l'index spécifié dans la zone étendue de la barre d'état du ruban. `NULL` si `nIndex` est négatif ou supérieur au nombre d'éléments dans la zone étendue de la barre d'état du ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getextendedarea"></a>  CMFCRibbonStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rect`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getspace"></a>  CMFCRibbonStatusBar::GetSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSpace() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="isbottomframe"></a>  CMFCRibbonStatusBar::IsBottomFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsBottomFrame() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="isextendedelement"></a>  CMFCRibbonStatusBar::IsExtendedElement  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pElement`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="isinformationmode"></a>  CMFCRibbonStatusBar::IsInformationMode  
 Détermine si le mode d’informations est activé pour la barre d’état du ruban.  
  
```  
BOOL IsInformationMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` Si la barre d’état peut fonctionner en mode d’informations ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 En mode d’informations, la barre d’état masque tous les volets standards et affiche une chaîne de message.  
  
##  <a name="ondrawinformation"></a>  CMFCRibbonStatusBar::OnDrawInformation  
 Affiche la chaîne qui apparaît sur l’état de ruban barre lorsque le mode d’informations est activé.  
  
```  
virtual void OnDrawInformation(
    CDC* pDC,  
    CString& strInfo,  
    CRect rectInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `strInfo`  
 La chaîne d’informations.  
  
 [in] `rectInfo`  
 Rectangle englobant.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode dans une classe dérivée si vous souhaitez personnaliser l’apparence de la chaîne d’informations sur la barre d’état. Utilisez le [CMFCRibbonStatusBar::SetInformation](#setinformation) méthode permettant de placer la barre d’état dans le mode d’informations. Dans ce mode, la barre d’état masque tous les volets et affiche la chaîne d’informations spécifiée par `strInfo`.  
  
##  <a name="recalclayout"></a>  CMFCRibbonStatusBar::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="removeall"></a>  CMFCRibbonStatusBar::RemoveAll  
 Supprime tous les éléments de la barre d’état du ruban.  
  
```  
void RemoveAll();
```  
  
##  <a name="removeelement"></a>  CMFCRibbonStatusBar::RemoveElement  
 Supprime l’élément qui a un ID de commande spécifié à partir de la barre d’état du ruban.  
  
```  
BOOL RemoveElement(UINT uiID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiID`  
 L’ID de l’élément à supprimer de la barre d’état.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` Si un élément avec l’objet `uiID` est supprimé. Sinon, `FALSE`.  
  
##  <a name="setinformation"></a>  CMFCRibbonStatusBar::SetInformation  
 Active ou désactive le mode d’informations pour la barre d’état du ruban.  
  
```  
void SetInformation(LPCTSTR lpszInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszInfo`  
 La chaîne d’informations.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour placer la barre d’état dans le mode d’informations. Dans ce mode, la barre d’état masque tous les volets et affiche la chaîne d’informations spécifiée par `lpszInfo`.  
  
 Lorsque lpszInfo est `NULL`, la barre d’état revienne au mode normal.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)   
 [Classe de CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar, classe](../../mfc/reference/cmfcribbonbar-class.md)
