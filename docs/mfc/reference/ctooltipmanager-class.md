---
title: Classe de CTooltipManager | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager class
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 3bbf191aacdd318f2afb0bd1a126c3eff290fad6
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipmanager-class"></a>CTooltipManager (classe)
Gère les informations d'exécution relatives aux info-bulles. La classe `CTooltipManager` est instanciée une fois par application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|Crée un contrôle d'info-bulle pour les types de contrôles Windows spécifiés.|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Supprime un contrôle d'info-bulle.|  
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Personnalise l'apparence visuelle du contrôle d'info-bulle pour les types de contrôles Windows spécifiés.|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|Définit le texte et la description d'un contrôle d'info-bulle.|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>Remarques  
 Utilisez [CMFCToolTipCtrl classe](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, et `CTooltipManager` pour implémenter des info-bulles personnalisées dans votre application. Pour obtenir un exemple d’utilisation de ces classes d’info-bulle, consultez le [CMFCToolTipCtrl classe](../../mfc/reference/cmfctooltipctrl-class.md) rubrique.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtooltipmanager.h  
  
##  <a name="createtooltip"></a>CTooltipManager::CreateToolTip  
 Crée un contrôle d’info-bulle.  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `pToolTip`  
 Une référence à un pointeur d’info-bulle. Il est configuré pour pointer vers l’info-bulle qui vient d’être créée lorsque la fonction retourne une valeur.  
  
 [in] `pWndParent`  
 Parent de l’info-bulle.  
  
 [in] `nType`  
 Type de l’info-bulle.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si une info-bulle a été créé avec succès.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [CTooltipManager::DeleteToolTip](#deletetooltip) pour supprimer le contrôle d’info-bulle qui a été renvoyé dans `pToolTip`.  
  
 Le [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) définit les paramètres d’affichage de chaque info-bulle, il crée en fonction de l’info-bulle de type qui `nType` spécifie. Pour modifier les paramètres pour un ou plusieurs types d’info-bulle, appelez [CTooltipManager::SetTooltipParams](#settooltipparams).  
  
 Types d’info-bulle valides sont répertoriés dans le tableau suivant :  
  
|Type de l’info-bulle|Catégorie de contrôle|Exemples de types|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|Un bouton.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Une barre de légende.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|Tous les contrôles qui ne tient pas dans une autre catégorie.|Aucun|  
|AFX_TOOLTIP_TYPE_DOCKBAR|Un volet Ancrable.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|Une zone de texte.|Aucun|  
|AFX_TOOLTIP_TYPE_MINIFRAME|Un mini-frame.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|Un planificateur.|Aucun|  
|AFX_TOOLTIP_TYPE_RIBBON|Une barre de ruban.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|Un contrôle onglet.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|Une barre d’outils.|CMFCToolBar, CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|Une boîte à outils.|Aucun.|  
  
##  <a name="deletetooltip"></a>CTooltipManager::DeleteToolTip  
 Supprime un contrôle d'info-bulle.  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `pToolTip`  
 Une référence à un pointeur vers une info-bulle à détruire.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour chaque [CToolTipCtrl (classe)](../../mfc/reference/ctooltipctrl-class.md) qui a été créé par [CTooltipManager::CreateToolTip](#createtooltip). Le contrôle parent doit appeler cette méthode à partir de son `OnDestroy` gestionnaire. Cela est nécessaire pour supprimer correctement l’info-bulle du framework. Cette méthode définit `pToolTip` à `NULL` avant d’être retournée.  
  
##  <a name="settooltipparams"></a>CTooltipManager::SetTooltipParams  
 Personnalise l’apparence du contrôle d’info-bulle pour les types de contrôle Windows spécifiés.  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nTypes`  
 Spécifie les types de contrôle.  
  
 [in] `pRTC`  
 Classe d’exécution de l’info-bulle personnalisée.  
  
 [in] `pParams`  
 Paramètres de l’info-bulle.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode définit la classe d’exécution et les paramètres initiaux qui le [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) utilise lorsqu’il crée des info-bulles. Lorsqu’un contrôle appelle [CTooltipManager::CreateToolTip](#createtooltip) et passe dans une info-bulle type qui est un des types indiqués par `nTypes`, le Gestionnaire d’info-bulle crée un contrôle d’info-bulle qui est une instance de la classe d’exécution spécifiée par `pRTC` et passe les paramètres spécifiés par `pParams` à la nouvelle info-bulle.  
  
 Lorsque vous appelez cette méthode, tous les propriétaires d’info-bulle existant reçoivent le message AFX_WM_UPDATETOOLTIPS et ils devront recréer leurs info-bulles à l’aide de [CTooltipManager::CreateToolTip](#createtooltip).  
  
 `nTypes`peut être n’importe quelle combinaison de l’info-bulle valide types [CTooltipManager::CreateToolTip](#createtooltip) utilise, ou il peut être AFX_TOOLTIP_TYPE_ALL. Si vous transmettez AFX_TOOLTIP_TYPE_ALL, tous les types d’info-bulle sont affectées.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `SetTooltipParams` procédé de la `CTooltipManager` classe. Cet extrait de code fait partie de la [Client dessiner, exemple](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&#11;](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="settooltiptext"></a>CTooltipManager::SetTooltipText  
 Définit le texte et la description d’une info-bulle.  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pTI`  
 Pointeur vers un objet TOOLINFO.  
  
 [in, out] `pToolTip`  
 Pointeur vers le contrôle d’info-bulle pour lequel définir le texte et la description.  
  
 [in] `nType`  
 Spécifie le type de contrôle auquel cette info-bulle est associée.  
  
 [in] `strText`  
 Le texte pour définir le texte d’info-bulle.  
  
 [in] `lpszDescr`  
 Pointeur vers la description de l’info-bulle. Peut être `NULL`.  
  
### <a name="remarks"></a>Remarques  
 La valeur de `nType` doit être la même valeur que la `nType` paramètre de [CTooltipManager::CreateToolTip](#createtooltip) lors de la création de l’info-bulle.  
  
##  <a name="updatetooltips"></a>CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl (classe)](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo (classe)](../../mfc/reference/cmfctooltipinfo-class.md)

