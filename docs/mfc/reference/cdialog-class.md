---
title: CDialog (classe) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CDialog [MFC], CDialog
- CDialog [MFC], Create
- CDialog [MFC], CreateIndirect
- CDialog [MFC], DoModal
- CDialog [MFC], EndDialog
- CDialog [MFC], GetDefID
- CDialog [MFC], GotoDlgCtrl
- CDialog [MFC], InitModalIndirect
- CDialog [MFC], MapDialogRect
- CDialog [MFC], NextDlgCtrl
- CDialog [MFC], OnInitDialog
- CDialog [MFC], OnSetFont
- CDialog [MFC], PrevDlgCtrl
- CDialog [MFC], SetDefID
- CDialog [MFC], SetHelpID
- CDialog [MFC], OnCancel
- CDialog [MFC], OnOK
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43f36dae3c383aebedf7e8340188e78961066a30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="cdialog-class"></a>CDialog (classe)
La classe de base utilisée pour afficher des boîtes de dialogue sur l’écran.  
  
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
|[CDialog::CreateIndirect](#createindirect)|Crée une boîte de dialogue non modale à partir d’un modèle de boîte de dialogue en mémoire (non ressource de base).|  
|[CDialog::DoModal](#domodal)|Appelle une boîte de dialogue modale et retourne lorsqu’il est terminé.|  
|[CDialog::EndDialog](#enddialog)|Ferme la boîte de dialogue modale.|  
|[CDialog::GetDefID](#getdefid)|Obtient l’ID du contrôle par défaut pour une boîte de dialogue.|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|Déplace le focus à un contrôle de boîte de dialogue spécifiée dans la boîte de dialogue.|  
|[CDialog::InitModalIndirect](#initmodalindirect)|Crée une boîte de dialogue modale à partir d’un modèle de boîte de dialogue en mémoire (non ressource de base). Les paramètres sont stockées jusqu'à ce que la fonction `DoModal` est appelée.|  
|[CDialog::MapDialogRect](#mapdialogrect)|Convertit les unités de boîte de dialogue d’un rectangle en unités de l’écran.|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|Déplace le focus vers le contrôle suivant de la boîte de dialogue dans la boîte de dialogue.|  
|[CDialog::OnInitDialog](#oninitdialog)|Substituez pour augmenter l’initialisation de la boîte de dialogue.|  
|[CDialog::OnSetFont](#onsetfont)|Substituer pour indiquer la police à un contrôle de boîte de dialogue consiste à utiliser lorsqu’il dessine le texte.|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|Déplace le focus vers le contrôle précédent de la boîte de dialogue dans la boîte de dialogue.|  
|[CDialog::SetDefID](#setdefid)|Modifie la valeur par défaut du contrôle pour une boîte de dialogue pour un bouton de commande spécifié.|  
|[CDialog::SetHelpID](#sethelpid)|Définit un ID de l’aide contextuelle pour la boîte de dialogue.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|Substituez pour effectuer le bouton Annuler ou l’action de touche ÉCHAP. La valeur par défaut ferme la boîte de dialogue et **DoModal** retourne **IDCANCEL**.|  
|[CDialog::OnOK](#onok)|Substituez pour effectuer l’action du bouton OK dans la boîte de dialogue modale. La valeur par défaut ferme la boîte de dialogue et `DoModal` retourne **IDOK**.|  
  
## <a name="remarks"></a>Notes  
 Boîtes de dialogue sont de deux types : modales et non modales. Boîte de dialogue modale doit être fermée par l’utilisateur avant que l’application continue. Une boîte de dialogue non modale permet à l’utilisateur afficher la boîte de dialogue et revenir à une autre tâche sans l’annulation ou la suppression de la boîte de dialogue.  
  
 A `CDialog` objet est une combinaison d’un modèle de boîte de dialogue et un `CDialog`-classe dérivée. Utilisez l’éditeur de boîte de dialogue pour créer le modèle de boîte de dialogue et le stocker dans une ressource, puis utiliser l’Assistant Ajouter une classe pour créer une classe dérivée de `CDialog`.  
  
 Une boîte de dialogue, comme toute autre fenêtre reçoit des messages à partir de Windows. Une boîte de dialogue vous intéressent particulièrement lors du traitement des messages de notification à partir de contrôles de la boîte de dialogue, car c’est la façon dont l’utilisateur interagit avec votre boîte de dialogue. Utilisez la fenêtre Propriétés pour sélectionner les messages que vous le souhaitez pour gérer et il ajoute les entrées de table des messages appropriée et les fonctions membres de gestionnaire de messages à la classe pour vous. Vous devez écrire du code spécifique à l’application dans les fonctions membres de gestionnaire uniquement.  
  
 Si vous préférez, vous pouvez toujours écrire des entrées de table des messages et les fonctions membres manuellement.  
  
 Dans tous les la plus simple de la boîte de dialogue, vous ajoutez des variables membres à votre classe de boîte de dialogue dérivée pour stocker les données entrées par l’utilisateur dans les contrôles de la boîte de dialogue ou pour afficher des données pour l’utilisateur. Vous pouvez utiliser l’Assistant Ajouter une Variable à créer des variables de membre et les associer à des contrôles. En même temps, vous choisissez un type de variable et de la plage autorisée de valeurs pour chaque variable. L’Assistant de code ajoute les variables de membre à votre classe dérivée de boîte de dialogue.  
  
 Un mappage de données est généré pour gérer automatiquement l’échange de données entre les variables de membre et des contrôles de la boîte de dialogue. Le mappage de données fournit des fonctions pour initialiser les contrôles dans la boîte de dialogue avec les valeurs correctes, récupèrent les données et valident les données.  
  
 Pour créer une boîte de dialogue modale, construisez un objet sur la pile à l’aide du constructeur pour votre classe dérivée de boîte de dialogue, puis appelez `DoModal` pour créer la fenêtre de dialogue et ses contrôles. Si vous souhaitez créer une boîte de dialogue non modale, appelez **créer** dans le constructeur de votre classe de boîte de dialogue.  
  
 Vous pouvez également créer un modèle en mémoire en utilisant un [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) structure de données comme décrit dans le Kit de développement logiciel Windows. Après avoir construit un `CDialog` de l’objet, appelez [CreateIndirect](#createindirect) pour créer un non modal boîte de dialogue, ou appelez [InitModalIndirect](#initmodalindirect) et [DoModal](#domodal) pour créer un modal boîte de dialogue.  
  
 Le mappage de données exchange et la validation est écrit dans une substitution de `CWnd::DoDataExchange` qui est ajouté à votre nouvelle classe de boîte de dialogue. Consultez le [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) fonction membre dans `CWnd` pour plus d’informations sur la fonctionnalité d’échange et validation.  
  
 Le programmeur et l’appel de framework `DoDataExchange` indirectement via un appel à [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata).  
  
 Le framework appelle `UpdateData` lorsque l’utilisateur clique sur le bouton OK pour fermer la boîte de dialogue modale. (Les données ne sont récupérées si le bouton Annuler est activé.) L’implémentation par défaut de [OnInitDialog](#oninitdialog) appelle également `UpdateData` pour définir les valeurs initiales des contrôles. En règle générale, vous substituez `OnInitDialog` pour initialiser des contrôles. `OnInitDialog` est appelée une fois que tous les contrôles de boîte de dialogue sont créés et juste avant la boîte de dialogue s’affiche.  
  
 Vous pouvez appeler `CWnd::UpdateData` à tout moment pendant l’exécution d’une boîte de dialogue modale ou non.  
  
 Si vous développez une boîte de dialogue à la main, vous ajoutez les variables membres nécessaires à la classe dérivée de la boîte de dialogue vous-même, et vous ajoutez des fonctions membres pour définir ou obtenir ces valeurs.  
  
 Une boîte de dialogue ferme automatiquement lorsque l’utilisateur appuie sur les boutons OK ou annuler ou lorsque votre code appelle la `EndDialog` fonction membre.  
  
 Lorsque vous implémentez une boîte de dialogue non modale, vous devez toujours remplacer le `OnCancel` fonction membre et appelez `DestroyWindow` à partir de qu’il contient. N’appelez pas la classe de base `CDialog::OnCancel`, car il appelle `EndDialog`, qui permettront à la boîte de dialogue invisibles mais détruira pas. Vous devez également substituer `PostNcDestroy` pour les boîtes de dialogue non modale afin de supprimer **cela**, étant donné que les boîtes de dialogue non modales sont généralement alloués avec **nouveau**. Boîtes de dialogue modales sont généralement construits sur le frame et n’avez pas besoin de `PostNcDestroy` nettoyage.  
  
 Pour plus d’informations sur `CDialog`, consultez :  
  
- [Boîtes de dialogue](../../mfc/dialog-boxes.md)  
  
-   L’article de la Base de connaissances Q262954 : comment faire : créer une boîte de dialogue redimensionnables avec barres de défilement  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cdialog"></a>  CDialog::CDialog  
 Pour construire une boîte de dialogue basée sur la ressource, appelez des deux formes public du constructeur.  
  
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
 Contient une chaîne se terminant par null qui est le nom d’une ressource de modèle de boîte de dialogue.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource de modèle de boîte de dialogue.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Notes  
 Une forme du constructeur permet d’accéder à la ressource de boîte de dialogue par le nom du modèle. L’autre constructeur fournit l’accès par numéro d’ID de modèle, généralement avec un **IDD_** préfixe (par exemple, IDD_DIALOG1).  
  
 Pour construire une boîte de dialogue modale à partir d’un modèle en mémoire, tout d’abord appeler le constructeur sans paramètre, protégé, puis appelez `InitModalIndirect`.  
  
 Une fois que vous construisez une boîte de dialogue modale avec l’une des méthodes ci-dessus, appelez `DoModal`.  
  
 Pour construire une boîte de dialogue non modale, utilisez la forme protégée de la `CDialog` constructeur. Le constructeur est protégé, car vous devez dériver votre propre classe de boîte de dialogue pour implémenter une boîte de dialogue non modale. Construction d’une boîte de dialogue non modale est un processus en deux étapes. Tout d’abord appeler le constructeur ; Appelez ensuite la **créer** fonction membre pour créer une boîte de dialogue basées sur une ressource, ou appeler `CreateIndirect` pour créer la boîte de dialogue à partir d’un modèle en mémoire.  
  
##  <a name="create"></a>  CDialog::Create  
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
 Contient une chaîne se terminant par null qui est le nom d’une ressource de modèle de boîte de dialogue.  
  
 `pParentWnd`  
 Pointe vers l’objet de la fenêtre parente (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource de modèle de boîte de dialogue.  
  
### <a name="return-value"></a>Valeur de retour  
 Les deux formes de retour différent de zéro si l’initialisation et la création de la boîte de dialogue a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez placer l’appel à **créer** dans le constructeur ou un appel après que le constructeur est appelé.  
  
 Deux formes de la **créer** fonction membre sont fournis pour accéder à la ressource de modèle de boîte de dialogue par le nom du modèle ou numéro d’ID de modèle (par exemple, IDD_DIALOG1).  
  
 Pour un formulaire, passez un pointeur à l’objet de fenêtre parent. Si `pParentWnd` est **NULL**, la boîte de dialogue sera créée avec sa fenêtre parente ou propriétaire défini dans la fenêtre principale de l’application.  
  
 Le **créer** fonction membre retourne immédiatement après avoir créé la boîte de dialogue.  
  
 Utilisez le **WS_VISIBLE** de style dans le modèle de boîte de dialogue si la boîte de dialogue doit apparaître lors de la création de la fenêtre parente. Sinon, vous devez appeler `ShowWindow`. Pour obtenir les styles de la boîte de dialogue et leur application, consultez la [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) structure dans le SDK Windows et [Styles de fenêtre](../../mfc/reference/styles-used-by-mfc.md#window-styles) dans les *référence MFC*.  
  
 Utilisez le `CWnd::DestroyWindow` fonction pour détruire une boîte de dialogue créée par le **créer** (fonction).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="createindirect"></a>  CDialog::CreateIndirect  
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
 Pointe vers la mémoire qui contient un modèle de boîte de dialogue permet de créer la boîte de dialogue. Ce modèle est sous la forme d’un [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) informations de structure et de contrôle, comme décrit dans le Kit de développement logiciel Windows.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parent de l’objet de la boîte de dialogue (de type [CWnd](../../mfc/reference/cwnd-class.md)). S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `lpDialogInit`  
 Pointe vers un **DLGINIT** ressource.  
  
 `hDialogTemplate`  
 Contient un handle de mémoire globale contenant un modèle de boîte de dialogue. Ce modèle est sous la forme d’un **DLGTEMPLATE** structure et les données pour chaque contrôle dans la boîte de dialogue.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la boîte de dialogue a été créée et initialisée avec succès ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Le `CreateIndirect` fonction membre retourne immédiatement après avoir créé la boîte de dialogue.  
  
 Utilisez le **WS_VISIBLE** de style dans le modèle de boîte de dialogue si la boîte de dialogue doit apparaître lors de la création de la fenêtre parente. Sinon, vous devez appeler `ShowWindow` pour qu’elle apparaisse. Pour plus d’informations sur la façon dont vous pouvez spécifier des autres styles de boîte de dialogue dans le modèle, consultez la [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) structure dans le SDK Windows.  
  
 Utilisez le `CWnd::DestroyWindow` fonction pour détruire une boîte de dialogue créée par le `CreateIndirect` (fonction).  
  
 Boîtes de dialogue qui contiennent des contrôles ActiveX nécessitent des informations supplémentaires fournies dans un **DLGINIT** ressource. Pour plus d’informations, consultez l’article de la Base de connaissances Q231591, « comment faire : utiliser un modèle de boîte de dialogue pour créer une boîte de dialogue MFC avec un contrôle ActiveX. » Articles de la Base de connaissances sont disponibles dans [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="domodal"></a>  CDialog::DoModal  
 Appelez cette fonction membre pour appeler la boîte de dialogue modale et retourner le résultat de la boîte de dialogue lorsque vous avez terminé.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `int` valeur qui spécifie la valeur de la `nResult` paramètre qui a été transmis à la [CDialog::EndDialog](#enddialog) fonction membre, qui est utilisée pour fermer la boîte de dialogue. La valeur de retour est -1 si la fonction n’a pas pu créer la boîte de dialogue ou **IDABORT** si une autre erreur s’est produite, auquel cas la fenêtre sortie contient des informations d’erreur à partir de [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre gère toutes les interactions avec l’utilisateur pendant que la boîte de dialogue est active. C’est ce qui rend la boîte de dialogue modale ; Autrement dit, l’utilisateur ne peut pas interagir avec d’autres fenêtres jusqu'à ce que la boîte de dialogue est fermée.  
  
 Si l’utilisateur clique sur un des boutons des commande dans la boîte de dialogue, telles que OK ou sur Annuler, une fonction membre de gestionnaire de messages, tels que [OnOK](#onok) ou [OnCancel](#oncancel), est appelé pour tenter de fermer la boîte de dialogue. La valeur par défaut `OnOK` fonction membre valider et mettre à jour les données de la boîte de dialogue et fermer la boîte de dialogue avec un résultat **IDOK**et la valeur par défaut `OnCancel` fonction membre ferme la boîte de dialogue avec un résultat  **IDCANCEL** sans validation ou de mise à jour les données de la boîte de dialogue. Vous pouvez remplacer ces fonctions de gestionnaire de messages pour modifier leur comportement.  
  
> [!NOTE]
> `PreTranslateMessage` est maintenant appelé pour le traitement du message de zone de boîte de dialogue modale.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="enddialog"></a>  CDialog::EndDialog  
 Appelez cette fonction membre pour mettre fin à une boîte de dialogue modale.  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>Paramètres  
 `nResult`  
 Contient la valeur à retourner à partir de la boîte de dialogue à l’appelant de `DoModal`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre retourne `nResult` en tant que valeur de retour de `DoModal`. Vous devez utiliser le `EndDialog` fonction terminer le traitement de chaque fois qu’une boîte de dialogue modale est créée.  
  
 Vous pouvez appeler `EndDialog` à tout moment, même dans [OnInitDialog](#oninitdialog), auquel cas vous devez fermer la boîte de dialogue avant qu’il est affichée ou avant de définir le focus d’entrée.  
  
 `EndDialog` ne fermez pas immédiatement la boîte de dialogue. Au lieu de cela, il définit un indicateur qui dirige la boîte de dialogue Fermer dès le Gestionnaire de messages en cours.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="getdefid"></a>  CDialog::GetDefID  
 Appelez le `GetDefID` fonction membre pour obtenir l’ID du contrôle par défaut pour une boîte de dialogue.  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur de 32 bits ( `DWORD`). Si le bouton de commande par défaut a une valeur d’ID, le mot de poids fort contient **DC_HASDEFID** et le mot de poids faible contient la valeur d’ID. Si le bouton de commande par défaut n’a pas une valeur d’ID, la valeur de retour est 0.  
  
### <a name="remarks"></a>Notes  
 Il s’agit généralement d’un bouton OK.  
  
##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl  
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
  
##  <a name="initmodalindirect"></a>  CDialog::InitModalIndirect  
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
 Pointe vers la mémoire qui contient un modèle de boîte de dialogue permet de créer la boîte de dialogue. Ce modèle est sous la forme d’un [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) informations de structure et de contrôle, comme décrit dans le Kit de développement logiciel Windows.  
  
 `hDialogTemplate`  
 Contient un handle de mémoire globale contenant un modèle de boîte de dialogue. Ce modèle est sous la forme d’un **DLGTEMPLATE** structure et les données pour chaque contrôle dans la boîte de dialogue.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `lpDialogInit`  
 Pointe vers un **DLGINIT** ressource.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet de la boîte de dialogue a été créé et initialisé avec succès ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Pour créer une boîte de dialogue modale indirectement, tout d’abord allouer un bloc global de mémoire et le remplir avec le modèle de boîte de dialogue. Appelez ensuite la vide `CDialog` constructeur pour construire l’objet de la boîte de dialogue. Ensuite, appelez `InitModalIndirect` pour stocker votre handle pour le modèle de boîte de dialogue en mémoire. La boîte de dialogue Windows est créée et affichée par la suite, quand le [DoModal](#domodal) fonction membre est appelée.  
  
 Boîtes de dialogue qui contiennent des contrôles ActiveX nécessitent des informations supplémentaires fournies dans un **DLGINIT** ressource. Pour plus d’informations, consultez l’article de la Base de connaissances Q231591, « comment faire : utiliser un modèle de boîte de dialogue pour créer une boîte de dialogue MFC avec un contrôle ActiveX. » Articles de la Base de connaissances sont disponibles dans [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect  
 L’appel à convertir les unités de boîte de dialogue d’un rectangle en unités de l’écran.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers un [RECT](../../mfc/reference/rect-structure1.md) structure ou [CRect](../../atl-mfc-shared/reference/crect-class.md) coordonne l’objet qui contient la boîte de dialogue à convertir.  
  
### <a name="remarks"></a>Notes  
 Unités de boîte de dialogue sont exprimées dans l’unité de base de la boîte de dialogue actuelle dérivée de la largeur moyenne et la hauteur des caractères de la police utilisée pour le texte de la boîte de dialogue. Une unité horizontale est un quart de l’unité de largeur de la base de la boîte de dialogue et une unité verticale est un huitième de l’unité de base de hauteur de la boîte de dialogue.  
  
 Le **GetDialogBaseUnits** fonction Windows retourne des informations sur la taille de la police système, mais vous pouvez spécifier une police différente pour chaque boîte de dialogue si vous utilisez la **DS_SETFONT** de style dans le fichier de définition de ressource. Le `MapDialogRect` fonction Windows utilise la police appropriée pour cette boîte de dialogue.  
  
 Le `MapDialogRect` fonction membre remplace les unités de boîte de dialogue de `lpRect` avec écran unités (pixels) afin que le rectangle peut être utilisé pour créer une boîte de dialogue ou de positionner un contrôle dans une zone.  
  
##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl  
 Déplace le focus vers le contrôle suivant dans la boîte de dialogue.  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Notes  
 Si le focus est sur le dernier contrôle dans la boîte de dialogue, il déplace vers le premier contrôle.  
  
##  <a name="oncancel"></a>  CDialog::OnCancel  
 L’infrastructure appelle cette méthode lorsque l’utilisateur clique sur **Annuler** ou appuie sur la touche ÉCHAP dans une boîte de dialogue modale ou non.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode pour effectuer des actions (telles que la restauration des données anciennes) lorsqu’un utilisateur ferme la boîte de dialogue en cliquant sur **Annuler** ou en appuyant sur la touche ÉCHAP. La valeur par défaut ferme la boîte de dialogue modale en appelant [EndDialog](#enddialog) et [DoModal](#domodal) pour retourner IDCANCEL.  
  
 Si vous implémentez le **Annuler** bouton dans une boîte de dialogue non modale, vous devez substituer la `OnCancel` méthode et appel [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) qu’il contient. N’appelez pas la méthode de classe de base, parce qu’elle appelle `EndDialog`, qui sera masquer la boîte de dialogue, mais pas la détruire.  
  
> [!NOTE]
>  Vous ne pouvez pas substituer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous Windows XP. Pour plus d’informations sur `CFileDialog`, consultez [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="oninitdialog"></a>  CDialog::OnInitDialog  
 Cette méthode est appelée en réponse à la `WM_INITDIALOG` message.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Spécifie si l’application a défini le focus d’entrée à un des contrôles dans la boîte de dialogue. Si `OnInitDialog` retourne différente de zéro, Windows définit le focus d’entrée à l’emplacement par défaut, le premier contrôle dans la boîte de dialogue. L’application peut retourner 0 uniquement si elle a défini explicitement le focus d’entrée à un des contrôles dans la boîte de dialogue.  
  
### <a name="remarks"></a>Notes  
 Windows envoie les `WM_INITDIALOG` message à la boîte de dialogue lors de la [créer](#create), [CreateIndirect](#createindirect), ou [DoModal](#domodal) appels, qui se produiront immédiatement avant la boîte de dialogue s’affiche.  
  
 Substituez cette méthode si vous souhaitez exécuter un traitement spécial lors de l’initialisation de la boîte de dialogue. Dans la version substituée, commencer par appeler la classe de base `OnInitDialog` mais qu’il ignore la valeur de retour. Retournent généralement `TRUE` à partir de votre méthode de substitution.  
  
 Appels Windows le `OnInitDialog` fonction à l’aide de la procédure de boîte de dialogue global standard commune à toutes les boîtes de dialogue Bibliothèque Microsoft Foundation Class. Il n’appelle pas cette fonction via votre table des messages, et par conséquent, il est inutile une entrée de mappage de message pour cette méthode.  
  
> [!NOTE]
> Vous ne pouvez pas substituer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous Windows Vista ou des systèmes d’exploitation ultérieurs. Pour plus d’informations sur les modifications apportées à `CFileDialog` sous Windows Vista et versions ultérieures, consultez [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="onok"></a>  CDialog::OnOK  
 Appelé lorsque l’utilisateur clique sur le **OK** bouton (le bouton avec un ID de IDOK).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode pour effectuer des actions lorsque le **OK** bouton est activé. Si la boîte de dialogue inclut l’échange et validation de données automatique, l’implémentation par défaut de cette méthode valide les données de boîte de dialogue et les variables appropriées dans votre application des mises à jour.  
  
 Si vous implémentez le **OK** bouton dans une boîte de dialogue non modale, vous devez substituer la `OnOK` méthode et appel [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) qu’il contient. N’appelez pas la méthode de classe de base, parce qu’elle appelle [EndDialog](#enddialog) qui rend la boîte de dialogue invisible, mais ne le supprime pas.  
  
> [!NOTE]
>  Vous ne pouvez pas substituer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous Windows XP. Pour plus d’informations sur `CFileDialog`, consultez [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="onsetfont"></a>  CDialog::OnSetFont  
 Spécifie la police de qu'un contrôle de boîte de dialogue utilisera pour dessiner du texte.  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFont`  
 Spécifie un pointeur vers la police à utiliser en tant que la police par défaut pour tous les contrôles dans cette boîte de dialogue.  
  
### <a name="remarks"></a>Notes  
 La boîte de dialogue utilisera la police spécifiée comme la valeur par défaut de tous ses contrôles.  
  
 En règle générale, l’éditeur de boîte de dialogue définit la police de la boîte de dialogue dans le cadre de la ressource de modèle de boîte de dialogue.  
  
> [!NOTE]
> Vous ne pouvez pas substituer cette méthode lorsque vous utilisez un `CFileDialog` objet dans un programme qui est compilé sous Windows Vista ou des systèmes d’exploitation ultérieurs. Pour plus d’informations sur les modifications apportées à `CFileDialog` sous Windows Vista et versions ultérieures, consultez [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).  
  
##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl  
 Définit le focus au contrôle précédent dans la boîte de dialogue.  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Notes  
 Si le focus est sur le premier contrôle dans la boîte de dialogue, il déplace vers le dernier contrôle dans la zone.  
  
##  <a name="setdefid"></a>  CDialog::SetDefID  
 Modifie la valeur par défaut du contrôle pour une boîte de dialogue.  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Spécifie l’ID du contrôle des qui deviendra la valeur par défaut.  
  
##  <a name="sethelpid"></a>  CDialog::SetHelpID  
 Définit un ID de l’aide contextuelle pour la boîte de dialogue.  
  
```  
void SetHelpID(UINT nIDR);
```  
  
### <a name="parameters"></a>Paramètres  
 *nIDR*  
 Spécifie l’ID de l’aide contextuelle.  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple DLGCBR32](../../visual-cpp-samples.md)   
 [Exemple MFC DLGTEMPL](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)

