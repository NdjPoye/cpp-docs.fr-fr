---
title: "/GENPROFILE, /FASTGENPROFILE (G&#233;n&#233;rer une build instrument&#233;e de profilage) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GENPROFILE"
  - "FASTGENPROFILE"
  - "/GENPROFILE"
  - "/FASTGENPROFILE"
helpviewer_keywords: 
  - "GENPROFILE"
  - "FASTGENPROFILE"
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GENPROFILE, /FASTGENPROFILE (G&#233;n&#233;rer une build instrument&#233;e de profilage)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie la génération d’un fichier .pgd par l’éditeur de liens pour prendre en charge l’optimisation guidée par profil.  \/GENPROFILE et \/FASTGENPROFILE utilisent des paramètres par défaut différents. Utilisez \/GENPROFILE pour privilégier la précision par rapport à la rapidité et à l’utilisation de la mémoire pendant le profilage. Utilisez \/FASTGENPROFILE pour privilégier une utilisation moins importante de la mémoire et la rapidité par rapport à la précision.  
  
## Syntaxe  
  
```  
/{GENPROFILE|FASTGENPROFILE}[:{COUNTER32|COUNTER64|EXACT|MEMMAX=#|MEMMIN=#|NOEXACT|NOPATH|NOTRACKEH|PATH|PGD=filename|TRACKEH}]   
```  
  
## Notes  
 COUNTER32 &#124; COUNTER64  
 Utilisez COUNTER32 pour spécifier l’utilisation de compteurs de sonde 32 bits et COUNTER64 pour spécifier des compteurs de sonde 64 bits. Quand vous spécifiez \/GENPROFILE, la valeur par défaut est COUNTER64. Quand vous spécifiez \/FASTGENPROFILE, la valeur par défaut est COUNTER32.  
  
 EXACT &#124; NOEXACT  
 Utilisez EXACT pour spécifier des incréments à blocage thread\-safe pour les sondes. NOEXACT spécifie les opérations d’incrément non protégées pour les sondes. La valeur par défaut est NOEXACT.  
  
 MEMMAX\=valeur, MEMMIN\=valeur  
 Utilisez MEMMAX et MEMMIN pour spécifier la taille de réservation maximale et minimale pour les données d’apprentissage dans la mémoire. La valeur est la quantité de mémoire à réserver en octets.  Par défaut, ces valeurs sont déterminées par une méthode heuristique interne.  
  
 PATH &#124; NOPATH  
 Utilisez PATH pour spécifier un ensemble distinct de compteurs PGO pour chaque chemin unique vers une fonction. Utilisez NOPATH pour spécifier un seul ensemble de compteurs pour chaque fonction.   Quand vous spécifiez \/GENPROFILE, la valeur par défaut est PATH. Quand vous spécifiez \/FASTGENPROFILE, la valeur par défaut est NOPATH.  
  
 TRACKEH &#124; NOTRACKEH  
 Spécifie s’il faut utiliser des compteurs supplémentaires pour conserver un décompte précis quand des exceptions sont levées au cours de l’apprentissage. Utilisez TRACKEH pour spécifier des compteurs supplémentaires pour un décompte exact. Utilisez NOTRACKEH pour spécifier des compteurs uniques pour le code qui n’utilisent pas la gestion des exceptions ou qui ne rencontrent pas d’exceptions dans vos scénarios d’apprentissage.  Quand vous spécifiez \/GENPROFILE, la valeur par défaut est TRACKEH. Quand vous spécifiez \/FASTGENPROFILE, la valeur par défaut est NOTRACKEH.  
  
 PGD\=nom\_fichier  
 Spécifie un nom de fichier de base pour le fichier .pgd. Par défaut, l’éditeur de liens utilise le nom du fichier image exécutable de base avec une extension .pgd.  
  
 Les options \/GENPROFILE et \/FASTGENPROFILE indiquent à l’éditeur de liens de générer le fichier d’instrumentation du profilage nécessaire pour prendre en charge de l’apprentissage de l’application pour l’optimisation guidée par profil. Les informations de profilage générées par l’apprentissage de l’application sont utilisées comme entrée pour effectuer les optimisations de la totalité du programme ciblé pendant les générations.   Vous pouvez définir des options supplémentaires pour contrôler différentes fonctionnalités de profilage pour les performances pendant l’apprentissage de l’application et les builds. Les options par défaut spécifiées par \/GENPROFILE donnent des résultats plus précis, en particulier pour les grosses applications multithreads complexes. L’option \/FASTGENPROFILE utilise des valeurs par défaut différentes pour un encombrement mémoire moindre et de meilleures performances lors de l’apprentissage, au détriment de la précision.  
  
 Les informations de profilage sont capturées quand vous exécutez l’application instrumentée après avoir généré la build en utilisant \/GENPROFILE ou \/FASTGENPROFILE. Ces informations sont utilisées par l’éditeur de liens quand vous spécifiez l’option \/USEPROFILE. Pour plus d’informations sur la façon d’effectuer l’apprentissage de votre application et sur les données collectées, consultez Optimisation guidée par profil.  
  
 Vous devez également spécifier \/LTCG quand vous spécifiez \/GENPROFILE ou \/FASTGENPROFILE.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [\/LTCG \(Génération de code durant l'édition de liens\)](../../build/reference/ltcg-link-time-code-generation.md)