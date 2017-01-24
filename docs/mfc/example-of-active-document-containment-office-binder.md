---
title: "Exemple de relation contenant-contenu de documents actifs&#160;: classeur Office | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "documents actifs (conteneurs) (C++), exemples"
  - "documents actifs (C++), conteneurs"
  - "conteneurs (C++), document actif"
  - "exemples (C++), documents actifs (contenance)"
  - "MFC COM (C++), documents actifs (contenance)"
  - "Classeur Office"
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exemple de relation contenant-contenu de documents actifs&#160;: classeur Office
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classeur Microsoft Office est un conteneur de documents actifs.  Un classeur Office comprend deux volets principaux, comme le font généralement les conteneurs.  Le volet gauche contient les icônes qui correspondent aux documents actifs dans le classeur.  Chaque document est appelé *une section* dans le classeur.  Par exemple, un classeur peut contenir des documents Word, PowerPoint classe, de feuilles de calcul Excel, etc.\).  
  
 Cliquez sur l'icône dans le volet gauche vérifie le document actif correspondant.  Le volet droit du classeur affiche le contenu du document actif sélectionné.  
  
 Si vous ouvrez la et sélectionnez un document Word dans un classeur, la barre de menus et les barres d'outils des mots apparaissent en haut du cadre de la vue, et vous pouvez modifier le contenu du document à n'importe quel ordre ou outil word.  Toutefois, la barre de menus est une combinaison de la barre de menus du classeur et le mot.  Étant donné que le classeur et le mot sont les champs de **Aide**, le contenu des menus respectifs est fusionné.  Les conteneurs de documents actifs tels que le classeur Office provoquent automatiquement la fusion de menus de **Aide** ; pour plus d'informations, consultez[Help Menu Merging](../mfc/help-menu-merging.md).  
  
 Lorsque vous sélectionnez un document actif d'un autre type d'application, l'interface du classeur change pour tenir compte que le type d'application du document actif.  Par exemple, si un classeur contient une feuille de calcul Excel, vous observerez listée dans les menus du classeur sont modifiés lorsque vous sélectionnez la section de feuille de calcul Excel.  
  
 Il existe, naturellement, d'autres types possibles de conteneurs en regard de les classeurs.  L'Explorateur de fichiers utilise l'interface scénario double volet dans lequel le volet gauche utilise un contrôle d'arborescence pour afficher une liste hiérarchique des répertoires dans un lecteur ou un réseau, tandis que le volet droit affiche les fichiers contenus dans le dossier actuellement sélectionné.  Un Internet navigateur TYPE de conteneur \(notamment Microsoft Internet Explorer\), au lieu d'utiliser une interface de deux volet, il y a un seul cadre et fournit la navigation à des liens hypertexte.  
  
## Voir aussi  
 [Relation contenant\-contenu de document actif](../mfc/active-document-containment.md)