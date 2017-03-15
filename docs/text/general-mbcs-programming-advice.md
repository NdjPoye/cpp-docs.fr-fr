---
title: "Conseils g&#233;n&#233;raux sur la programmation MBCS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boîtes de dialogue (C++), polices"
  - "MBCS (C++), polices de boîte de dialogue"
  - "MBCS (C++), programmation"
  - "MS Shell Dlg"
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Conseils g&#233;n&#233;raux sur la programmation MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les conseils suivants :  
  
-   Pour plus de flexibilité, utilisez les macros d'exécution telles que `_tcschr` et `_tcscpy` lorsque cela est possible.  Pour plus d'informations, consultez [Mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Utilisez la fonction runtime C `_getmbcp` pour obtenir des informations sur la page de codes active.  
  
-   Ne réutilisez pas de ressources de chaîne.  En fonction de la langue cible, une chaîne donnée peut avoir plusieurs significations lorsqu'elle est traduite.  Par exemple, « Fichier » dans le menu principal de l'application peut être traduit différemment de la chaîne « Fichier » dans une boîte de dialogue.  Si vous devez utiliser plusieurs chaînes avec le même nom, utilisez des ID de chaînes différents pour chacune d'entre elles.  
  
-   Vous souhaitez savoir si votre application s'exécute sur un système d'exploitation compatible MBCS.  Pour ce faire, définissez un indicateur au démarrage du programme, ne comptez pas sur les appels d'API.  
  
-   Lors de la conception de boîte de dialogue, prévoyez environ 30 % d'espace supplémentaire à la fin des contrôles de texte statiques, pour permettre la traduction MBCS.  
  
-   Lors de la sélection de polices pour votre application, faites attention car certaines polices ne sont pas disponibles sur tous les systèmes.  Par exemple, la version japonaise de Windows 2000 ne prend pas en charge la police Helvetica.  
  
-   Lorsque vous sélectionnez la police des boîtes de dialogue, préférez [MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112) à MS Sans Serif et Helvetica.  La police MS Shell Dlg est remplacée par la police appropriée avant la création de la boîte de dialogue.  L'utilisation de MS Shell Dlg permet de s'assurer que toutes les modifications opérées dans le système d'exploitation pour agir sur cette police seront disponibles automatiquement. \(MFC remplace MSShell Dlg par DEFAULT\_GUI\_FONT ou la police System sur Windows 95, Windows 98 et Windows NT 4 car ces systèmes d'exploitation ne gèrent pas correctement MS Shell Dlg.\)  
  
-   Lors de la conception de votre application, décidez des chaînes qui peuvent être localisées.  Dans le doute, toutes les chaînes seront localisées.  Il est conseillé de ne pas mélanger les chaînes localisables et les chaînes non localisables.  
  
## Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Incrémentation et décrémentation de pointeurs](../text/incrementing-and-decrementing-pointers.md)