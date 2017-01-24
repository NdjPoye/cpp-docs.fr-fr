---
title: "CMFCStatusBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStatusBar class"
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCStatusBar` implémente une barre d'état similaire à la classe d' `CStatusBar` .  Toutefois, la classe d' `CMFCStatusBar` possède des fonctionnalités non offertes par la classe d' `CStatusBar` , telle que la possibilité d'afficher des images, des animations, et les barres de progression ; et la possibilité de répondre à des doublons clics de souris.  
  
## Syntaxe  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](../Topic/CMFCStatusBar::CalcFixedLayout.md)|\(Substitutions [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCStatusBar::CommandToIndex](../Topic/CMFCStatusBar::CommandToIndex.md)||  
|[CMFCStatusBar::Create](../Topic/CMFCStatusBar::Create.md)|Crée une barre de contrôles et la attaché à l'objet de [CPane](../../mfc/reference/cpane-class.md) .  \(Substitutions [CPane::Create](../Topic/CPane::Create.md).\)|  
|[CMFCStatusBar::CreateEx](../Topic/CMFCStatusBar::CreateEx.md)|Crée une barre de contrôles et la attaché à l'objet de [CPane](../../mfc/reference/cpane-class.md) .  \(Substitutions [CPane::CreateEx](../Topic/CPane::CreateEx.md).\)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](../Topic/CMFCStatusBar::DoesAllowDynInsertBefore.md)|Détermine si un autre volet peut être dynamiquement inséré entre ce volet et le frame parent.  \(Substitutions [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CMFCStatusBar::EnablePaneDoubleClick](../Topic/CMFCStatusBar::EnablePaneDoubleClick.md)|Active ou désactive la gestion des doublons clics de souris dans la barre d'état.|  
|[CMFCStatusBar::EnablePaneProgressBar](../Topic/CMFCStatusBar::EnablePaneProgressBar.md)|Affiche une barre de progression dans le volet spécifié.|  
|[CMFCStatusBar::GetCount](../Topic/CMFCStatusBar::GetCount.md)|Retourne le nombre de volets dans la barre d'état.|  
|[CMFCStatusBar::GetDrawExtendedArea](../Topic/CMFCStatusBar::GetDrawExtendedArea.md)||  
|[CMFCStatusBar::GetExtendedArea](../Topic/CMFCStatusBar::GetExtendedArea.md)||  
|[CMFCStatusBar::GetItemID](../Topic/CMFCStatusBar::GetItemID.md)||  
|[CMFCStatusBar::GetItemRect](../Topic/CMFCStatusBar::GetItemRect.md)||  
|[CMFCStatusBar::GetPaneInfo](../Topic/CMFCStatusBar::GetPaneInfo.md)||  
|[CMFCStatusBar::GetPaneProgress](../Topic/CMFCStatusBar::GetPaneProgress.md)||  
|[CMFCStatusBar::GetPaneStyle](../Topic/CMFCStatusBar::GetPaneStyle.md)|Retourne le style de volet.  \(Substitutions [CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md).\)|  
|[CMFCStatusBar::GetPaneText](../Topic/CMFCStatusBar::GetPaneText.md)||  
|[CMFCStatusBar::GetPaneWidth](../Topic/CMFCStatusBar::GetPaneWidth.md)|Retourne la largeur, en pixels, du volet spécifié de la barre d'état.|  
|[CMFCStatusBar::GetTipText](../Topic/CMFCStatusBar::GetTipText.md)|Retourne le texte d'info\-bulle pour le volet spécifié de la barre d'état.|  
|[CMFCStatusBar::InvalidatePaneContent](../Topic/CMFCStatusBar::InvalidatePaneContent.md)|Invalide le volet spécifié et redessine son contenu.|  
|[CMFCStatusBar::PreCreateWindow](../Topic/CMFCStatusBar::PreCreateWindow.md)|Appelé par l'infrastructure avant la création de la fenêtre de windows attachée à cet objet d' `CWnd` .  \(Substitutions [CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md).\)|  
|[CMFCStatusBar::SetDrawExtendedArea](../Topic/CMFCStatusBar::SetDrawExtendedArea.md)||  
|[CMFCStatusBar::SetIndicators](../Topic/CMFCStatusBar::SetIndicators.md)||  
|[CMFCStatusBar::SetPaneAnimation](../Topic/CMFCStatusBar::SetPaneAnimation.md)|Assigne une animation dans le volet spécifié.|  
|[CMFCStatusBar::SetPaneBackgroundColor](../Topic/CMFCStatusBar::SetPaneBackgroundColor.md)|Définit la couleur d'arrière\-plan du volet spécifié de la barre d'état.|  
|[CMFCStatusBar::SetPaneIcon](../Topic/CMFCStatusBar::SetPaneIcon.md)|Définit l'icône d'indicateur pour le volet spécifié de la barre d'état.|  
|[CMFCStatusBar::SetPaneInfo](../Topic/CMFCStatusBar::SetPaneInfo.md)||  
|[CMFCStatusBar::SetPaneProgress](../Topic/CMFCStatusBar::SetPaneProgress.md)|Définit la progression actuelle de la barre de progression du volet spécifié de la barre d'état.|  
|[CMFCStatusBar::SetPaneStyle](../Topic/CMFCStatusBar::SetPaneStyle.md)|Définit le style du volet.  \(Substitutions [CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md).\)|  
|[CMFCStatusBar::SetPaneText](../Topic/CMFCStatusBar::SetPaneText.md)||  
|[CMFCStatusBar::SetPaneTextColor](../Topic/CMFCStatusBar::SetPaneTextColor.md)|Définit la couleur de texte du volet spécifié de la barre d'état.|  
|[CMFCStatusBar::SetPaneWidth](../Topic/CMFCStatusBar::SetPaneWidth.md)|Définit la largeur en pixels du volet spécifié de la barre d'état.|  
|[CMFCStatusBar::SetTipText](../Topic/CMFCStatusBar::SetTipText.md)|Définit le texte d'info\-bulle pour le volet spécifié de la barre d'état.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCStatusBar::OnDrawPane](../Topic/CMFCStatusBar::OnDrawPane.md)|Appelé par l'infrastructure lorsqu'elle redessine le volet de la barre d'état.|  
  
## Notes  
 Le diagramme suivant illustre une illustration de la barre d'état de l'application d' [Exemple de démonstration de barre d'état](../../top/visual-cpp-samples.md) .  
  
 ![Exemple de CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar")  
  
## Exemple  
 L'exemple suivant illustre l'utilisation des variables locales que l'application utilise pour appeler des méthodes dans la classe d' `CMFCStatusBar` .  Ces variables sont déclarées dans StatusBarDemoView.h.  Le frame principal est déclaré dans MainFrm.h, le document est déclaré dans StatusBarDemoDoc.h, et la vue est déclarée dans StatusBarDemoView.h.  Cet extrait de code fait partie d' [Exemple de démonstration de barre d'état](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_1.h)]  
  
## Exemple  
 L'exemple suivant montre comment obtenir une référence à l'objet d' `CMFCStatusBar` en tapant la méthode d' `GetStatusBar` dans MainFrm.h puis en appelant cette méthode de la méthode d' `GetStatusBar` dans StatusBarDemoView.h.  Cet extrait de code fait partie d' [Exemple de démonstration de barre d'état](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_3.h)]  
  
## Exemple  
 L'exemple suivant montre comment appeler des méthodes dans la classe d' `CMFCStatusBar` dans StatusBarDemoView.cpp.  Les constantes sont déclarées dans MainFrm.h.  L'exemple suivant indique comment définir l'icône, définir le texte d'info\-bulle du volet de barre d'état, afficher une barre de progression dans le volet spécifié, assigner une animation dans le volet spécifié, définir le texte et la largeur du volet de barre d'état, et définir l'indicateur de progression actuel de la barre de progression du volet de barre d'état.  Cet extrait de code fait partie d' [Exemple de démonstration de barre d'état](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_9.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxstatusbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)