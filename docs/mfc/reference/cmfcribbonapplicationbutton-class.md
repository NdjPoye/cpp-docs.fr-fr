---
title: Classe de CMFCRibbonApplicationButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonApplicationButton class
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
caps.latest.revision: 25
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
ms.openlocfilehash: a6fc19c2af854f3cd4ee3dc3a3008abcb4714ba3
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton (classe)
Implémente un bouton spécial situé dans l'angle supérieur gauche de la fenêtre d'application. Une fois activé, le bouton ouvre un menu qui contient généralement des commandes **Fichier** courantes telles que **Ouvrir**, **Enregistrer**et **Quitter**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Construit et initialise un objet `CMFCRibbonApplicationButton`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonApplicationButton::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCRibbonApplicationButton::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Assigne une image pour le bouton application de ruban.|  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans la `CMFCRibbonApplicationButton` classe. L’exemple montre comment définir une image pour le bouton de l’application et comment définir son info-bulle. Cet extrait de code fait partie de la [Client dessiner, exemple](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient n °&4;](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient n °&5;](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxRibbonBar.h  
  
##  <a name="cmfcribbonapplicationbutton"></a>CMFCRibbonApplicationButton::CMFCRibbonApplicationButton  
 Construit et initialise un [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) objet.  
  
```  
CMFCRibbonApplicationButton();  
CMFCRibbonApplicationButton(UINT uiBmpResID);  
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>Paramètres  
 `uiBmpResID`  
 L’ID de ressource de l’image à afficher sur le bouton de l’application.  
  
 `hBmp`  
 Handle d’une image bitmap à afficher sur le bouton de l’application.  
  
### <a name="remarks"></a>Notes  
 Le bouton application de ruban est un bouton spécial situé dans le coin supérieur gauche de la fenêtre d’application. Lorsqu’un utilisateur clique sur ce bouton, l’application ouvre un menu qui contient généralement commun **fichier** des commandes, telles que **Open**, **enregistrer**, et **Exit**.  
  
##  <a name="setimage"></a>CMFCRibbonApplicationButton::SetImage  
 Assigne une image sur le bouton de l’application.  
  
```  
void SetImage(UINT uiBmpResID);  
void SetImage(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiBmpResID`  
 L’ID de ressource de l’image à afficher sur le bouton de l’application.  
  
 [in] `hBmp`  
 Handle d’une image bitmap à afficher sur le bouton de l’application.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour affecter une nouvelle image pour le bouton application de ruban après avoir créé le bouton. Le bouton de l’application se trouve dans le coin supérieur gauche de la fenêtre d’application.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton (classe)](../../mfc/reference/cmfcribbonbutton-class.md)

