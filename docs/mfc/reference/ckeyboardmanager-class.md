---
title: "CKeyboardManager Class | Microsoft Docs"
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
  - "CKeyboardManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyboardManager class"
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CKeyboardManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère les tables de touches de raccourci pour les fenêtres frames de fenêtre frame principale et enfants.  
  
## Syntaxe  
  
```  
class CKeyboardManager : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|[CKeyboardManager::CKeyboardManager](../Topic/CKeyboardManager::CKeyboardManager.md)|Construit un objet `CKeyboardManager`.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CKeyboardManager::CleanUp](../Topic/CKeyboardManager::CleanUp.md)|Efface les tables de touches de raccourci.|  
|[CKeyboardManager::FindDefaultAccelerator](../Topic/CKeyboardManager::FindDefaultAccelerator.md)|Extrait la touche de raccourci par défaut pour la commande et la fenêtre spécifiées.|  
|[CKeyboardManager::IsKeyHandled](../Topic/CKeyboardManager::IsKeyHandled.md)|Détermine si une clé est traitée par la table d'accélérateurs.|  
|[CKeyboardManager::IsKeyPrintable](../Topic/CKeyboardManager::IsKeyPrintable.md)|Indique si un caractère imprimable est.|  
|[CKeyboardManager::IsShowAllAccelerators](../Topic/CKeyboardManager::IsShowAllAccelerators.md)|Indique si les menus montrent les touches de raccourci pour une commande ou uniquement la touche de raccourci par défaut.|  
|[CKeyboardManager::LoadState](../Topic/CKeyboardManager::LoadState.md)|Charge les tables de touches de raccourci du Registre Windows.|  
|[CKeyboardManager::ResetAll](../Topic/CKeyboardManager::ResetAll.md)|Recharge les tables de touches de raccourci de ressources d'application.|  
|[CKeyboardManager::SaveState](../Topic/CKeyboardManager::SaveState.md)|Enregistre les tables de touches de raccourci au Registre Windows.|  
|[CKeyboardManager::ShowAllAccelerators](../Topic/CKeyboardManager::ShowAllAccelerators.md)|Spécifie si l'infrastructure affiche toutes les touches de raccourci pour toutes les commandes, ou une touche de raccourci unique pour chaque commande.  Cette méthode n'affecte pas les commandes qui ont une seule touche de raccourci associée.|  
|[CKeyboardManager::TranslateCharToUpper](../Topic/CKeyboardManager::TranslateCharToUpper.md)|Convertit un caractère à son registre supérieur.|  
|[CKeyboardManager::UpdateAccelTable](../Topic/CKeyboardManager::UpdateAccelTable.md)|Met à jour une table de touches de raccourci avec une table de touches de raccourci.|  
  
## Notes  
 Les membres de cette classe vous permettent d'enregistrer et charger des tables de touches de raccourci au Registre Windows, d'utiliser un modèle pour mettre à jour les tables de touche de raccourci, et rechercher la touche de raccourci par défaut pour une commande dans une fenêtre frame.  De plus, l'objet d' `CKeyboardManager` vous permet de contrôler la façon dont les touches de raccourci sont affichées à l'utilisateur.  
  
 Vous ne devez pas créer un objet d' `CKeyboardManager` manuellement.  Il sera créé automatiquement par l'infrastructure de votre application.  Toutefois, vous devez appeler [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md) pendant le processus d'initialisation de votre application.  Pour obtenir un pointeur vers le gestionnaire de clavier pour votre application, appelez [CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md).  
  
## Exemple  
 L'exemple suivant montre comment récupérer un pointeur vers un objet d' `CKeyboardManager` d'une classe d' `CWinAppEx` , et comment afficher toutes les touches de raccourci associées aux commandes de menu.  Cet extrait de code fait partie de [Le personnalisé pages l'exemple](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/CPP/ckeyboardmanager-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxkeyboardmanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)   
 [Personnalisation du clavier et de la souris](../../mfc/keyboard-and-mouse-customization.md)