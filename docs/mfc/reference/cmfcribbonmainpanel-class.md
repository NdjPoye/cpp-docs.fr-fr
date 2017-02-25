---
title: "CMFCRibbonMainPanel Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonMainPanel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMainPanel class"
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMFCRibbonMainPanel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un panneau de ruban qui s'affiche lorsque vous cliquez sur [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md).  
  
## Syntaxe  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|Constructeur par défaut.|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCRibbonMainPanel::Add](../Topic/CMFCRibbonMainPanel::Add.md)|Ajoute un élément ruban dans le volet gauche du panneau de touche application.  \(Substitutions [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).\)|  
|[CMFCRibbonMainPanel::AddRecentFilesList](../Topic/CMFCRibbonMainPanel::AddRecentFilesList.md)|Ajoute une chaîne de texte au menu récente de liste de fichiers.|  
|[CMFCRibbonMainPanel::AddToBottom](../Topic/CMFCRibbonMainPanel::AddToBottom.md)|Ajoute un élément ruban au volet inférieur du panneau d'application de ruban.|  
|[CMFCRibbonMainPanel::AddToRight](../Topic/CMFCRibbonMainPanel::AddToRight.md)|Ajoute un élément ruban au volet de droite du panneau de touche application.|  
|`CMFCRibbonMainPanel::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCRibbonMainPanel::GetCommandsFrame](../Topic/CMFCRibbonMainPanel::GetCommandsFrame.md)|Retourne un rectangle qui représente la région du panneau principal du ruban.|  
|`CMFCRibbonMainPanel::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
  
## Notes  
 L'infrastructure affiche `CMFCRibbonMainPanel` lorsque vous ouvrez le panneau d'application.  Elle contient trois volets :  
  
-   Le volet gauche contient des commandes associées aux fichiers, tels que **Ouvrir**, **Enregistrer**, **copie**, et **Fermer**.  Pour ajouter une commande à ce volet, appelez [CMFCRibbonMainPanel::Add](../Topic/CMFCRibbonMainPanel::Add.md).  
  
-   Le volet droit contient les options qui modifient la commande que vous cliquez sur dans le volet gauche.  Par exemple, si vous cliquez sur **Enregistrer sous** du volet gauche, le volet de droite peut afficher les types de fichiers disponibles.  Pour ajouter un élément à ce volet, appelez [CMFCRibbonMainPanel::AddToRight](../Topic/CMFCRibbonMainPanel::AddToRight.md).  
  
-   Le volet inférieur contient des boutons qui vous permettent de modifier les paramètres de l'application et pour quitter le programme.  Pour ajouter un élément à ce volet, appelez [CMFCRibbonMainPanel::AddToBottom](../Topic/CMFCRibbonMainPanel::AddToBottom.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## Configuration requise  
 **en\-tête :** afxRibbonMainPanel.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)