---
title: "CMFCDesktopAlertWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDesktopAlertWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWnd class"
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCDesktopAlertWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCDesktopAlertWnd` implémente les fonctionnalités d'une boîte de dialogue non modale qui apparaît sur l'écran informer l'utilisateur sur un événement.  
  
## Syntaxe  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)|Crée et initialise la fenêtre d'alerte sur le bureau.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::GetAnimationSpeed.md)|Retourne la vitesse d'animation.|  
|[CMFCDesktopAlertWnd::GetAnimationType](../Topic/CMFCDesktopAlertWnd::GetAnimationType.md)|Retourne le type d'animation.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::GetAutoCloseTime.md)|Retourne l'heure de fin automatique.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](../Topic/CMFCDesktopAlertWnd::GetCaptionHeight.md)|Retourne la hauteur de la légende.|  
|[CMFCDesktopAlertWnd::GetDialogSize](../Topic/CMFCDesktopAlertWnd::GetDialogSize.md)||  
|[CMFCDesktopAlertWnd::GetLastPos](../Topic/CMFCDesktopAlertWnd::GetLastPos.md)|Retourne la dernière position valide de la fenêtre d'alerte sur le bureau à l'écran.|  
|[CMFCDesktopAlertWnd::GetTransparency](../Topic/CMFCDesktopAlertWnd::GetTransparency.md)|Retourne le niveau de transparence.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](../Topic/CMFCDesktopAlertWnd::HasSmallCaption.md)|Détermine si la fenêtre d'alerte sur le bureau est affichée avec la petite légende.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](../Topic/CMFCDesktopAlertWnd::OnBeforeShow.md)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](../Topic/CMFCDesktopAlertWnd::OnClickLinkButton.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur un bouton de lien situé dans le menu d'alerte sur le bureau.|  
|[CMFCDesktopAlertWnd::OnCommand](../Topic/CMFCDesktopAlertWnd::OnCommand.md)|L'infrastructure appelle cette fonction membre lorsque l'utilisateur sélectionne un élément d'un menu, lorsqu'un contrôle enfant envoie un message de notification, ou lorsqu'une séquence de touches d'accélérateur est traduite.  \(Substitutions [CWnd::OnCommand](../Topic/CWnd::OnCommand.md).\)|  
|[CMFCDesktopAlertWnd::OnDraw](../Topic/CMFCDesktopAlertWnd::OnDraw.md)||  
|[CMFCDesktopAlertWnd::ProcessCommand](../Topic/CMFCDesktopAlertWnd::ProcessCommand.md)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md)|Définit la nouvelle vitesse d'animation.|  
|[CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md)|Définit le type d'animation.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::SetAutoCloseTime.md)|Définit la durée totale automatique fin.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md)|Bascule entre des petites et normales légendes.|  
|[CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md)|Définit le niveau de transparence.|  
  
## Notes  
 Une fenêtre d'alerte sur le bureau peut être transparente, elle peut apparaître avec des effets d'animation, et peut disparaître \(après un délai spécifié ou lorsque l'utilisateur éloigne en cliquant sur le bouton Fermer.\)  
  
 Une fenêtre d'alerte sur le bureau peut également contenir une boîte de dialogue par défaut qui contient une icône, le texte du message \(une étiquette\), et un lien.  Sinon, une fenêtre d'alerte sur le bureau peut contenir une boîte de dialogue personnalisé des ressources de l'application.  
  
 Vous créez une fenêtre d'alerte sur le bureau en deux étapes.  d'abord, appelez le constructeur pour construire l'objet d' `CMFCDesktopAlertWnd` .  Ensuite, appelez la fonction membre de [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) pour créer la fenêtre et pour la liaison à l'objet d' `CMFCDesktopAlertWnd` .  
  
 L'objet d' `CMFCDesktopAlertWnd` crée une boîte de dialogue enfant spéciale qui remplit la zone cliente de la fenêtre d'alerte sur le bureau.  La boîte de dialogue détient tous les contrôles qui sont positionnés sur.  
  
 Pour afficher une boîte de dialogue personnalisée de la fenêtre contextuelle, suivez ces étapes :  
  
1.  Dériver une classe de `CMFCDesktopAlertDialog`.  
  
2.  Créez un modèle de boîte de dialogue enfant dans les ressources.  
  
3.  Appelez [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) à l'aide de l'ID de ressource de modèle de boîte de dialogue et d'un pointeur vers des informations de classe d'exécution de la classe dérivée.  
  
4.  Programmez la boîte de dialogue personnalisée pour traiter les notifications provenant de contrôles hébergés, ou programmez les contrôles hébergés pour traiter ces notifications directement.  
  
 Utilisez les fonctions suivantes pour contrôler le comportement de la fenêtre d'alerte sur le Bureau :  
  
-   Définissez le type d'animation en appelant [CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md).  Les options valides incluent dévoilent, faites glisser, et si atténuent.  
  
-   Définissez la vitesse de frame d'animation en appelant [CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md).  
  
-   Définissez le niveau de transparence en appelant [CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md).  
  
-   Remplacez la taille de la légende par petit en appelant [CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md).  La petite légende est 7 pixels de haut.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCDesktopAlertWnd` pour configurer un objet d' `CMFCDesktopAlertWnd` .  L'exemple montre comment définir un type d'animation, un fixé la transparence de la fenêtre indépendante, spécifient que la fenêtre signale affiche une petite légende, et définissent le temps qui s'exécute avant la fenêtre signale ferme automatiquement.  L'exemple montre également comment créer et initialiser la fenêtre d'alerte sur le bureau.  Cet extrait de code fait partie d' [Exemple d'alerte de démonstration de Bureau](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwnd-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## Configuration requise  
 **en\-tête :** afxDesktopAlertWnd.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo Class](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)