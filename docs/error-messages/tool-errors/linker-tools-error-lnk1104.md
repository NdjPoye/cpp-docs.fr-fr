---
title: "Erreur LNK1104 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: c6121f598bc2913b65fe781b07bcc27e6b55375b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk1104"></a>Erreur des outils Éditeur de liens LNK1104
Impossible d’ouvrir le fichier '*nom de fichier*'  
  
L’éditeur de liens n’a pas pu ouvrir le fichier spécifié.  
  
## <a name="possible-causes-and-solutions"></a>Causes et solutions possibles
  
Cette erreur peut se produire lorsque l’éditeur de liens tente d’ouvrir un fichier en lecture ou en écriture. Les causes les plus courantes de ce problème sont que le fichier n’existe pas, ne figure pas dans un répertoires de l’éditeur de liens recherche, ou est en cours d’utilisation et verrouillé par un autre processus. Moins fréquemment, vous avez pouvez manquer d’espace disque, le fichier est peut-être trop grand, le chemin d’accès au fichier est trop long ou vous n’êtes ne peut-être pas autorisé à accéder au fichier.  

Recherchez un de ces problèmes courants :  

-   Votre application est déjà en cours d’exécution lorsque vous essayez de régénérer. Si le fichier ne peut pas être ouvert est le fichier exécutable ou un fichier de débogage comme un fichier .pdb, il s’agit d’une cause courante. Pour résoudre ce problème, arrêtez le programme et le déchargement du débogueur avant de réexécuter la génération.  
  
-   Le fichier *nom de fichier* est généré par votre solution, mais n’existe pas lorsque l’éditeur de liens tente d’y accéder. Cela peut se produire quand un projet dépend d’un autre projet pour générer ce fichier, mais les projets ne sont pas générés dans l’ordre approprié. Pour résoudre ce problème, assurez-vous que vos références de projet sont définies dans le projet qui utilise le fichier pour le fichier manquant est généré avant qu’il soit nécessaire. Pour plus d’informations, consultez [ajouter des références de projets Visual C++](../../ide/adding-references-in-visual-cpp-projects.md) et [gestion des références dans un projet](/visualstudio/ide/managing-references-in-a-project).  
  
-   Le nom de fichier ou le chemin d’accès spécifié sur la ligne de commande ou dans une directive de lib #pragma est incorrect, ou le chemin d’accès a une spécification de lecteur non valide. Vérifiez l’orthographe et que le fichier existe à l’emplacement spécifié.  
  
-   Si vous utilisez l’IDE de Visual Studio pour générer un projet qui a été copié à partir d’un autre ordinateur, les emplacements d’installation pour les bibliothèques peuvent être différents. Vérifiez la propriété de répertoires de bibliothèques sur le [Page de propriétés répertoires VC ++](../../ide/vcpp-directories-property-page.md) et mettre à jour si nécessaire. Pour afficher et modifier les chemins d’accès de bibliothèque actuel dans l’environnement IDE, cliquez sur le contrôle de liste déroulante pour la propriété de répertoires de bibliothèques, choisissez **modifier**. Le **évaluée valeur** section de la boîte de dialogue répertoires de bibliothèques répertorie les chemins d’accès actuels, recherchées les fichiers de bibliothèque.  
  
-   Si vous générez un projet qui a été créé à l’aide d’une version antérieure de Visual Studio, les outils de plateforme et les bibliothèques de cette version ne peuvent pas être pas installés. Pour résoudre ce problème, vous avez deux options : vous pouvez mettre à niveau le projet pour utiliser l’ensemble d’outils de plateforme actuelle que vous avez installé, ou vous pouvez installer l’ensemble d’outils plus anciens et générez le projet sans modification. Pour plus d’informations, consultez [la mise à niveau des projets à partir de Versions antérieures de Visual C++](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) et [utiliser multi-ciblage natif dans Visual Studio pour générer des projets ancien](../../porting/use-native-multi-targeting.md).
  
-   Les bibliothèques pour la configuration de projet actuelle ou d’un ensemble d’outils de plateforme ne sont pas installés. Vérifiez que les outils de plateforme et le Kit de développement logiciel Windows spécifié dans le [page de propriétés général](../../ide/general-property-page-project.md) pour votre projet sont installés et vérifiez que les bibliothèques requises sont disponibles dans les répertoires de bibliothèque spécifié dans le [Page de propriétés répertoires VC ++](../../ide/vcpp-directories-property-page.md) pour vos paramètres de configuration. Il existe des paramètres distincts pour les configurations Debug et la vente au détail, par conséquent, si une build fonctionne, mais que l’autre provoque une erreur, vérifiez les paramètres sont corrects et que les bibliothèques et les outils requis sont installés pour les deux configurations.  
  
-   Le chemin d’accès au Kit de développement est obsolète. Si vous avez installé une version du Kit de développement qui est plus récente que la version de Visual Studio, assurez-vous que les chemins d’accès spécifié dans le [Page de propriétés répertoires VC ++](../../ide/vcpp-directories-property-page.md) sont mis à jour le nouveau SDK. Si vous utilisez l’invite de commandes développeur, assurez-vous que le fichier de commandes qui initialise les variables d’environnement est mis à jour pour les nouveaux chemins de kit de développement logiciel.  
  
-   Un autre programme a peut-être ouvert le fichier et l’éditeur de liens ne peut pas y accéder en écriture. Les programmes antivirus souvent bloquent temporairement l’accès aux fichiers qui vient d’être créés. Pour résoudre ce problème, essayez d’excluant les répertoires de génération de projet à partir de l’antivirus.  
  
-   Si vous utilisez une option de génération en parallèle, il est possible que Visual Studio a verrouillé le fichier sur un autre thread. Pour résoudre ce problème, vérifiez que vous ne créez pas le même objet de code ou de la bibliothèque dans plusieurs projets, et utiliser les dépendances de génération ou de références de projet pour prendre les binaires générés dans votre projet.  
  
-   Vous disposez d’une variable d’environnement LIB incorrecte. Dans les versions de ligne de commande, vérifiez que la variable d’environnement LIB est définie et contient tous les répertoires pour les bibliothèques que vous utilisez. Dans l’IDE, la variable LIB est définie par la propriété de répertoires de bibliothèques sur le [Page de propriétés répertoires VC ++](../../ide/vcpp-directories-property-page.md). Vérifiez que tous les répertoires qui contiennent les bibliothèques que vous avez besoin sont répertoriées ici. Si vous avez besoin fournir un répertoire de la bibliothèque qui substitue un répertoire de la bibliothèque standard, vous pouvez utiliser la [/LIBPATH](../../build/reference/libpath-additional-libpath.md)) option sur la ligne de commande ou de la propriété de répertoires de bibliothèques supplémentaires dans la page de propriétés de l’éditeur de liens pour votre projet.  
  
-   Lorsque vous spécifiez des bibliothèques dans la boîte de dialogue Pages de propriétés d’un projet, les noms de bibliothèques doivent être séparés par des espaces, et non par des virgules.  
  
-   Le chemin d’accès pour *nom de fichier* s’étend sur plus de 260 caractères. Modifier les noms ou réorganiser votre structure de répertoires si nécessaire pour raccourcir les chemins d’accès aux fichiers requis.  
  
-   Le fichier est trop volumineux. Objet ou bibliothèques les fichiers plus un gigaoctet taille peut provoquer des problèmes pour l’éditeur de liens 32 bits. Un correctif pour résoudre ce problème est d’utiliser l’ensemble d’outils 64 bits. Pour plus d’informations sur la façon de procéder à la ligne de commande, consultez [Comment : activer un 64 bits Visual C++ ensemble d’outils de la ligne de commande](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). Pour plus d’informations sur la façon de procéder dans l’IDE, consultez [à l’aide de MSBuild avec le compilateur et outils 64 bits](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) et ce billet de débordement de pile : [comment Visual Studio utiliser la chaîne d’outils native amd64](http://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).  
  
-   Vous disposez des autorisations de fichier est insuffisante pour accéder à *nom de fichier*. Cela peut se produire si vous accéder aux fichiers de bibliothèque dans les répertoires du système protégé, ou que vous utilisez des fichiers copiés à partir d’autres utilisateurs qui ont leurs autorisations d’origine définie. Pour résoudre ce problème, déplacez le fichier vers un répertoire de projet accessible en écriture. Si le fichier se trouve dans un répertoire accessible en écriture, mais il possède des autorisations inaccessibles, vous pouvez utiliser une invite de commandes administrateur et exécutez la commande takeown.exe de prendre possession du fichier.  
  
-   Vous n’avez pas suffisamment d’espace disque. L’éditeur de liens utilise des fichiers temporaires dans plusieurs cas. Même si vous disposez de suffisamment d’espace disque, un lien très volumineux peut épuiser ou fragmenter l’espace disque disponible. Envisagez d’utiliser le [/OPT (optimisations)](../../build/reference/opt-optimizations.md) option ; les lectures comdat transitive élimination tous les fichiers objets plusieurs fois.  
  
-   Si le *nom de fichier* est nommé LNK*n*, qui est un nom de fichier généré par l’éditeur de liens pour un fichier temporaire, le répertoire spécifié dans la variable d’environnement TMP n’existe pas, ou plusieurs répertoires peut être spécifié pour la variable d’environnement TMP. Chemin d’accès d’un seul répertoire doit être spécifié pour la variable d’environnement TMP.  
  
-   Si le message d’erreur s’affiche pour un nom de bibliothèque et que vous avez porté récemment le fichier .mak à partir d’un système de développement Microsoft Visual C++ antérieur, la bibliothèque n’est peut-être plus valide. Vérifiez que le nom de la bibliothèque est correct et qu’il existe toujours dans l’emplacement spécifié, ou mettre à jour le chemin d’accès LIB pour pointer vers le nouvel emplacement.  

