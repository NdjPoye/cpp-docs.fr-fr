---
title: Classe de CColorDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- colors, dialog box
- dialog boxes, colors
- CColorDialog class
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
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
ms.openlocfilehash: a8aee088aadbca18acda348c574c8f4b55d1ecbb
ms.lasthandoff: 02/24/2017

---
# <a name="ccolordialog-class"></a>CColorDialog (classe)
Vous pouvez ainsi incorporer une boîte de dialogue de sélection de couleurs dans votre application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|Construit un objet `CColorDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|Affiche une boîte de dialogue couleurs et permet à l’utilisateur d’effectuer une sélection.|  
|[CColorDialog::GetColor](#getcolor)|Retourne un **COLORREF** structure contenant les valeurs de la couleur sélectionnée.|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Récupère les couleurs personnalisées créées par l’utilisateur.|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Force la sélection actuelle de la couleur de la couleur spécifiée.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|Substituez pour valider des entrées dans la boîte de dialogue couleur.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|Une structure utilisée pour personnaliser les paramètres de la boîte de dialogue.|  
  
## <a name="remarks"></a>Remarques  
 Un `CColorDialog` objet est une boîte de dialogue avec une liste de couleurs qui sont définies pour le système d’affichage. L’utilisateur peut sélectionner ou créer une couleur particulière dans la liste, qui est ensuite renvoyée à l’application lors de la boîte de dialogue se ferme.  
  
 Pour construire un `CColorDialog` de l’objet, utilisez le constructeur fourni ou dériver une nouvelle classe et utilisez votre propre constructeur personnalisé.  
  
 Une fois que la boîte de dialogue a été construite, vous pouvez définir ou modifier des valeurs dans le [m_cc](#m_cc) structure pour initialiser les valeurs des contrôles de la boîte de dialogue. Le `m_cc` structure est de type [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 Après l’initialisation des contrôles de la boîte de dialogue, appelez le `DoModal` fonction membre pour afficher la boîte de dialogue et permettent aux utilisateurs de sélectionner une couleur. `DoModal`Retourne la sélection d’utilisateur du OK de la boîte de dialogue ( **IDOK**) ou Annuler ( **IDCANCEL**) bouton.  
  
 Si `DoModal` retourne **IDOK**, vous pouvez utiliser une des `CColorDialog`de fonctions membres pour récupérer les informations entrées par l’utilisateur.  
  
 Vous pouvez utiliser les fenêtres [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) fonction pour déterminer si une erreur s’est produite lors de l’initialisation de la boîte de dialogue et pour en savoir plus sur l’erreur.  
  
 `CColorDialog`s’appuie sur le COMMDLG. Fichier DLL qui est fourni avec Windows 3.1 et versions ultérieures.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe de `CColorDialog`, fournir un modèle de boîte de dialogue personnalisée et ajouter une table des messages pour traiter les messages de notification à partir de contrôles étendus. Tous les messages non traités doivent être passés à la classe de base.  
  
 Personnalisation de la fonction de raccordement n’est pas nécessaire.  
  
> [!NOTE]
>  Sur certaines installations de la `CColorDialog` objet n’affiche pas, avec un arrière-plan grisé, si vous avez utilisé l’infrastructure pour apporter d’autres `CDialog` gris d’objets.  
  
 Pour plus d’informations sur l’utilisation de `CColorDialog`, consultez la page [des Classes de boîte de dialogue communes](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="ccolordialog"></a>CColorDialog::CColorDialog  
 Construit un objet `CColorDialog`.  
  
```  
CColorDialog(
    COLORREF clrInit = 0,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *clrInit*  
 La sélection de couleur par défaut. Si aucune valeur n’est spécifiée, la valeur par défaut est RGB(0,0,0) (noir).  
  
 `dwFlags`  
 Un jeu d’indicateurs qui personnalisent la fonction et l’apparence de la boîte de dialogue. Pour plus d’informations, consultez la [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parente ou propriétaire de la boîte de dialogue.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[49 NVC_MFCDocView](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CColorDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue couleur Windows courants et permettre à l’utilisateur de sélectionner une couleur.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 **IDOK** ou **IDCANCEL**. Si **IDCANCEL** est retourné, appelez Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) fonction pour déterminer si une erreur s’est produite.  
  
 **IDOK** et **IDCANCEL** sont des constantes qui indiquent si l’utilisateur a sélectionné le bouton OK ou annuler.  
  
### <a name="remarks"></a>Remarques  
 Si vous souhaitez initialiser les diverses options de la boîte de dialogue couleur en définissant les membres de la [m_cc](#m_cc) structure, vous devez le faire avant d’appeler `DoModal` mais après la construction de l’objet de la boîte de dialogue.  
  
 Après avoir appelé `DoModal`, vous pouvez appeler des fonctions à récupérer les paramètres ou les informations saisies par l’utilisateur dans la boîte de dialogue autres membres.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CColorDialog::CColorDialog](#ccolordialog).  
  
##  <a name="getcolor"></a>CColorDialog::GetColor  
 Appelez cette fonction après avoir appelé `DoModal` pour extraire des informations sur la couleur sélectionnée par l’utilisateur.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur qui contient les informations RVB de la couleur sélectionnée dans la boîte de dialogue couleur.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#50;](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="getsavedcustomcolors"></a>CColorDialog::GetSavedCustomColors  
 `CColorDialog`objets permettent à l’utilisateur, en plus de choix de couleurs, définir des couleurs personnalisées jusqu'à 16.  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un tableau de valeurs de couleur RVB 16 qui stocke les couleurs personnalisées créées par l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
 Le `GetSavedCustomColors` fonction membre fournit l’accès à ces couleurs. Ces couleurs peuvent être récupérées après [DoModal](#domodal) retourne **IDOK**.  
  
 Chacune des valeurs RVB 16 dans le tableau retourné est initialisée à RGB(255,255,255) (blanc). Les couleurs personnalisées choisis par l’utilisateur sont enregistrées uniquement entre les appels de boîte de dialogue dans l’application. Si vous souhaitez enregistrer ces couleurs entre les appels de l’application, vous devez les enregistrer dans une autre manière, comme une initialisation (. Fichier INI).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#51;](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="m_cc"></a>CColorDialog::m_cc  
 Une structure de type [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830), dont les membres stocker les caractéristiques et les valeurs de la boîte de dialogue.  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>Remarques  
 Après avoir construit un `CColorDialog` de l’objet, vous pouvez utiliser `m_cc` pour définir les divers aspects de la boîte de dialogue avant d’appeler le [DoModal](#domodal) fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#53;](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="oncolorok"></a>CColorDialog::OnColorOK  
 Substituez pour valider des entrées dans la boîte de dialogue couleur.  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la boîte de dialogue ne doit pas être fermée ; sinon 0 pour accepter la couleur qui a été entrée.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction uniquement si vous souhaitez fournir une validation personnalisée de la couleur de que l’utilisateur sélectionne dans la boîte de dialogue couleur.  
  
 L’utilisateur peut sélectionner une couleur par une des deux méthodes suivantes :  
  
-   En cliquant sur une couleur dans la palette de couleurs. Les valeurs RVB de la couleur sélectionnée sont alors reflétés dans les zones d’édition RVB appropriés.  
  
-   Saisie de valeurs dans le RVB des zones d’édition  
  
 Substitution `OnColorOK` vous permet de rejeter une couleur de l’utilisateur entre dans une boîte de dialogue couleur pour une raison quelconque spécifiques à l’application.  
  
 En règle générale, il est inutile d’utiliser cette fonction, car l’infrastructure fournit une validation par défaut de couleurs et affiche un message si une couleur non valide est entrée.  
  
 Vous pouvez appeler [SetCurrentColor](#setcurrentcolor) depuis `OnColorOK` pour forcer une sélection de couleurs. Une fois `OnColorOK` a été déclenché (autrement dit, l’utilisateur clique sur **OK** pour accepter la modification de la couleur), vous pouvez appeler [GetColor](#getcolor) pour obtenir la valeur de la nouvelle couleur RVB.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#52;](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="setcurrentcolor"></a>CColorDialog::SetCurrentColor  
 Appelez cette fonction après avoir appelé `DoModal` pour forcer la sélection de la couleur actuelle à la valeur de la couleur spécifiée dans `clr`.  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Paramètres  
 `clr`  
 Une valeur de couleur RVB.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée depuis un gestionnaire de messages ou `OnColorOK`. La boîte de dialogue met automatiquement à jour la sélection d’utilisateur basée sur la valeur de le `clr` paramètre.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CColorDialog::OnColorOK](#oncolorok).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MDI](../../visual-cpp-samples.md)   
 [Exemple MFC DRAWCLI](../../visual-cpp-samples.md)   
 [CCommonDialog (classe)](../../mfc/reference/ccommondialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)


