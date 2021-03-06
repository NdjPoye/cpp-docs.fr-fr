---
title: Concepts d’Applications isolées et les assemblys côte à côte | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- side-by-side assemblies [C++]
- isolated assemblies [C++]
ms.assetid: 945a885f-cb3e-4c8a-a0b9-2c2e3e02cc50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095737bf4684f4ba9ed58483bca664f734d1a534
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="concepts-of-isolated-applications-and-side-by-side-assemblies"></a>Concepts d'applications isolées et d'assemblys côte à côte
Une application est considérée comme une [application isolée](http://msdn.microsoft.com/library/aa375190) si tous ses composants sont des [assemblys côte à côte](http://msdn.microsoft.com/library/ff951640). Un assembly côte à côte est une collection de ressources (un groupe de DLL, de classes de fenêtres, de serveurs COM, de bibliothèques de types ou d'interfaces) déployées ensemble et qu'une application peut utiliser au moment de l'exécution. En général, un assembly côte à côte est composé d'une ou de plusieurs DLL.  
  
## <a name="shared-or-private"></a>Partagé ou privé  
 Un assembly côte à côte peut ou être partagé ou privé. Les[assemblys côte à côte partagés](https://msdn.microsoft.com/en-us/library/aa375996.aspx) peuvent être utilisés par plusieurs applications qui spécifient, dans leur manifeste, une dépendance vis-à-vis de ces derniers. Plusieurs versions d'un assembly côte à côte peuvent être partagées par différentes applications qui s'exécutent en même temps. Un [assembly privé](http://msdn.microsoft.com/library/ff951638) est un assembly déployé avec une application et réservé à l'usage exclusif de cette dernière. Les assemblys privés sont installés dans le dossier qui contient le fichier exécutable de l'application ou l'un de ses sous-dossiers.  
  
## <a name="manifests-and-search-order"></a>Manifestes et ordre de recherche  
 Les applications isolées et les assemblys côte à côte sont décrits par des [manifestes](http://msdn.microsoft.com/library/aa375365). Un manifeste est un document XML qui peut être un fichier externe ou qui peut être incorporé dans une application ou un assembly en tant que ressource. Le fichier manifeste d'une application isolée sert à gérer les noms et les versions des assemblys partagés côte à côte auxquels l'application doit se lier au moment de l'exécution. Le manifeste d'un assembly côte à côte spécifie les noms, les versions, les ressources et les assemblys dépendants d'assemblys côte à côte. Dans le cas d'un assembly partagé côte à côte, le manifeste est installé dans le dossier %WINDIR%\WinSxS\Manifests\. Dans le cas d'un assembly privé, il est recommandé d'inclure le manifeste dans la DLL en tant que ressource dont l'ID est égal à 1. Vous pouvez également donner à l'assembly privé le même nom que celui de la DLL. Pour plus d’informations, consultez [sur les assemblys privés](http://msdn.microsoft.com/library/ff951638).  
  
 Au moment de l'exécution, Windows utilise les informations d'assembly provenant du manifeste de l'application pour rechercher et charger l'assembly côte à côte correspondant. Si une application isolée spécifie une dépendance d'assembly, le système d'exploitation recherche d'abord l'assembly parmi les assemblys partagés contenus dans le cache d'assembly natif au sein du dossier %WINDIR%\WinSxS\. Si l'assembly requis n'y figure pas, le système d'exploitation recherche un assembly privé dans un dossier de la structure de répertoire de l'application. Pour plus d’informations, consultez [Séquence de recherche d’assemblys](http://msdn.microsoft.com/library/aa374224).  
  
## <a name="changing-dependencies"></a>Modification des dépendances  
 Vous pouvez modifier des dépendances d’assemblys côte à côte après qu’une application a été déployée en modifiant les [fichiers de configuration d’éditeur](http://msdn.microsoft.com/library/aa375682) et les [fichiers de configuration de l’application](http://msdn.microsoft.com/library/aa374182). Un fichier de configuration d'éditeur, également appelé fichier de stratégie d'éditeur, est un fichier XML qui redirige globalement des applications et des assemblys, les empêchant d'utiliser une version d'un assembly côte à côte pour les contraindre à utiliser une autre version du même assembly. Par exemple, vous pouvez modifier une dépendance lorsqu'une résolution de bogue ou un correctif de sécurité est déployé pour un assembly côte à côte et que vous souhaitez rediriger toutes les applications de manière à utiliser la version corrigée. Un fichier de configuration de l'application est un fichier XML qui redirige une application spécifique de façon à ce qu'elle utilise, plutôt qu'une version d'un assembly côte à côte, une autre version du même assembly. Vous pouvez utiliser un fichier de configuration de l'application pour rediriger une application spécifique afin qu'elle utilise une autre version d'un assembly côte à côte que celle définie dans le fichier de configuration d'éditeur. Pour plus d’informations, consultez [Configuration](http://msdn.microsoft.com/library/aa375123).  
  
## <a name="visual-c-libraries"></a>Bibliothèques Visual C++  
 Dans Visual Studio 2005 et Visual Studio 2008, les bibliothèques redistribuables telles qu'ATL, MFC, CRT, Standard C++, OpenMP et MSDIA ont été déployées en tant qu'assemblys côte à côte partagés dans le cache d'assembly natif. Dans la version actuelle, les bibliothèques redistribuables utilisent un déploiement central. Par défaut, toutes les applications en Visual C++ sont générées avec le manifeste incorporé au fichier binaire final. Par ailleurs, le manifeste décrit les dépendances de ce fichier binaire vis-à-vis des bibliothèques Visual C++. Pour en savoir plus sur la génération de manifestes d’applications Visual C++, consultez [Understanding Manifest Generation for C/C++ Programs](../build/understanding-manifest-generation-for-c-cpp-programs.md). Un manifeste n'est pas obligatoire pour les applications qui sont liées de façon statique aux bibliothèques qu'elles utilisent, ou qui utilisent un déploiement local. Pour plus d’informations sur le déploiement, consultez [Deployment in Visual C++](../ide/deployment-in-visual-cpp.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Génération d’applications isolées et d’assemblys côte à côte C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)