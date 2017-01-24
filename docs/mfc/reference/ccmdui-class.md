---
title: "CCmdUI Class | Microsoft Docs"
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
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boutons (C++), mettre à jour au fur et à mesure des changements de contexte"
  - "CCmdUI class"
  - "command user interface"
  - "commandes (C++), updating UI"
  - "menus [C++], mettre à jour au fur et à mesure des changements de contexte"
  - "états, updating user interface object"
  - "barres d'outils (C++), mettre à jour"
  - "updating user interfaces for commands"
  - "interfaces utilisateur, mettre à jour"
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCmdUI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Est utilisé uniquement dans un gestionnaire d' `ON_UPDATE_COMMAND_UI` dans `CCmdTarget`classe dérivée.  
  
## Syntaxe  
  
```  
class CCmdUI  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCmdUI::ContinueRouting](../Topic/CCmdUI::ContinueRouting.md)|Indique le mécanisme de routage des commandes de continuer à router le message actuel vers le bas de la chaîne des gestionnaires.|  
|[CCmdUI::Enable](../Topic/CCmdUI::Enable.md)|Active ou désactive l'élément d'interface utilisateur pour cette commande.|  
|[CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)|Définit l'état d'activation de l'élément d'interface utilisateur pour cette commande.|  
|[CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)|Comme la fonction membre d' `SetCheck` , mais traite les groupes de cases d'option.|  
|[CCmdUI::SetText](../Topic/CCmdUI::SetText.md)|Définit le texte de l'élément d'interface utilisateur pour cette commande.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCmdUI::m\_nID](../Topic/CCmdUI::m_nID.md)|L'ID de l'objet d'interface utilisateur.|  
|[CCmdUI::m\_nIndex](../Topic/CCmdUI::m_nIndex.md)|L'index de l'objet d'interface utilisateur.|  
|[CCmdUI::m\_pMenu](../Topic/CCmdUI::m_pMenu.md)|Pointe vers le menu représenté par `CCmdUI` objet.|  
|[CCmdUI::m\_pOther](../Topic/CCmdUI::m_pOther.md)|Pointe vers l'objet window qui a envoyé la notification.|  
|[CCmdUI::m\_pSubMenu](../Topic/CCmdUI::m_pSubMenu.md)|Pointe vers le sous\-menu contenu représenté par `CCmdUI` objet.|  
  
## Notes  
 `CCmdUI` n'a pas de classe de base.  
  
 Lorsqu'un utilisateur de votre application déplace un menu, chaque élément de menu doit savoir s'il doit s'afficher comme activé ou désactivé.  La cible d'une commande de menu fournit ces informations en implémentant un gestionnaire d' `ON_UPDATE_COMMAND_UI` .  Pour chacun des objets interface utilisateur de commande dans votre application, utilisez la fenêtre Propriétés pour créer une entrée de la table des messages et un prototype de fonction pour chaque gestionnaire.  
  
 Lorsque le menu est abaissé, les recherches d'infrastructure pour les appels les fonctions membres d' `CCmdUI` de chaque gestionnaire d' `ON_UPDATE_COMMAND_UI` , des appels de chaque gestionnaire telles que **Activer** et **Activer**, et l'infrastructure affiche alors correctement chaque élément de menu.  
  
 Un élément de menu peut être remplacé par un bouton de la barre de contrôle ou d'un autre objet interface utilisateur de commande sans modifier le code dans le gestionnaire d' `ON_UPDATE_COMMAND_UI` .  
  
 Le tableau suivant résume les fonctions membres d'`CCmdUI` d'effet ont sur différents éléments d'interface utilisateur de commande.  
  
|Élément d'interface utilisateur|Activer|SetCheck|SetRadio|SetText|  
|-------------------------------------|-------------|--------------|--------------|-------------|  
|Menu Item|Active ou désactive les|Les contrôles \(x\) ou désactive|Contrôles à le point \(•\)|Définit le texte de l'élément|  
|Bouton de barre d'outils|Active ou désactive les|Sélectionne, désélectionne, ou indéterminé|De la même façon qu' `SetCheck`|\(Non applicable\)|  
|Volet de barre d'état|Rend le texte visible ou invisible|Définit POP\) ou la bordure de normale|De la même façon qu' `SetCheck`|Définit le texte du volet|  
|Bouton normal dans `CDialogBar`|Active ou désactive les|Les contrôles ou désactive la case à cocher|De la même façon qu' `SetCheck`|Définit le texte du bouton|  
|Contrôle de normale dans `CDialogBar`|Active ou désactive les|\(Non applicable\)|\(Non applicable\)|Définit le texte variable de fenêtre|  
  
 Pour plus d'informations sur l'utilisation de cette classe, consultez [Procédure objets interface utilisateur de mise à jour](../../mfc/how-to-update-user-interface-objects.md).  
  
## Hiérarchie d'héritage  
 `CCmdUI`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)