---
title: Classe de CMFCImageEditorDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog class
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1a629f9699aa2d6fb185737b51b36259ce574fe0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditordialog-class"></a>Classe de CMFCImageEditorDialog
La `CMFCImageEditorDialog` classe prend en charge une image de boîte de dialogue de l’éditeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Construit un objet `CMFCImageEditorDialog`.|  
  
## <a name="remarks"></a>Remarques  
 La `CMFCImageEditorDialog` classe fournit une boîte de dialogue qui inclut :  
  
-   Une zone d’image qui vous permet de modifier les pixels individuels dans une image.  
  
-   Outils pour modifier les pixels de la zone de dessin.  
  
-   Une palette de couleurs pour spécifier la couleur qui est utilisée par les outils de dessin.  
  
-   Une zone d’aperçu qui affiche l’effet de votre modification.  
  
 L’illustration suivante montre un éditeur d’images de boîte de dialogue.  
  
 ![Boîte de dialogue CMFCImageEditorDialog](../../mfc/reference/media/imageedit.png "imageedit")  
  
 Pour utiliser un `CMFCImageEditorDialog` objet consiste à transmettre un `CBitmap` l’image à modifier. Ne créez pas une grande image, car l’image de la zone de modification a une taille limitée et la taille en pixels logiques est ajustée à la zone. Appelez le `DoModal` méthode de démarrage d’une boîte de dialogue modale.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afximageeditordialog.h  
  
##  <a name="a-namecmfcimageeditordialoga--cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>CMFCImageEditorDialog::CMFCImageEditorDialog  
 Construit un objet `CMFCImageEditorDialog`.  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBitmap`  
 Pointeur vers une image.  
  
 `pParent`  
 Pointeur vers la fenêtre parente de la boîte de dialogue Éditeur image actuelle.  
  
 `nBitsPixel`  
 Le nombre de bits utilisés pour représenter la couleur d’un pixel, qui est également appelé une profondeur de couleurs.  Si le `nBitsPixel` paramètre est -1, la profondeur de couleur est dérivée de l’image spécifiée par la `pBitmap` paramètre. La valeur par défaut est -1.  
  
### <a name="return-value"></a>Valeur de retour  
 Pour modifier une image, passez un pointeur de l’image pour le `CMFCImageEditorDialog` constructeur. Appelez ensuite la `DoModal` méthode pour ouvrir la boîte de dialogue modale. Lors de la `DoModal` méthode est retournée, la bitmap contient la nouvelle image.  
  
### <a name="remarks"></a>Remarques  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un objet de la `CMFCImageEditorDialog` classe. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls n °&8;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls numéro&40;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar (classe)](../../mfc/reference/cmfctoolbar-class.md)

