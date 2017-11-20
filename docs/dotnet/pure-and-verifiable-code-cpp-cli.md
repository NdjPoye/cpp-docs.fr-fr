---
title: "Code pur et vérifiable (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ec68a6179cd74020638aa895028942bc76e21f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="pure-and-verifiable-code-ccli"></a>Code pur et vérifiable (C++/CLI)
Pour la programmation .NET, Visual C++ prend en charge la création de trois types distincts de composants et applications : mixte, pure et vérifiable. Les trois sont disponibles via le [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur.  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations sur les assemblys vérifiables, voir :  
  
-   [Comparaison entre les fonctionnalités mixte, pure et vérifiable (C++-CLI)](../dotnet/mixed-pure-and-verifiable-feature-comparison-cpp-cli.md)  
  
-   [Comment : migrer vers/clr : pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [Guide pratique pour créer des projets C++ vérifiables (C++-CLI)](../dotnet/how-to-create-verifiable-cpp-projects-cpp-cli.md)  
  
-   [Comment : migrer vers/clr : safe (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)  
  
-   [Utilisation d’assemblys vérifiables avec SQL Server (C++-CLI)](../dotnet/using-verifiable-assemblies-with-sql-server-cpp-cli.md)  
  
-   [Bonnes pratiques de sécurité](../security/security-best-practices-for-cpp.md)  
  
-   [Conversion de projets du mode mixte en langage intermédiaire pur](../dotnet/converting-projects-from-mixed-mode-to-pure-intermediate-language.md)  
  
## <a name="mixed-clr"></a>Mixte (/ clr)  
 Assemblys mixtes (compilés avec **/CLR**), tous les deux non managée et les parties managées, ce qui permet d’utiliser les fonctionnalités de .NET, tout en contenant du code non managé. Ainsi, les applications et des composants à mettre à jour utiliser les fonctionnalités .NET sans avoir à réécrire de l’ensemble du projet. À l’aide de Visual C++ permet de combiner du code managé et de cette manière est appelé l’interopérabilité C++. Pour plus d’informations, consultez [mixte (natif et managé) assemblys](../dotnet/mixed-native-and-managed-assemblies.md) et [natif et l’interopérabilité .NET](../dotnet/native-and-dotnet-interoperability.md).  
  
## <a name="pure-clrpure"></a>Pure (/ clr : pure)  
 Assemblys purs (compilés avec **/CLR : pure**) peut contenir les deux types de données natifs et managés, mais uniquement des fonctions managées. Comme les assemblys mixtes, les assemblys purs autorisent l’interopérabilité avec des DLL natives via P/Invoke (consultez [à l’aide de PInvoke explicite en C++ (attribut DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)), mais les fonctionnalités d’interopérabilité C++ ne sont pas disponibles. En outre, les assemblys purs ne peut pas exporter les fonctions pouvant être appelées depuis des fonctions natives car les points d’entrée dans un assembly pur, utilisez le [__clrcall](../cpp/clrcall.md) convention d’appel.  
  
### <a name="advantages-of-clrpure"></a>Avantages de/CLR : pure  
  
-   Meilleures performances : Les assemblys purs contiennent uniquement du MSIL, aucune fonction native, et par conséquent, aucune transition managés/non managés non n’est nécessaires. (Les appels de fonction effectués via P/Invoke sont une exception à cette règle.)  
  
-   Détection d’AppDomain : Les fonctions managées et les types de données CLR existent dans `Application Domains`, ce qui affecte leur visibilité et leur accessibilité. Assemblys purs prennent en charge de domaine (__declspec ([appdomain](../cpp/appdomain.md)) est impliqué pour chaque type) afin d’accéder à leurs types et les fonctionnalités d’autres composants .NET est plus facile et plus sûre. Par conséquent, les assemblys purs interagissent plus facilement avec d’autres composants .NET que les assemblys mixtes.  
  
-   Chargement hors disque : les assemblys purs peuvent être chargées en mémoire et même transmis en continu. Ceci est essentiel pour l’utilisation d’assemblys .NET en tant que procédures stockées. Cela diffère des assemblys mixtes, qui, en raison d’une dépendance sur les fenêtres de mécanismes, de chargement doit exister sur le disque afin d’exécuter.  
  
-   Réflexion : Il n’est pas possible de réfléchir aux fichiers exécutables mixtes, tandis que les assemblys purs prennent en charge complète de réflexion. Pour plus d’informations, consultez [réflexion (C + c++ / CLI)](../dotnet/reflection-cpp-cli.md).  
  
-   Contrôle de l’hôte : Les assemblys purs contiennent uniquement du MSIL, leur comportement plus prévisible et plus souple que les assemblys mixtes lorsqu’utilisée dans les applications qui hébergent le CLR et de modifier son comportement par défaut.  
  
### <a name="limitations-of-clrpure"></a>Limitations de/CLR : pure  
 Cette section traite des fonctionnalités non prises en charge par **/CLR : pure**.  
  
-   Les assemblys purs ne peut pas être appelées par les fonctions non managées. Par conséquent, les assemblys purs ne peuvent pas implémenter des interfaces COM ou exposer des rappels natifs. Les assemblys purs ne peut pas exporter de fonctions via __declspec (dllexport) ou. Fichiers DEF. En outre, les fonctions déclarées avec le \__clrcall convention ne peut pas être importée par \__declspec (dllimport). Fonctions dans un module natif peuvent être appelées à partir d’un assembly pur, mais les assemblys purs ne peuvent pas exposer de fonctions pouvant être appelé en natif, afin d’exposer des fonctionnalités dans un assembly pur doit être effectuée par le biais des fonctions managées dans un assembly mixte. Consultez [Comment : migrer vers/clr : pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md) pour plus d’informations.  
  
-   Les bibliothèques ATL et MFC ne sont pas pris en charge par la compilation en mode pur dans Visual C++.  
  
-   .Netmodules purs ne sont pas acceptés en tant qu’entrée dans l’éditeur de liens Visual C++. Toutefois, les fichiers .obj purs sont acceptés par l’éditeur de liens et les fichiers .obj contiennent un sur-ensemble des informations contenues dans les netmodules. Consultez [fichiers .netmodule en tant qu’entrée de l’éditeur de liens](../build/reference/netmodule-files-as-linker-input.md) pour plus d’informations.  
  
-   Prise en charge COM du compilateur (#import) n’est pas prise en charge car cela introduirait des instructions non managées dans l’assembly pur.  
  
-   Options d’alignement et de gestion des exceptions ne sont pas réglables pour les assemblys purs de virgule flottante. Par conséquent, __declspec (Align) ne peut pas être utilisé. Cela rend les fichiers d’en-tête, tels que fpieee.h, incompatible avec/clr : pure.  
  
-   La fonction GetLastError dans le PSDK peut entraîner un comportement indéfini lors de la compilation avec **/CLR : pure**.  
  
## <a name="verifiable-clrsafe"></a>Vérifiable (/ CLR : safe)  
 Le **/CLR : safe** option du compilateur génère des assemblys vérifiables, telles que celles écrites en Visual Basic et c#, se conformer aux exigences qui permettent le common language runtime (CLR) pour garantir que le code ne viole pas en cours paramètres de sécurité. Par exemple, si les paramètres de sécurité empêchent un composant à partir de l’écriture sur le disque, le CLR peut déterminer si un composant vérifiable répond à ce critère avant d’exécuter du code. Il n’existe aucune prise en charge de CRT pour les assemblys vérifiables. (Prise en charge CRT est disponible pour les assemblys purs via une version MSIL pur de la bibliothèque Runtime C).  
  
 Assemblys vérifiables offrent les avantages sur les assemblys purs et mixtes :  
  
-   Sécurité accrue.  
  
-   Certaines situations les exigent (les composants SQL, par exemple).  
  
-   Les versions ultérieures de Windows nécessitera plus en plus des composants et applications pour être vérifiable.  
  
 Un inconvénient est que les fonctionnalités d’interopérabilité C++ ne sont pas disponibles. Assemblys vérifiables ne peut pas contenir les fonctions non managées ou les types de données natifs, même si elles ne sont pas référencées par le code managé.  
  
 En dépit de l’utilisation du mot « safe », la compilation des applications avec **/CLR : safe** ne signifie pas il n’existe pas de bogues ; cela signifie simplement que le CLR peut vérifier les paramètres de sécurité en cours d’exécution.  
  
 Quel que soit le type d’assembly, les appels effectués à partir d’assemblys managés dans des DLL natives via P/Invoke sont compilés mais risque d’échouer lors de l’exécution en fonction des paramètres de sécurité.  
  
> [!NOTE]
>  Il existe un scénario de programmation qui passera le compilateur mais le résultat sera dans un assembly non vérifiable : appel de fonction virtuelle via une instance d’objet à l’aide de l’opérateur de résolution de portée.  Par exemple : `MyObj -> A::VirtualFunction();`.  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation .NET avec C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)