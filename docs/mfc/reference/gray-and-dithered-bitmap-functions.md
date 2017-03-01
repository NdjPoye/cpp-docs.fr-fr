---
title: "Fonctions d’image Bitmap tramée et grise | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: b8b6f43917dfe211f477b3dde0c94323015d18b2
ms.lasthandoff: 02/24/2017

---
# <a name="gray-and-dithered-bitmap-functions"></a>Fonctions d'image bitmap tramée et grise
**Fonctions d’image Bitmap en gris**  
  
 MFC propose deux fonctions qui permettent de donner à une image bitmap l’apparence d’un contrôle désactivé.  
  
 ![Comparaison des versions d’icônes d’origine et grise](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Dessine une version grise d’une image bitmap.|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Copie une version grise d’une image bitmap.|  
  
 **Fonctions d’image Bitmap tramée**  
  
 MFC propose également deux fonctions qui permettent de remplacer l’arrière-plan d’une image bitmap par un motif tramé.  
  
 ![Comparaison des versions d’icônes dégradées et d’origine](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Dessine une image bitmap avec un arrière-plan tramé.|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Copie une image bitmap avec un arrière-plan tramé.|  
  
##  <a name="a-nameafxdrawgraybitmapa--afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a>AfxDrawGrayBitmap  
 Dessine une version grise d’une image bitmap.  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointe vers le contrôleur de domaine de destination.  
  
 *x*  
 Coordonnée x de destination.  
  
 *y*  
 Coordonnée y de destination.  
  
 `rSrc`  
 Image bitmap source.  
  
 `crBackground`  
 Nouvelle couleur d’arrière-plan (généralement grise, comme COLOR_MENU).  
  
### <a name="remarks"></a>Notes  
 Une image bitmap dessinée avec `AfxDrawGrayBitmap` a l’apparence d’un contrôle désactivé.  
  
 ![Comparaison des versions d’icônes d’origine et grise](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#191;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  

##  <a name="a-nameafxgetgraybitmapa--afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a>AfxGetGrayBitmap  
 Copie une version grise d’une image bitmap.  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Paramètres  
 `rSrc`  
 Image bitmap source.  
  
 `pDest`  
 Image bitmap de destination.  
  
 `crBackground`  
 Nouvelle couleur d’arrière-plan (généralement grise, comme COLOR_MENU).  
  
### <a name="remarks"></a>Notes  
 Une image bitmap copiée avec `AfxGetGrayBitmap` a l’apparence d’un contrôle désactivé.  
  
 ![Comparaison des versions d’icônes d’origine et grise](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#193;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-nameafxdrawditheredbitmapa--afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a>AfxDrawDitheredBitmap  
 Dessine une bitmap, en remplaçant son arrière-plan avec un modèle de tramé (checker).  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointe vers le contrôleur de domaine de destination.  
  
 *x*  
 Coordonnée x de destination.  
  
 *y*  
 Coordonnée y de destination.  
  
 `rSrc`  
 Image bitmap source.  
  
 `cr1`  
 Une des couleurs par deux points, généralement sur blanc.  
  
 `cr2`  
 Autres tramage couleur, généralement gris clair (COLOR_MENU).  
  
### <a name="remarks"></a>Remarques  
 Le bitmap source est dessiné sur le DC de destination avec deux couleurs ( `cr1` et `cr2`) Damier remplacement en arrière-plan de la bitmap. L’arrière-plan de l’image bitmap source est défini comme son blanc et tous les pixels correspondant à la couleur du pixel dans le coin supérieur gauche de la bitmap.  
  
 ![Comparaison des versions d’icônes dégradées et d’origine](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#190;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  


##  <a name="a-nameafxgetditheredbitmapa--afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a>AfxGetDitheredBitmap  
 Copie une image bitmap, en remplaçant son arrière-plan avec un modèle de tramé (checker).  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Paramètres  
 `rSrc`  
 Image bitmap source.  
  
 `pDest`  
 Image bitmap de destination.  
  
 `cr1`  
 Une des couleurs par deux points, généralement sur blanc.  
  
 `cr2`  
 Autres tramage couleur, généralement gris clair (COLOR_MENU).  
  
### <a name="remarks"></a>Notes  
 Le bitmap source est copié vers la bitmap de destination avec deux couleurs ( `cr1` et `cr2`) Damier remplacement en arrière-plan de la bitmap source. L’arrière-plan de l’image bitmap source est défini comme son blanc et tous les pixels correspondant à la couleur du pixel dans le coin supérieur gauche de la bitmap.  
  
 ![Comparaison des versions d’icônes dégradées et d’origine](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#192;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

