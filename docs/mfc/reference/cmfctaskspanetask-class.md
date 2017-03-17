---
title: Classe de CMFCTasksPaneTask | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTask class
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
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
ms.openlocfilehash: 20713b45c4b6aadc5cdfeaadb6ed269aaf7b337f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask (classe)
Le `CMFCTasksPaneTask` classe est une classe d’assistance qui représente des tâches pour le contrôle de volet Office ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). L’objet de tâche représente un élément dans le groupe de tâches ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Chaque tâche peut avoir une commande exécutée par l’infrastructure lorsqu’un utilisateur clique sur la tâche et une icône qui apparaît à gauche du nom de la tâche.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Crée et initialise un `CMFCTasksPaneTask` objet.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Détermine les données d’accessibilité pour la tâche actuelle.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Détermine si la fenêtre de la tâche est automatiquement détruite.|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Détermine si l’infrastructure Dessine une étiquette de la tâche en gras.|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Contient des données définies par l’utilisateur, le framework associe à la tâche. La valeur zéro si la tâche n’a pas de données.|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Handle vers la fenêtre des tâches.|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Index dans la liste d’images de l’image de l’infrastructure s’affiche en regard de la tâche.|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|La hauteur de la fenêtre des tâches. Si la tâche a aucune fenêtre de tâche, cette valeur est zéro.|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Un pointeur vers le `CMFCTasksPaneTaskGroup` appartenant à cette tâche.|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|Spécifie le rectangle englobant de la tâche.|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|Le nom de la tâche.|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Spécifie l’ID de commande de la commande exécutée par l’infrastructure lorsque l’utilisateur clique sur la tâche. Si cette valeur n’est pas un ID de commande valide, la tâche est traitée comme une simple étiquette.|  
  
## <a name="remarks"></a>Remarques  
 L’illustration suivante montre un groupe de tâches contenant trois tâches :  
  
 ![Groupe de tâches, développé](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
> [!NOTE]
>  Si une tâche n’a pas d’ID de commande valides, il est traité comme une simple étiquette.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxTasksPane.h  
  
##  <a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask  
 Crée et initialise un `CMFCTasksPaneTask` objet.  
  
```  
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,  
    LPCTSTR lpszName,  
    int nIcon,  
    UINT uiCommandID,  
    DWORD dwUserData = 0,  
    HWND hwndTask = NULL,  
    BOOL bAutoDestroyWindow = FALSE,  
    int nWindowHeight = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `pGroup`  
 Spécifie le [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) auquel appartient la tâche.  
  
 `lpszName`  
 Spécifie le nom de la tâche.  
  
 `nIcon`  
 Spécifie l’index d’image de la tâche dans la liste d’images.  
  
 `uiCommandID`  
 Spécifie l’ID de commande de la commande est exécutée lorsque vous cliquez sur la tâche.  
  
 `dwUserData`  
 Données définies par l’utilisateur.  
  
 `hwndTask`  
 Spécifie le handle vers la fenêtre des tâches.  
  
 `bAutoDestroyWindow`  
 Si `TRUE`, sera détruite automatiquement la fenêtre des tâches.  
  
 `nWindowHeight`  
 Spécifie la hauteur de la fenêtre de la tâche.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow  
 Détermine si la fenêtre de la tâche est automatiquement détruite.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>Notes  
 La valeur `TRUE` pour spécifier que la fenêtre des tâches ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) doit être détruit automatiquement ; sinon, `FALSE`.  
  
##  <a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold  
 Détermine si une étiquette de tâche est dessinée dans le texte en gras.  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez ce membre sur `TRUE` pour afficher le texte en gras pour l’étiquette de la tâche.  
  
##  <a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData  
 Contient des données définies par l’utilisateur qui sont associées à la tâche. La valeur zéro si aucune donnée n’est associée à la tâche.  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask  
 Handle vers la fenêtre des tâches.  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>Notes  
 Pour ajouter une fenêtre de tâche, appelez [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).  
  
##  <a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon  
 Position d’index dans une liste d’images qui identifie une image qui s’affiche en regard de la tâche spécifiée.  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>Notes  
 La liste d’images est définie par [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).  
  
 Définissez `m_nIcon` -1 si vous souhaitez afficher la tâche sans image.  
  
##  <a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight  
 La hauteur de la fenêtre des tâches. Si la tâche a aucune fenêtre de tâche, cette valeur est zéro.  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup  
 Pointeur vers le [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) à laquelle appartient cette tâche.  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>Remarques  
 Chaque tâche doit posséder un groupe parent. Vous ajoutez des groupes à un volet Office en appelant [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_rect"></a>CMFCTasksPaneTask::m_rect  
 Spécifie le rectangle englobant de la tâche.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette valeur est calculée par l’infrastructure lorsque la tâche est dessinée.  
  
##  <a name="m_strname"></a>CMFCTasksPaneTask::m_strName  
 Le nom de la tâche.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID  
 Spécifie l’ID de commande de la commande est exécutée lorsque l’utilisateur clique sur la tâche. Si cette valeur n’est pas un ID de commande valide, la tâche est traitée comme une simple étiquette.  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData  
 Détermine les données d’accessibilité pour la tâche actuelle.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParent`  
 Représente la fenêtre parente de la tâche en cours.  
  
 [out] `data`  
 Un objet de type `CAccessibilityData` qui est rempli avec les données d’accessibilité de la tâche en cours.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le `data` paramètre a été remplie avec les données d’accessibilité de la tâche en cours ; sinon, `FALSE`.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject (classe)](../../mfc/reference/cobject-class.md)

