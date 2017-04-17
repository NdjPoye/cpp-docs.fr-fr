---
title: "Compatibilit&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compatibilité"
  - "compatibilité, bibliothèques Runtime C"
  - "CRT, compatibilité"
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Compatibilit&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque UCRT \(Universal C Run\-Time\) prend en charge la majeure partie de la bibliothèque standard C requise pour la conformité C\+\+. Elle implémente la bibliothèque C99 \(ISO\/IEC 9899:1999\), à l’exception des macros de type générique définies dans \<tgmath.h\> et de la compatibilité de type stricte dans \<complex.h\>. La bibliothèque UCRT implémente également une grande partie de la bibliothèque C POSIX.1 \(ISO\/IEC 9945\-1:1996, l’API système de POSIX\), mais elle n’est pas entièrement conforme aux normes POSIX spécifiques.  En outre, la bibliothèque UCRT implémente plusieurs fonctions spécifiques à Microsoft et des macros qui ne font pas partie d’un standard.  
  
 Les fonctions spécifiques à l’implémentation Microsoft de Visual C\+\+ se trouvent dans la bibliothèque vcruntime.  Beaucoup de ces fonctions sont destinées à un usage interne et ne peuvent pas être appelées par du code utilisateur. La documentation décrit certaines fonctions destinées au débogage et à l’implémentation de la compatibilité.  
  
 La norme C\+\+ réserve à l’implémentation des noms qui commencent par un trait de soulignement dans l’espace de noms global. Comme les fonctions POSIX sont dans l’espace de noms global, mais qu’elles ne font pas partie de la bibliothèque Runtime C standard, les implémentations spécifiques à Microsoft de ces fonctions commencent par un trait de soulignement. Pour des raisons de portabilité, la bibliothèque UCRT prend également en charge les noms par défaut, mais le compilateur Visual C\+\+ émet un avertissement quand du code qui les utilise est compilé, indiquant qu’elles sont déconseillées. Seuls les noms POSIX par défaut sont déconseillés, mais pas les fonctions elles\-mêmes. Pour supprimer l’avertissement, définissez `_CRT_NONSTDC_NO_WARNINGS` avant d’inclure des en\-têtes dans le code qui utilise les noms POSIX d’origine.  
  
 Certaines fonctions de la bibliothèque C standard ont un historique d’utilisation non sécurisée, en raison de paramètres mal utilisés et de mémoires tampons non vérifiées. Ces fonctions sont souvent à l’origine de problèmes de sécurité dans le code. Microsoft a créé un ensemble de versions plus sécurisées de ces fonctions qui vérifient l’utilisation des paramètres et qui appellent le gestionnaire de paramètre non valide quand un problème est détecté à l’exécution.  Par défaut, le compilateur Visual C\+\+ émet un avertissement quand une variante plus sécurisée d’une fonction déconseillée utilisée est disponible. Quand vous compilez votre code en C\+\+, vous pouvez définir `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` sur 1 pour éliminer la plupart des avertissements. Ceci utilise des surcharges de modèle pour appeler les variantes plus sécurisées tout en conservant le code source portable. Pour supprimer l’avertissement, définissez `_CRT_SECURE_NO_WARNINGS` avant d’inclure des en\-têtes dans le code qui utilise ces fonctions. Pour plus d'informations, consultez [Fonctionnalités de sécurité dans le CRT](../c-runtime-library/security-features-in-the-crt.md).  
  
 À l’exception de ce qui est indiqué dans la documentation pour des fonctions spécifiques, la bibliothèque UCRT est compatible avec l’API Windows.  Certaines fonctions ne sont pas prises en charge dans les applications du  Windows Store pour Windows 8 ni dans les applications Windows universelles sur Windows 10. Ces fonctions sont répertoriées dans [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx), qui énumère les fonctions non prises en charge par le [Windows Runtime](http://msdn.microsoft.com/fr-fr/9a1a18b8-9802-4ec5-b9de-0d2dfdf414e9).  
  
## Articles connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Applications Windows Store, Windows Runtime et exécution C](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|Décrit quand les routines de la bibliothèque UCRT ne sont pas compatibles avec les applications Windows universelles ou avec les applications du Windows Store.|  
|[Conformité ANSI C](../c-runtime-library/ansi-c-compliance.md)|Décrit l’affectation de noms dans la bibliothèque UCRT conforme à la norme.|  
|[UNIX](../c-runtime-library/unix.md)|Fournit des instructions pour le portage de programmes vers UNIX.|  
|[Plateformes Windows \(CRT\)](../c-runtime-library/windows-platforms-crt.md)|Répertorie les systèmes d'exploitation qui offrent une prise en charge CRT.|  
|[Compatibilité descendante](../c-runtime-library/backward-compatibility.md)|Explique comment mapper les anciens noms CRT aux nouveaux.|  
|[Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)|Offre une vue d'ensemble des fichiers de bibliothèque CRT \(.lib\) et les options de compilateur associées.|