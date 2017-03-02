---
title: Classe de CMFCRibbonMainPanel | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel class
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3fc37a953e62e6ea90de8402b7f2912b06967e13
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel (classe)
Implémente un panneau de ruban qui s’affiche lorsque vous cliquez sur le [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Constructeur par défaut.|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|Ajoute un élément de ruban dans le volet gauche du panneau bouton application. (Substitue [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|Ajoute une chaîne de texte dans le menu de liste de fichiers récents.|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|Ajoute un élément de ruban dans le volet inférieur du panneau d’application de ruban.|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|Ajoute un élément de ruban dans le volet droit du panneau bouton application.|  
|`CMFCRibbonMainPanel::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|Retourne un rectangle qui représente la zone du panneau principal du ruban.|  
|`CMFCRibbonMainPanel::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
  
## <a name="remarks"></a>Remarques  
 Le framework affiche la `CMFCRibbonMainPanel` lorsque vous ouvrez le panneau de configuration d’application. Il contient trois volets :  
  
-   Le volet gauche contient les commandes associées aux fichiers, telles que **Open**, **enregistrer**, **Print**, et **fermer**. Pour ajouter une commande à ce volet, appelez [CMFCRibbonMainPanel::Add](#add).  
  
-   Le volet droit contient les options qui modifient la commande que vous sélectionnez dans le volet gauche. Par exemple, si vous cliquez sur **Enregistrer sous** dans le volet gauche, le volet droit pour afficher les types de fichiers disponibles. Pour ajouter un élément dans ce volet, appelez [CMFCRibbonMainPanel::AddToRight](#addtoright).  
  
-   Le volet inférieur contient des boutons qui vous permettent de modifier les paramètres de l’application et de quitter le programme. Pour ajouter un élément dans ce volet, appelez [CMFCRibbonMainPanel::AddToBottom](#addtobottom).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxRibbonMainPanel.h  
  
##  <a name="a-nameadda--cmfcribbonmainpaneladd"></a><a name="add"></a>CMFCRibbonMainPanel::Add  
 Ajoute un élément de ruban dans le volet gauche du panneau bouton application.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] [out]`pElem`  
 Pointeur vers l’élément de ruban à ajouter dans le volet principal.  
  
### <a name="remarks"></a>Remarques  
 Ajoute un élément de ruban dans le panneau. Les éléments ajoutés à l’aide de cette méthode seront situées dans la colonne gauche du panneau principal.  
  
##  <a name="a-nameaddrecentfileslista--cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList  
 Ajoute une chaîne de texte dans le menu de liste de fichiers récents.  
  
```  
void AddRecentFilesList(
    LPCTSTR lpszLabel,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszLabel`  
 Spécifie la chaîne à ajouter à la liste des fichiers récents.  
  
 `nWidth`  
 Spécifie la largeur, en pixels, du panneau liste des fichiers récents.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameaddtobottoma--cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a>CMFCRibbonMainPanel::AddToBottom  
 Ajoute un élément de ruban dans le volet inférieur du panneau d’application de ruban.  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] [out]`pElem`  
 Pointeur vers l’élément de ruban à ajouter au bas du panneau principal.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddtorighta--cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a>CMFCRibbonMainPanel::AddToRight  
 Ajoute un élément de ruban dans le volet droit du panneau bouton application.  
  
```  
void AddToRight(
    CMFCRibbonBaseElement* pElem,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>Paramètres  
 `pElem`  
 Pointeur vers un élément de ruban à ajouter à la partie droite de la fenêtre principale.  
  
 `nWidth`  
 Spécifie la largeur, en pixels, du volet de droite.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction permet d’ajouter un élément de ruban dans le volet de droite. Le volet droit affiche généralement la liste des fichiers récents, mais vous pouvez ajouter n’importe quel autre élément de ruban ici.  
  
##  <a name="a-namegetcommandsframea--cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a>CMFCRibbonMainPanel::GetCommandsFrame  
 Retourne un rectangle qui représente la zone du panneau principal du ruban.  
  
```  
CRect GetCommandsFrame() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un rectangle qui représente la zone du panneau principal du ruban.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel (classe)](../../mfc/reference/cmfcribbonpanel-class.md)

