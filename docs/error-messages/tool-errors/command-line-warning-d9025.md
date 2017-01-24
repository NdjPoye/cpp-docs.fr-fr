---
title: "Avertissement de ligne de commande D9025 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9025"
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement de ligne de commande D9025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

substitution de 'option1' par 'option2'  
  
 L'option *option1* a été spécifiée mais a ensuite été substituée par *option2*.  C'est l'option *option2* qui a été utilisée.  
  
 Si deux options spécifient des directives contradictoires ou incompatibles, c'est la directive spécifiée ou implicite dans l'option située le plus à droite de la ligne de commande qui est utilisée.  
  
 Si vous obtenez cet avertissement lors de la compilation à partir de l'environnement de développement, et si vous n'êtes pas certain de connaître l'origine des options en conflit, tenez compte des éléments suivants :  
  
-   Une option peut être spécifiée dans le code ou dans les paramètres de projet pour le projet.  Observez les [Pages de propriétés Ligne de commande](../../ide/command-line-property-pages.md) du compilateur et si les options en conflit sont affichées dans le champ **Toutes les options**, les options sont définies dans les pages de propriétés du projet ; sinon, les options sont définies dans le code source.  
  
     Si les options sont définies dans les pages de propriétés du projet, consultez la page de propriétés Préprocesseur \(avec le nœud de projet sélectionné dans l'Explorateur de solutions\) du compilateur.  Si les options ne sont pas définies à cet endroit, consultez les paramètres de la page de propriétés Préprocesseur pour chaque fichier de code source \(dans l'Explorateur de solutions\) pour être certain qu'elles n'y ont pas été ajoutées.  
  
     Si les options sont définies dans le code, elles peuvent soit se trouver dans le code, soit les en\-têtes de fenêtres.  Vous pouvez essayer de créer un fichier prétraité \([\/P](../../build/reference/p-preprocess-to-a-file.md)\) et de rechercher le symbole à l'intérieur.