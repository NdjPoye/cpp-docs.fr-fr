---
title: Classe de la classe COleChangeIconDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE dialog boxes, Change Icon
- OLE Change Icon dialog box
- dialog boxes, OLE
- COleChangeIconDialog class
- Change Icon dialog box
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 07dfd7995bbbdb0f52f55dceedc318d8d702111b
ms.lasthandoff: 02/24/2017

---
# <a name="colechangeicondialog-class"></a>Classe de la classe COleChangeIconDialog
Utilisé pour la boîte de dialogue OLE Changer d'icône.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Construit un objet `COleChangeIconDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Effectue la modification spécifiée dans la boîte de dialogue.|  
|[COleChangeIconDialog::DoModal](#domodal)|Affiche la boîte de dialogue OLE 2 changer d’icône.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Obtient un handle de métafichier associé au formulaire sous forme d’icône de cet élément.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|Structure qui contrôle le comportement de la boîte de dialogue.|  
  
## <a name="remarks"></a>Remarques  
 Créer un objet de classe `COleChangeIconDialog` lorsque vous souhaitez appeler cette boîte de dialogue. Après un `COleChangeIconDialog` objet a été construit, vous pouvez utiliser la [m_ci](#m_ci) structure pour initialiser les valeurs ou les États des contrôles dans la boîte de dialogue. Le `m_ci` structure est de type **OLEUICHANGEICON**. Pour plus d’informations sur l’utilisation de cette classe de boîte de dialogue, consultez la [DoModal](#domodal) fonction membre.  
  
 Pour plus d’informations, consultez la [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="a-namecolechangeicondialoga--colechangeicondialogcolechangeicondialog"></a><a name="colechangeicondialog"></a>COleChangeIconDialog::COleChangeIconDialog  
 Cette fonction crée uniquement une `COleChangeIconDialog` objet.  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointe vers l’élément à convertir.  
  
 `dwFlags`  
 Indicateur de création, qui contient un nombre quelconque des valeurs suivantes associées à l’aide de l’opérateur de bits- ou un opérateur :  
  
- **CIF_SELECTCURRENT** Spécifie que la case d’option en cours sera sélectionnée initialement lorsque la boîte de dialogue est appelée. Il s'agit de la valeur par défaut.  
  
- **CIF_SELECTDEFAULT** Spécifie que la case d’option par défaut est sélectionnée initialement lorsque la boîte de dialogue est appelée.  
  
- **CIF_SELECTFROMFILE** Spécifie que la case d’option à partir du fichier sera sélectionnée initialement lorsque la boîte de dialogue est appelée.  
  
- **CIF_SHOWHELP** Spécifie que le bouton aide s’affichera lorsque la boîte de dialogue est appelée.  
  
- **CIF_USEICONEXE** Spécifie que l’icône doit être extraites de l’exécutable spécifié dans le **szIconExe** champ [m_ci](#m_ci) au lieu de récupérer à partir du type. Cela est utile pour incorporer ou lier les fichiers non-OLE.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de la boîte de dialogue sera définie sur la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Remarques  
 Pour afficher la boîte de dialogue, appelez le [DoModal](#domodal) (fonction).  
  
 Pour plus d’informations, consultez la [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedochangeicona--colechangeicondialogdochangeicon"></a><a name="dochangeicon"></a>COleChangeIconDialog::DoChangeIcon  
 Appelez cette fonction pour modifier l’icône qui représente l’élément à celui sélectionné dans la boîte de dialogue après [DoModal](#domodal) retourne **IDOK**.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointe vers l’élément dont l’icône change.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la modification aboutit ; sinon 0.  
  
##  <a name="a-namedomodala--colechangeicondialogdomodal"></a><a name="domodal"></a>COleChangeIconDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue OLE changer d’icône.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
- **IDOK** si la boîte de dialogue est affichée avec succès.  
  
- **IDCANCEL** si l’utilisateur a annulé la boîte de dialogue.  
  
- **IDABORT** si une erreur s’est produite. Si **IDABORT** est retourné, appelez le `COleDialog::GetLastError` fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez initialiser les différents contrôles de boîte de dialogue en définissant les membres de la [m_ci](#m_ci) structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Si `DoModal` retourne **IDOK**, vous pouvez appeler des fonctions pour récupérer les paramètres ou les informations qui a été entrées par l’utilisateur dans la boîte de dialogue autres membres.  
  
##  <a name="a-namegeticonicmetafilea--colechangeicondialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COleChangeIconDialog::GetIconicMetafile  
 Appelez cette fonction pour obtenir un handle de métafichier qui contient l’aspect de l’élément sélectionné sous forme d’icône.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le handle du métafichier contenant l’aspect sous forme d’icône de l’icône Nouveau, si la boîte de dialogue a été fermée en choisissant **OK**; sinon, l’icône telle qu’elle était avant l’affichage de la boîte de dialogue.  
  
##  <a name="a-namemcia--colechangeicondialogmci"></a><a name="m_ci"></a>COleChangeIconDialog::m_ci  
 Structure de type **OLEUICHANGEICON** utilisé pour contrôler le comportement de la boîte de dialogue Changer d’icône.  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Remarques  
 Les membres de cette structure peuvent être modifiés directement ou via les fonctions membres.  
  
 Pour plus d’informations, consultez la [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

