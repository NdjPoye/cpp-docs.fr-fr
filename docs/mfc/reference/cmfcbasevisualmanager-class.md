---
title: "CMFCBaseVisualManager Class | Microsoft Docs"
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
  - "CMFCBaseVisualManager"
  - "CMFCBaseVisualManager.~CMFCBaseVisualManager"
  - "~CMFCBaseVisualManager"
  - "CMFCBaseVisualManager::~CMFCBaseVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCBaseVisualManager destructor"
  - "CMFCBaseVisualManager class"
  - "CMFCBaseVisualManager class, destructeur"
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCBaseVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une couche entre les gestionnaires visuels dérivés et l'API de thème windows.  
  
 `CMFCBaseVisualManager` charge UxTheme.dll, si disponible, et gère l'accès aux méthodes API de thème windows.  
  
 Cette classe sert à un usage interne uniquement.  
  
## Syntaxe  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](../Topic/CMFCBaseVisualManager::CMFCBaseVisualManager.md)|Les éléments et initialise un objet d' `CMFCBaseVisualManager` .|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|Destructor.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCBaseVisualManager::DrawCheckBox](../Topic/CMFCBaseVisualManager::DrawCheckBox.md)|Dessine un contrôle de case à cocher à l'aide de le thème windows actuel.|  
|[CMFCBaseVisualManager::DrawComboBorder](../Topic/CMFCBaseVisualManager::DrawComboBorder.md)|Dessine une bordure de zone de liste déroulante à l'aide de le thème windows actuel.|  
|[CMFCBaseVisualManager::DrawComboDropButton](../Topic/CMFCBaseVisualManager::DrawComboDropButton.md)|Dessine un bouton de liste déroulante de la zone de liste déroulante à l'aide de le thème windows actuel.|  
|[CMFCBaseVisualManager::DrawPushButton](../Topic/CMFCBaseVisualManager::DrawPushButton.md)|Dessine un bouton de commande à l'aide de le thème windows actuel.|  
|[CMFCBaseVisualManager::DrawRadioButton](../Topic/CMFCBaseVisualManager::DrawRadioButton.md)|Dessine un contrôle de case d'option à l'aide de le thème windows actuel.|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](../Topic/CMFCBaseVisualManager::DrawStatusBarProgress.md)|Dessine une barre de progression sur un contrôle de barre d'état \([CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md)\) à l'aide de le thème windows actuel.|  
|[CMFCBaseVisualManager::FillReBarPane](../Topic/CMFCBaseVisualManager::FillReBarPane.md)|Remplit arrière\-plan du contrôle rebar à l'aide de le thème windows actuel.|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](../Topic/CMFCBaseVisualManager::GetStandardWindowsTheme.md)|Obtient le thème windows actuel.|  
  
### Méthodes protégées  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCBaseVisualManager::CleanUpThemes](../Topic/CMFCBaseVisualManager::CleanUpThemes.md)|Appelle `CloseThemeData` pour tous les handles obtenus en `UpdateSystemColors`.|  
|[CMFCBaseVisualManager::UpdateSystemColors](../Topic/CMFCBaseVisualManager::UpdateSystemColors.md)|Appels `OpenThemeData` pour obtenir des handles pour dessiner des contrôles : fenêtres, les barres d'outils, boutons, et ainsi de suite.|  
  
## Notes  
 Vous ne devez pas instancier des objets de cette classe directement.  
  
 Comme il s'agit d'une classe de base pour tous les gestionnaires visuels, il vous suffit d'appeler [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md), obtient un pointeur vers le gestionnaire visuel actuel, puis accédez aux méthodes pour `CMFCBaseVisualManager` à l'aide de ce pointeur.  Toutefois, si vous devez afficher un contrôle à l'aide de le thème windows actuel, il est préférable d'utiliser l'interface d' `CMFCVisualManagerWindows` .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxvisualmanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)