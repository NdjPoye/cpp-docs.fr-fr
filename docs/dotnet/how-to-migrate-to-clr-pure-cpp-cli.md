---
title: "Comment : migrer vers - clr : pure (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], migrating to /clr:pure
- migration [C++], pure MSIL
- pure MSIL [C++], porting to
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b8d49ee233167c02570408ba091c2a99b78487d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-migrate-to-clrpure-ccli"></a>Comment : effectuer une migration vers /clr:pure (C++/CLI)
Cette rubrique décrit les problèmes susceptibles de survenir lors de la migration vers le code MSIL pur à l’aide **/CLR : pure** (consultez [/clr (Compilation pour le Common Language Runtime)](../build/reference/clr-common-language-runtime-compilation.md) pour plus d’informations). Cette rubrique suppose que le code en cours de migration est actuellement accepté comme assembly mixte à l’aide de la **/CLR** option, car le chemin d’accès de la migration du code non managé en langage MSIL pure n’est pas direct. Du code non managé, consultez [Comment : migrer vers/CLR](../dotnet/how-to-migrate-to-clr.md) avant de migrer vers le code MSIL pur.  
  
## <a name="basic-changes"></a>Modifications de base  
 MSIL pur est constitué d’instructions MSIL afin de code contenant des fonctions qui ne peuvent pas être exprimées dans le langage MSIL empêchera la compilation. Cela inclut les fonctions définies comme utilisant conventions d’appel autre que [__clrcall](../cpp/clrcall.md). (Non __clrcall fonctions peuvent être appelées dans un composant MSIL pur, mais pas définies.)  
  
 Pour garantir des erreurs d’exécution, vous devez activer l’avertissement C4412. Activez C4412 en ajoutant `#pragma warning (default : 4412)` à chaque module compiland que vous compilez avec **/CLR : pure** et qui passe des types C++ vers et depuis IJW (**/CLR)** ou du code natif. Consultez [l’avertissement du compilateur (niveau 2) C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) pour plus d’informations.  
  
## <a name="architectural-considerations"></a>Considérations sur l’architecturales  
 Certaines des limitations des assemblys MSIL purs répertoriés dans [Code pur et vérifiable (C + c++ / CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) avoir des implications de haut niveau de la stratégie de conception et de migration des applications. Plus particulièrement, contrairement aux assemblys mixtes, les assemblys MSIL pures ne bénéficient pas d’une compatibilité complète avec les modules non managés.  
  
 Les assemblys MSIL purs peuvent appeler des fonctions non managées, mais ne peut pas être appelées par les fonctions non managées. Par conséquent, MSIL pur est un meilleur candidat pour le code client qui utilise les fonctions non managées que pour le code de serveur qui est utilisé par les fonctions non managées. Si la fonctionnalité contenue dans un assembly MSIL pur est utilisable par les fonctions non managées, un assembly mixte doit être utilisé comme couche d’interface.  
  
 Les applications qui utilisent ATL ou MFC ne sont pas idéales pour la migration vers le code MSIL pur, car ces bibliothèques ne sont pas pris en charge dans cette version. De même, la [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] contient les fichiers d’en-tête qui ne sont pas compilés sous **/CLR : pure**.  
  
 Alors que les assemblys MSIL pures peuvent appeler des fonctions non managées, cette possibilité est limitée à des fonctions de style C simples. L’utilisation d’API non managées plus complexes est probablement besoin des fonctionnalités non managée doit être exposée sous la forme d’une interface COM ou un assembly mixte peut agir comme une interface entre le code MSIL pur et les composants non managés. À l’aide d’une couche d’assembly mixte est la seule façon d’utiliser des fonctions non managées qui utilisent des fonctions de rappel, par exemple, comme un assembly pur est incapable de fournir une fonction native appelable à utiliser comme un rappel.  
  
## <a name="application-domains-and-calling-conventions"></a>Domaines d’application et les Conventions d’appel  
 Bien qu’il soit possible pour MSIL pure assemblys utilisent des fonctionnalités non managées, fonctions et données statiques sont gérées différemment. Dans les assemblys purs, les fonctions sont implémentées avec la [__clrcall](../cpp/clrcall.md) convention d’appel et les données statiques est stockée par domaine d’application. Cela diffère de la valeur par défaut pour les assemblys mixtes et non managées, qui utilisent la [__cdecl](../cpp/cdecl.md) convention d’appel de fonctions et de stocker des données statiques par processus.  
  
 Dans le contexte du code MSIL pur (et du code vérifiable compilé avec/clr : safe), ces valeurs par défaut sont transparentes, en tant que [__clrcall](../cpp/clrcall.md) est la convention d’appel par défaut du CLR et les domaines d’application sont la portée native pour statique et données globales dans les applications .NET. Toutefois, lorsque vous utilisez des composants non managés ou mixtes, le traitement différent des fonctions et des données globales peut entraîner des problèmes.  
  
 Par exemple, si un composant MSIL pur doit appeler des fonctions dans une DLL non managée ou mixte, un fichier d’en-tête pour la DLL sera utilisé pour compiler l’assembly pur. Toutefois, à moins que la convention d’appel pour chaque fonction dans l’en-tête est indiquée explicitement, elles seront toutes considéré comme étant [__clrcall](../cpp/clrcall.md). Cela entraîne plus tard les échecs d’exécution, car ces fonctions sont généralement implémentées avec la [__cdecl](../cpp/cdecl.md) convention. Les fonctions dans le fichier d’en-tête non managé peuvent être marquées explicitement comme [__cdecl](../cpp/cdecl.md), ou l’ensemble du code source DLL doit être recompilé sous **/CLR : pure**.  
  
 De même, les pointeurs fonction sont supposés pour pointer vers [__clrcall](../cpp/clrcall.md) fonctionne sous **/CLR : pure** compilation. Ces trop doivent être explicitement annotés avec la convention d’appel appropriée.  
  
 Pour plus d’informations, consultez [domaines d’Application et Visual C++](../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="linking-limitations"></a>Limitations des liens  
 L’éditeur de liens Visual C++ ne tente pas de lier des fichiers OBJ mixtes et pures, comme les conventions d’étendue et l’appel de stockage sont différentes.  
  
## <a name="see-also"></a>Voir aussi  
 [Code pur et vérifiable (C++-CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)