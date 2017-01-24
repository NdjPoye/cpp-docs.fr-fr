---
title: "CToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitmaps (C++), button controls"
  - "boutons (C++), MFC toolbars"
  - "control bars [C++], CToolBar class"
  - "CToolBar class"
  - "barres d'outils (C++), CToolBar class"
  - "Windows common controls [C++], CToolBar class"
  - "Windows toolbar common controls [C++]"
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Barres de contrôles qui ont une ligne de boutons générés une correspondance de bits et de séparateurs facultatifs.  
  
## Syntaxe  
  
```  
class CToolBar : public CControlBar  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CToolBar::CToolBar](../Topic/CToolBar::CToolBar.md)|Construit un objet `CToolBar`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CToolBar::CommandToIndex](../Topic/CToolBar::CommandToIndex.md)|Retourne l'index d'un bouton avec l'ID de commande donnée|  
|[CToolBar::Create](../Topic/CToolBar::Create.md)|Crée la barre d'outils windows et l'attache à l'objet d' `CToolBar` .|  
|[CToolBar::CreateEx](../Topic/CToolBar::CreateEx.md)|Crée un objet d' `CToolBar` avec les styles supplémentaires pour l'objet incorporé d' `CToolBarCtrl` .|  
|[CToolBar::GetButtonInfo](../Topic/CToolBar::GetButtonInfo.md)|Extrait l'ID, le style, et le nombre d'image d'un bouton.|  
|[CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md)|Récupère le style d'un bouton.|  
|[CToolBar::GetButtonText](../Topic/CToolBar::GetButtonText.md)|Extrait le texte qui apparaîtra sur un bouton.|  
|[CToolBar::GetItemID](../Topic/CToolBar::GetItemID.md)|Retourne l'ID de commande d'un bouton ou un séparateur à l'index donné.|  
|[CToolBar::GetItemRect](../Topic/CToolBar::GetItemRect.md)|Récupère le rectangle d'affichage de l'élément à l'index donné.|  
|[CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md)|Autorise l'accès direct au contrôle commun sous\-jacent.|  
|[CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)|Charge la bitmap contenant des images de bouton bitmap.|  
|[CToolBar::LoadToolBar](../Topic/CToolBar::LoadToolBar.md)|Charge une ressource de barre d'outils créée avec l'éditeur de ressources.|  
|[CToolBar::SetBitmap](../Topic/CToolBar::SetBitmap.md)|Définit une image générée une correspondance de bits.|  
|[CToolBar::SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md)|Définit l'ID, le style, et le nombre d'image d'un bouton.|  
|[CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)|Définit les styles des boutons et un index des images de bouton dans la bitmap.|  
|[CToolBar::SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md)|Définit le style d'un bouton.|  
|[CToolBar::SetButtonText](../Topic/CToolBar::SetButtonText.md)|Définit le texte qui apparaîtra sur un bouton.|  
|[CToolBar::SetHeight](../Topic/CToolBar::SetHeight.md)|Définit la hauteur de la barre d'outils.|  
|[CToolBar::SetSizes](../Topic/CToolBar::SetSizes.md)|Définit les tailles des boutons et leurs bitmap.|  
  
## Notes  
 Les boutons peuvent agir comme des boutons poussoir, les boutons de case à cocher, ou des cases d'option.  Les objets d'`CToolBar` sont généralement les membres incorporé des objets de fenêtre frame dérivés de la classe [CFrameWnd](../../mfc/reference/cframewnd-class.md) ou [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).  
  
 [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md), une fonction membre nouvelle aux MFC 4,0, vous permet de tirer parti de la prise en charge de contrôles communs Windows à la personnalisation et de la fonctionnalité supplémentaire de barre d'outils.  Les fonctions membres d'`CToolBar` vous fournissent plus de les fonctionnalités des contrôles communs Windows ; toutefois, lorsque vous appelez `GetToolBarCtrl`, vous pouvez permettre à vos barres d'outils bien plus les caractéristiques des barres d'outils Windows 95\/98.  Lorsque vous appelez `GetToolBarCtrl`, il retourne une référence à un objet d' `CToolBarCtrl` .  Consultez [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) pour plus d'informations sur la conception de barres d'outils à des contrôles communs Windows.  Pour plus d'informations générales sur les contrôles communs, consultez [contrôles communs](http://msdn.microsoft.com/library/windows/desktop/bb775493) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Visual C\+\+ fournit deux méthodes pour créer une barre d'outils.  Pour créer une ressource de barre d'outils à l'aide de l'éditeur de ressources, suivez ces étapes :  
  
1.  Créez une ressource de barre d'outils.  
  
2.  Construisez l'objet d' `CToolBar` .  
  
3.  Appelez la fonction de [Create](../Topic/CToolBar::Create.md) \(ou [CreateEx](../Topic/CToolBar::CreateEx.md)\) pour créer la barre d'outils windows et pour la liaison à l'objet d' `CToolBar` .  
  
4.  Appel [LoadToolBar](../Topic/CToolBar::LoadToolBar.md) pour charger la ressource de barre d'outils.  
  
 Sinon, suivez ces étapes :  
  
1.  Construisez l'objet d' `CToolBar` .  
  
2.  Appelez la fonction de [Create](../Topic/CToolBar::Create.md) \(ou [CreateEx](../Topic/CToolBar::CreateEx.md)\) pour créer la barre d'outils windows et pour la liaison à l'objet d' `CToolBar` .  
  
3.  Appelez [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) pour charger la bitmap qui contient des images de bouton de barre d'outils.  
  
4.  Appelez [SetButtons](../Topic/CToolBar::SetButtons.md) pour définir le style de boutons et associer chaque bouton avec une image dans la bitmap.  
  
 Toutes les images de bouton dans la barre d'outils sont prises d'une bitmap, qui doit contenir une image pour chaque bouton.  Toutes les images doivent être la même taille ; la valeur par défaut est 16 pixels de largeur et de 15 pixels de haut.  Les images doivent être côte à côte dans la bitmap.  
  
 La fonction d' `SetButtons` prend un pointeur vers un tableau des ID de contrôle et d'un entier qui spécifie le nombre d'éléments du tableau.  La fonction définit l'ID de chaque bouton à la valeur de l'élément correspondant du tableau et l'assigne à chaque bouton un index d'image, qui spécifie la position de l'image du bouton dans la bitmap.  Si un élément de tableau a la valeur **ID\_SEPARATOR**, aucun index d'image n'est assigné.  
  
 L'ordre des images dans la bitmap est généralement l'ordre dans lequel ils sont dessinés à l'écran, mais vous pouvez utiliser la fonction de [SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md) pour modifier la relation entre la commande d'image et l'ordre de dessin.  
  
 Tous les boutons d'une barre d'outils ont la même taille.  La valeur par défaut est conforme au format 24 x 22 pixels, *les indications d'interface Windows pour la conception de logiciels*.  Tout espace supplémentaire entre l'image et les dimensions du bouton est utilisé pour former une bordure autour de l'image.  
  
 Chaque bouton a une image.  Les différents états de bouton et styles \(appuyés, en haut, vers le bas, de désactivé, désactivé vers le bas, et indéterminé\) sont générés de cette image.  Bien que les bitmaps puissent être n'importe quelle couleur, vous pouvez obtenir les meilleurs résultats possibles avec des images dans le noir et les nuances de gris.  
  
> [!WARNING]
>  Bitmap prend en charge d'`CToolBar` avec un maximum de 16 couleurs.  Lorsque vous chargez une image dans un éditeur de barre d'outils, Visual Studio convertit automatiquement l'image à une couleur 16 bitmap si nécessaire, et affiche un message d'avertissement si l'image est convertie.  Si vous utilisez une image avec plus de 16 couleurs \(à l'aide d'un éditeur externe de modifier l'image\), l'application peut se comporter de façon inattendue.  
  
 Les boutons de barre d'outils imitent des boutons poussoir par défaut.  Toutefois, les boutons de barre d'outils peuvent également imiter des boutons ou des cases d'option de case à cocher.  Les boutons de case à cocher ont trois états : contrôlé, supprimé, et indéterminé.  Les cases d'option ont deux états : contrôlé et supprimé.  
  
 Pour définir un style individuelles de bouton ou de séparateur sans pointer vers un tableau, un appel [GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) pour récupérer le style, puis appeler [SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md) au lieu d' `SetButtons`.  `SetButtonStyle` est très utile lorsque vous souhaitez modifier le style d'un bouton au moment de l'exécution.  
  
 Pour assigner le texte à afficher sur un bouton, un appel [GetButtonText](../Topic/CToolBar::GetButtonText.md) pour récupérer le texte à afficher sur le bouton, puis appeler [SetButtonText](../Topic/CToolBar::SetButtonText.md) pour définir le texte.  
  
 Pour créer un bouton de case à cocher, assignez \-lui le style **TBBS\_CHECKBOX** ou utilisez la fonction membre d' `SetCheck` d'un objet d' `CCmdUI` dans un gestionnaire d' `ON_UPDATE_COMMAND_UI` .  Appeler `SetCheck` transforme un bouton poussoir en bouton de case à cocher.  Passez `SetCheck` un argument de 0 pour non réprimé, de 1 pour vérifié, ou 2 indéterminé.  
  
 Pour créer une case d'option, appelez la fonction membre de [SetRadio](../Topic/CCmdUI::SetRadio.md) d'un objet de [CCmdUI](../../mfc/reference/ccmdui-class.md) d'un gestionnaire d' `ON_UPDATE_COMMAND_UI` .  Passez `SetRadio` un argument de 0 pour non réprimé ou différent de zéro pour contrôlé.  Pour fournir un groupe de cases d'option mutuellement exclusif comportement, vous devez avoir des gestionnaires d' `ON_UPDATE_COMMAND_UI` pour tous les boutons au groupe.  
  
 Pour plus d'informations sur l'utilisation `CToolBar`, consultez l'article [Implémentation de barre d'outils MFC](../../mfc/mfc-toolbar-implementation.md) et [note technique 31 : barres de contrôles](../../mfc/tn031-control-bars.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [CTRLBARS exemple MFC](../../top/visual-cpp-samples.md)   
 [MFC exemple DLGCBR32](../../top/visual-cpp-samples.md)   
 [MFC exemple DOCKTOOL](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CToolBar::Create](../Topic/CToolBar::Create.md)   
 [CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)   
 [CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)   
 [CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)   
 [CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)