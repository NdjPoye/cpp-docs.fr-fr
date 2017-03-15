---
title: Classe de CMFCCustomColorsPropertyPage | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCCustomColorsPropertyPage class
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
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
ms.openlocfilehash: fa534f22438b7be37e7893e545c3e060df69384f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage (classe)
Représente une page de propriétés que vous pouvez sélectionner des couleurs personnalisées dans une boîte de dialogue couleur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Constructeur par défaut.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCCustomColorsPropertyPage::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Définit les composants de couleur de la page de propriétés.|  
  
### <a name="remarks"></a>Notes  
 La `CMFCColorDialog` classe utilise cette classe pour afficher la page de propriété de couleur personnalisée. Pour plus d’informations sur `CMFCColorDialog`, consultez [CMFCColorDialog classe](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCCustomColorsPropertyPage` de l’objet et les composants de couleur de la page de propriétés.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#35;](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcustomcolorspropertypage.h  
  
##  <a name="a-namesetupa--cmfccustomcolorspropertypagesetup"></a><a name="setup"></a>CMFCCustomColorsPropertyPage::Setup  
 Définit les composants de couleur de la page de propriétés.  
  
```  
void Setup(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `R`|La composante rouge de la valeur RVB.|  
|[in] `G`|La composante verte de la valeur RVB.|  
|[in] `B`|La composante bleue de la valeur RVB.|  
  
### <a name="remarks"></a>Remarques  
 Cette méthode met à jour le cours RVB et TSL (teinte, luminosité et saturation) couleur valeurs associées de la page de propriétés. Le [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) méthode appelle cette méthode lorsque le framework initialise la boîte de dialogue couleur ou l’utilisateur appuie sur le bouton gauche de la souris. Pour plus d’informations sur `CMFCColorDialog`, consultez [CMFCColorDialog classe](../../mfc/reference/cmfccolordialog-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog (classe)](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage (classe)](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

