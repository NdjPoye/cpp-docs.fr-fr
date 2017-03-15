---
title: "Comment&#160;: organiser des fichiers de sortie de projet pour les g&#233;n&#233;rations | Microsoft Docs"
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
  - "fichiers de sortie, organiser"
  - "Visual C++, fichiers de sortie"
ms.assetid: 521d95ea-2dcc-4da0-b5eb-ac3e57941446
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Comment&#160;: organiser des fichiers de sortie de projet pour les g&#233;n&#233;rations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les meilleures pratiques pour organiser des fichiers de sortie de projet.  Une installation incorrecte des fichiers de sortie d'un projet peut entraîner des erreurs de build.  Cette rubrique décrit également les avantages et les inconvénients de chaque solution possible pour organiser vos fichiers de sortie de projet.  
  
## Référencement des assemblys CLR  
  
#### Pour référencer des assemblys avec \#using  
  
1.  Vous pouvez référencer un assembly directement depuis votre code à l'aide de la directive \#using ; par exemple, `#using <System.Data.dll>`.  Pour plus d'informations, consultez [\#using, directive](../preprocessor/hash-using-directive-cpp.md).  
  
     Le fichier spécifié peut être un fichier .dll, .exe, .netmodule, ou un fichier .obj, tant qu'il se trouve dans MSIL.  Le composant référencé peut être généré dans tout langage.  Cette option vous donne accès à Intellisense étant donné que les métadonnées sont extraites du code MSIL.  Le fichier en question doit figurer dans le chemin d'accès du projet ; sinon, le projet ne se compile pas et la fonctionnalité Intellisense n'est pas disponible.  Un moyen simple de déterminer si le fichier figure ou non dans le chemin d'accès consiste à cliquer avec le bouton droit sur la ligne \#using, puis à sélectionner la commande **Ouvrir le document**.  Vous êtes alors notifié si le fichier est introuvable.  
  
     Si vous ne souhaitez pas fournir le chemin d'accès complet au fichier, vous pouvez utiliser l'option de compilateur **\/AI** pour modifier le chemin de recherche pour les références \#using.  Pour plus d'informations, consultez [\/AI \(Spécifier les répertoires des métadonnées\)](../build/reference/ai-specify-metadata-directories.md).  
  
#### Pour référencer des assemblys avec \/FU  
  
1.  Au lieu de référencer directement un assembly à partir d'un fichier de code, comme décrit ci\-dessus, vous pouvez utiliser l'option de compilateur **\/FU**.  L'avantage de cette méthode tient dans ce que vous n'avez pas besoin d'ajouter d'instruction \#using distincte à chaque fichier qui référence un assembly donné.  
  
     Pour activer cette option, ouvrez les **Pages de propriétés** du projet.  Développez le nœud **Propriétés de configuration**, puis le nœud **C\/C\+\+**. Sélectionnez **Avancé**.  Ajoutez les assemblys désirés en regard de **Fichiers \#using forcés**.  Pour plus d'informations, consultez [\/FU \(Nom du fichier \#using imposé\)](../build/reference/fu-name-forced-hash-using-file.md).  
  
#### Pour référencer des assemblys avec Ajouter une nouvelle référence  
  
1.  C'est la manière la plus facile d'exploiter des assemblys CLR.  En premier lieu, assurez\-vous que le projet est compilé avec l'option de compilateur **\/clr**.  Puis, cliquez avec le bouton droit sur le projet dans l'**Explorateur de solutions** et sélectionnez **Ajouter**, **Références**.  La boîte de dialogue **Pages de propriétés** s'affiche.  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, sélectionnez **Ajouter une nouvelle référence**.  Une boîte de dialogue s'affiche. Elle répertorie tous les assemblys, notamment .NET et COM, disponibles dans le projet actuel.  Sélectionnez l'assembly souhaité, puis cliquez sur **OK**.  
  
     Une fois qu'une référence de projet est définie, les dépendances correspondantes sont contrôlées automatiquement.  De plus, sachant que les métadonnées font partie intégrante d'un assembly, il n'y a aucun besoin d'ajouter un fichier d'en\-tête ou de prototyper les éléments utilisés à partir d'assemblys managés.  
  
## En référençant des DLL natives ou des bibliothèques statiques  
  
#### Pour référencer des DLL natives ou des bibliothèques statiques  
  
1.  Référencez le fichier d'en\-tête approprié dans votre code à l'aide de la directive \#include.  Le fichier d'en\-tête doit être dans le chemin d'accès Include ou faire partie du projet actuel.  Pour plus d'informations, consultez [\#include, directive](../preprocessor/hash-include-directive-c-cpp.md).  
  
2.  Vous pouvez également définir des dépendances de projet.  La définition de dépendances de projet garantit deux aspects.  En premier lieu, elle garantit que les projets sont générés dans l'ordre correct afin qu'ils trouvent toujours les fichiers dépendants dont ils ont besoin.  Ensuite, elle ajoute implicitement le répertoire de sortie du projet dépendant au chemin d'accès afin que les fichiers puissent être facilement trouvés au moment de la liaison.  
  
3.  Pour déployer l'application, vous devez placer la DLL à un emplacement approprié.  Il peut s'agir de l'une des valeurs suivantes :  
  
    1.  Le même chemin d'accès que le fichier exécutable.  
  
    2.  N'importe où sur le chemin d'accès système \(la variable d'environnement **path**\).  
  
    3.  Dans l'assembly côte à côte.  Pour plus d'informations, consultez [Génération d'assemblys côte à côte C\/C\+\+](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## Utilisation de projets multiples  
 Par défaut, les projets sont générés de sorte que tous les fichiers de sortie sont créés dans un sous\-répertoire du répertoire de projet.  Le répertoire est nommé en fonction de la configuration de build \(par exemple,  Debug ou Release\).  Pour que des projets frères se référencent les uns les autres, chacun d'eux doit ajouter explicitement les répertoires de sortie des autres à son chemin d'accès propre pour que le processus de liaison aboutisse.  Ce procédé est automatique lorsque vous définissez les dépendances de projet.  Toutefois, si vous n'utilisez pas de dépendances, vous ne devez pas négliger cet aspect car les générations peuvent devenir très difficiles à gérer.  Par exemple, lorsqu'un projet présente des configurations Debug et Release, et inclut une bibliothèque externe issue d'un projet frère, il doit utiliser un fichier bibliothèque distinct en fonction de la configuration générée.  Donc, un codage irréversible de ces chemins peut s'avérer délicat.  
  
 Tous les fichiers de sortie essentiels \(tels que les fichiers exécutables, les fichiers de liens incrémentiels et les fichiers PDB\) sont copiés dans un répertoire de solution commun.  Aussi, lorsque vous travaillez avec une solution qui contient plusieurs projets C\+\+ avec des configurations équivalentes, tous les fichiers de sortie sont centralisés pour simplifier la liaison et le déploiement.  Vous pouvez être sûr que le fonctionnement de leur application\/bibliothèque est conforme aux attentes dès lors que les projets enregistrent ces fichiers de manière centralisée \(sachant que la présence de ces derniers est garantie sur le chemin d'accès\).  
  
 L'emplacement des fichiers de sortie peut constituer un problème majeur lors du déploiement dans un environnement de production.  Ainsi, si les projets s'exécutent dans l'IDE, les chemins d'accès aux bibliothèques incluses ne sont pas nécessairement les mêmes dans l'environnement de production.  Par exemple, si votre code contient `#using "../../lib/debug/mylib.dll"`, tandis que vous déployez mylib.dll à un emplacement relatif différent, l'application échoue au moment de l'exécution.  Pour empêcher cette situation, vous devez éviter d'utiliser des chemins d'accès relatifs dans les instructions \#include de votre code.  Mieux vaut garantir que les fichiers nécessaires sont bien sur le chemin d'accès de la génération de projet et garantir de la même façon que les fichiers de production correspondants sont placés correctement.  
  
#### Comment spécifier la destination des fichiers de sortie  
  
1.  L'emplacement des paramètres de sortie de projet peut être identifié dans les **Pages de propriétés** du projet.  Développez le nœud placé en regard de **Propriétés de configuration** et sélectionnez **Général**.  L'emplacement de sortie est spécifié en regard de **Répertoire de sortie**.  Pour plus d'informations, consultez [Général, page de propriétés \(Projet\)](../ide/general-property-page-project.md).  
  
## Voir aussi  
 [Types de projets Visual C\+\+](../ide/visual-cpp-project-types.md)