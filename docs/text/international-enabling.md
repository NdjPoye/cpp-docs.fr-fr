---
title: "Compatibilit&#233; internationale | Microsoft Docs"
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
  - "globalisation (C++), jeux de caractères"
  - "localisation (C++), jeux de caractères"
  - "MBCS (C++), activer"
  - "chaînes (C++), compatibilité internationale"
  - "Unicode (C++), activer"
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Compatibilit&#233; internationale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les codes traditionnels C et C\+\+ manipulent les caractères et les chaînes d'une manière qui n'est pas compatible avec la création d'applications internationales.  Si MFC et la bibliothèque Runtime prennent en charge Unicode ou MBCS, il vous reste encore du travail.  Pour vous guider, cette section explique la signification d'«  activation internationale » dans Visual C\+\+ :  
  
-   Unicode et MBCS sont activés par l'intermédiaire de types de données portables dans les listes de paramètres de fonction MFC et de types de retours.  Ces types sont définis conditionnellement de la façon adéquate, selon que votre compilation définit le symbole **\_UNICODE** ou le symbole **\_MBCS** \(ce qui signifie DBCS\).  Différents variants des bibliothèques MFC sont automatiquement liés à votre application, selon les symboles que votre compilation définit.  
  
-   Le code de la bibliothèque de classes utilise des fonctions runtime portables et d'autres méthodes pour garantir le comportement Unicode ou MBCS.  
  
-   Vous devez toujours gérer certains types de tâches d'internationalisation dans votre code :  
  
    -   Utilisez les mêmes fonctions runtime portables qui rendent MFC portable sous les deux environnements.  
  
    -   Rendez les chaînes et les caractères de type littéral portables sous les deux environnements, en utilisant la macro **\_T**.  Pour plus d'informations, consultez [Mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
    -   Prenez des précautions lors de l'analyse de chaînes sous MBCS.  Ces précautions ne sont pas nécessaires sous Unicode.  Pour plus d'informations, consultez [Conseils de programmation MBCS](../text/mbcs-programming-tips.md).  
  
    -   Faites attention lorsque vous mélangez des caractères ANSI \(8 bits\) et Unicode \(16 bits\) dans votre application.  Il est possible d'utiliser des caractères ANSI dans certaines parties de votre programme et des caractères Unicode dans d'autres, mais vous ne pouvez pas les mélanger dans la même chaîne.  
  
    -   Ne codez pas en dur des chaînes dans votre application.  Utilisez plutôt des ressources STRINGTABLE en les ajoutant au fichier .rc de l'application.  Votre application peut ensuite être localisée sans modification du code source ou recompilation.  Pour plus d'informations sur les ressources STRINGTABLE, consultez [Éditeur de chaînes](../mfc/string-editor.md).  
  
> [!NOTE]
>  Les jeux de caractères européens et MBCS utilisent des caractères, tels que les lettres accentuées, avec des codes de caractères supérieurs à 0x80.  Dans la mesure où la plupart du code utilise des caractères signés, ces caractères supérieurs à 0x80 sont étendus signés lorsqu'ils sont convertis en `int`.  C'est un problème pour l'indexation de tableau car les caractères étendus signés, étant négatifs, sont indexés en dehors du tableau.  Les langues qui utilisent MBCS, telles que le japonais, sont également uniques.  Dans la mesure où un caractère peut se composer de 1 ou 2 octets, vous devez toujours manipuler les deux octets en même temps.  
  
## Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Stratégies d'internationalisation](../text/internationalization-strategies.md)