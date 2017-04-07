---
title: Classe de CWinFormsDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsDialog class
- Windows Forms [C++], MFC support
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
caps.latest.revision: 26
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
ms.openlocfilehash: 86768a849b0112f7c4f8b6b2a694b80065169575
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog (classe)
Wrapper pour une classe de boîte de dialogue MFC qui héberge un contrôle utilisateur Windows Forms.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
    public CDialog  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TManagedControl`  
 Le contrôle utilisateur .NET Framework s’affichent dans l’application MFC.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Construit un objet `CWinFormsDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Récupère une référence au contrôle utilisateur Windows Forms.|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Récupère un handle de fenêtre pour le contrôle utilisateur Windows Forms.|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Initialise la boîte de dialogue MFC à la création et l’hébergement d’un contrôle utilisateur Windows Forms.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Remplace [CWinFormsDialog::GetControl](#getcontrol) dans les expressions.|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Convertit un type en tant que référence à un contrôle utilisateur Windows Forms.|  
  
## <a name="remarks"></a>Remarques  
 `CWinFormsDialog`est un wrapper pour une classe de boîte de dialogue MFC ( [CDialog](../../mfc/reference/cdialog-class.md)) qui héberge un contrôle utilisateur Windows Forms. Cela permet d’afficher des contrôles .NET Framework dans une boîte de dialogue MFC modale ou non modale.  
  
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) et [qui héberge un contrôle Windows Form utilisateur en tant que boîte de dialogue MFC](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>CWinFormsDialog::CWinFormsDialog  
 Construit un objet `CWinFormsDialog`.  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDTemplate`  
 Contient l’ID d’une ressource modèle de boîte de dialogue. Utilisez l’éditeur de boîtes de dialogue pour créer le modèle de boîte de dialogue et les stocker dans le fichier de script de ressources de l’application. Pour plus d’informations sur les modèles de la boîte de dialogue, consultez [CDialog (classe)](../../mfc/reference/cdialog-class.md).  
  
##  <a name="getcontrol"></a>CWinFormsDialog::GetControl  
 Récupère une référence au contrôle utilisateur Windows Forms.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence au contrôle Windows Forms dans la boîte de dialogue MFC.  
  
##  <a name="getcontrolhandle"></a>CWinFormsDialog::GetControlHandle  
 Récupère un handle de fenêtre pour le contrôle utilisateur Windows Forms.  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle de fenêtre pour le contrôle utilisateur Windows Forms.  
  
##  <a name="oninitdialog"></a>CWinFormsDialog::OnInitDialog  
 Initialise la boîte de dialogue MFC à la création et l’hébergement d’un contrôle utilisateur Windows Forms.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne qui spécifie si l’application a défini le focus d’entrée à l’un des contrôles dans la boîte de dialogue. Si `OnInitDialog` retourne zéro, Windows définit le focus d’entrée sur le premier contrôle dans la boîte de dialogue. Cette méthode peut retourner 0 uniquement si l’application a défini explicitement le focus d’entrée sur un des contrôles dans la boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Lorsque la boîte de dialogue MFC est créée (à l’aide de la [créer](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), ou [DoModal](../../mfc/reference/cdialog-class.md#domodal) héritée de la méthode [CDialog](../../mfc/reference/cdialog-class.md)), un `WM_INITDIALOG` message est envoyé, cette méthode est appelée. Il crée une instance d’un contrôle Windows Forms dans la boîte de dialogue et ajuste la taille de la boîte de dialogue pour prendre en compte pour la taille du contrôle utilisateur. Il héberge ensuite le nouveau contrôle dans la boîte de dialogue MFC.  
  
 Remplacez cette fonction membre, si vous avez besoin exécuter un traitement spécial lors de l’initialisation de la boîte de dialogue. Pour plus d’informations sur l’utilisation de cette méthode, consultez [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).  
  
##  <a name="operator_-_gt"></a>CWinFormsDialog::operator-&gt;  
 Remplace [CWinFormsDialog::GetControl](#getcontrol) dans les expressions.  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>Notes  
 Cet opérateur fournit une syntaxe qui remplace `GetControl` dans les expressions.  
  
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol_xor"></a>CWinFormsDialog::operator TManagedControl ^  
 Convertit un type en tant que référence à un contrôle utilisateur Windows Forms.  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur convertit un type en tant que référence à un contrôle Windows Forms. Il est utilisé pour passer un `CWinFormsDialog<``TManagedControl``>` boîte de dialogue pour les fonctions qui acceptent un pointeur vers un objet de contrôle utilisateur Windows Forms.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Classe CWinFormsView](../../mfc/reference/cwinformsview-class.md)   
 [CDialog (classe)](../../mfc/reference/cdialog-class.md)

