---
title: "Comparaison entre les fonctionnalités mixte, Pure et vérifiable (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- safe assemblies [C++], vs. pure
- mixed assemblies [C++], vs. pure
- safe assemblies [C++], vs. mixed
- pure MSIL [C++]
- verifiable assemblies [C++]
- pure MSIL [C++], vs. safe
- pure MSIL [C++], vs. mixed
- pure MSIL [C++], compared to mixed and safe
- verifiable assemblies [C++], vs. mixed
- mixed assemblies [C++], vs. safe
- verifiable assemblies [C++], vs. pure
- pure assemblies [C++]
- safe assemblies [C++]
- mixed assemblies [C++]
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 92c3b6b95bc1ddb51900d8274f76993c32a71ceb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Comparaison entre les fonctionnalités mixte, pure et vérifiable (C++/CLI)
Cette rubrique compare les fonctionnalités des différents **/CLR** modes de compilation. Pour plus d’informations, consultez l’article [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
## <a name="feature-comparison"></a>Comparaison des fonctionnalités  
  
|Fonctionnalité|Mixte (/ clr)|Pure (/ clr : pure)|Sécurisé (/ CLR : safe)|Informations connexes|  
|-------------|---------------------|-------------------------|-------------------------|-------------------------|  
|Bibliothèque CRT|Prise en charge|Prise en charge||[Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)|  
|MFC/ATL|Prise en charge|||[Les Applications de bureau MFC](../mfc/mfc-desktop-applications.md) &#124; [Vue d’ensemble de la classe](../atl/atl-class-overview.md)|  
|Fonctions non managées|Prise en charge|||[Assemblys mixtes (natif et managé)](../dotnet/mixed-native-and-managed-assemblies.md)|  
|Données non managées|Prise en charge|Prise en charge||[Code pur et vérifiable (C++-CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|Peut être appelé à partir de fonctions non managées|Prise en charge|||[Comment : migrer vers/clr : pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)|  
|Prend en charge l’appel de fonctions non managées|Prise en charge|Fonctions de style C uniquement|P/Invoke uniquement|[Utilisation de l’interopérabilité C++ (PInvoke implicite)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|Prend en charge la réflexion|DLL uniquement|Prise en charge|Prise en charge|[Réflexion (C++-CLI)](../dotnet/reflection-cpp-cli.md)|  
  
## <a name="see-also"></a>Voir aussi  
 [Code pur et vérifiable (C++-CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)