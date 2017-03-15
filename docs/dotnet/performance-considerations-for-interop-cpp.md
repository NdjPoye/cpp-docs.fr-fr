---
title: "Consid&#233;rations sur les performances de l&#39;interop&#233;rabilit&#233; (C++) | Microsoft Docs"
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
  - "/clr (option du compilateur C++), interopérabilité (considérations sur les performances)"
  - "Interop (C++), considérations sur les performances"
  - "interopérabilité (C++), considérations sur les performances"
  - "assemblys mixtes (C++), considérations sur les performances"
  - "appel de code non managé (C++), interopérabilité"
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Consid&#233;rations sur les performances de l&#39;interop&#233;rabilit&#233; (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique fournit des indications permettant de réduire l'effet de transitions d'interopérabilité managées\/non managées sur les performances d'exécution.  
  
 Visual C\+\+ prend en charge les mêmes mécanismes d'interopérabilité que d'autres langages .NET tels que Visual Basic et C\# \(P\/Invoke\), mais il fournit également la prise en charge de l'interopérabilité spécifique à Visual C\+\+ \(interopérabilité C\+\+\).  Pour les applications aux performances critiques, il est important de comprendre les conséquences des performances de chaque technique d'interopérabilité.  
  
 Quelle que soit la technique d'interopérabilité utilisée, des séquences de transition spéciales \(appelées thunks\) sont nécessaires chaque fois qu'une fonction managée appelle une fonction non managée et inversement.  Ces thunks sont insérés automatiquement par le compilateur Visual C\+\+, mais il est important de ne pas oublier qu'ensemble, ces transitions peuvent être coûteuses en termes de performances.  
  
## Réduction des transitions  
 Une façon d'éviter ou de réduire le coût des thunks d'interopérabilité consiste à refactoriser les interfaces impliquées afin de réduire les transitions managées\/non managées.  Des améliorations considérables des performances peuvent être réalisées en ciblant les interfaces qui impliquent des appels fréquents entre la limite managée\/non managée.  Une fonction managée qui appelle une fonction non managée dans une boucle serrée, par exemple, est bon candidat à la refactorisation.  Si la boucle proprement dite est déplacée vers le côté non managé ou si une alternative managée à l'appel non managé est créée \(en mettant éventuellement en file d'attente les données du côté managé et en les marshalant simultanément vers l'API non managée après la boucle\), le nombre de transitions peut être considérablement réduit.  
  
## P\/Invoke contre C\+\+ Interop  
 Pour les langages .NET, tels que Visual Basic et C\#, la méthode prescrite pour interagir avec les composants natifs est P\/Invoke.  Comme P\/Invoke est pris en charge par le .NET Framework, Visual C\+\+ le prend également en charge, mais Visual C\+\+ fournit aussi sa propre prise en charge de l'interopérabilité qui est connue sous le nom d'interopérabilité C\+\+.  L'interopérabilité C\+\+ doit être utilisée de préférence plutôt que P\/Invoke, car ce dernier n'est pas de type sécurisé.  En conséquence, les erreurs sont principalement signalées au moment de l'exécution, mais l'interopérabilité C\+\+ procure également des avantages de performances par rapport à P\/Invoke.  
  
 Ces deux techniques exigent l'exécution de plusieurs opérations chaque fois qu'une fonction managée appelle une fonction non managée :  
  
-   Les arguments de l'appel de fonction sont marshalés à partir du CLR vers des types natifs.  
  
-   Un thunk managé\-non managé est exécuté.  
  
-   La fonction non managée est appelée \(à l'aide des versions natives des arguments\).  
  
-   Un thunk non managé\-managé est exécuté.  
  
-   Le type de retour et tout argument "out" ou "in,out" sont marshalés de types natifs vers des types CLR.  
  
 Les thunks managés\/non managés sont nécessaires pour que l'interopérabilité fonctionne, mais le marshaling de données requis dépend des types de données impliqués, de la signature de la fonction, ainsi que de la manière dont les données seront utilisées.  
  
 Le marshaling de données exécuté par l'interopérabilité C\+\+ est le plus simple possible :  les paramètres sont copiés entre la limite managée\/non managée au niveau du bit ; aucune transformation n'est effectuée.  Pour P\/Invoke, cela ne s'applique que si tous les paramètres sont des types blittables simples.  Sinon, P\/Invoke exécute une procédure très fiable pour convertir chaque paramètre managé en type natif approprié, et inversement, si les arguments sont marqués comme "out" ou "in,out".  
  
 En d'autres termes, l'interopérabilité C\+\+ utilise la méthode la plus rapide possible de marshaling de données, alors que P\/Invoke  utilise la méthode la plus fiable.  Cela signifie que l'interopérabilité C\+\+ \(d'une manière propre à C\+\+\) fournit des performances optimales par défaut, et que le programmeur est responsable de résoudre les cas où ce comportement n'est pas sûr ou approprié.  
  
 L'interopérabilité C\+\+ exige par conséquent que le marshaling de données soit fourni explicitement, mais offre l'avantage de laisser le programmeur libre de décider ce qui est approprié, en fonction de la nature des données et de la manière dont elles seront utilisées.  En outre, même si le comportement du marshaling de données de P\/Invoke peut être modifié et personnalisé jusqu'à un certain niveau, l'interopérabilité C\+\+ permet de personnaliser le marshaling de données appel par appel.  Cela n'est pas possible avec P\/Invoke.  
  
 Pour plus d'informations sur l'interopérabilité C\+\+, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)