---
title: "Assemblys mixtes (natif et manag&#233;) | Microsoft Docs"
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
  - "/clr (option du compilateur C++), assemblys mixtes"
  - "assemblys (C++), mixtes"
  - "Interop (C++), assemblys mixtes"
  - "interopérabilité (C++), assemblys mixtes"
  - "code managé (C++), interopérabilité"
  - "assemblys mixtes (C++)"
  - "assemblys mixtes (C++), à propos des assemblys mixtes"
  - "DLL mixte (chargement) (C++)"
  - "code natif (C++), interopérabilité .NET"
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# Assemblys mixtes (natif et manag&#233;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les assemblys mixtes sont capables de contenir à la fois des instructions machine non managées et des instructions MSIL.  Cela leur permet d'appeler et d'être appelés par des composants .NET, tout en restant compatibles avec des composants totalement non managés.  Grâce aux assemblys mixtes, les développeurs peuvent créer des applications utilisant un mélange de fonctionnalités managées et non managées.  Les assemblys mixtes conviennent parfaitement pour faire migrer les applications Visual C\+\+ existantes vers la plateforme .NET.  
  
 Par exemple, une application existante entièrement composée de fonctions non managées peut être portée sur la plateforme .NET en recompilant simplement un unique module à l'aide du commutateur de compilation **\/clr**.  Ce module est alors capable d'utiliser des fonctionnalités .NET, mais reste compatible avec le reste de l'application.  Ainsi, une application peut être convertie vers la plateforme .NET de façon graduelle et par tranches.  Il est même possible de choisir fonction par fonction une compilation managée ou non managée dans le même fichier \(consultez [managé, non managé](../preprocessor/managed-unmanaged.md)\).  
  
 Visual C\+\+ prend en charge la génération de trois types distincts d'assemblys managés : mixtes, purs et vérifiables.  Les deux derniers sont traités dans [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## Dans cette section  
 [Comment : effectuer une migration vers \/clr](../dotnet/how-to-migrate-to-clr.md)  
 Décrit les étapes recommandées pour introduire ou mettre à niveau des fonctionnalités .NET dans votre application.  
  
 [Comment : compiler du code MFC et ATL à l'aide de \/clr](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)  
 Explique comment compiler des programmes MFC et ATL existants pour cibler le Common Language Runtime.  
  
 [Initialisation d'assemblys mixtes](../dotnet/initialization-of-mixed-assemblies.md)  
 Décrit le problème dit du « verrouillage de chargeur » et ses solutions.  
  
 [Prise en charge de bibliothèque pour les assemblys mixtes](../dotnet/library-support-for-mixed-assemblies.md)  
 Traite de la façon d'utiliser des bibliothèques natives dans les compilations **\/clr**.  
  
 [Considérations sur les performances](../dotnet/performance-considerations-for-interop-cpp.md)  
 Décrit les conséquences des assemblys mixtes et du marshaling de données sur les performances.  
  
 [Domaines d'application et Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)  
 Traite de la prise en charge par Visual C\+\+ des domaines d'application.  
  
 [Double conversion de code \(thunking\)](../dotnet/double-thunking-cpp.md)  
 Traite des conséquences, en termes de performances, de l'utilisation d'un point d'entrée natif pour une fonction managée.  
  
 [Éviter des exceptions à l'arrêt du CLR lors de l'utilisation d'objets COM générés avec \/clr](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)  
 Traite de la façon de garantir l'arrêt correct d'une application managée qui consomme un objet COM compilé avec **\/clr**.  
  
 [Comment : créer une application partiellement approuvée en supprimant la dépendance de la DLL de la bibliothèque CRT](../dotnet/create-a-partially-trusted-application.md)  
 Explique comment créer une application du Common Language Runtime de niveau de confiance partiel à l'aide de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] en supprimant la dépendance vis\-à\-vis de msvcm90.dll.  
  
 Pour plus d'informations sur les conventions de codage des assemblys mixtes, consultez l'article MSDN « Une présentation de l'interopérabilité de code managé\/non managé » via [http:\/\/msdn.microsoft.com\/netframework\/default.aspx?pull\=\/library\/dndotnet\/html\/manunmancode.asp](http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp).  
  
## Voir aussi  
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)