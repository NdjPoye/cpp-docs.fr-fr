---
title: "Code pur et v&#233;rifiable (C++/CLI) | Microsoft Docs"
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
  - ".NET Framework (C++), code pure et vérifiable"
  - "/clr (option du compilateur C++), assemblys mixtes"
  - "/clr (option du compilateur C++), assemblys purs"
  - "/clr (option du compilateur C++), assemblys vérifiables"
  - "assemblys (C++), code mixte"
  - "assemblys (C++), code pure"
  - "assemblys (C++), code vérifiable"
  - "assemblys mixtes (C++)"
  - "assemblys mixtes (C++), à propos des assemblys mixtes"
  - "MSIL pur (C++)"
  - "MSIL pur (C++), à propos du code pure"
  - "assemblys vérifiables (C++)"
  - "assemblys vérifiables (C++), à propos des assemblys vérifiables"
  - "vérifié (code de type sécurisé) (C++)"
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: 31
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Code pur et v&#233;rifiable (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour la programmation sur .NET, Visual C\+\+ prend en charge la création de trois types distincts de composants et d'applications : mixte, pur et vérifiable.  Tous trois sont disponibles via l'option [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md) du compilateur.  
  
## Notes  
 Pour plus d'informations sur les assemblys vérifiables, voir :  
  
-   [Comparaison entre les fonctionnalités mixte, pure et vérifiable](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [Comment : effectuer une migration vers \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [Comment : créer des projets C\+\+ vérifiables](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [Comment : effectuer une migration vers \/clr:safe](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [Utilisation d'assemblys vérifiables avec SQL Server](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [Meilleures pratiques pour la sécurité](../top/security-best-practices-for-cpp.md)  
  
-   [Conversion de projets du mode mixte en langage intermédiaire pur](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## Mixte \(\/clr\)  
 Les assemblys mixtes \(compilés avec **\/clr**\), contiennent à la fois des parties non managées et managées, ce qui leur permet d'utiliser les fonctionnalités de .NET, tout en contenant du code non managé.  Les applications et les composants peuvent ainsi être mis à jour pour pouvoir utiliser des fonctionnalités de .NET, sans qu'il soit nécessaire de réécrire le projet tout entier.  L'utilisation de Visual C\+\+ pour mélanger ainsi du code managé et du code non managé est appelée C\+\+ Interop.  Pour plus d’informations, consultez [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md) et [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md).  
  
## Pur \(\/clr:pure\)  
 Les assemblys purs \(compilés avec **\/clr:pure**\) peuvent contenir des types de données à la fois natifs et managés, mais uniquement des fonctions managées.  Tout comme les assemblys mixtes, les assemblys purs autorisent l'interopérabilité avec des DLL natives via P\/Invoke \(consultez [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)\), mais les fonctionnalités d'interopérabilité C\+\+ ne sont pas disponibles.  En outre, les assemblys purs ne peuvent pas exporter les fonctions pouvant être appelées depuis des fonctions natives car les points d'entrée dans un assembly pur utilisent la convention d'appel [\_\_clrcall](../cpp/clrcall.md).  
  
### Avantages de \/clr:pure  
  
-   Meilleures performances : les assemblys purs contenant uniquement du MSIL, il n'y a pas de fonctions natives et, par conséquent, aucune transition managée\/non managée n'est nécessaire. \(Les appels de fonction effectués via P\/Invoke sont une exception à cette règle\).  
  
-   Détection d'AppDomain : les fonctions managées et les types de données du CLR existent dans des `Application Domains`, ce qui affecte leur visibilité et leur accessibilité.  Les assemblys purs reconnaissent les domaines \(\_\_declspec \([appdomain](../cpp/appdomain.md) est impliqué pour chaque type\), l'accès à leurs types et à leurs fonctionnalités depuis d'autres composants .NET est donc plus facile et plus sûr.  En conséquence, les assemblys purs interagissent plus facilement avec d'autres composants .NET que les assemblys mixtes.  
  
-   Chargement hors disque : les assemblys purs peuvent être chargés en mémoire et même transmis en continu.  Cela est essentiel pour pouvoir utiliser des assemblys .NET comme des procédures stockées.  Les assemblys mixtes, au contraire, doivent exister sur disque pour pouvoir s'exécuter, en raison de leur dépendance vis\-à\-vis des mécanismes de chargement de Windows.  
  
-   Réflexion: il n'est pas possible de refléter sur des fichiers exécutables mixtes, tandis que les assemblys purs prennent totalement en charge la réflexion.  Pour plus d'informations, consultez [Réflexion](../dotnet/reflection-cpp-cli.md).  
  
-   Contrôle de l'hôte : les assemblys purs contiennent uniquement du MSIL et se comportent donc de façon plus prévisible et plus souple que les assemblys mixtes lorsqu'on les utilise dans des applications qui hébergent le CLR et modifient son comportement par défaut.  
  
### Limitations de \/clr:pure  
 Cette section couvre des fonctionnalités actuellement non prises en charge par **\/clr:pure**.  
  
-   Les assemblys purs ne peuvent pas être appelés par des fonctions non managées.  Ils ne peuvent donc pas implémenter d'interfaces COM ou exposer des rappels natifs.  Les assemblys purs ne peuvent pas exporter de fonctions via des fichiers \_\_declspec \(dllexport\) ou .DEF.  En outre, les fonctions déclarées avec la convention \_\_clrcall ne peuvent pas être importées via \_\_declspec \(dllimport\).  Les fonctions d'un module natif peuvent être appelées depuis un assembly pur, mais les assemblys purs ne peuvent pas exposer de fonctions appelables en natif, si bien que l'exposition des fonctionnalités dans un assembly pur doit avoir lieu via des fonctions managées dans un assembly mixte.  Pour plus d'informations, consultez [Comment : effectuer une migration vers \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
-   Les bibliothèques ATL et MFC ne sont pas prises en charge par la compilation en mode pur dans Visual C\+\+.  
  
-   Les .netmodules purs ne sont pas acceptés comme entrées de l'éditeur de liens Visual C\+\+.  Toutefois, les fichiers .obj purs sont acceptés par l'éditeur de liens, et les fichiers .obj contiennent un sur\-ensemble d'informations que contiennent les netmodules.  Pour plus d'informations, consultez [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../build/reference/netmodule-files-as-linker-input.md).  
  
-   Le support COM du compilateur \(\#import\) n'est pas pris en charge, car cela introduirait des instructions non managées dans l'assembly pur.  
  
-   Les options de virgule flottante pour l'alignement et la gestion des exceptions ne sont pas réglables pour les assemblys purs.  En conséquence, \_\_declspec\(align\) ne peut pas être utilisé.  Certains fichiers d'en\-tête, tels que fpieee.h, deviennent dès lors incompatibles avec \/clr:pure.  
  
-   La fonction GetLastError dans le PSDK peut entraîner un comportement indéfini lors de la compilation avec **\/clr:pure**.  
  
## Vérifiable \(\/clr:safe\)  
 L'option du compilateur **\/clr:safe** génère des assemblys vérifiables, comme ceux écrits en Visual Basic et en C\#, en se conformant aux exigences qui permettent au Common Language Runtime \(CLR\) de garantir que le code ne viole aucun paramètre de sécurité actuel.  Par exemple, si les paramètres de sécurité interdisent à un composant d'écrire sur le disque, le CLR peut déterminer si un composant vérifiable répond à ce critère avant d'exécuter du code.  Il n'y a pas de prise en charge du CRT par les assemblys vérifiables. \(La prise en charge du CRT est disponible pour les assemblys purs via une version MSIL pur de la bibliothèque Runtime C\).  
  
 Les assemblys vérifiables offrent les avantages suivants par rapport aux assemblys purs et mixtes :  
  
-   Une meilleure sécurité.  
  
-   Certaines situations les exigent \(les composants SQL, par exemple\).  
  
-   Les futures versions de Windows exigeront de plus en plus que les composants et les applications soient vérifiables.  
  
 Le fait que les fonctionnalités d'interopérabilité C\+\+ soient non disponibles est un inconvénient.  Les assemblys vérifiables ne peuvent pas contenir de fonctions non managées ou de types de données natifs, même s'ils ne sont pas référencés par le code managé.  
  
 En dépit de l'utilisation du mot "safe", compiler des applications avec **\/clr:safe** ne signifie pas qu'il n'y a pas de bogues ; cela signifie seulement que le CLR peut vérifier les paramètres de sécurité au moment de l'exécution.  
  
 Quel que soit le type d'assembly, les appels effectués depuis des assemblys managés vers des DLL natives via P\/Invoke compileront, mais risqueront d'échouer à l'exécution selon le réglage des paramètres de sécurité.  
  
> [!NOTE]
>  Il existe un scénario de programmation qui passera le compilateur, mais le résultat sera un assembly invérifiable : il s'agit de l'appel à une fonction virtuelle via une instance d'objet à l'aide de l'opérateur de résolution de portée.  Par exemple : `MyObj -> A::VirtualFunction();`.  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)