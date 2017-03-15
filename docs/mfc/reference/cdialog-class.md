---
title: CDialog (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialog
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes, creating
- MFC dialog boxes, base class
- modeless dialog boxes, creating
- modeless dialog boxes, displaying
- CDialog class
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
caps.latest.revision: 23
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
ms.openlocfilehash: 0944d815e8aca591f2a09c09af60fa591a9b1a6d
ms.lasthandoff: 02/24/2017

---
# <a name="cdialog-class"></a>CDialog (classe)
La classe de base permettant d’afficher des boîtes de dialogue à l’écran.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDialog : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDialog::CDialog](#cdialog)|Construit un objet `CDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDialog::Create](#create)|Initialise le `CDialog` objet. Crée une boîte de dialogue non modale et l’attache à le `CDialog` objet.|  
|[CDialog::CreateIndirect](#createindirect)|Crée une boîte de dialogue non modale à partir d’un modèle de boîte de dialogue en mémoire (non basée sur la ressource).|  
|[CDialog::DoModal](#domodal)|Appelle une boîte de dialogue modale et retourne lorsque vous avez terminé.|  
|[CDialog::EndDialog](#enddialog)|Ferme la boîte de dialogue modale.|  
|[CDialog::GetDefID](#getdefid)|Obtient l’ID du contrôle par défaut pour une boîte de dialogue.|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|Déplace le focus vers un contrôle de boîte de dialogue spécifié dans la boîte de dialogue.|  
|[CDialog::InitModalIndirect](#initmodalindirect)|Crée une boîte de dialogue modale à partir d’un modèle de boîte de dialogue en mémoire (non basée sur la ressource). Les paramètres sont stockés jusqu'à ce que la fonction `DoModal` est appelée.|  
|[CDialog::MapDialogRect](#mapdialogrect)|Convertit les unités de boîte de dialogue d’un rectangle en unités d’écran.|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|Déplace le focus vers le contrôle suivant de la boîte de dialogue dans la boîte de dialogue.|  
|[CDialog::OnInitDialog](#oninitdialog)|Substituez pour augmenter l’initialisation de la boîte de dialogue.|  
|[CDialog::OnSetFont](#onsetfont)|Substituez pour spécifier la police à utiliser lorsqu’il dessine le texte par un contrôle de boîte de dialogue.|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|Déplace le focus vers le contrôle précédent de la boîte de dialogue dans la boîte de dialogue.|  
|[CDialog::SetDefID](#setdefid)|Remplace le contrôle par défaut pour une boîte de dialogue un bouton de commande spécifié.|  
|[CDialog::SetHelpID](#sethelpid)|Définit un ID d’aide contextuelle pour la boîte de dialogue.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|Substituez pour effectuer une action touche ÉCHAP ou un bouton Annuler. La valeur par défaut ferme la boîte de dialogue et **DoModal** retourne **IDCANCEL**.|  
|[CDialog::OnOK](#onok)|Substituez pour effectuer l’action du bouton OK dans la boîte de dialogue modale. La valeur par défaut ferme la boîte de dialogue et `DoModal` retourne **IDOK**.|  
  
## <a name="remarks"></a>Remarques  
 Boîtes de dialogue sont de deux types : modales et non modales. Boîte de dialogue modale doit être fermée par l’utilisateur avant que l’application continue. Une boîte de dialogue non modale permet à l’utilisateur afficher la boîte de dialogue et revenir à une autre tâche sans l’annulation ou la suppression de la boîte de dialogue.  
  
 A `CDialog` objet est une combinaison d’un modèle de boîte de dialogue et un `CDialog`-classe dérivée. Utilisez l’éditeur de boîtes de dialogue pour créer le modèle de boîte de dialogue et les stocker dans une ressource, puis utiliser l’Assistant Ajouter une classe pour créer une classe dérivée de `CDialog`.  
  
 Une boîte de dialogue, comme toute autre fenêtre reçoit des messages à partir de Windows. Une boîte de dialogue vous intéressent particulièrement dans le traitement des messages de notification à partir de contrôles de la boîte de dialogue, c'est-à-dire la façon dont l’utilisateur interagit avec votre boîte de dialogue. Utilisez la fenêtre Propriétés pour sélectionner les messages que vous le souhaitez pour gérer et il ajoutera les entrées de table des messages appropriée et les fonctions membres de gestionnaire de messages à la classe pour vous. Vous devez uniquement écrire du code spécifique à l’application dans les fonctions membres de gestionnaire.  
  
 Si vous préférez, vous pouvez toujours écrire des entrées de table des messages et des fonctions membres manuellement.  
  
 Dans tous les la plus simple de la boîte de dialogue, vous ajoutez des variables membres à votre classe de boîte de dialogue dérivée pour stocker les données entrées par l’utilisateur dans les contrôles de la boîte de dialogue ou d’afficher les données de l’utilisateur. Vous pouvez utiliser l’Assistant Ajouter une Variable à créer des variables de membre et les associer à des contrôles. En même temps, vous choisissez un type de variable et de la plage autorisée de valeurs pour chaque variable. L’Assistant de code ajoute les variables membres à votre classe de boîte de dialogue dérivée.  
  
 Un mappage de données est généré pour gérer automatiquement l’échange de données entre les variables de membre et les contrôles de la boîte de dialogue. Le mappage de données fournit des fonctions pour initialiser les contrôles dans la boîte de dialogue avec les valeurs appropriées, récupèrent les données et valident les données.  
  
 Pour créer une boîte de dialogue modale, construisez un objet sur la pile à l’aide du constructeur pour votre classe dérivée de boîte de dialogue, puis appelez `DoModal` pour créer la boîte de dialogue et ses contrôles. Si vous souhaitez créer une boîte de dialogue non modale, appelez **créer** dans le constructeur de votre classe de boîte de dialogue.  
  
 Vous pouvez également créer un modèle en mémoire en utilisant un [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) structure de données comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Après avoir construit un `CDialog` de l’objet, appelez [CreateIndirect](#createindirect) pour créer un non modal boîte de dialogue ou appelez [InitModalIndirect](#initmodalindirect) et [DoModal](#domodal) pour créer une boîte de dialogue modale.  
  
 Le mappage de données exchange et la validation est écrit dans une substitution de `CWnd::DoDataExchange` qui est ajouté à votre nouvelle classe de boîte de dialogue. Consultez le [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) fonction membre dans `CWnd` pour plus d’informations sur la fonctionnalité d’échange et validation.  
  
 Le programmeur et l’appel de framework `DoDataExchange` indirectement via un appel à [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata).  
  
 Le framework appelle `UpdateData` lorsque l’utilisateur clique sur le bouton OK pour fermer la boîte de dialogue modale. (Les données ne sont récupérées en cas de clic du bouton Annuler.) L’implémentation par défaut de [OnInitDialog](#oninitdialog) appelle également `UpdateData` pour définir les valeurs initiales des contrôles. Vous substituez en général `OnInitDialog` pour initialiser des contrôles. `OnInitDialog`est appelée une fois que tous les contrôles de boîte de dialogue sont créés et juste avant la boîte de dialogue s’affiche.  
  
 Vous pouvez appeler `CWnd::UpdateData` à tout moment pendant l’exécution d’une boîte de dialogue modale ou non modale.  
  
 Si vous développez une boîte de dialogue à la main, vous ajoutez les variables membres nécessaires à la classe dérivée de la boîte de dialogue vous-même, et vous ajoutez des fonctions membres pour définir ou obtenir ces valeurs.  
  
 Une boîte de dialogue ferme automatiquement lorsque l’utilisateur appuie sur le bouton OK ou annuler ou lorsque votre code appelle la `EndDialog` fonction membre.  
  
 Lorsque vous implémentez une boîte de dialogue non modale, vous devez toujours remplacer le `OnCancel` fonction membre et appelez `DestroyWindow` à partir de qu’il contient. N’appelez pas la classe de base `CDialog::OnCancel`, car il appelle `EndDialog`, ce qui rendra la boîte de dialogue invisibles mais détruira pas. Vous devez également substituer `PostNcDestroy` pour les boîtes de dialogue non modales pour supprimer **cela**, étant donné que les boîtes de dialogue non modales sont généralement alloués avec **nouveau**. Boîtes de dialogue modales sont généralement construits sur le frame et ne doivent pas `PostNcDestroy` nettoyage.  
  
 Pour plus d’informations sur `CDialog`, voir :  
  
- [Boîtes de dialogue](../../mfc/dialog-boxes.md)  
  
-   L’article de la Base de connaissances Q262954 : comment faire : créer une boîte de dialogue redimensionnables avec barres de défilement  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-namecdialoga--cdialogcdialog"></a><a name="cdialog"></a>CDialog::CDialog  
 Pour construire une boîte de dialogue basée sur la ressource, appelez une forme du constructeur public.  
  
```  
explicit CDialog(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
explicit CDialog(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);  
  
CDialog();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Contient une chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Remarques  
 Un formulaire du constructeur fournit l’accès à la ressource de boîte de dialogue Nom du modèle. L’autre constructeur offre un accès par numéro de modèle, généralement un **IDD_** préfixe (par exemple, IDD_DIALOG1).  
  
 Pour construire une boîte de dialogue modale à partir d’un modèle en mémoire, tout d’abord appeler le constructeur sans paramètre, protégé, puis appeler `InitModalIndirect`.  
  
 Une fois que vous construisez une boîte de dialogue modale avec l’une de ces méthodes, appelez `DoModal`.  
  
 Pour construire une boîte de dialogue non modale, utilisez la forme protégée de la `CDialog` constructeur. Le constructeur est protégé, car vous devez dériver votre propre classe de la boîte de dialogue pour implémenter une boîte de dialogue non modale. Construction d’une boîte de dialogue non modale est un processus en deux étapes. Tout d’abord appeler le constructeur ; puis appelez le **créer** fonction membre pour créer une boîte de dialogue basée sur la ressource, ou appeler `CreateIndirect` pour créer la boîte de dialogue à partir d’un modèle en mémoire.  
  
##  <a name="a-namecreatea--cdialogcreate"></a><a name="create"></a>CDialog::Create  
 Appelez **créer** pour créer une boîte de dialogue non modale à l’aide d’un modèle de boîte de dialogue à partir d’une ressource.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
virtual BOOL Create(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Contient une chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parent (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
### <a name="return-value"></a>Valeur de retour  
 Les deux formes de retour différent de zéro si l’initialisation et la création de la boîte de dialogue ont réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez placer l’appel à **créer** dans le constructeur ou un appel après que le constructeur est appelé.  
  
 Deux formes de la **créer** fonction membre sont fournis pour accéder à la ressource modèle de boîte de dialogue par le nom du modèle ou numéro d’ID de modèle (par exemple, IDD_DIALOG1).  
  
 Pour un formulaire, passez un pointeur à l’objet de fenêtre parent. Si `pParentWnd` est **NULL**, la boîte de dialogue s’affichera avec sa fenêtre parente ou propriétaire défini dans la fenêtre principale de l’application.  
  
 Le **créer** fonction membre retourne immédiatement après avoir créé la boîte de dialogue.  
  
 Utilisez le **WS_VISIBLE** de style dans le modèle de boîte de dialogue si la boîte de dialogue doit s’afficher lors de la création de la fenêtre parente. Dans le cas contraire, vous devez appeler `ShowWindow`. Pour les autres styles de la boîte de dialogue et leur application, consultez la [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] et [Styles de fenêtre](../../mfc/reference/window-styles.md) dans les *référence MFC*.  
  
 Utilisez le `CWnd::DestroyWindow` fonction pour détruire une boîte de dialogue créée par le **créer** (fonction).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#62;](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="a-namecreateindirecta--cdialogcreateindirect"></a><a name="createindirect"></a>CDialog::CreateIndirect  
 Appelez cette fonction membre pour créer une boîte de dialogue non modale à partir d’un modèle de boîte de dialogue en mémoire.  
  
```  
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpDialogTemplate`  
 Pointe vers une mémoire qui contient un modèle de boîte de dialogue permet de créer la boîte de dialogue. Ce modèle est sous la forme d’un [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) informations de structure et de contrôle, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parent de l’objet de la boîte de dialogue (de type [CWnd](../../mfc/reference/cwnd-class.md)). S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `lpDialogInit`  
 Pointe vers une **DLGINIT** ressource.  
  
 `hDialogTemplate`  
 Contient un handle de mémoire globale contenant un modèle de boîte de dialogue. Ce modèle est sous la forme d’un **DLGTEMPLATE** structure et les données pour chaque contrôle dans la boîte de dialogue.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la boîte de dialogue a été créée et initialisée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Le `CreateIndirect` fonction membre retourne immédiatement après avoir créé la boîte de dialogue.  
  
 Utilisez le **WS_VISIBLE** de style dans le modèle de boîte de dialogue si la boîte de dialogue doit s’afficher lors de la création de la fenêtre parente. Dans le cas contraire, vous devez appeler `ShowWindow` pour qu’elle apparaisse. Pour plus d’informations sur comment vous pouvez spécifier les autres styles de la boîte de dialogue dans le modèle, consultez la [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Utilisez le `CWnd::DestroyWindow` fonction pour détruire une boîte de dialogue créée par le `CreateIndirect` (fonction).  
  
 Boîtes de dialogue qui contiennent des contrôles ActiveX requièrent des informations supplémentaires fournies dans un **DLGINIT** ressource. Pour plus d’informations, consultez l’article de la Base de connaissances Q231591, « comment faire : utiliser un modèle de boîte de dialogue pour créer une boîte de dialogue MFC avec un contrôle ActiveX. » Articles de la Base de connaissances sont disponibles dans la documentation Visual Studio de MSDN Library ou à [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-namedomodala--cdialogdomodal"></a><a name="domodal"></a>CDialog::DoModal  
 Appelez cette fonction membre pour appeler la boîte de dialogue modale et retourne le résultat de la boîte de dialogue lorsque vous avez terminé.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `int` valeur qui spécifie la valeur de la `nResult` paramètre passé à la [CDialog::EndDialog](#enddialog) fonction membre, qui est utilisée pour fermer la boîte de dialogue. La valeur de retour est égale à –&1; si la fonction n’a pas pu créer la boîte de dialogue ou **IDABORT** si une autre erreur s’est produite, auquel cas la fenêtre de sortie contient des informations d’erreurs [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre gère l’interaction avec l’utilisateur pendant que la boîte de dialogue est active. C’est ce qui rend la boîte de dialogue modale ; Autrement dit, l’utilisateur ne peut pas interagir avec d’autres fenêtres jusqu'à ce que la boîte de dialogue est fermée.  
  
 Si l’utilisateur clique sur les boutons de commande dans la boîte de dialogue, tel que OK ou annuler, une fonction membre gestionnaire de messages, tel que [OnOK](#onok) ou [OnCancel](#oncancel), est appelé pour tenter de fermer la boîte de dialogue. La valeur par défaut `OnOK` fonction membre valider et mettre à jour les données de la boîte de dialogue et fermez la boîte de dialogue avec un résultat **IDOK**et la valeur par défaut `OnCancel` fonction membre se ferme la boîte de dialogue avec un résultat **IDCANCEL** sans validation ou de mise à jour les données de la boîte de dialogue. Vous pouvez remplacer ces fonctions de gestionnaire de messages pour modifier leur comportement.  
  
> [!NOTE]
> `PreTranslateMessage`est désormais appelée pour le traitement de message de boîte de boîte de dialogue modale.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#63;](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="a-nameenddialoga--cdialogenddialog"></a><a name="enddialog"></a>CDialog::EndDialog  
 Appelez cette fonction membre pour mettre fin à une boîte de dialogue modale.  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>Paramètres  
 `nResult`  
 Contient la valeur à retourner à partir de la boîte de dialogue à l’appelant de `DoModal`.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre retourne `nResult` en tant que valeur de retour de `DoModal`. Vous devez utiliser le `EndDialog` fonction terminer le traitement dès la création d’une boîte de dialogue modale.  
  
 Vous pouvez appeler `EndDialog` à tout moment, même en [OnInitDialog](#oninitdialog), auquel cas vous devez fermer la boîte de dialogue avant qu’il est affichée ou avant de définir le focus d’entrée.  
  
 `EndDialog`ne fermez pas la boîte de dialogue immédiatement. Au lieu de cela, il définit un indicateur qui indique à la boîte de dialogue Fermer dès le Gestionnaire de messages en cours.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#64;](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#65;](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="a-namegetdefida--cdialoggetdefid"></a><a name="getdefid"></a>CDialog::GetDefID  
 Appelez le `GetDefID` fonction membre pour obtenir l’ID du contrôle par défaut pour une boîte de dialogue.  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur de 32 bits ( `DWORD`). Si le bouton de commande par défaut a une valeur d’ID, le mot de poids fort contient **DC_HASDEFID** et le mot de poids faible contient la valeur d’ID. Si le bouton de commande par défaut n’a pas une valeur d’ID, la valeur de retour est 0.  
  
### <a name="remarks"></a>Remarques  
 Il s’agit généralement d’un bouton OK.  
  
##  <a name="a-namegotodlgctrla--cdialoggotodlgctrl"></a><a name="gotodlgctrl"></a>CDialog::GotoDlgCtrl  
 Déplace le focus vers le contrôle spécifié dans la boîte de dialogue.  
  
```  
void GotoDlgCtrl(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWndCtrl`  
 Identifie la fenêtre (contrôle) qui doit recevoir le focus.  
  
### <a name="remarks"></a>Notes  
 Pour obtenir un pointeur vers le contrôle (fenêtre enfant) pour passer en tant que `pWndCtrl`, appelez le `CWnd::GetDlgItem` fonction membre, qui retourne un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem).  
  
##  <a name="a-nameinitmodalindirecta--cdialoginitmodalindirect"></a><a name="initmodalindirect"></a>CDialog::InitModalIndirect  
 Appelez cette fonction membre pour initialiser un objet de la boîte de dialogue modale à l’aide d’un modèle de boîte de dialogue que vous construisez dans la mémoire.  
  
```  
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpDialogTemplate`  
 Pointe vers une mémoire qui contient un modèle de boîte de dialogue permet de créer la boîte de dialogue. Ce modèle est sous la forme d’un [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) informations de structure et de contrôle, comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `hDialogTemplate`  
 Contient un handle de mémoire globale contenant un modèle de boîte de dialogue. Ce modèle est sous la forme d’un **DLGTEMPLATE** structure et les données pour chaque contrôle dans la boîte de dialogue.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `lpDialogInit`  
 Pointe vers une **DLGINIT** ressource.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet de la boîte de dialogue a été créé et initialisé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Pour créer une boîte de dialogue modale indirectement, tout d’abord allouer un bloc de mémoire global et le remplir avec le modèle de boîte de dialogue. Appelez ensuite la vider `CDialog` constructeur pour construire l’objet de la boîte de dialogue. Ensuite, appelez `InitModalIndirect` pour stocker votre handle pour le modèle de boîte de dialogue en mémoire. La boîte de dialogue Windows est créée et affichée par la suite, quand le [DoModal](#domodal) la fonction membre est appelée.  
  
 Boîtes de dialogue qui contiennent des contrôles ActiveX requièrent des informations supplémentaires fournies dans un **DLGINIT** ressource. Pour plus d’informations, consultez l’article de la Base de connaissances Q231591, « comment faire : utiliser un modèle de boîte de dialogue pour créer une boîte de dialogue MFC avec un contrôle ActiveX. » Articles de la Base de connaissances sont disponibles dans la documentation Visual Studio de MSDN Library ou à [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-namemapdialogrecta--cdialogmapdialogrect"></a><a name="mapdialogrect"></a>CDialog::MapDialogRect  
 L’appel à convertir les unités de boîte de dialogue d’un rectangle en unités d’écran.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui contient la boîte de dialogue coordonnées à convertir.  
  
### <a name="remarks"></a>Notes  
 Unités de boîte de dialogue sont exprimées dans l’unité de base de la boîte de dialogue actuelle dérivée de la largeur moyenne et la hauteur des caractères de la police utilisée pour le texte de la boîte de dialogue. Une unité horizontale est un quart de l’unité de largeur de la base de la boîte de dialogue et une unité verticale est un huitième de l’unité de base hauteur de la boîte de dialogue.  
  
 Le **GetDialogBaseUnits** fonction Windows retourne des informations sur la taille de la police système, mais vous pouvez spécifier une police différente pour chaque boîte de dialogue si vous utilisez la **DS_SETFONT** style dans le fichier de définition de la ressource. Le `MapDialogRect` fonction Windows utilise la police appropriée pour cette boîte de dialogue.  
  
 Le `MapDialogRect` fonction membre remplace les unités de boîte de dialogue de `lpRect` avec afin que le rectangle peut être utilisé pour créer une boîte de dialogue ou la position d’un contrôle dans une zone de l’écran unités (pixels).  
  
##  <a name="a-namenextdlgctrla--cdialognextdlgctrl"></a><a name="nextdlgctrl"></a>CDialog::NextDlgCtrl  
 Déplace le focus vers le contrôle suivant dans la boîte de dialogue.  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Notes  
 Si le focus est sur le dernier contrôle de la boîte de dialogue, il déplace vers le premier contrôle.  
  
##  <a name="a-nameoncancela--cdialogoncancel"></a><a name="oncancel"></a>CDialog::OnCancel  
 Le framework appelle cette méthode lorsque l’utilisateur clique sur **Annuler** ou appuie sur la touche ÉCHAP dans une boîte de dialogue modale ou non modale.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour effectuer des actions (telles que la restauration des données anciennes) lorsqu’un utilisateur ferme la boîte de dialogue en cliquant sur **Annuler** ou en appuyant sur la touche ÉCHAP. La valeur par défaut ferme la boîte de dialogue modale en appelant [EndDialog](#enddialog) et [DoModal](#domodal) pour renvoyer IDCANCEL.  
  
 Si vous implémentez le **Annuler** bouton dans une boîte de dialogue non modale, vous devez substituer les `OnCancel` méthode et appeler [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) qu’elle contient. N’appelez pas la méthode de classe de base, car il appelle `EndDialog`, qui sera masquer la boîte de dialogue, mais pas la détruire.  
  
> [!NOTE]
>  Vous ne pouvez pas remplacer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous Windows XP. Pour plus d’informations sur `CFileDialog`, consultez [classe CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#66;](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="a-nameoninitdialoga--cdialogoninitdialog"></a><a name="oninitdialog"></a>CDialog::OnInitDialog  
 Cette méthode est appelée en réponse à la `WM_INITDIALOG` message.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Spécifie si l’application a défini le focus d’entrée à l’un des contrôles dans la boîte de dialogue. Si `OnInitDialog` retourne zéro, Windows définit le focus d’entrée à l’emplacement par défaut, le premier contrôle dans la boîte de dialogue. L’application peut retourner 0 uniquement si elle a défini explicitement le focus d’entrée sur un des contrôles dans la boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Windows envoie les `WM_INITDIALOG` message à la boîte de dialogue lors de la [créer](#create), [CreateIndirect](#createindirect), ou [DoModal](#domodal) appels, qui se produisent immédiatement avant l’affichage de la boîte de dialogue.  
  
 Substituez cette méthode si vous souhaitez exécuter un traitement spécial lors de l’initialisation de la boîte de dialogue. Dans la version substituée, appelez d’abord la classe de base `OnInitDialog` mais ignorez sa valeur de retour. Vous renverrez généralement `TRUE` à partir de votre méthode de substitution.  
  
 Appels Windows le `OnInitDialog` fonction à l’aide de la procédure standard global-boîte de dialogue commune à toutes les boîtes de dialogue Microsoft Foundation Class Library. Il n’appelle pas cette fonction via votre table des messages, et par conséquent, il est inutile une entrée dans la table message pour cette méthode.  
  
> [!NOTE]
>  Vous ne pouvez pas remplacer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Pour plus d’informations sur la modification de `CFileDialog` sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] voir [classe CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#67;](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="a-nameonoka--cdialogonok"></a><a name="onok"></a>CDialog::OnOK  
 Appelé lorsque l’utilisateur clique sur le **OK** bouton (le bouton avec un ID de IDOK).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour effectuer des actions lors de la **OK** bouton est activé. Si la boîte de dialogue comprend l’échange et validation de données automatique, l’implémentation par défaut de cette méthode valide les données de boîte de dialogue et met à jour les variables appropriées dans votre application.  
  
 Si vous implémentez le **OK** bouton dans une boîte de dialogue non modale, vous devez substituer les `OnOK` méthode et appeler [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) qu’elle contient. N’appelez pas la méthode de classe de base, car il appelle [EndDialog](#enddialog) qui rend la boîte de dialogue invisible, mais ne la supprime pas.  
  
> [!NOTE]
>  Vous ne pouvez pas remplacer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous Windows XP. Pour plus d’informations sur `CFileDialog`, consultez [classe CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#68;](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="a-nameonsetfonta--cdialogonsetfont"></a><a name="onsetfont"></a>CDialog::OnSetFont  
 Spécifie la police de qu'un contrôle de boîte de dialogue utilise pour dessiner du texte.  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFont`  
 Spécifie un pointeur vers la police qui va être utilisé comme la police par défaut pour tous les contrôles dans cette boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 La boîte de dialogue utilisera la police spécifiée comme la valeur par défaut de tous ses contrôles.  
  
 Généralement, l’éditeur de boîtes de dialogue définit la police de la boîte de dialogue dans le cadre de la ressource de modèle de boîte de dialogue.  
  
> [!NOTE]
>  Vous ne pouvez pas remplacer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Pour plus d’informations sur la modification de `CFileDialog` sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] voir [classe CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
##  <a name="a-nameprevdlgctrla--cdialogprevdlgctrl"></a><a name="prevdlgctrl"></a>CDialog::PrevDlgCtrl  
 Définit le focus au contrôle précédent dans la boîte de dialogue.  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Remarques  
 Si le focus se trouve sur le premier contrôle dans la boîte de dialogue, il déplace vers le dernier contrôle dans la zone.  
  
##  <a name="a-namesetdefida--cdialogsetdefid"></a><a name="setdefid"></a>CDialog::SetDefID  
 Remplace le contrôle par défaut pour une boîte de dialogue.  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Spécifie l’ID du contrôle des qui deviendra la valeur par défaut.  
  
##  <a name="a-namesethelpida--cdialogsethelpid"></a><a name="sethelpid"></a>CDialog::SetHelpID  
 Définit un ID d’aide contextuelle pour la boîte de dialogue.  
  
```  
void SetHelpID(UINT nIDR);
```  
  
### <a name="parameters"></a>Paramètres  
 *nIDR*  
 Spécifie l’ID d’aide contextuelle.  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple DLGCBR32](../../visual-cpp-samples.md)   
 [Exemple MFC DLGTEMPL](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)


