---
title: Classe de CMFCImagePaintArea | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCImagePaintArea class
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
caps.latest.revision: 21
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
ms.openlocfilehash: c16fd9605474e57f167646ddc9bc91d235d1cba5
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea (classe)
Fournit la zone d’image qui vous permet de modifier une image dans une boîte de dialogue Éditeur image.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Construit un objet `CMFCImagePaintArea`.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCImagePaintArea::GetMode](#getmode)|Récupère le mode de dessin en cours.|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Définit l’image bitmap de la zone d’image.|  
|[CMFCImagePaintArea::SetColor](#setcolor)|Définit la couleur de dessin actuelle.|  
|[CMFCImagePaintArea::SetMode](#setmode)|Définit le mode de dessin en cours.|  
  
### <a name="remarks"></a>Notes  
 Cette classe n’est pas destinée à être utilisée directement à partir de votre code.  
  
 Le framework utilise cette classe pour afficher la zone d’image dans la zone de boîte de dialogue Éditeur d’image. Pour plus d’informations sur la boîte de dialogue Éditeur image, consultez [CMFCImageEditorDialog classe](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un objet de la `CMFCImagePaintArea` de classe, défini en cours de dessin couleur, définir le mode de dessin en cours et définir l’image bitmap de la zone d’image.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#37;](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afximagepaintarea.h  
  
##  <a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea  
 Construit un objet `CMFCImagePaintArea`.  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `pParentDlg`|Pointeur vers la boîte de dialogue qui est le parent de l’éditeur d’images.|  
  
##  <a name="getmode"></a>CMFCImagePaintArea::GetMode  
 Récupère le mode de dessin en cours.  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) valeur qui spécifie le mode de dessin en cours.  
  
##  <a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap  
 Définit l’image bitmap de la zone d’image.  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `pBitmap`|La nouvelle image bitmap à afficher.|  
  
### <a name="remarks"></a>Remarques  
 Si `pBitmap` est `NULL`, cette méthode définit la taille de la zone modifiable de peinture à zéro. Dans le cas contraire, il définit la taille de la zone modifiable de peinture à la taille de l’image bitmap fourni.  
  
##  <a name="setcolor"></a>CMFCImagePaintArea::SetColor  
 Définit la couleur de dessin actuelle.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `color`|La nouvelle couleur de dessin.|  
  
### <a name="remarks"></a>Notes  
 Lorsque vous sélectionnez une couleur dans la barre de palette éditeur image ou un sélecteur de couleurs, le framework appelle cette méthode pour mettre à jour la couleur de dessin actuelle. La couleur de dessin initiale est noire (un `COLORREF` la valeur 0).  
  
 La couleur de dessin est utilisée par la boîte de dialogue Éditeur image pour tous les modes de dessin à l’exception de `IMAGE_EDIT_MODE_COLOR`. Pour plus d’informations sur les modes de dessin, consultez [CMFCImagePaintArea::IMAGE_EDIT_MODE énumération](cmfcimagepaintarea-image-edit-mode-enumeration.md).  
  
##  <a name="setmode"></a>CMFCImagePaintArea::SetMode  
 Définit le mode de dessin en cours.  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `mode`|Un [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) valeur qui spécifie le mode de dessin en cours.|  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe de CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

