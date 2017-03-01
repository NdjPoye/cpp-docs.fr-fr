---
title: Classe de COleChangeSourceDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- OLEUICHANGESOURCE
dev_langs:
- C++
helpviewer_keywords:
- OLE Change Source dialog box
- COleChangeSourceDialog class
- dialog boxes, OLE
- OLE dialog boxes, Change Source
- OleUIChangeSource structure
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4a1af032b9a10a0262f0267056b675eed7da509c
ms.lasthandoff: 02/24/2017

---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog (classe)
Utilisé pour la boîte de dialogue OLE Changer de source.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Construit un objet `COleChangeSourceDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|Affiche la boîte de dialogue OLE changer de Source.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Obtient le nom d’affichage source complet.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Obtient le nom de fichier de la source.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Obtient le préfixe de la source précédente.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Obtient le nom de l’élément de la source.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Obtient le préfixe de la nouvelle source|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Indique si la source est correcte.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|Structure qui contrôle le comportement de la boîte de dialogue.|  
  
## <a name="remarks"></a>Notes  
 Créer un objet de classe `COleChangeSourceDialog` lorsque vous souhaitez appeler cette boîte de dialogue. Après un `COleChangeSourceDialog` objet a été construit, vous pouvez utiliser la [m_cs](#m_cs) structure pour initialiser les valeurs ou les États des contrôles dans la boîte de dialogue. Le `m_cs` structure est de type [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160). Pour plus d’informations sur l’utilisation de cette classe de boîte de dialogue, consultez la [DoModal](#domodal) fonction membre.  
  
 Pour plus d’informations, consultez la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) dans la structure [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="a-namecolechangesourcedialoga--colechangesourcedialogcolechangesourcedialog"></a><a name="colechangesourcedialog"></a>COleChangeSourceDialog::COleChangeSourceDialog  
 Cette fonction génère une `COleChangeSourceDialog` objet.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointeur vers l’élément lié [COleClientItem](../../mfc/reference/coleclientitem-class.md) dont la source est mise à jour.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de la boîte de dialogue sera définie sur la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Remarques  
 Pour afficher la boîte de dialogue, appelez le [DoModal](#domodal) (fonction).  
  
 Pour plus d’informations, consultez la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure et [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) fonction [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedomodala--colechangesourcedialogdomodal"></a><a name="domodal"></a>COleChangeSourceDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue OLE changer de Source.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
- **IDOK** si la boîte de dialogue est affichée avec succès.  
  
- **IDCANCEL** si l’utilisateur a annulé la boîte de dialogue.  
  
- **IDABORT** si une erreur s’est produite. Si **IDABORT** est retourné, appelez le [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) fonction [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Si vous souhaitez initialiser les différents contrôles de boîte de dialogue en définissant les membres de la [m_cs](#m_cs) structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Si `DoModal` retourne **IDOK**, vous pouvez appeler des fonctions pour récupérer les paramètres entré par l’utilisateur ou les informations à partir de la boîte de dialogue membres. La liste suivante nomme les fonctions de requête classique :  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="a-namegetdisplaynamea--colechangesourcedialoggetdisplayname"></a><a name="getdisplayname"></a>COleChangeSourceDialog::GetDisplayName  
 Appelez cette fonction pour récupérer le nom d’affichage complet de l’élément client lié.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nom d’affichage (moniker) source complet pour le [COleClientItem](../../mfc/reference/coleclientitem-class.md) spécifié dans le constructeur.  
  
##  <a name="a-namegetfilenamea--colechangesourcedialoggetfilename"></a><a name="getfilename"></a>COleChangeSourceDialog::GetFileName  
 Appelez cette fonction pour récupérer la partie du moniker de fichier du nom complet de l’élément client lié.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La partie de moniker du fichier le nom d’affichage source pour le [COleClientItem](../../mfc/reference/coleclientitem-class.md) spécifié dans le constructeur.  
  
### <a name="remarks"></a>Remarques  
 Le moniker du fichier ainsi que le moniker d’élément donne le nom de l’affichage complet.  
  
##  <a name="a-namegetfromprefixa--colechangesourcedialoggetfromprefix"></a><a name="getfromprefix"></a>COleChangeSourceDialog::GetFromPrefix  
 Appelez cette fonction pour obtenir la chaîne de préfixe précédent de la source.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne de préfixe précédent de la source.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette fonction uniquement après avoir [DoModal](#domodal) retourne **IDOK**.  
  
 Cette valeur provient directement le **lpszFrom** membre de la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure.  
  
 Pour plus d’informations, consultez la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) dans la structure [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetitemnamea--colechangesourcedialoggetitemname"></a><a name="getitemname"></a>COleChangeSourceDialog::GetItemName  
 Appelez cette fonction pour récupérer la partie de moniker d’élément du nom complet de l’élément client lié.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La partie de moniker élément du nom d’affichage de la source pour le [COleClientItem](../../mfc/reference/coleclientitem-class.md) spécifié dans le constructeur.  
  
### <a name="remarks"></a>Remarques  
 Le moniker du fichier ainsi que le moniker d’élément donne le nom de l’affichage complet.  
  
##  <a name="a-namegettoprefixa--colechangesourcedialoggettoprefix"></a><a name="gettoprefix"></a>COleChangeSourceDialog::GetToPrefix  
 Appelez cette fonction pour obtenir la nouvelle chaîne de préfixe pour la source.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La nouvelle chaîne de préfixe de la source.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette fonction uniquement après avoir [DoModal](#domodal) retourne **IDOK**.  
  
 Cette valeur provient directement le **lpszTo** membre de la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure.  
  
 Pour plus d’informations, consultez la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) dans la structure [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemcsa--colechangesourcedialogmcs"></a><a name="m_cs"></a>COleChangeSourceDialog::m_cs  
 Ce membre de données est une structure de type [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Notes  
 `OLEUICHANGESOURCE`est utilisé pour contrôler le comportement de la boîte de dialogue OLE changer de Source. Les membres de cette structure peuvent être modifiés directement.  
  
 Pour plus d’informations, consultez la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) dans la structure [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisvalidsourcea--colechangesourcedialogisvalidsource"></a><a name="isvalidsource"></a>COleChangeSourceDialog::IsValidSource  
 Appelez cette fonction pour déterminer si la nouvelle source est valide.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la nouvelle source est valide, sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette fonction uniquement après avoir [DoModal](#domodal) retourne **IDOK**.  
  
 Pour plus d’informations, consultez la [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) dans la structure [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

