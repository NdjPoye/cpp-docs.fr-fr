---
title: 'Comment : organiser des fichiers de sortie de projet pour les générations | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, output files
- output files, organizing
ms.assetid: 521d95ea-2dcc-4da0-b5eb-ac3e57941446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0d1e7f8ea67db0e87199e0c12128555fa039112
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-organize-project-output-files-for-builds"></a>Comment : organiser des fichiers de sortie de projet pour les générations
Cette rubrique décrit les meilleures pratiques pour organiser des fichiers de sortie de projet. Générer erreurs peuvent se produire lorsque vous configurez correctement les fichiers de sortie de projet. Cette rubrique décrit également les avantages et inconvénients de chaque solution possible pour organiser vos fichiers de sortie du projet.  
  
## <a name="referencing-clr-assemblies"></a>Référencement des assemblys CLR  
  
#### <a name="to-reference-assemblies-with-using"></a>Pour les assemblys de référence avec #using  
  
1.  Vous pouvez référencer un assembly directement depuis votre code à l’aide de la #using, directive, tel que `#using <System.Data.dll>`. Pour plus d’informations, consultez [#using, Directive](../preprocessor/hash-using-directive-cpp.md).  
  
     Le fichier spécifié peut être un fichier .dll, .exe, .netmodule ou .obj, à condition qu’il soit dans le langage MSIL. Le composant référencé peut être généré dans n’importe quel langage. À l’aide de cette option, vous aurez accès à Intellisense étant donné que les métadonnées sont extraites du code MSIL. Le fichier en question doit être dans le chemin d’accès pour le projet. Sinon, le projet ne peut pas être compilé et Intellisense ne sera pas disponible. Un moyen simple pour déterminer si le fichier est dans le chemin d’accès est avec le bouton droit sur le #using une ligne et choisissez la **document ouvert** commande. Vous êtes averti si le fichier est introuvable.  
  
     Si vous ne souhaitez pas fournir le chemin d’accès complet au fichier, vous pouvez utiliser la **/AI** modifier le chemin de recherche pour l’option du compilateur #using de références. Pour plus d’informations, consultez l’article [/AI (Spécifier les répertoires des métadonnées)](../build/reference/ai-specify-metadata-directories.md).  
  
#### <a name="to-reference-assemblies-with-fu"></a>Pour référencer des assemblys avec /FU  
  
1.  Au lieu de référencer un assembly directement à partir d’un fichier de code, comme décrit ci-dessus, vous pouvez utiliser la **/FU** option du compilateur. L’avantage de cette méthode est que vous n’avez pas à ajouter une #using à chaque fichier qui fait référence à un assembly donné.  
  
     Pour définir cette option, ouvrez le **Pages de propriétés** pour le projet. Développez le **propriétés de Configuration** nœud, puis développez le **C/C++** nœud et sélectionnez **avancé**. Ajoutez les assemblys désirés regard **Force #using**. Pour plus d’informations, consultez l’article [/FU (Nom du fichier #using imposé)](../build/reference/fu-name-forced-hash-using-file.md).  
  
#### <a name="to-reference-assemblies-with-add-new-reference"></a>Référencer des assemblys avec Ajouter une nouvelle référence  
  
1.  Il s’agit de la façon la plus simple d’utiliser des assemblys CLR. Tout d’abord, assurez-vous que le projet est compilé avec le **/CLR** option du compilateur. Ensuite, cliquez avec le bouton droit sur le projet à partir de la **l’Explorateur de solutions** et sélectionnez **ajouter**, **références**. Le **Pages de propriétés** boîte de dialogue apparaît.  
  
2.  À partir de la **Pages de propriétés** boîte de dialogue, sélectionnez **ajouter une nouvelle référence**. Une boîte de dialogue qui répertorie tous les .NET, COM et des autres assemblys disponibles dans le projet actuel. Sélectionnez l’assembly souhaité et cliquez sur **OK**.  
  
     Une fois qu’une référence de projet est définie, les dépendances correspondantes sont gérées automatiquement. En outre, étant donné que les métadonnées fait partie d’un assembly, il n’est pas nécessaire d’ajouter un fichier d’en-tête ou un prototype les éléments qui sont utilisés à partir d’assemblys managés.  
  
## <a name="referencing-native-dlls-or-static-libraries"></a>Référence à des DLL natives ou des bibliothèques statiques  
  
#### <a name="to-reference-native-dlls-or-static-libraries"></a>Pour référencer des DLL natives ou des bibliothèques statiques  
  
1.  Référencer le fichier d’en-tête approprié dans votre code en utilisant le #include (directive). Le fichier d’en-tête doit être dans le chemin d’accès include ou une partie du projet actuel. Pour plus d’informations, consultez [#include, Directive (C/C++)](../preprocessor/hash-include-directive-c-cpp.md).  
  
2.  Vous pouvez également définir des dépendances du projet. Définition des dépendances de projet garantit deux choses. Tout d’abord, elle garantit que les projets sont générés dans le bon ordre afin qu’un projet peut toujours trouver les fichiers dépendants dont il a besoin. Ensuite, elle ajoute implicitement répertoire de sortie du projet dépendant pour le chemin d’accès afin que les fichiers se trouvent facilement au moment de la liaison.  
  
3.  Pour déployer l’application, vous devez placer la DLL dans un emplacement approprié. Cela peut prendre l’une des opérations suivantes :  
  
    1.  Le même chemin que le fichier exécutable.  
  
    2.  N’importe où dans le chemin d’accès système (le **chemin d’accès** variable d’environnement).  
  
    3.  Dans l’assembly côte à côte. Pour plus d’informations, consultez [création d’assemblys C/C++ côte-à-côte](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="working-with-multiple-projects"></a>Utilisation de plusieurs projets  
 Par défaut, les projets sont générés tels que tous les fichiers de sortie sont créés dans un sous-répertoire du répertoire du projet. Le répertoire est nommé en fonction de la configuration de build (par exemple, Debug ou Release). Dans l’ordre pour les projets de frères faire référence à l’autre, chaque projet doit ajouter explicitement les autres répertoires de sortie de projet à leur chemin d’accès dans l’ordre de liaison pour réussir. Cette opération est effectuée automatiquement lorsque vous définissez les dépendances du projet. Toutefois, si vous n’utilisez pas de dépendances, vous devez soigneusement gérer cela, car les générations peuvent devenir très difficiles à gérer. Par exemple, lorsqu’un projet a configurations Debug et Release, et il inclut une bibliothèque externe à partir d’un projet frère, elle doit utiliser un fichier de bibliothèque différent en fonction de la configuration générée. Par conséquent, le codage en dur ces chemins d’accès peut être compliquée.  
  
 Tous les fichiers de sortie essentiels (tels que les exécutables, les fichiers de liens incrémentiels et les fichiers PDB) sont copiés dans un répertoire de solution commun. Par conséquent, lorsque vous travaillez avec une solution qui contient un nombre de projets C++ avec des configurations équivalentes, tous les fichiers de sortie sont centralisés pour simplifier la liaison et le déploiement. Vous pouvez être sûr que leur application/bibliothèque fonctionne comme prévu si elles conserver ces fichiers (étant donné que les fichiers sont toujours le chemin d’accès).  
  
 L’emplacement des fichiers de sortie peut être un problème majeur lors du déploiement vers un environnement de production. Lors de l’exécution de projets dans l’IDE, les chemins d’accès aux bibliothèques incluses ne sont pas nécessairement les mêmes que dans l’environnement de production. Par exemple, si vous avez `#using "../../lib/debug/mylib.dll"` dans votre code mais puis déployez mylib.dll à un emplacement relatif différent, l’application échoue lors de l’exécution. Pour éviter ce problème, vous devez éviter d’utiliser des chemins d’accès relatifs dans #include instructions dans votre code. Il est préférable de vous assurer que les fichiers nécessaires sont dans le chemin d’accès de build de projet et de la même façon en garantissant que les fichiers de production correspondants sont correctement placées.  
  
#### <a name="how-to-specify-where-output-files-go"></a>Comment spécifier où des fichiers de sortie  
  
1.  Paramètres se trouvent dans le fichier de sortie de l’emplacement du projet **Pages de propriétés**. Développez le nœud à côté **propriétés de Configuration** et sélectionnez **général**. L’emplacement de sortie est spécifié en regard **répertoire de sortie**. Pour plus d’informations, consultez [général, Page de propriétés (projet)](../ide/general-property-page-project.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Types de projets Visual C++](../ide/visual-cpp-project-types.md)