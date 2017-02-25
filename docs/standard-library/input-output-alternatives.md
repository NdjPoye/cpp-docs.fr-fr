---
title: "Alternatives d&#39;entr&#233;e/sortie | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "E/S (C++), alternatives"
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Alternatives d&#39;entr&#233;e/sortie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ fournit plusieurs méthodes pour la programmation d'E\/S :  
  
-   Bibliothèque Runtime C directe, E\/S non tamponnée.  
  
-   E\/S de flux de données de bibliothèque Runtime C ANSI.  
  
-   E\/S directe de la console et de port.  
  
-   Bibliothèque MFC.  
  
-   Bibliothèque C\+\+ standard de Microsoft.  
  
 Les classes iostream sont utiles pour mis en mémoire tampon, E\/S de texte mis en forme.  Elles sont également utiles pour les E\/S non tamponnée ou binaire si vous avez besoin de l'interface de programmation du actuel \+\+ c et décidez de ne pas utiliser la bibliothèque Microsoft Foundation Class \(MFC\).  Les classes iostream constituent une alternative orienté objet d'E\/S aux fonctions runtime C.  
  
 Vous pouvez utiliser les classes iostream avec le système d'exploitation Microsoft Windows.  La chaîne et le flux de fichier s'exécutent sans restrictions, mais les objets de flux en mode caractère `cin`, `cout`, `cerr`, et `clog` divergent à l'interface graphique utilisateur Windows.  Vous pouvez également dériver les classes personnalisées de flux de données qui interagissent directement avec l'environnement Windows.  
  
## Voir aussi  
 [Définition d'un flux](../standard-library/what-a-stream-is.md)