---
title: "Comment&#160;: effectuer une migration vers /clr:pure (C++/CLI) | Microsoft Docs"
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
  - "/clr (option du compilateur C++), migrer vers /clr:pure"
  - "migration (C++), MSIL pur"
  - "MSIL pur (C++), porter vers"
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: effectuer une migration vers /clr:pure (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les problèmes susceptibles de survenir lors de la migration vers le code MSIL pur à l'aide de **\/clr:pure** \(consultez [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md) pour plus d'informations\).  Cette rubrique suppose que le code en cours de migration est actuellement accepté comme assembly mixte à l'aide de l'option **\/clr**, car le chemin de migration du code non managé vers le code MSIL pur n'est pas direct.  Pour le code non managé, consultez [Comment : effectuer une migration vers \/clr](../dotnet/how-to-migrate-to-clr.md) avant de tenter une migration vers le code MSIL pur.  
  
## Modifications de base  
 Le code MSIL pur est constitué d'instructions MSIL ; par conséquent, un code contenant des fonctions qui ne peuvent pas être exprimées en MSIL empêchera toute compilation.  Il comprend des fonctions définies comme utilisant conventions d'appel différentes de [\_\_clrcall](../cpp/clrcall.md). \(Les fonctions qui n'utilisent pas \_\_clrcall peuvent être appelées dans un composant MSIL pur, mais ne sont pas définies.\)  
  
 Pour éviter toute erreur d'exécution, vous devez activer l'avertissement C4412.  Activez C4412 en ajoutant `#pragma warning (default : 4412)` à chaque module \(compiland\) que vous compilez avec **\/clr:pure** et qui passe des types C\+\+ de\/vers IJW \(**\/clr\)** ou du code natif.  Pour plus d'informations, consultez [Avertissement du compilateur \(niveau 2\) C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md).  
  
## Considérations sur l'architecture  
 Certaines des limitations des assemblys MSIL purs répertoriés dans [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md) ont des conséquences plus importantes pour la conception d'applications et la stratégie de migration.  En particulier, contrairement aux assemblys mixtes, les assemblys MSIL purs ne bénéficient pas d'une compatibilité complète avec les modules non managés.  
  
 Les assemblys MSIL purs peuvent appeler des fonctions non managées, mais ne peuvent pas être appelés par des fonctions non managées.  Par conséquent, le code MSIL pur est plus conseillé pour le code client qui utilise des fonctions non managées que pour le code serveur utilisé par les fonctions non managées.  Si les fonctionnalités contenues dans un assembly MSIL pur sont utilisées par des fonctions non managées, un assembly mixte doit être utilisé comme couche d'interface.  
  
 Les applications qui utilisent ATL ou MFC ne sont pas adaptées à la migration vers le code MSIL pur, car ces bibliothèques ne sont pas prises en charge dans cette version.  De même, le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] contient des fichiers d'en\-tête qui ne sont pas compilés sous **\/clr:pure**.  
  
 Même si les assemblys MSIL purs peuvent appeler des fonctions non managées, cette capacité est limitée aux fonctions de style C simples.  L'utilisation d'API non managées plus complexes exige l'exposition des fonctionnalités non managées sous la forme d'une interface COM, ou un assembly mixte pouvant jouer le rôle d'interface entre le code MSIL pur et les composants non managés.  L'utilisation d'une couche d'assembly mixte est le seul moyen d'utiliser des fonctions non managées qui prennent des fonctions de rappel, par exemple, car un assembly pur est incapable de fournir une fonction native appelable à utiliser comme rappel.  
  
## Domaines d'application et conventions d'appel  
 Même si les assemblys MSIL purs peuvent utiliser des fonctionnalités non managées, les fonctions et données statiques sont gérées différemment.  Dans les assemblys purs, les fonctions sont implémentées avec la convention d'appel [\_\_clrcall](../cpp/clrcall.md), et les données statiques sont stockées dans le domaine propre à l'application.  Cela diffère de la valeur par défaut pour les assemblys non managés et mixtes qui utilisent la convention d'appel [\_\_cdecl](../cpp/cdecl.md) pour les fonctions et stockent les données statiques processus par processus.  
  
 Dans le contexte du code MSIL pur \(et du code vérifiable compilé avec \/clr:safe\), ces valeurs par défaut sont transparentes, car [\_\_clrcall](../cpp/clrcall.md) est la convention d'appel par défaut du CLR, et les domaines d'application sont la portée native pour les données statiques et globales dans les applications .NET.  Toutefois, en cas de dialogue avec des composants non managés ou mixtes, le traitement différent des fonctions et des données globales peut entraîner des problèmes.  
  
 Par exemple, si un composant MSIL pur doit appeler des fonctions dans une DLL non managée ou mixte, un fichier d'en\-tête pour la DLL est utilisé pour compiler l'assembly pur.  Toutefois, à moins que la convention d'appel pour chaque fonction comprise dans l'en\-tête soit indiquée explicitement, elles sont toutes supposées utiliser la convention [\_\_clrcall](../cpp/clrcall.md).  Cela provoquera des défaillances ultérieures au moment de l'exécution, car ces fonctions sont généralement implémentées avec la convention [\_\_cdecl](../cpp/cdecl.md).  Les fonctions contenues dans le fichier d'en\-tête non managé peuvent être marquées explicitement comme [\_\_cdecl](../cpp/cdecl.md), ou le code source de la DLL entière doit être recompilé sous **\/clr:pure**.  
  
 De la même façon, les pointeurs fonction sont supposés désigner des fonctions [\_\_clrcall](../cpp/clrcall.md) sous compilation **\/clr:pure**.  Celles\-ci doivent également être annotées explicitement avec la convention d'appel correcte.  
  
 Pour plus d'informations, consultez [Domaines d'application et Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
## Limitations des liens  
 L'éditeur de liens Visual C\+\+ n'essaie pas de lier des fichiers OBJ mixtes et purs, car la portée de stockage et les conventions d'appel sont différentes.  
  
## Voir aussi  
 [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md)