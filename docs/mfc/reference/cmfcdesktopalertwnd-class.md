---
title: Classe de CMFCDesktopAlertWnd | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWnd class
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
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
ms.openlocfilehash: be9d81ffff003119aa7ff9e0cd100c575bd82d36
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
La `CMFCDesktopAlertWnd` classe implémente les fonctionnalités d’une boîte de dialogue non modale qui apparaît à l’écran pour informer l’utilisateur d’un événement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCDesktopAlertWnd::Create](#create)|Crée et initialise la fenêtre d’alerte de bureau.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Retourne la vitesse d’animation.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Retourne le type d’animation.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Retourne le délai d’attente de fermeture automatique.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Retourne la hauteur de la légende.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Retourne la dernière position valide de la fenêtre d’alerte de postes de travail à l’écran.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Retourne le niveau de transparence.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Détermine si la fenêtre d’alerte de bureau est affichée avec la barre de titre réduite.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Appelé par l’infrastructure lorsque l’utilisateur clique sur un bouton de lien dans le menu alerte bureau.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|L’infrastructure appelle cette fonction membre lorsque l’utilisateur sélectionne un élément dans un menu, lorsqu’un contrôle enfant envoie un message de notification, ou lors de la traduction d’une séquence de touches accélérateur. (Substitue [fonction membre CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Définit la vitesse d’animation.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Définit le type d’animation.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Définit le délai d’attente de fermeture automatique.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Bascule entre les légendes des petites et normales.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Définit le niveau de transparence.|  
  
## <a name="remarks"></a>Remarques  
 Une fenêtre d’alerte bureau peut être transparente, il peut apparaître avec des effets d’animation et il peut disparaître (après un délai spécifié ou lorsque l’action de l’utilisateur en cliquant sur le bouton Fermer).  
  
 Une fenêtre d’alerte bureau peut également contenir une boîte de dialogue par défaut qui contient un lien, une icône et texte du message (une étiquette). Sinon, une fenêtre d’alerte bureau peut contenir une boîte de dialogue personnalisée à partir des ressources de l’application.  
  
 Vous créez une fenêtre d’alerte bureau en deux étapes. Tout d’abord, appelez le constructeur pour construire le `CMFCDesktopAlertWnd` objet. Ensuite, appelez le [CMFCDesktopAlertWnd::Create](#create) fonction membre pour créer la fenêtre et l’attacher à la `CMFCDesktopAlertWnd` objet.  
  
 Le `CMFCDesktopAlertWnd` objet crée une boîte de dialogue enfants spéciaux qui remplit la zone cliente de la fenêtre d’alerte de bureau. La boîte de dialogue possède tous les contrôles qui sont placés sur ce dernier.  
  
 Pour afficher une boîte de dialogue personnalisée dans la fenêtre contextuelle, procédez comme suit :  
  
1.  Dérivez une classe de `CMFCDesktopAlertDialog`.  
  
2.  Créer un modèle de boîte de dialogue enfant dans les ressources.  
  
3.  Appelez [CMFCDesktopAlertWnd::Create](#create) à l’aide de l’ID de ressource de la boîte de dialogue modèle et un pointeur vers les informations de classe d’exécution de la classe dérivée.  
  
4.  La boîte de dialogue pour gérer toutes les notifications provenant de contrôles hébergés de programmes ou les contrôles hébergés pour gérer ces notifications directement du programme.  
  
 Pour contrôler le comportement de la fenêtre d’alerte de postes de travail, utilisez les fonctions suivantes :  
  
-   Définir le type d’animation en appelant [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Les options valides incluent dérouler, diapositives et fondu.  
  
-   Définir la vitesse d’animation du cadre en appelant [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).  
  
-   Définir le niveau de transparence en appelant [CMFCDesktopAlertWnd::SetTransparency](#settransparency).  
  
-   Modifier la taille de la légende à petite en appelant [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). La petite légende est 7 pixels de haut.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans le `CMFCDesktopAlertWnd` classe pour configurer un `CMFCDesktopAlertWnd` objet. L’exemple montre comment définir un type d’animation, définir la transparence de la fenêtre contextuelle, spécifiez que la fenêtre d’alerte affiche une barre de titre réduite et le temps qui s’écoule avant que la fenêtre d’alerte se ferme automatiquement. L’exemple montre également comment créer et initialiser la fenêtre d’alerte de bureau. Cet extrait de code fait partie de la [exemple de démonstration alerte bureau](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo n °&1;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxDesktopAlertWnd.h  
  
##  <a name="create"></a>CMFCDesktopAlertWnd::Create  
 Crée et initialise la fenêtre d’alerte de bureau.  
  
```  
virtual BOOL Create(
    CWnd* pWndOwner,  
    UINT uiDlgResID,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1),  
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

 
virtual BOOL Create(
    CWnd* pWndOwner,  
    CMFCDesktopAlertWndInfo& params,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1));
```  
  
### <a name="parameters"></a>Paramètres  
 [in] [out]`pWndOwner`  
 Spécifie le propriétaire de la fenêtre d’alerte. Ce dernier recevra alors toutes les notifications de la fenêtre d’alerte de bureau. Cette valeur ne peut pas être `NULL`.  
  
 [in] `uiDlgResID`  
 Spécifie l’ID de ressource de la fenêtre d’alerte.  
  
 [in] `hMenu`  
 Spécifie le menu qui s’affiche lorsque l’utilisateur clique sur le bouton de menu. Si `NULL`, le bouton de menu n’est pas affiché.  
  
 [in] `ptPos`  
 Spécifie la position initiale dans laquelle la fenêtre d’alerte s’affiche, à l’aide des coordonnées d’écran. Si ce paramètre est (-1, -1), la fenêtre d’alerte s’affiche dans le coin inférieur droit de l’écran.  
  
 [in] `pRTIDlgBar`  
 Informations de classe d’exécution pour une classe de boîte de dialogue personnalisée qui couvre la zone cliente de la fenêtre alerte.  
  
 [in] `params`  
 Spécifie les paramètres qui sont utilisés pour créer une fenêtre d’alerte.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la fenêtre d’alerte a été créée avec succès ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour créer une fenêtre d’alerte. La zone cliente de la fenêtre d’alerte contient une boîte de dialogue enfant qui héberge tous les contrôles qui sont affichent à l’utilisateur.  
  
 La première surcharge de méthode crée une fenêtre qui contient une boîte de dialogue enfant qui est chargée à partir de ressources de l’application. La première surcharge de méthode peut également spécifier des informations de classe d’exécution pour une classe de boîte de dialogue personnalisée.  
  
 La deuxième surcharge de méthode crée une fenêtre qui contient les contrôles par défaut. Vous pouvez spécifier les contrôles à afficher en modifiant le [CMFCDesktopAlertWndInfo classe](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).  
  
##  <a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed  
 Retourne la vitesse d’animation.  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La vitesse d’animation de la fenêtre d’alerte, en millisecondes.  
  
### <a name="remarks"></a>Notes  
 La vitesse d’animation décrit la vitesse à laquelle la fenêtre d’alerte s’ouvre et se ferme.  
  
##  <a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType  
 Retourne le type d’animation.  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un des types d’animation suivants :  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime  
 Retourne le délai d’attente de fermeture automatique.  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La durée, en millisecondes, après laquelle la fenêtre se fermera automatiquement.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour déterminer combien de temps qui doit s’écouler avant que la fenêtre d’alerte se ferme automatiquement.  
  
##  <a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 Retourne la hauteur de la légende.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur, en pixels, de la légende.  
  
### <a name="remarks"></a>Notes  
 Cette méthode peut être substituée dans une classe dérivée. L’implémentation par défaut soit : renvoie la valeur de hauteur de barre de titre réduite (7 pixels) si la fenêtre contextuelle doit afficher la barre de titre réduite, ou la valeur obtenue à partir de la fonction API Windows `GetSystemMetrics(SM_CYSMCAPTION)`.  
  
##  <a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos  
 Retourne la dernière position de la fenêtre d’alerte de postes de travail à l’écran.  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un point, en coordonnées d’écran.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne la dernière position valide de la fenêtre d’alerte sur l’écran.  
  
##  <a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency  
 Retourne le niveau de transparence.  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un niveau de transparence comprise entre 0 et 255, inclus. Plus la valeur, la partie la plus opaque la fenêtre.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour récupérer le niveau actuel de la transparence de la fenêtre d’alerte.  
  
##  <a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 Détermine si la fenêtre d’alerte bureau possède une barre de titre réduite ou une légende de taille standard.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la fenêtre contextuelle s’affiche avec une barre de titre réduite ; `FALSE` si la fenêtre contextuelle s’affiche avec une légende de taille normale.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour déterminer si la fenêtre possède une barre de titre réduite ou une légende de taille standard. Par défaut, la barre de titre réduite est 7 pixels de haut. Vous pouvez obtenir la hauteur de la légende de taille standard en appelant la fonction API Windows `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `CPoint&`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton  
 Appelé par l’infrastructure lorsque l’utilisateur clique sur un bouton de lien dans le menu alerte bureau.  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode dans une classe dérivée si vous souhaitez être averti lorsqu’un utilisateur clique sur le lien dans la fenêtre d’alerte.  
  
##  <a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `wParam`  
 [in] `lParam`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hwnd`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed  
 Définit la vitesse d’animation.  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nSpeed`  
 Spécifie la vitesse d’animation nouvelle, en millisecondes.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour définir la vitesse d’animation de la fenêtre d’alerte. La vitesse d’animation par défaut est de 30 millisecondes.  
  
##  <a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType  
 Définit le type d’animation.  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `type`  
 Spécifie le type d’animation.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour définir le type d’animation. Vous pouvez spécifier l'une des valeurs suivantes :  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime  
 Définit le délai d’attente de fermeture automatique.  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nTime`  
 La durée, en millisecondes, qui s’écoule avant que la fenêtre d’alerte se ferme automatiquement.  
  
### <a name="remarks"></a>Remarques  
 La fenêtre d’alerte est fermée automatiquement après l’heure spécifiée si l’utilisateur n’interagit pas avec la fenêtre.  
  
##  <a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 Bascule entre les légendes de petite et de taille standard.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSmallCaption`  
 `TRUE`Pour spécifier que la fenêtre d’alerte affiche une barre de titre réduite ; dans le cas contraire, `FALSE` pour indiquer que la fenêtre d’alerte affiche une légende de taille standard.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour afficher la légende de petite taille ou de taille standard. Par défaut, la barre de titre réduite est 7 pixels de haut. Vous pouvez obtenir la taille de la légende régulière en appelant la fonction API Windows `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 Définit le niveau de transparence de la fenêtre contextuelle.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nTransparency`  
 Spécifie le niveau de transparence. Cette valeur doit être comprise entre 0 et 255, inclus. Plus la valeur, la partie la plus opaque la fenêtre.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour définir le niveau de transparence de la fenêtre contextuelle.  
  
##  <a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetDialogSize();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo (classe)](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog (classe)](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)

