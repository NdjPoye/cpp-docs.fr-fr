---
title: CHeaderCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeaderCtrl
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class
- Windows common controls [C++], CHeaderCtrl
- header controls, CHeaderCtrl class
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 24
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
ms.openlocfilehash: ab3cef5d72bad004832cb85ca4b1b3604eb3a18c
ms.lasthandoff: 02/24/2017

---
# <a name="cheaderctrl-class"></a>CHeaderCtrl (classe)
Fournit les fonctionnalités du contrôle commun d'en-tête Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Construit un objet `CHeaderCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Efface tous les filtres d’un contrôle header.|  
|[CHeaderCtrl::ClearFilter](#clearfilter)|Efface le filtre pour un contrôle d’en-tête.|  
|[CHeaderCtrl::Create](#create)|Crée un contrôle header et l’attache à une `CHeaderCtrl` objet.|  
|[Fonction membre CHeaderCtrl::CreateDragImage](#createdragimage)|Crée une version de l’image d’un élément dans un contrôle d’en-tête transparente.|  
|[CHeaderCtrl::CreateEx](#createex)|Crée un contrôle d’en-tête avec les styles étendus Windows spécifiés et l’attache à une `CListCtrl` objet.|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|Supprime un élément d’un contrôle header.|  
|[CHeaderCtrl::DrawItem](#drawitem)|Dessine l’élément spécifié d’un contrôle header.|  
|[CHeaderCtrl::EditFilter](#editfilter)|Commence à modifier le filtre d’un contrôle d’en-tête spécifié.|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Récupère la largeur de la marge de la bitmap dans un contrôle d’en-tête.|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Obtient l’identificateur de l’élément dans le contrôle header actuelle qui a le focus.|  
|[CHeaderCtrl::GetImageList](#getimagelist)|Récupère le handle d’une liste d’images utilisée pour les éléments d’en-tête dessin dans un contrôle d’en-tête.|  
|[Appelant CHeaderCtrl::GetItem](#getitem)|Récupère des informations sur un élément dans un contrôle d’en-tête.|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|Récupère le nombre d’éléments dans un contrôle d’en-tête.|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Obtient les informations de rectangle englobant pour le bouton de liste déroulante spécifié dans un contrôle d’en-tête.|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|Récupère le rectangle englobant d’un élément donné dans un contrôle d’en-tête.|  
|[CHeaderCtrl::GetOrderArray](#getorderarray)|Récupère l’ordre de gauche à droite des éléments dans un contrôle d’en-tête.|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Obtient le rectangle englobant du bouton de dépassement de capacité pour le contrôle d’en-tête actuel.|  
|[CHeaderCtrl::HitTest](#hittest)|Détermine quel élément d’en-tête, le cas échéant, se trouve à un point spécifié.|  
|[CHeaderCtrl::InsertItem](#insertitem)|Insère un nouvel élément dans un contrôle d’en-tête.|  
|[CHeaderCtrl::Layout](#layout)|Récupère la taille et la position d’un contrôle d’en-tête dans un rectangle.|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Récupère la valeur d’index d’un élément en fonction de son ordre dans le contrôle header.|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Définit la largeur de la marge de la bitmap dans un contrôle d’en-tête.|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Définit l’intervalle de délai d’attente entre le moment une modification a lieu dans les attributs de filtre et de la validation d’une `HDN_FILTERCHANGE` notification.|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Définit le focus à un élément d’en-tête spécifié dans le contrôle d’en-tête actuel.|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Faites glisser le séparateur entre les éléments d’en-tête pour indiquer un manuel des modifications et suppression d’un élément d’en-tête.|  
|[CHeaderCtrl::SetImageList](#setimagelist)|Affecte une liste d’images à un contrôle d’en-tête.|  
|[CHeaderCtrl::SetItem](#setitem)|Définit les attributs de l’élément spécifié dans un contrôle d’en-tête.|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Définit l’ordre de gauche à droite des éléments dans un contrôle d’en-tête.|  
  
## <a name="remarks"></a>Remarques  
 Un contrôle d’en-tête est une fenêtre qui est généralement placée au-dessus d’un ensemble de colonnes de texte ou des nombres. Il contient un titre pour chaque colonne, et il peut être divisé en parties. L’utilisateur peut faire glisser les séparateurs qui séparent les parties pour définir la largeur de chaque colonne. Pour obtenir une illustration d’un contrôle header, consultez [contrôles Header](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Ce contrôle (et par conséquent la `CHeaderCtrl` classe) est disponible uniquement pour les programmes qui s’exécutent sous Windows 95/98 et Windows NT version 3.51 et ultérieures.  
  
 Cette fonctionnalité est ajoutée pour les contrôles communs Windows 95/Internet Explorer 4.0 inclut les éléments suivants :  
  
-   En-tête personnalisé classement des éléments.  
  
-   Élément d’en-tête glisser-déplacer, la réorganisation des éléments d’en-tête. Utilisez le `HDS_DRAGDROP` de style lorsque vous créez le `CHeaderCtrl` objet.  
  
-   Texte de colonne en-tête constamment visible lors du redimensionnement de colonne. Utilisez le `HDS_FULLDRAG` de style lorsque vous créez un `CHeaderCtrl` objet.  
  
-   En-tête réactive, ce qui met en surbrillance l’élément d’en-tête lorsque le pointeur est positionné sur lui. Utilisez le `HDS_HOTTRACK` de style lorsque vous créez le `CHeaderCtrl` objet.  
  
-   Prise en charge de la liste des images. Éléments d’en-tête peuvent contenir des images stockées dans un `CImageList` objet ou le texte.  
  
 Pour plus d’informations sur l’utilisation de `CHeaderCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [l’utilisation de CHeaderCtrl](../../mfc/using-cheaderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="a-namecheaderctrla--cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl  
 Construit un objet `CHeaderCtrl`.  
  
```  
CHeaderCtrl();
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl n °&1;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="a-nameclearallfiltersa--cheaderctrlclearallfilters"></a><a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters  
 Efface tous les filtres d’un contrôle header.  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode implémente le comportement du message Win32 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) avec une valeur de colonne de –&1;, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl n °&2;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="a-nameclearfiltera--cheaderctrlclearfilter"></a><a name="clearfilter"></a>CHeaderCtrl::ClearFilter  
 Efface le filtre pour un contrôle d’en-tête.  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>Paramètres  
 `nColumn`  
 Valeur de colonne qui indique le filtre à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode implémente le comportement du message Win32 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl n °&3;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="a-namecreatea--cheaderctrlcreate"></a><a name="create"></a>CHeaderCtrl::Create  
 Crée un contrôle header et l’attache à une `CHeaderCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle d’en-tête. Pour obtenir une description des styles de contrôle d’en-tête, consultez [Styles de contrôle d’en-tête](http://msdn.microsoft.com/library/windows/desktop/bb775241) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Spécifie la taille et la position du contrôle header. Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure.  
  
 `pParentWnd`  
 Spécifie les fenêtre du parent du contrôle d’en-tête, généralement un `CDialog`. Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID. du contrôle de l’en-tête  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation a réussi ; Sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CHeaderCtrl` objet en deux étapes. Tout d’abord, appelez le constructeur, puis **créer**, qui crée le contrôle header et l’attache à le `CHeaderCtrl` objet.  
  
 Outre les styles de contrôle d’en-tête, vous pouvez utiliser les styles de contrôle courants suivants pour déterminer comment le contrôle header positionne et redimensionne (voir [des Styles de contrôle commun](http://msdn.microsoft.com/library/windows/desktop/bb775498) pour plus d’informations) :  
  
- `CCS_BOTTOM`Force le contrôle à se positionner en bas de la zone cliente de la fenêtre parente et définit la largeur de la même que le parent largeur de la fenêtre.  
  
- `CCS_NODIVIDER`Empêche une surbrillance deux pixels d’être dessinés en haut du contrôle.  
  
- `CCS_NOMOVEY`Force le contrôle à redimensionner et se déplacer horizontalement, mais non verticalement, en réponse à une `WM_SIZE` message. Si le `CCS_NORESIZE` style est utilisé, ce style ne s’applique pas. Contrôles header ont ce style par défaut.  
  
- `CCS_NOPARENTALIGN`Empêche le contrôle de déplacement automatique vers le haut ou le bas de la fenêtre parente. Au lieu de cela, le contrôle conserve sa position dans la fenêtre parente en dépit des modifications apportées à la taille de la fenêtre parente. Si le `CCS_TOP` ou `CCS_BOTTOM` style est également utilisé, la hauteur est ajustée à la valeur par défaut, mais la position et la largeur restent inchangés.  
  
- `CCS_NORESIZE`Empêche le contrôle de l’utilisation de la largeur par défaut et la hauteur lors de la définition de sa taille initiale ou une nouvelle taille. En revanche, le contrôle utilise la largeur et la hauteur spécifiée dans la demande de création ou de dimensionnement.  
  
- `CCS_TOP`Force le contrôle à se positionner en haut de la zone cliente de la fenêtre parente et définit la largeur de la même que le parent largeur de la fenêtre.  
  
 Vous pouvez également appliquer les styles de fenêtre suivants à un contrôle header (voir [Styles de fenêtre](../../mfc/reference/window-styles.md) pour plus d’informations) :  
  
- **WS_CHILD** crée une fenêtre enfant. Ne peut pas être utilisé avec les `WS_POPUP` style.  
  
- **WS_VISIBLE** crée une fenêtre qui est initialement visible.  
  
- **WS_DISABLED** crée une fenêtre qui est initialement désactivée.  
  
- **WS_GROUP** Spécifie le premier contrôle d’un groupe de contrôles dans lesquels l’utilisateur peut déplacer d’un contrôle à l’autre avec les touches de direction. Tous les contrôles définis avec la **WS_GROUP** après le premier contrôle appartiennent au même groupe de style. Le contrôle suivant avec les **WS_GROUP** style met fin au groupe de style et démarre le groupe suivant (autrement dit, un groupe se termine où commence la prochaine).  
  
- **WS_TABSTOP** spécifie un nombre quelconque de contrôles par le biais duquel l’utilisateur peut passer à l’aide de la touche TAB. La touche TAB déplace l’utilisateur vers le contrôle suivant est spécifié par le **WS_TABSTOP** style.  
  
 Si vous souhaitez utiliser les styles étendus windows avec votre contrôle, appelez [CreateEx](#createex) au lieu de **créer**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl n °&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
##  <a name="a-namecreateexa--cheaderctrlcreateex"></a><a name="createex"></a>CHeaderCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et y associer le `CHeaderCtrl` objet.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwExStyle`  
 Spécifie le style étendu du contrôle en cours de création. Pour obtenir la liste des styles étendus de Windows, consultez le `dwExStyle` paramètre [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Style du contrôle d’en-tête. Pour obtenir une description des styles de contrôle d’en-tête, consultez [Styles de contrôle d’en-tête](http://msdn.microsoft.com/library/windows/desktop/bb775241) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Consultez la page [créer](#create) pour obtenir la liste des styles supplémentaires.  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, dans les coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `CreateEx` au lieu de **créer** pour appliquer des styles étendus Windows, spécifiés par la préface de style étendu Windows **WS_EX_**.  
  
##  <a name="a-namecreatedragimagea--cheaderctrlcreatedragimage"></a><a name="createdragimage"></a>Fonction membre CHeaderCtrl::CreateDragImage  
 Crée une version de l’image d’un élément dans un contrôle d’en-tête transparente.  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro de l’élément dans le contrôle header. L’image attribuée à cet élément est la base de l’image transparente.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet en cas de réussite ; sinon **NULL**. La liste renvoyée contient une seule image.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Il est fourni pour prendre en charge d’en-tête élément glisser -déplacer.  
  
 Le `CImageList` objet auquel les points de pointeur retourné est un objet temporaire et est supprimée dans le prochain traitement de temps d’inactivité.  
  
##  <a name="a-namedeleteitema--cheaderctrldeleteitem"></a><a name="deleteitem"></a>CHeaderCtrl::DeleteItem  
 Supprime un élément d’un contrôle header.  
  
```  
BOOL DeleteItem(int nPos);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPos`  
 Spécifie l’index de base zéro de l’élément à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl n °&5;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="a-namedrawitema--cheaderctrldrawitem"></a><a name="drawitem"></a>CHeaderCtrl::DrawItem  
 Appelé par l’infrastructure lorsqu’un aspect visuel d’un mode owner-draw en-tête contrôle change.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpDrawItemStruct`  
 Un pointeur vers un [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) structure décrivant l’élément à peindre.  
  
### <a name="remarks"></a>Remarques  
 Le **itemAction** membre de la `DRAWITEMSTRUCT` structure définit l’action de dessin qui doit être effectuée.  
  
 Par défaut, cette fonction membre ne fait rien. Remplacez cette fonction membre pour implémenter le dessin pour un mode owner-draw `CHeaderCtrl` objet.  
  
 L’application doit restaurer tous les objets interface (GDI) périphérique graphique sélectionnés pour le contexte d’affichage fournie dans `lpDrawItemStruct` avant cette fonction se termine.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl n °&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="a-nameeditfiltera--cheaderctrleditfilter"></a><a name="editfilter"></a>CHeaderCtrl::EditFilter  
 Commence à modifier le filtre d’un contrôle d’en-tête spécifié.  
  
```  
BOOL EditFilter(
    int nColumn,  
    BOOL bDiscardChanges);
```  
  
### <a name="parameters"></a>Paramètres  
 `nColumn`  
 La colonne à modifier.  
  
 `bDiscardChanges`  
 Une valeur qui spécifie comment gérer les utilisateurs de modifications si l’utilisateur est en train de modifier le filtre lorsque le [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312) envoyé.  
  
 Spécifier `true` pour ignorer les modifications apportées par l’utilisateur, ou `false` pour accepter les modifications apportées par l’utilisateur.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode implémente le comportement du message Win32 [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#7;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="a-namegetbitmapmargina--cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin  
 Récupère la largeur de la marge de la bitmap dans un contrôle d’en-tête.  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur de la marge d’image bitmap en pixels.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl n °&8;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="a-namegetfocuseditema--cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem  
 Obtient l’index de l’élément qui a le focus dans le contrôle d’en-tête actuel.  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément d’en-tête qui a le focus.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_headerCtrl`, qui est utilisé pour accéder au contrôle d’en-tête actuel. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant montre la `SetFocusedItem` et `GetFocusedItem` méthodes. Dans une section précédente du code, nous avons créé un contrôle d’en-tête avec cinq colonnes. Toutefois, vous pouvez faire glisser un séparateur de colonne afin que la colonne n’est pas visible. L’exemple suivant définit, puis confirme le dernier en-tête de colonne en tant que l’élément actif.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="a-namegetimagelista--cheaderctrlgetimagelist"></a><a name="getimagelist"></a>CHeaderCtrl::GetImageList  
 Récupère le handle d’une liste d’images utilisée pour les éléments d’en-tête dessin dans un contrôle d’en-tête.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CImageList](../../mfc/reference/cimagelist-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Le `CImageList` objet auquel les points de pointeur retourné est un objet temporaire et est supprimée dans le prochain traitement de temps d’inactivité.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#9;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="a-namegetitema--cheaderctrlgetitem"></a><a name="getitem"></a>Appelant CHeaderCtrl::GetItem  
 Récupère des informations sur un élément de contrôle d’en-tête.  
  
```  
BOOL GetItem(
    int nPos,  
    HDITEM* pHeaderItem) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nPos`  
 Spécifie l’index de base zéro de l’élément à récupérer.  
  
 `pHeaderItem`  
 Pointeur vers un [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) structure qui reçoit le nouvel élément. Cette structure est utilisée avec la `InsertItem` et `SetItem` les fonctions membres. Les indicateurs définis dans le **masque** élément vous assurer que les valeurs dans les éléments correspondants sont correctement renseignés au moment du retour. Si le **masque** élément a la valeur zéro, les valeurs dans les autres éléments de structure sont sans importance.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#10;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="a-namegetitemcounta--cheaderctrlgetitemcount"></a><a name="getitemcount"></a>CHeaderCtrl::GetItemCount  
 Récupère le nombre d’éléments dans un contrôle d’en-tête.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’éléments de contrôle d’en-tête en cas de réussite ; Sinon,-1.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CHeaderCtrl::DeleteItem](#deleteitem).  
  
##  <a name="a-namegetitemdropdownrecta--cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect  
 Obtient le rectangle englobant du bouton de liste déroulante pour un élément d’en-tête dans le contrôle d’en-tête actuel.  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `iItem`|Index de base zéro d’un élément d’en-tête dont le style est `HDF_SPLITBUTTON`. Pour plus d’informations, consultez la `fmt` membre de la [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) structure.|  
|[out] `lpRect`|Pointeur vers un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure pour recevoir les informations de rectangle englobant.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette fonction a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_headerCtrl`, qui est utilisé pour accéder au contrôle d’en-tête actuel. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant montre la `GetItemDropDownRect` méthode. Dans une section précédente du code, nous avons créé un contrôle d’en-tête avec cinq colonnes. L’exemple de code suivant dessine un rectangle 3D autour de l’emplacement sur la première colonne est réservée pour le bouton de liste déroulante d’en-tête.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&2;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="a-namegetitemrecta--cheaderctrlgetitemrect"></a><a name="getitemrect"></a>CHeaderCtrl::GetItemRect  
 Récupère le rectangle englobant d’un élément donné dans un contrôle d’en-tête.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro de l’élément de contrôle d’en-tête.  
  
 `lpRect`  
 Un pointeur vers l’adresse d’un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure qui reçoit les informations de rectangle englobant.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode implémente le comportement du message Win32 [HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetorderarraya--cheaderctrlgetorderarray"></a><a name="getorderarray"></a>CHeaderCtrl::GetOrderArray  
 Récupère l’ordre de gauche à droite des éléments dans un contrôle d’en-tête.  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>Paramètres  
 `piArray`  
 Pointeur vers l’adresse d’une mémoire tampon qui reçoit les valeurs d’index des éléments dans le contrôle header, dans l’ordre dans lequel elles apparaissent de gauche à droite.  
  
 `iCount`  
 Le nombre d’éléments de contrôle d’en-tête. Doit être non négatif.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Il est fourni pour prendre en charge le classement des éléments d’en-tête.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#11;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="a-namegetoverflowrecta--cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect  
 Obtient le rectangle englobant du bouton de dépassement de capacité du contrôle d’en-tête actuel.  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[out] `lpRect`|Pointeur vers un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure qui reçoit les informations de rectangle englobant.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette fonction a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Si le contrôle d’en-tête contient trop d’éléments peuvent être affichés simultanément, le contrôle peut afficher un bouton de dépassement de capacité qui fait défiler l’écran pour les éléments qui ne sont pas visibles. Le contrôle d’en-tête doit avoir le `HDS_OVERFLOW` et `HDF_SPLITBUTTON` styles pour afficher le bouton de dépassement de capacité. Le rectangle englobant englobe le bouton de dépassement de capacité et existe uniquement lorsque le bouton de dépassement de capacité s’affiche. Pour plus d’informations, consultez [Styles de contrôle d’en-tête](http://msdn.microsoft.com/library/windows/desktop/bb775241).  
  
 Cette méthode envoie le [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_headerCtrl`, qui est utilisé pour accéder au contrôle d’en-tête actuel. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant montre la `GetOverflowRect` méthode. Dans une section précédente du code, nous avons créé un contrôle d’en-tête avec cinq colonnes. Toutefois, vous pouvez faire glisser un séparateur de colonne afin que la colonne n’est pas visible. Si certaines colonnes ne sont pas visibles, le contrôle header Dessine un bouton de dépassement de capacité. L’exemple de code suivant dessine un rectangle 3D autour de l’emplacement du bouton de dépassement de capacité.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&3;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="a-namehittesta--cheaderctrlhittest"></a><a name="hittest"></a>CHeaderCtrl::HitTest  
 Détermine quel élément d’en-tête, le cas échéant, se trouve à un point spécifié.  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in, out] `phdhti`|Pointeur vers un [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245) structure qui spécifie le point à tester et reçoit les résultats du test.|  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément d’en-tête, le cas échéant, la position spécifiée ; Sinon, valeur -1.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_headerCtrl`, qui est utilisé pour accéder au contrôle d’en-tête actuel. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant montre la `HitTest` méthode. Dans une section précédente de cet exemple de code, nous avons créé un contrôle d’en-tête avec cinq colonnes. Toutefois, vous pouvez faire glisser un séparateur de colonne afin que la colonne n’est pas visible. Cet exemple signale l’index de la colonne si elle est visible et -1 si la colonne n’est pas visible.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&1;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="a-nameinsertitema--cheaderctrlinsertitem"></a><a name="insertitem"></a>CHeaderCtrl::InsertItem  
 Insère un nouvel élément dans un contrôle d’en-tête à l’index spécifié.  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPos`  
 Index de base zéro de l'élément à insérer. Si la valeur est zéro, l’élément est inséré au début du contrôle header. Si la valeur est supérieure à la valeur maximale, l’élément est inséré à la fin du contrôle header.  
  
 *phdi*  
 Pointeur vers un [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) structure qui contient des informations sur l’élément à insérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Index du nouvel élément en cas de réussite ; Sinon,-1.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#12;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="a-namelayouta--cheaderctrllayout"></a><a name="layout"></a>CHeaderCtrl::Layout  
 Récupère la taille et la position d’un contrôle d’en-tête dans un rectangle.  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>Paramètres  
 *pHeaderLayout*  
 Pointeur vers un [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249) structure qui contient les informations utilisées pour définir la taille et la position d’un contrôle d’en-tête.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est utilisée pour déterminer les dimensions appropriées pour un nouveau contrôle d’en-tête qui doit occuper le rectangle donné.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#13;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="a-nameordertoindexa--cheaderctrlordertoindex"></a><a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex  
 Récupère la valeur d’index d’un élément en fonction de son ordre dans le contrôle header.  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *nOrder*  
 L’ordre de base zéro qui l’élément s’affiche dans le contrôle d’en-tête, de gauche à droite.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index de l’élément, en fonction de son ordre dans le contrôle header. L’index de compte de gauche à droite, en commençant par 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement de la macro Win32 [HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Il est fourni pour prendre en charge le classement des éléments d’en-tête.  
  
##  <a name="a-namesetbitmapmargina--cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin  
 Définit la largeur de la marge de la bitmap dans un contrôle d’en-tête.  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>Paramètres  
 `nWidth`  
 Largeur en pixels de la marge qui entoure une image bitmap dans un contrôle d’en-tête existant.  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur de la marge d’image bitmap en pixels.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#14;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="a-namesetfilterchangetimeouta--cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout  
 Définit l’intervalle de délai d’attente entre le moment une modification a lieu dans les attributs de filtre et de la validation d’une [HDN_FILTERCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb775277) notification.  
  
```  
int SetFilterChangeTimeout(DWORD dwTimeOut);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwTimeOut*  
 Valeur de délai d’attente, en millisecondes.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index du contrôle de filtre en cours de modification.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [HDM_SETFILTERCHANGETIMEOUT](http://msdn.microsoft.com/library/windows/desktop/bb775359), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#15;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="a-namesetfocuseditema--cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem  
 Définit le focus à un élément d’en-tête spécifié dans le contrôle d’en-tête actuel.  
  
```  
BOOL SetFocusedItem(int iItem);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `iItem`|Index de base zéro d’un élément d’en-tête.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_headerCtrl`, qui est utilisé pour accéder au contrôle d’en-tête actuel. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant montre la `SetFocusedItem` et `GetFocusedItem` méthodes. Dans une section précédente du code, nous avons créé un contrôle d’en-tête avec cinq colonnes. Toutefois, vous pouvez faire glisser un séparateur de colonne afin que la colonne n’est pas visible. L’exemple suivant définit, puis confirme le dernier en-tête de colonne en tant que l’élément actif.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4 n °&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="a-namesethotdividera--cheaderctrlsethotdivider"></a><a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider  
 Faites glisser le séparateur entre les éléments d’en-tête pour indiquer un manuel des modifications et suppression d’un élément d’en-tête.  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `pt`  
 La position du pointeur. Le contrôle header met en surbrillance la ligne de séparation approprié en fonction de la position du pointeur.  
  
 `nIndex`  
 Index de la ligne de séparation en surbrillance.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de la ligne de séparation en surbrillance.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Il est fourni pour prendre en charge d’en-tête élément glisser -déplacer.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#16;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="a-namesetimagelista--cheaderctrlsetimagelist"></a><a name="setimagelist"></a>CHeaderCtrl::SetImageList  
 Affecte une liste d’images à un contrôle d’en-tête.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 `pImageList`  
 Un pointeur vers un `CImageList` objet contenant la liste d’images à assigner au contrôle header.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le [CImageList](../../mfc/reference/cimagelist-class.md) objet précédemment affecté au contrôle header.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Le `CImageList` objet auquel les points de pointeur retourné est un objet temporaire et est supprimée dans le prochain traitement de temps d’inactivité.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CHeaderCtrl::GetImageList](#getimagelist).  
  
##  <a name="a-namesetitema--cheaderctrlsetitem"></a><a name="setitem"></a>CHeaderCtrl::SetItem  
 Définit les attributs de l’élément spécifié dans un contrôle d’en-tête.  
  
```  
BOOL SetItem(
    int nPos,  
    HDITEM* pHeaderItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPos`  
 Index de base zéro de l’élément à manipuler.  
  
 `pHeaderItem`  
 Pointeur vers un [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) structure qui contient des informations sur le nouvel élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [appelant CHeaderCtrl::GetItem](#getitem).  
  
##  <a name="a-namesetorderarraya--cheaderctrlsetorderarray"></a><a name="setorderarray"></a>CHeaderCtrl::SetOrderArray  
 Définit l’ordre de gauche à droite des éléments dans un contrôle d’en-tête.  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>Paramètres  
 `iCount`  
 Le nombre d’éléments de contrôle d’en-tête.  
  
 `piArray`  
 Pointeur vers l’adresse d’une mémoire tampon qui reçoit les valeurs d’index des éléments dans le contrôle header, dans l’ordre dans lequel elles apparaissent de gauche à droite.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement de la macro Win32 [HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Il est fourni pour prendre en charge le classement des éléments d’en-tête.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CHeaderCtrl::GetOrderArray](#getorderarray).  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CTabCtrl (classe)](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl (classe)](../../mfc/reference/clistctrl-class.md)   
 [CImageList (classe)](../../mfc/reference/cimagelist-class.md)

