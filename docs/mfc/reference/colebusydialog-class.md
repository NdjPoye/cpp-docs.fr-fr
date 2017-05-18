---
title: Classe de la classe COleBusyDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs:
- C++
helpviewer_keywords:
- Server Not Responding dialog box
- Server Busy dialog box
- COleBusyDialog class
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0c3ed264cdb83bc97337f13279a20f26b21d454b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="colebusydialog-class"></a>Classe de la classe COleBusyDialog
Utilisé pour les boîtes de dialogue OLE Le serveur ne répond pas ou Le serveur est occupé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Construit un objet `COleBusyDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|Affiche la boîte de dialogue OLE le serveur est occupé.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Détermine le choix effectué dans la boîte de dialogue.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|Structure de type **OLEUIBUSY** qui contrôle le comportement de la boîte de dialogue.|  
  
## <a name="remarks"></a>Notes  
 Créer un objet de classe `COleBusyDialog` lorsque vous souhaitez appeler ces boîtes de dialogue. Après un `COleBusyDialog` objet a été construit, vous pouvez utiliser la [m_bz](#m_bz) structure pour initialiser les valeurs ou les États des contrôles dans la boîte de dialogue. Le `m_bz` structure est de type **OLEUIBUSY**. Pour plus d’informations sur l’utilisation de cette classe de boîte de dialogue, consultez la [DoModal](#domodal) fonction membre.  
  
> [!NOTE]
>  Code de l’application conteneur généré par l’Assistant utilise cette classe.  
  
 Pour plus d’informations, consultez la [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog  
 Cette fonction crée uniquement une `COleBusyDialog` objet.  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *htaskBusy*  
 Handle vers la tâche de serveur est occupée.  
  
 *bNotResponding*  
 Si **TRUE**, appeler la boîte de dialogue ne répond pas au lieu de la boîte de dialogue serveur occupé. Le libellé dans la boîte de dialogue ne répond pas est légèrement différent de celle du texte dans la boîte de dialogue serveur occupé, et le bouton Annuler est désactivé.  
  
 `dwFlags`  
 Indicateur de création. Peut contenir zéro ou plusieurs des valeurs suivantes combinées avec l’opérateur de bits OR :  
  
- **BZ_DISABLECANCELBUTTON** désactiver le bouton Annuler lors de l’appel de la boîte de dialogue.  
  
- **BZ_DISABLESWITCHTOBUTTON** désactiver le bouton Basculer vers lors de l’appel de la boîte de dialogue.  
  
- **BZ_DISABLERETRYBUTTON** désactiver le bouton de nouvelle tentative lors de l’appel de la boîte de dialogue.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de l’objet de la boîte de dialogue est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Remarques  
 Pour afficher la boîte de dialogue, appelez [DoModal](#domodal).  
  
 Pour plus d’informations, consultez la [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="domodal"></a>COleBusyDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue OLE le serveur est occupé ou serveur ne répond pas.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
- **IDOK** si la boîte de dialogue est affichée avec succès.  
  
- **IDCANCEL** si l’utilisateur a annulé la boîte de dialogue.  
  
- **IDABORT** si une erreur s’est produite. Si **IDABORT** est retourné, appelez le `COleDialog::GetLastError` fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Si vous souhaitez initialiser les différents contrôles de boîte de dialogue en définissant les membres de la [m_bz](#m_bz) structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Si `DoModal` retourne **IDOK**, vous pouvez appeler des fonctions pour récupérer les paramètres ou les informations qui a été entrées par l’utilisateur dans la boîte de dialogue autres membres.  
  
##  <a name="getselectiontype"></a>COleBusyDialog::GetSelectionType  
 Appelez cette fonction pour obtenir le type de sélection choisi par l’utilisateur dans la boîte de dialogue serveur occupé.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Type de sélection.  
  
### <a name="remarks"></a>Remarques  
 Les valeurs de type de retour sont spécifiés par le **sélection** type énumération déclarée dans la `COleBusyDialog` classe.  
  
```  
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```  
  
 Suivent de brèves descriptions de ces valeurs :  
  
- **COleBusyDialog::switchTo** basculer vers a cliqué.  
  
- **COleBusyDialog::retry** a cliqué sur Réessayer.  
  
- **COleBusyDialog::callUnblocked** appel pour activer le serveur est maintenant débloqué.  
  
##  <a name="m_bz"></a>COleBusyDialog::m_bz  
 Structure de type **OLEUIBUSY** utilisé pour contrôler le comportement de la boîte de dialogue serveur occupé.  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>Remarques  
 Les membres de cette structure peuvent être modifiés directement ou via les fonctions membres.  
  
 Pour plus d’informations, consultez la [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

