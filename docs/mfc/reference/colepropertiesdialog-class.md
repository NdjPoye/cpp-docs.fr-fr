---
title: Classe de COlePropertiesDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertiesDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE Object Properties dialog box
- Object Properties dialog box
- dialog boxes, OLE
- OLE documents, modifying properties
- property pages, OLE
- COlePropertiesDialog class
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0c07766bca6bbc546f877e10255d80bd388d30d7
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog (classe)
Encapsule la boîte de dialogue Propriétés d'objet OLE courante Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COlePropertiesDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Construit un objet `COlePropertiesDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](#domodal)|Affiche la boîte de dialogue et permet à l’utilisateur d’effectuer une sélection.|  
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Appelé par l’infrastructure lors de la mise à l’échelle de l’élément de document a changé.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePropertiesDialog::m_gp](#m_gp)|Une structure utilisée pour initialiser la page « Générale » d’un `COlePropertiesDialog` objet.|  
|[COlePropertiesDialog::m_lp](#m_lp)|Une structure utilisée pour initialiser la page « Lien » d’un `COlePropertiesDialog` objet.|  
|[COlePropertiesDialog::m_op](#m_op)|Une structure utilisée pour initialiser le `COlePropertiesDialog` objet.|  
|[COlePropertiesDialog::m_psh](#m_psh)|Une structure utilisée pour ajouter des pages de propriétés personnalisées supplémentaires.|  
|[COlePropertiesDialog::m_vp](#m_vp)|Une structure permettant de personnaliser la page « Vue » d’un `COlePropertiesDialog` objet.|  
  
## <a name="remarks"></a>Remarques  
 Les boîtes de dialogue Propriétés de l’objet OLE communes fournissent un moyen simple pour afficher et modifier les propriétés d’un élément de document OLE d’une manière compatible avec les normes de Windows. Ces propriétés incluent, entre autres, des informations sur le fichier représenté par l’élément de document, options d’affichage de l’icône et mise à l’échelle de l’image et des informations sur le lien de l’article (si l’élément est lié).  
  
 Pour utiliser un `COlePropertiesDialog` d’objet, commencez par créer l’objet en utilisant la `COlePropertiesDialog` constructeur. Une fois la boîte de dialogue a été construite, appelez le `DoModal` fonction membre pour afficher la boîte de dialogue et permettent aux utilisateurs de modifier les propriétés de l’élément. `DoModal`Retourne si l’utilisateur a sélectionné le OK ( **IDOK**) ou l’annulation ( **IDCANCEL**) bouton. Outre les boutons OK et Annuler, il existe un bouton Appliquer. Lorsque l’utilisateur sélectionne l’appliquer, les modifications apportées aux propriétés de l’élément de document sont appliquées à l’élément et son image est automatiquement mis à jour, mais il reste actif.  
  
 Le [m_psh](#m_psh) membre de données est un pointeur vers un **PROPSHEETHEADER** structure et dans la plupart des cas, vous ne devez pas y accéder explicitement. Une exception est lorsque vous avez besoin de pages de propriétés supplémentaires au-delà des pages Général, vue et lien par défaut. Dans ce cas, vous pouvez modifier le `m_psh` membre de données pour inclure des pages personnalisées avant d’appeler le `DoModal` fonction membre.  
  
 Pour plus d’informations sur les boîtes de dialogue OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="a-namecolepropertiesdialoga--colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>COlePropertiesDialog::COlePropertiesDialog  
 Crée un objet `COlePropertiesDialog`.  
  
```  
COlePropertiesDialog(
    COleClientItem* pItem,  
    UINT nScaleMin = 10,  
    UINT nScaleMax = 500,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointeur vers l’élément de document dont les propriétés sont ouverts.  
  
 *nScaleMin*  
 Valeur minimale de la mise à l’échelle de pourcentage pour l’image d’élément de document.  
  
 *nScaleMax*  
 Nombre maximal de mise à l’échelle de pourcentage pour l’image d’élément de document.  
  
 `pParentWnd`  
 Pointeur vers la boîte de dialogue parente ou propriétaire.  
  
### <a name="remarks"></a>Remarques  
 Dérivez votre classe de boîte de dialogue Propriétés de l’objet OLE courants de `COlePropertiesDialog` pour implémenter la mise à l’échelle des éléments de votre document. Les boîtes de dialogue implémentées par une instance de cette classe ne prendra pas en charge mise à l’échelle de l’élément de document.  
  
 Par défaut, la boîte de dialogue Propriétés de l’objet OLE a trois pages par défaut :  
  
-   Général  
  
     Cette page contient des informations système pour le fichier représenté par l’élément de document sélectionné. Cette page, l’utilisateur peut convertir l’élément sélectionné vers un autre type.  
  
-   Afficher  
  
     Cette page contient les options d’affichage de l’élément, modification de l’icône et la modification de la mise à l’échelle de l’image.  
  
-   Link  
  
     Cette page contient les options de modification de l’emplacement de l’élément lié et de mise à jour de l’élément lié. À partir de cette page, l’utilisateur peut rompre la liaison de l’élément sélectionné.  
  
 Pour ajouter des pages au-delà de celles fournies par défaut, modifiez le [m_psh](#m_psh) variable membre avant de quitter le constructeur de votre `COlePropertiesDialog`-classe dérivée. Il s’agit d’une implémentation avancée de la `COlePropertiesDialog` constructeur.  
  
##  <a name="a-namedomodala--colepropertiesdialogdomodal"></a><a name="domodal"></a>COlePropertiesDialog::DoModal  
 Appelez cette fonction membre pour afficher la boîte de dialogue Propriétés de l’objet OLE Windows courants et autoriser l’utilisateur à afficher ou modifier les diverses propriétés de l’élément de document.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 **IDOK** ou **IDCANCEL** cas de réussite ; sinon, 0. **IDOK** et **IDCANCEL** sont des constantes qui indiquent si l’utilisateur a sélectionné le bouton OK ou annuler.  
  
 Si **IDCANCEL** est retourné, vous pouvez appeler les fenêtres [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) fonction pour déterminer si une erreur s’est produite.  
  
##  <a name="a-namemgpa--colepropertiesdialogmgp"></a><a name="m_gp"></a>COlePropertiesDialog::m_gp  
 Une structure de type [OLEUIGNRLPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687297), utilisé pour initialiser la page Général de la boîte de dialogue Propriétés de l’objet OLE.  
  
```  
OLEUIGNRLPROPS m_gp;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette page affiche le type et la taille d’une incorporation et permet à l’utilisateur l’accès à cette boîte de dialogue. Cette page affiche également la destination du lien si l’objet est un lien.  
  
 Pour plus d’informations sur la **OLEUIGNRLPROPS** de la structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemlpa--colepropertiesdialogmlp"></a><a name="m_lp"></a>COlePropertiesDialog::m_lp  
 Une structure de type [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735), utilisé pour initialiser la page de lien de la boîte de dialogue Propriétés de l’objet OLE.  
  
```  
OLEUILINKPROPS m_lp;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette page indique l’emplacement de l’élément lié et lui permet de mettre à jour ou l’arrêter, le lien vers l’élément.  
  
 Pour plus d’informations sur la **OLEUILINKPROPS** de la structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemopa--colepropertiesdialogmop"></a><a name="m_op"></a>COlePropertiesDialog::m_op  
 Une structure de type [OLEUIOBJECTPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687199), utilisé pour initialiser la boîte de dialogue Propriétés de l’objet OLE.  
  
```  
OLEUIOBJECTPROPS m_op;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette structure contient les membres utilisés pour initialiser les pages Général, lier et afficher.  
  
 Pour plus d’informations, consultez la **OLEUIOBJECTPROPS** et [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735) structures dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namempsha--colepropertiesdialogmpsh"></a><a name="m_psh"></a>COlePropertiesDialog::m_psh  
 Une structure de type [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546), dont les membres stockent les caractéristiques de l’objet de la boîte de dialogue.  
  
```  
PROPSHEETHEADER m_psh;  
```  
  
### <a name="remarks"></a>Notes  
 Après avoir construit un `COlePropertiesDialog` de l’objet, vous pouvez utiliser `m_psh` pour définir les divers aspects de la boîte de dialogue avant d’appeler le `DoModal` fonction membre.  
  
 Si vous modifiez le `m_psh` membre de données directement, vous devez remplacer un comportement par défaut.  
  
 Pour plus d’informations sur la **PROPSHEETHEADER** de la structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemvpa--colepropertiesdialogmvp"></a><a name="m_vp"></a>COlePropertiesDialog::m_vp  
 Une structure de type [OLEUIVIEWPROPS](http://msdn.microsoft.com/library/windows/desktop/ms693751), utilisé pour initialiser la page Affichage de la boîte de dialogue Propriétés de l’objet OLE.  
  
```  
OLEUIVIEWPROPS m_vp;  
```  
  
### <a name="remarks"></a>Remarques  
 Cette page permet à l’utilisateur de basculer entre « content » et « icônes » vues de l’objet et modifier sa mise à l’échelle dans le conteneur. Il permet également l’accès utilisateur à la boîte de dialogue Changer d’icône lorsque l’objet est affiché sous la forme d’une icône.  
  
 Pour plus d’informations sur la **OLEUIVIEWPROPS** de la structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonapplyscalea--colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>COlePropertiesDialog::OnApplyScale  
 Appelé par l’infrastructure lors de la modification de la valeur mise à l’échelle et OK ou appliquer a été sélectionné.  
  
```  
virtual BOOL OnApplyScale(
    COleClientItem* pItem,  
    int nCurrentScale,  
    BOOL bRelativeToOrig);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointeur vers l’élément de document dont les propriétés sont ouverts.  
  
 `nCurrentScale`  
 Valeur numérique de l’échelle de la boîte de dialogue.  
  
 *bRelativeToOrig*  
 Indique si l’échelle s’applique à la taille d’origine de l’élément de document.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si géré ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 L'implémentation par défaut n'exécute aucune opération. Vous devez substituer cette fonction pour activer les contrôles de mise à l’échelle.  
  
> [!NOTE]
>  Avant l’affichage de la boîte de dialogue Propriétés de l’objet OLE, le framework appelle cette fonction avec un **NULL** de `pItem` et -1 pour `nCurrentScale`. Cela vise à déterminer si les contrôles de mise à l’échelle doivent être activés.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CERC](../../visual-cpp-samples.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage (classe)](../../mfc/reference/cpropertypage-class.md)

