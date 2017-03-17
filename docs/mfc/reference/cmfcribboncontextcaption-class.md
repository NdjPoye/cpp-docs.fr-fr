---
title: Classe de CMFCRibbonContextCaption | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonContextCaption class
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
caps.latest.revision: 24
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
ms.openlocfilehash: 54f71af5ec46a8ddac4459e9ffdbc5b10f3106d4
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption (classe)
Implémente une légende colorée qui apparaît en haut d'une catégorie de ruban ou d'une catégorie de contexte.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonContextCaption : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonContextCaption::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCRibbonContextCaption::GetColor](#getcolor)|Retourne la couleur de la légende.|  
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||  
|`CMFCRibbonContextCaption::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe ne peut pas être instanciée directement. Le [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) classe utilise cette classe en interne pour ajouter une couleur à des catégories de ruban.  
  
 Pour définir la couleur pour les catégories du ruban, appelez [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor). Pour définir la couleur pour les catégories de contexte, appelez [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxRibbonBar.h  
  
##  <a name="getcolor"></a>CMFCRibbonContextCaption::GetColor  
 Retourne la couleur d’arrière-plan de la légende.  
  
```  
AFX_RibbonCategoryColor GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur retournée peut être une des valeurs énumérées suivantes :  
  
- `AFX_CategoryColor_None`  
  
- `AFX_CategoryColor_Red`  
  
- `AFX_CategoryColor_Orange`  
  
- `AFX_CategoryColor_Yellow`  
  
- `AFX_CategoryColor_Green`  
  
- `AFX_CategoryColor_Blue`  
  
- `AFX_CategoryColor_Indigo`  
  
- `AFX_CategoryColor_Violet`  
  
### <a name="remarks"></a>Remarques  
 La couleur de la légende peut être définie en appelant [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) ou [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).  
  
##  <a name="getrighttabx"></a>CMFCRibbonContextCaption::GetRightTabX  
 Récupère la position du bord droit de l’onglet de ruban de la catégorie.  
  
```  
int GetRightTabX() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de X droite du rectangle englobant de le `CMFCRibbonCategory` onglet de ruban de l’objet ou la valeur -1 si l’onglet est tronqué.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton (classe)](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Classe de CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBar (classe)](../../mfc/reference/cmfcribbonbar-class.md)

