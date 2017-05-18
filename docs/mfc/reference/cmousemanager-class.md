---
title: Classe de CMouseManager | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
dev_langs:
- C++
helpviewer_keywords:
- CMouseManager class
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7ba50f976f6cf9d6b701e39304c50507cfa34cc5
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmousemanager-class"></a>CMouseManager (classe)
Autorise un utilisateur à associer différentes commandes à un rôle particulier [CView](../../mfc/reference/cview-class.md) de l’objet lorsque l’utilisateur double-clique dans cette vue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|Ajoute un `CView` de l’objet à le **personnalisation** boîte de dialogue. Le **personnalisation** boîte de dialogue permet à l’utilisateur à associer un double-clic à une commande pour chacune des vues répertoriées.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Retourne la commande est exécutée lorsque l’utilisateur double-clique dans la vue fournie.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|Retourne l’icône associée à l’ID de la vue fournis.|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Retourne l’ID de la vue associée au nom de la vue fournis.|  
|[CMouseManager::GetViewNames](#getviewnames)|Récupère une liste de tous les noms d’affichage ajouté.|  
|[CMouseManager::LoadState](#loadstate)|Charge le `CMouseManager` l’état à partir du Registre Windows.|  
|[CMouseManager::SaveState](#savestate)|Écrit la `CMouseManager` état dans le Registre Windows.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Associe la commande fournie et la vue fournie.|  
  
## <a name="remarks"></a>Notes  
 Le `CMouseManager` classe maintient une collection de `CView` objets. Chaque vue est identifié par un nom et par un code. Ces vues sont affichés dans le **personnalisation** boîte de dialogue. L’utilisateur peut modifier la commande associée à n’importe quelle vue via la **personnalisation** boîte de dialogue. La commande associée est exécutée lorsque l’utilisateur double-clique dans cette vue. Pour prendre en charge ce point de vue de codage, vous devez traiter le `WM_LBUTTONDBLCLK` message et appeler le [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) fonction dans le code correspondant `CView` objet...  
  
 Vous ne devez pas créer un `CMouseManager` de l’objet manuellement. Il sera créé par l’infrastructure de votre application. Il sera également détruit automatiquement lorsque l’utilisateur quitte l’application. Pour obtenir un pointeur vers le Gestionnaire de souris pour votre application, appelez [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmousemanager.h  
  
##  <a name="addview"></a>CMouseManager::AddView  
 Inscrit un [CView](../../mfc/reference/cview-class.md) de l’objet avec la [CMouseManager classe](../../mfc/reference/cmousemanager-class.md) pour prendre en charge le comportement de la souris personnalisé.  
  
```  
BOOL AddView(
    int iViewId,  
    UINT uiViewNameResId,  
    UINT uiIconId = 0);

 
BOOL AddView(
    int iId,  
    LPCTSTR lpszViewName,  
    UINT uiIconId = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iViewId`  
 Un ID de la vue.  
  
 [in] `uiViewNameResId`  
 Un ID de chaîne de ressource qui référence le nom de la vue.  
  
 [in] `uiIconId`  
 Un ID d’icône de vue.  
  
 [in] `iId`  
 Un ID de la vue.  
  
 [in] `lpszViewName`  
 Un nom de la vue.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Pour prendre en charge du comportement personnalisé de la souris, une vue doit être enregistrée avec le `CMouseManager` objet. N’importe quel objet dérivé de la `CView` classe peut être enregistrée avec le Gestionnaire de la souris. La chaîne et l’icône associée à une vue s’affichent dans le **souris** onglet de la **personnaliser** boîte de dialogue.  
  
 Il incombe au programmeur de créer et gérer des ID d’affichage telles que `iViewId` et `iId`.  
  
 Pour plus d’informations sur la façon de fournir un comportement personnalisé de la souris, consultez [personnalisation du clavier et souris](../../mfc/keyboard-and-mouse-customization.md).  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment récupérer un pointeur vers un `CMouseManager` à l’aide de la `CWinAppEx::GetMouseManager` (méthode) et le `AddView` méthode dans la `CMouseManager` classe. Cet extrait de code fait partie de la [échantillon de collecte de l’état](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection n °&4;](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>CMouseManager::GetViewDblClickCommand  
 Retourne la commande est exécutée lorsque l’utilisateur double-clique dans la vue fournie.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iId`  
 L’ID de la vue.  
  
### <a name="return-value"></a>Valeur de retour  
 L’identificateur de commande si la vue est associée à une commande ; sinon 0.  
  
##  <a name="getviewiconid"></a>CMouseManager::GetViewIconId  
 Récupère l’icône associée à un ID de la vue.  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iViewId`  
 L’ID de la vue.  
  
### <a name="return-value"></a>Valeur de retour  
 Un identificateur de ressource d’icône en cas de réussite ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette méthode échoue si la vue n’est pas tout d’abord enregistrée à l’aide de [CMouseManager::AddView](#addview).  
  
##  <a name="getviewidbyname"></a>CMouseManager::GetViewIdByName  
 Récupère l’ID de la vue associée à un nom de vue.  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszName`  
 Le nom de la vue.  
  
### <a name="return-value"></a>Valeur de retour  
 Un ID de vue en cas de réussite ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode parcourt inscrits à l’aide de vues [CMouseManager::AddView](#addview).  
  
##  <a name="getviewnames"></a>CMouseManager::GetViewNames  
 Récupère une liste de tous les noms d’affichage enregistré.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `listOfNames`  
 Une référence à `CStringList` objet.  
  
### <a name="remarks"></a>Notes  
 Cette méthode remplit le paramètre `listOfNames` avec les noms de tous les affichages inscrits à l’aide de [CMouseManager::AddView](#addview).  
  
##  <a name="loadstate"></a>CMouseManager::LoadState  
 Charge l’état de la [CMouseManager classe](../../mfc/reference/cmousemanager-class.md) à partir du Registre.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Un chemin d’accès d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Les informations d’état chargées à partir du Registre incluent les vues des identificateurs de vue et les commandes associées. Si le paramètre `lpszProfileName` est `NULL`, cette fonction charge la `CMouseManager` les données à partir de l’emplacement de Registre par défaut contrôlé par le [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
 Dans la plupart des cas, vous n’avez pas à appeler directement cette fonction. Elle est appelée dans le cadre du processus d’initialisation de l’espace de travail. Pour plus d’informations sur le processus d’initialisation de l’espace de travail, consultez [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).  
  
##  <a name="savestate"></a>CMouseManager::SaveState  
 Écrit l’état de la [CMouseManager classe](../../mfc/reference/cmousemanager-class.md) dans le Registre.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Un chemin d’accès d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Les informations d’état écrites dans le Registre incluent inscrits toutes les vues, les identificateurs de vue et les commandes associées. Si le paramètre `lpszProfileName` est `NULL`, cette fonction écrit le `CMouseManager` les données à l’emplacement de Registre par défaut contrôlé par le [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
 Dans la plupart des cas, vous n’avez pas à appeler directement cette fonction. Elle est appelée dans le cadre du processus de sérialisation d’espace de travail. Pour plus d’informations sur le processus de sérialisation d’espace de travail, consultez [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
##  <a name="setcommandfordblclk"></a>CMouseManager::SetCommandForDblClk  
 Associe une commande personnalisée à une vue qui est d’abord enregistrée avec le Gestionnaire de la souris.  
  
```  
void SetCommandForDblClk(
    int iViewId,  
    UINT uiCmd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iViewId`  
 L’identificateur de la vue.  
  
 [in] `uiCmd`  
 Identificateur de commande.  
  
### <a name="remarks"></a>Remarques  
 Pour associer une commande personnalisée à une vue, vous devez d’abord inscrire l’affichage à l’aide de [CMouseManager::AddView](#addview). Le `AddView` méthode nécessite un identificateur d’affichage en tant que paramètre d’entrée. Une fois que vous enregistrez une vue, vous pouvez appeler `CMouseManager::SetCommandForDblClk` avec la même vue identificateur paramètre d’entrée que vous avez fournies à `AddView`. Par la suite, lorsque l’utilisateur double-clique sur la souris dans l’affichage enregistré, l’application exécute la commande indiquée par `uiCmd.` pour prendre en charge le comportement de la souris personnalisé, vous devez également personnaliser la vue enregistrée dans le Gestionnaire de la souris. Pour plus d’informations sur le comportement de la souris personnalisé, consultez [personnalisation du clavier et souris]--brokenlink--(.. / souris-et-clavier-customization.md).  
  
 Si `uiCmd` est défini sur 0, la vue spécifiée n’est plus associée à une commande.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx (classe)](../../mfc/reference/cwinappex-class.md)   
 [Personnalisation du clavier et souris](../../mfc/keyboard-and-mouse-customization.md)




