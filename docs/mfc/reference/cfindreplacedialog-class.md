---
title: Classe de CFindReplaceDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
dev_langs:
- C++
helpviewer_keywords:
- text searches, replacing text
- text searches, CFindReplaceDialog class
- Find/Replace dialog box
- replacing text, CFindReplaceDialog class
- CFindReplaceDialog class
- replacing text
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
caps.latest.revision: 25
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
ms.openlocfilehash: 510f6a763dbacb7d4e1b14ea808a4baaaf3d6bf3
ms.lasthandoff: 02/24/2017

---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog (classe)
Vous permet d’implémenter des boîtes de dialogue Rechercher/Remplacer standard dans votre application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Appelez cette fonction pour construire un `CFindReplaceDialog` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](#create)|Crée et affiche un `CFindReplaceDialog` boîte de dialogue.|  
|[CFindReplaceDialog::FindNext](#findnext)|Appelez cette fonction pour déterminer si l’utilisateur souhaite rechercher l’occurrence suivante de la chaîne de recherche.|  
|[CFindReplaceDialog::GetFindString](#getfindstring)|Appelez cette fonction pour extraire la chaîne de recherche actuel.|  
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Appelez cette fonction pour récupérer la **FINDREPLACE** structure dans votre gestionnaire de messages enregistrés.|  
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Appelez cette fonction pour extraire la chaîne de remplacement en cours.|  
|[CFindReplaceDialog::IsTerminating](#isterminating)|Appelez cette fonction pour déterminer si la boîte de dialogue se termine.|  
|[CFindReplaceDialog::MatchCase](#matchcase)|Appelez cette fonction pour déterminer si l’utilisateur doit correspondre exactement à la casse de la chaîne de recherche.|  
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Appelez cette fonction pour déterminer si l’utilisateur doit correspondre aux mots entiers uniquement.|  
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Appelez cette fonction pour déterminer si l’utilisateur souhaite obtenir toutes les occurrences de la chaîne à remplacer.|  
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Appelez cette fonction pour déterminer si l’utilisateur veut ce mot à remplacer.|  
|[CFindReplaceDialog::SearchDown](#searchdown)|Appelez cette fonction pour déterminer si l’utilisateur souhaite que la recherche vers le bas.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFindReplaceDialog::m_fr](#m_fr)|Une structure utilisée pour personnaliser un `CFindReplaceDialog` objet.|  
  
## <a name="remarks"></a>Remarques  
 Contrairement à d’autres Windows courants boîtes de dialogue, `CFindReplaceDialog` objets sont non modales, ce qui permet aux utilisateurs d’interagir avec d’autres fenêtres pendant qu’elles sont à l’écran. Il existe deux types de `CFindReplaceDialog` objets : trouver les boîtes de dialogue et les boîtes de dialogue Rechercher/Remplacer. Bien que les boîtes de dialogue Autoriser l’utilisateur à la recherche d’entrée et les chaînes de recherche et de remplacement, ils n’effectuent pas de la recherche ou en remplaçant les fonctions. Vous devez les ajouter à l’application.  
  
 Pour construire un `CFindReplaceDialog` d’objet, utilisez le constructeur fourni (qui ne comporte aucun argument). Dans la mesure où il s’agit d’une boîte de dialogue non modale, d’allouer l’objet sur le segment de mémoire à l’aide de la **nouveau** opérateur, plutôt que sur la pile.  
  
 Une fois un `CFindReplaceDialog` objet a été construit, vous devez appeler le [créer](#create) fonction membre pour créer et afficher la boîte de dialogue.  
  
 Utilisez le [m_fr](#m_fr) structure pour initialiser la boîte de dialogue avant d’appeler **créer**. Le `m_fr` structure est de type [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Pour plus d’informations sur cette structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Dans l’ordre de la fenêtre parente être avertis des demandes de recherche/remplacement, vous devez utiliser les fenêtres [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) la fonction et utiliser le [ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d) macro de table des messages dans votre fenêtre frame qui gère ce message enregistré.  
  
 Vous pouvez déterminer si l’utilisateur a décidé de mettre fin à la boîte de dialogue avec le `IsTerminating` fonction membre.  
  
 `CFindReplaceDialog`s’appuie sur le COMMDLG. Fichier DLL qui est fourni avec Windows 3.1 et versions ultérieures.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe de `CFindReplaceDialog`, fournir un modèle de boîte de dialogue personnalisée et ajouter une table des messages pour traiter les messages de notification à partir de contrôles étendus. Tous les messages non traités doivent être passés à la classe de base.  
  
 Personnalisation de la fonction de raccordement n’est pas nécessaire.  
  
 Pour plus d’informations sur l’utilisation de `CFindReplaceDialog`, consultez [Classes de](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="cfindreplacedialog"></a>CFindReplaceDialog::CFindReplaceDialog  
 Construit un objet `CFindReplaceDialog`.  
  
```  
CFindReplaceDialog();
```  
  
### <a name="remarks"></a>Remarques  
 Étant donné que la `CFindReplaceDialog` objet est une boîte de dialogue non modale, vous devez construire sur le segment de mémoire à l’aide de la `new` (opérateur).  
  
 Au cours de destruction, l’infrastructure essaie d’exécuter un `delete this` sur le pointeur vers la boîte de dialogue. Si vous avez créé la boîte de dialogue sur la pile, le `this` pointeur n’existe pas et peut entraîner des comportement non défini.  
  
 Pour plus d’informations sur la construction de `CFindReplaceDialog` , voir la [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) vue d’ensemble. Utilisez le [CFindReplaceDialog::Create](#create) fonction membre pour afficher la boîte de dialogue.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#170;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]  
  
##  <a name="create"></a>CFindReplaceDialog::Create  
 Crée et affiche une recherche ou une recherche/remplacement objet boîte de dialogue, selon la valeur de `bFindDialogOnly`.  
  
```  
virtual BOOL Create(
    BOOL bFindDialogOnly,  
    LPCTSTR lpszFindWhat,  
    LPCTSTR lpszReplaceWith = NULL,  
    DWORD dwFlags = FR_DOWN,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `bFindDialogOnly`  
 Définissez ce paramètre sur `TRUE` pour afficher une **trouver** boîte de dialogue. Affectez-lui la valeur `FALSE` pour afficher une **rechercher/remplacer** boîte de dialogue.  
  
 `lpszFindWhat`  
 Pointeur vers la chaîne de recherche par défaut lorsque la boîte de dialogue s’affiche. Si `NULL`, la boîte de dialogue ne contient pas une chaîne de recherche par défaut.  
  
 `lpszReplaceWith`  
 Pointeur vers la chaîne de remplacement par défaut lorsque la boîte de dialogue s’affiche. Si `NULL`, la boîte de dialogue ne contient pas une chaîne de remplacement par défaut.  
  
 `dwFlags`  
 Un ou plusieurs indicateurs que vous pouvez utiliser pour personnaliser les paramètres de la boîte de dialogue, combinées à l’aide de l’opérateur OR. La valeur par défaut est `FR_DOWN`, qui spécifie que la recherche doit continuer vers le bas. Consultez le [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur ces indicateurs.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parente ou propriétaire de la boîte de dialogue. Il s’agit de la fenêtre qui reçoit le message spécial indiquant qu’une action Rechercher/Remplacer est demandée. Si `NULL`, la fenêtre principale de l’application est utilisée.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet de boîte de dialogue a été créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Dans l’ordre de la fenêtre parente être avertis des demandes de recherche/remplacement, vous devez utiliser les fenêtres [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) fonction dont la valeur renvoyée est un message unique à l’instance de l’application. Votre fenêtre frame doit avoir une entrée de mappage de message qui déclare la fonction de rappel ( `OnFindReplace` dans l’exemple qui suit) qui gère ce message enregistré. Le fragment de code suivant est un exemple de procédure à suivre pour une classe de fenêtre frame nommée `CMyRichEditView`:  
  
 [!code-cpp[NVC_MFCDocView&#171;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]  
  
 [!code-cpp[NVC_MFCDocView&#172;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#173;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]  
  
 Dans votre `OnFindReplace` (fonction), interpréter les intentions de l’utilisateur à l’aide de la [CFindReplaceDialog::FindNext](#findnext) et [CFindReplaceDialog::IsTerminating](#isterminating) méthodes et que vous créez le code pour les opérations Rechercher/Remplacer.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="findnext"></a>CFindReplaceDialog::FindNext  
 Appelez cette fonction à partir de votre fonction de rappel pour déterminer si l’utilisateur souhaite rechercher l’occurrence suivante de la chaîne de recherche.  
  
```  
BOOL FindNext() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur souhaite rechercher l’occurrence suivante de la chaîne de recherche. sinon 0.  
  
##  <a name="getfindstring"></a>CFindReplaceDialog::GetFindString  
 Appelez cette fonction à partir de votre fonction de rappel pour extraire la chaîne par défaut à rechercher.  
  
```  
CString GetFindString() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne par défaut à rechercher.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getnotifier"></a>CFindReplaceDialog::GetNotifier  
 Appelez cette fonction pour récupérer un pointeur vers la boîte de dialogue Rechercher et remplacer en cours.  
  
```  
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `lParam`  
 Le **lparam** la valeur passée à la fenêtre frame **OnFindReplace** fonction membre.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la boîte de dialogue.  
  
### <a name="remarks"></a>Notes  
 Il doit être utilisé pour accéder à la boîte de dialogue, appeler ses membres des accès et des fonctions dans votre fonction de rappel du `m_fr` structure.  
  
### <a name="example"></a>Exemple  
 Consultez la page [CFindReplaceDialog::Create](#create) pour obtenir un exemple de procédure inscrire le gestionnaire OnFindReplace pour recevoir des notifications à partir de la boîte de dialogue Rechercher et remplacer.  
  
 [!code-cpp[NVC_MFCDocView&#69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getreplacestring"></a>CFindReplaceDialog::GetReplaceString  
 Appelez cette fonction pour extraire la chaîne de remplacement en cours.  
  
```  
CString GetReplaceString() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne par défaut qui remplace des chaînes est trouvés.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="isterminating"></a>CFindReplaceDialog::IsTerminating  
 Appelez cette fonction dans votre fonction de rappel pour déterminer si l’utilisateur a décidé de mettre fin à la boîte de dialogue.  
  
```  
BOOL IsTerminating() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur a décidé de mettre fin à la boîte de dialogue sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Si cette fonction retourne zéro, vous devez appeler le `DestroyWindow` fonction membre de la boîte de dialogue active et ensemble toute boîte de dialogue zone variable pointeur à **NULL**. Si vous le souhaitez, vous pouvez également stocker le texte de recherche/remplacement entré en dernier et l’utiliser pour initialiser la boîte de dialogue Rechercher/Remplacer suivante.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="m_fr"></a>CFindReplaceDialog::m_fr  
 Permet de personnaliser un `CFindReplaceDialog` objet.  
  
```  
FINDREPLACE m_fr;  
```  
  
### <a name="remarks"></a>Remarques  
 `m_fr`est une structure de type [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Ses membres stockent les caractéristiques de l’objet de la boîte de dialogue. Après avoir construit un `CFindReplaceDialog` de l’objet, vous pouvez utiliser `m_fr` pour modifier des valeurs différentes dans la boîte de dialogue.  
  
 Pour plus d’informations sur cette structure, consultez la **FINDREPLACE** de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="matchcase"></a>CFindReplaceDialog::MatchCase  
 Appelez cette fonction pour déterminer si l’utilisateur doit correspondre exactement à la casse de la chaîne de recherche.  
  
```  
BOOL MatchCase() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur souhaite rechercher des occurrences de la chaîne de recherche qui correspondent exactement à la casse de la chaîne de recherche ; sinon 0.  
  
##  <a name="matchwholeword"></a>CFindReplaceDialog::MatchWholeWord  
 Appelez cette fonction pour déterminer si l’utilisateur doit correspondre aux mots entiers uniquement.  
  
```  
BOOL MatchWholeWord() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur veut faire correspondre uniquement les mots entiers de la chaîne de recherche. sinon 0.  
  
##  <a name="replaceall"></a>CFindReplaceDialog::ReplaceAll  
 Appelez cette fonction pour déterminer si l’utilisateur souhaite obtenir toutes les occurrences de la chaîne à remplacer.  
  
```  
BOOL ReplaceAll() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur a demandé que toutes les chaînes correspondant à la chaîne de remplacement remplacé ; sinon 0.  
  
##  <a name="replacecurrent"></a>CFindReplaceDialog::ReplaceCurrent  
 Appelez cette fonction pour déterminer si l’utilisateur veut ce mot à remplacer.  
  
```  
BOOL ReplaceCurrent() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur a demandé que la chaîne actuellement sélectionnée soient remplacés par la chaîne de remplacement. sinon 0.  
  
##  <a name="searchdown"></a>CFindReplaceDialog::SearchDown  
 Appelez cette fonction pour déterminer si l’utilisateur souhaite que la recherche vers le bas.  
  
```  
BOOL SearchDown() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur souhaite que la recherche dans une direction vers le bas ; 0 si l’utilisateur veut rechercher vers le haut.  
  
## <a name="see-also"></a>Voir aussi  
 [CCommonDialog (classe)](../../mfc/reference/ccommondialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)  

