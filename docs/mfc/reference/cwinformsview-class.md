---
title: Classe CWinFormsView | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsView class
- Windows Forms [C++], MFC support
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6c49d711da747e4c6cbad0f883d93196b6a98057
ms.openlocfilehash: 7aadcc1aa887cb6be1ddbb8f3797c4a9e1af5b6a
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsview-class"></a>Classe CWinFormsView
Fournit les fonctionnalités génériques pour l'hébergement d'un contrôle Windows Forms en tant que vue MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|Construit un objet `CWinFormsView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinFormsView::GetControl](#getcontrol)|Récupère un pointeur vers le contrôle Windows Forms.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom||  
|----------|-|  
|[Contrôle de CWinFormsView::operator ^](#operator_control)|Convertit un type comme un pointeur vers un contrôle Windows Forms.|  
  
## <a name="remarks"></a>Remarques  
 MFC utilise la `CWinFormsView` classe pour héberger un contrôle Windows Forms .NET Framework dans une vue MFC. Le contrôle est un enfant de la vue native et occupe la zone cliente entière de la vue MFC. Le résultat est similaire à un `CFormView` vue, ce qui vous permet de tirer parti du Concepteur Windows Forms et d’exécution pour créer des vues basées sur formulaire riches.  
  
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  Intégration de MFC Windows Forms fonctionne uniquement dans les projets qui se lient dynamiquement avec MFC (projets dans lesquels AFXDLL est défini).  
  
> [!NOTE]
>  CWinFormsView ne prend pas en charge la fenêtre fractionnée MFC ( [CSplitterWnd classe](../../mfc/reference/csplitterwnd-class.md)). Actuellement uniquement la Splitter Windows Forms contrôle est pris en charge.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwinforms.h  
  
##  <a name="cwinformsview"></a>CWinFormsView::CWinFormsView  
 Construit un objet `CWinFormsView`.  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>Paramètres  
 `pManagedViewType`  
 Pointeur vers le type de données du contrôle utilisateur Windows Forms.   
  
### <a name="example"></a>Exemple  
 Dans l’exemple suivant, la `CUserView` hérite de la classe `CWinFormsView` et passe le type de `UserControl1` à le `CWinFormsView` constructeur. `UserControl1`est un contrôle personnalisé dans ControlLibrary1.dll.  
  
 [!code-cpp[NVC_MFC_Managed n °&1;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed n °&2;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="getcontrol"></a>CWinFormsView::GetControl  
 Récupère un pointeur vers le contrôle Windows Forms.  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `System.Windows.Forms.Control` objet.  
  
### <a name="remarks"></a>Remarques  
 Pour obtenir un exemple d’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_control"></a>Contrôle de CWinFormsView::operator ^  
 Convertit un type comme un pointeur vers un contrôle Windows Forms.  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur vous permet de transmettre un `CWinFormsView` affichage pour les fonctions qui acceptent un pointeur vers un contrôle Windows Forms de type <xref:System.Windows.Forms.Control>.</xref:System.Windows.Forms.Control>  
  
### <a name="example"></a>Exemple  
  Consultez la page [CWinFormsView::GetControl](#getcontrol).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl (classe)](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog (classe)](../../mfc/reference/cwinformsdialog-class.md)   
 [Classe de CFormView](../../mfc/reference/cformview-class.md)

