---
title: "Générer du Code C/C++ sur la ligne de commande | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1e780bda6850ef2096ecaf1dbffeefdb9d11c9f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="build-cc-code-on-the-command-line"></a>Générer du code C/C++ sur la ligne de commande

Vous pouvez générer des applications C et C++ sur la ligne de commande en utilisant les outils inclus dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].

Lorsque vous choisissez une des charges de travail C++ dans le [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] programme d’installation, il installe un ensemble d’outils qui inclut les compilateurs C/C++, les éditeurs de liens, et d’autres outils de génération. Ces outils sont utilisés par le [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE et ils peuvent également servir à la ligne de commande. Il existe des compilateurs hébergés x86 et hébergé x64 distincts et les outils de génération de code pour x86, x64 et cibles d’ARM. Chaque ensemble d’outils pour une architecture de build hôte et cible particulière est stockée dans son propre répertoire. Pour fonctionner correctement, ces outils nécessitent plusieurs variables d’environnement spécifiques pour les ajouter au chemin d’accès et pour définir incluent le fichier, le fichier de bibliothèque et d’emplacements de kit de développement logiciel. Pour faciliter la définir ces variables d’environnement, le programme d’installation crée des fichiers de commande personnalisés, également appelés fichiers de commandes, lors de l’installation. Vous pouvez exécuter un de ces fichiers de commandes dans une fenêtre d’invite de commandes pour définir une architecture de build spécifique. Pour plus de commodité, le programme d’installation crée également des raccourcis dans le menu Démarrer (ou page de démarrage sur Windows 8.x) qui démarre windows d’invite de commandes développeur à l’aide de ces fichiers de commandes, toutes les variables d’environnement requises sont définis et prête à fonctionner. 

Les variables d’environnement requises sont spécifiques à votre installation et de l’architecture de build, vous choisissez et pouvez être modifié par les mises à jour de produit ou des mises à niveau. Par conséquent, nous recommandons que vous utilisiez une des raccourcis d’invite de commandes installée ou des fichiers de commandes au lieu de définir les variables d’environnement dans Windows vous-même. Pour plus d’informations, consultez [définir le chemin d’accès et les Variables d’environnement pour les générations de ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  

Les ensembles d’outils de ligne de commande, les fichiers de commande et les raccourcis d’invite de commandes qui sont installés dépendent de processeur de votre ordinateur et les options sélectionnées lors de l’installation. Au minimum, les outils 32 bits hébergés x86 générer du code natif x86 de 32 bits et Cross-outils qui génèrent du code de x64 natif 64 bits sont installés. Si vous avez Windows 64 bits, les outils x64 hébergés 64 bits qui générer du code natif 64 bits et les outils qui génèrent du code natif 32 bits se croisent sont également installés. Si vous choisissez d’installer les outils de plateforme Windows universelle de C++ facultatifs, puis les outils natifs 32 bits et 64 bits générer du code ARM sont également installés. Autres charges de travail peuvent installer d’autres outils.

<a name="developer_command_prompt_shortcuts"></a>
## <a name="developer-command-prompt-shortcuts"></a>Raccourcis d’invite de commandes développeur

Les raccourcis d’invite de commande sont installés dans une version spécifique [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] dossier dans le menu Démarrer. Voici une liste des raccourcis d’invite de commandes base et les architectures de build que pris en charge :

- **Invite de commandes développeur** définit l’environnement à utiliser les outils 32 bits, x86 en mode natif pour générer du code 32 bits, x86 en mode natif.  
- **x86 invite de commandes des outils natifs** définit l’environnement à utiliser les outils 32 bits, x86 en mode natif pour générer du code 32 bits, x86 en mode natif.  
- **x64 invite de commandes des outils natifs** définit l’environnement à utiliser les outils 64 bits, x64 en mode natif pour générer le code 64 bits, x64 en mode natif.  
- **Invite de commande des outils croisés x86_x64** définit l’environnement à utiliser les outils 32 bits, x86 en mode natif pour générer le code 64 bits, x64 en mode natif.  
- **Invite de commande des outils croisés x64_x86** définit l’environnement à utiliser les outils 64 bits, x64 en mode natif pour générer du code 32 bits, x86 en mode natif.  

Les véritable démarrer menu contextuel noms des dossiers et varient selon la version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] que vous avez installé et l’installation du surnom si vous définissez une. Par exemple, si vous avez Visual Studio 2017 installé, et vous lui avez affecté une installation surnom de 15.3, le raccourci d’invite de commandes développeur est nommé **invite de commandes développeur pour VS 2017 (15,3)**, dans un dossier nommé  **Visual Studio 2017**. 

Si vous avez installé le [outils de génération pour Visual Studio 2017](https://go.microsoft.com/fwlink/?linkid=840931) ou [outils Visual C++ 2015 générer](http://landinghub.visualstudio.com/visual-cpp-build-tools) edition, il se peut seulement natif spécifique ou options d’invite de commandes développeur des outils croisés. 

<a name="developer_command_prompt"></a>
## <a name="to-open-a-developer-command-prompt-window"></a>Pour ouvrir une fenêtre d’invite de commandes développeur  
  
1.  Sur le bureau, ouvrez Windows **Démarrer** menu, puis faites défiler pour rechercher et ouvrir le dossier correspondant à votre version de Visual Studio, par exemple, **Visual Studio 2017**. Dans certaines versions antérieures de Visual Studio, les raccourcis sont dans un sous-dossier appelé **Visual Studio Tools**.  
  
2.  Dans le dossier, choisissez le **invite de commandes développeur** pour votre version de Visual Studio. Ce raccourci démarre une fenêtre d’invite de commandes développeur qui utilise l’architecture de génération par défaut des outils 32 bits, x86 en mode natif pour générer du code 32 bits, x86 en mode natif. Si vous préférez une architecture de génération de celle par défaut, choisissez une des natif ou pour spécifier l’architecture de l’hôte et la cible des invites de commandes des outils croisés. 

Un moyen plus rapide pour ouvrir une fenêtre d’invite de commandes développeur consiste à entrer *invite de commandes développeur* dans la zone de recherche sur le bureau, puis choisissez le résultat souhaité.

<a name="developer_command_files"></a>
## <a name="developer-command-files-and-locations"></a>Emplacements et des fichiers de commandes développeur

Si vous préférez définir l’environnement d’architecture de génération dans une fenêtre d’invite de commandes existant, vous pouvez utiliser un des fichiers de commande créées par le programme d’installation. L’emplacement de ces fichiers dépend de la version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] vous avez installé et sur l’emplacement et le choix d’affectation de noms que vous avez apportées pendant l’installation. Pour Visual Studio 2017, l’installation par défaut sur un ordinateur 64 bits se trouve dans \Program fichiers (x86) \Microsoft Visual Studio\2017\\*édition*, où *édition* peut-être la Communauté, Professionnel, entreprise, BuildTools ou un autre nom que vous avez fournies. Pour Visual Studio 2015, l’emplacement d’installation par défaut est dans \Program Files (x86) \Microsoft Visual Studio 14.0. 

Le fichier de commandes d’invite de commandes développeur principal, VsDevCmd.bat, se trouve dans le sous-répertoire Common7\Tools du répertoire d’installation. Lorsque aucun paramètre est spécifié, cela définit l’architecture d’environnement et de build à utiliser les outils de x86 natif 32 bits pour générer les x86 32 bits code.

Fichiers de commandes supplémentaires sont disponibles pour configurer des architectures de build spécifique, en fonction de votre architecture de processeur et le [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] les charges de travail et les options que vous avez installé. Dans Visual Studio 2017, ceux-ci sont situés dans le sous-répertoire VC\Auxiliary\Build de le [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] répertoire d’installation. Dans Visual Studio 2015, ceux-ci se trouvent dans le VC, VC\bin ou VC\bin\\*architectures* dans les sous-répertoires du répertoire d’installation, où *architectures* est un des natifs ou croisés options du compilateur. Ces fichiers de commande de définir les paramètres et appellent VsDevCmd.bat pour configurer l’environnement d’architecture de build spécifiée. Une installation classique peut inclure ces fichiers de commandes :

- **vcvars32.bat** utiliser les outils de x86 en mode natif de 32 bits pour générer des 32 bits x86 code.  
- **VCVARS64.bat** utiliser les outils de x64 en mode natif de 64 bits pour générer les 64 bits x64 code.  
- **vcvarsx86_amd64.bat** utiliser les outils de croisée de x86 en mode natif de 32 bits pour générer les 64 bits x64 code.  
- **vcvarsamd64_x86.bat** utilisez les outils de croisée de x64 en mode natif 64 bits pour générer des 32 bits x86 code.  
- **vcvarsx86_arm.bat** utiliser les outils de croisé x86 natif 32 bits pour générer le code d’ARM.  
- **vcvarsamd64_arm.bat** utiliser les outils de croisé x64 natif 64 bits pour générer le code d’ARM.  
- **vcvarsall.bat** paramètres permet de spécifier l’hôte et architectures cibles, ainsi que les options de kit de développement logiciel et de plateforme. Appeler à l’aide un `/help` paramètre pour obtenir la liste des options.  

> [!CAUTION]
>  Le fichier vcvarsall.bat et autres fichiers de commande peuvent varier d’un ordinateur à l’autre. Ne remplacez pas un fichier vcvarsall.bat manquant ou endommagé en utilisant un fichier provenant d'un autre ordinateur. Réexécutez la [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] programme d’installation pour remplacer le fichier manquant.  
>   
> Le fichier vcvarsall.bat varie également d'une version à l'autre. Si la version actuelle de Visual C++ est installée sur un ordinateur qui possède également une version antérieure de Visual C++, n’exécutez pas vcvarsall.bat ou un autre fichier de commandes à partir de versions différentes dans la même fenêtre d’invite de commandes.  
 
La façon la plus simple pour spécifier une architecture de build particulière dans une fenêtre de commande existante est d’utiliser le fichier vcvarsall.bat. Vous pouvez utiliser vcvarsall.bat pour définir les variables d’environnement pour configurer la ligne de commande pour la compilation native de 32 bits ou 64 bits, ou pour une compilation croisée x86, x64 ou des processeurs ARM. pour cibler Windows Store, plateforme Windows universelle ou plateformes de bureau Windows ; Pour spécifier le Kit de développement logiciel Windows à utiliser ; et pour spécifier la version d’ensemble d’outils de plateforme. Si aucun argument n’est fourni, vcvarsall.bat configure les variables d’environnement pour utiliser le compilateur natif 32 bits actuel pour x86 cibles de bureau Windows. Toutefois, vous pouvez l’utiliser pour configurer un natifs ou croisés outils du compilateur. Si vous spécifiez une configuration de compilateur qui n’est pas installée ou n’est pas disponible sur l’architecture de votre ordinateur de build, un message d’erreur s’affiche. Ce tableau montre les arguments de l’architecture prise en charge :  
  
|Argument d’architecture vcvarsall.bat|Compilateur|Architecture de l’ordinateur hôte|Architecture de sortie de génération|  
|----------------------------|--------------|----------------------------------|-------------------------------|  
|x86|natif 32 bits x86|x86, x64|x86|  
|x86\_amd64 ou x86\_x64|x64 sur x86 croisée|x86, x64|x64|  
|x86_arm|ARM sur x86 croisé|x86, x64|ARM|  
|AMD64 ou x64|x64 64 bits natif|x64|x64|  
|AMD64\_x86 ou x64\_x86|x86 sur x64 croisée|x64|x86|  
|AMD64\_arm ou x64\_arm|ARM sur x64 croisée|x64|ARM|  
  
Vous pouvez utiliser la **stocker** ou **uwp** options pour spécifier le type de plateforme ou aucune des deux pour spécifier une application de bureau. Pour spécifier la version du Kit de développement, vous pouvez un nombre de SDK Windows 10 complète comme 10.0.10240.0, ou spécifier 8.1 pour utiliser le Kit de développement logiciel Windows 8.1. Permet de spécifier l’ensemble d’outils du compilateur Visual Studio 2015 ; 14.0 par défaut, l’environnement est configuré pour utiliser l’ensemble d’outils du compilateur Visual Studio 2017.

<a name="vcvarsall"></a>
## <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Pour configurer l’environnement de génération dans une fenêtre d’invite de commandes existant  
  
1.  À l’invite de commandes, utilisez la commande CD pour changer le répertoire d’installation de Visual Studio. Ensuite, utilisez des CD à nouveau vers le sous-répertoire du répertoire qui contient les fichiers de commandes de configuration spécifiques. Pour Visual Studio 2017, il s’agit du sous-répertoire VC\Auxiliary\Build. Pour Visual Studio 2015, utilisez le sous-répertoire VC.  
  
1.  Pour configurer cette fenêtre d’invite de commandes pour utiliser les outils 32 bits pour générer le code pour x86 les plateformes, à l’invite de commandes, entrez :  
  
     `vcvarsall`  

1.  Pour configurer cette fenêtre d’invite de commandes pour utiliser les outils 32 bits pour générer le code pour x64 les plateformes, à l’invite de commandes, entrez :  
  
     `vcvarsall x86_amd64`  
  
1.  Pour configurer cette fenêtre d’invite de commandes pour utiliser les outils 32 bits pour générer le code pour les plateformes ARM, à l’invite de commandes, entrez :  
  
     `vcvarsall x86_arm`  
  
1.  Pour configurer cette fenêtre d’invite de commandes pour utiliser les outils 64 bits pour générer le code pour x64 les plateformes, à l’invite de commandes, entrez :  
  
     `vcvarsall amd64`  
  
1.  Pour configurer cette fenêtre d’invite de commandes pour utiliser les outils 64 bits pour générer le code pour x86 les plateformes, à l’invite de commandes, entrez :  
  
     `vcvarsall amd64_x86`  
  
1.  Pour configurer cette fenêtre d’invite de commandes pour utiliser les outils 64 bits pour générer le code pour les plateformes ARM, à l’invite de commandes, entrez :  
  
     `vcvarsall amd64_arm`  

Le fichier de commandes définit les variables d’environnement requises pour les chemins d’accès pour les outils de génération, les bibliothèques et les en-têtes. Vous pouvez maintenant utiliser cette fenêtre d’invite de commandes pour exécuter les outils et le compilateur de ligne de commande.  
  
Si vous utilisez [DEVENV](/visualstudio/ide/reference/devenv-command-line-switches) pour les versions de ligne de commande, l’environnement défini par vcvarsall.bat ou d’autres fichiers de commande n’affecte pas vos builds, sauf si vous spécifiez également le **/useenv** option.  

## <a name="command-line-tools"></a>Outils de ligne de commande
  
Pour générer un projet C/C++ sur la ligne de commande, vous pouvez utiliser ces outils de ligne de commande Visual C++ :  
  
[CL](../build/reference/compiling-a-c-cpp-program.md)  
Utilisez le compilateur (cl.exe) pour compiler et lier les fichiers de code source dans les applications, les bibliothèques et les DLL.  
  
[Lien](../build/reference/linking.md)  
Utilisez l'éditeur de liens (link.exe) pour lier les bibliothèques et les fichiers objets compilés dans les applications et les DLL.  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
Utilisez MSBuild (msbuild.exe) pour générer des projets Visual C++ et [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] solutions. Cela équivaut à exécuter la **générer** projet ou **générer la Solution** dans le [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE.  
  
[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)  
Utilisez DEVENV (devenv.exe) combiné à un commutateur de ligne de commande, par exemple, **/Build** ou **/Clean**: pour effectuer certaines commandes de génération sans afficher le [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE.  
  
[NMAKE](../build/nmake-reference.md)  
Utilisez NMAKE (nmake.exe) pour automatiser les tâches qui génèrent des projets Visual C++ à l’aide d’un fichier makefile traditionnel.  
  
Quand vous générez sur la ligne de commande, vous pouvez obtenir plus d’informations sur les erreurs, avertissements et des messages. Démarrer [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] , puis dans la barre de menus, choisissez **aide**, **recherche**.  
  
## <a name="in-this-section"></a>Dans cette section  

Les articles répertoriés dans cette section de la documentation montrent comment générer des applications sur la ligne de commande. Ils expliquent aussi comment personnaliser l'environnement de build en ligne de commande pour utiliser les ensembles d'outils 64 bits et cibler les plateformes x86, x64 et ARM. Enfin, ils illustrent l'utilisation des outils de génération en ligne de commande MSBuild et NMAKE.  
  
[Procédure pas à pas : compilation d’un programme C++ natif sur la ligne de commande](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
Fournit un exemple illustrant la création et la compilation un programme C++ simple sur la ligne de commande.  
  
[Procédure pas à pas : Compilation d’un programme C sur la ligne de commande](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
Décrit comment compiler un programme écrit dans le langage de programmation C.  
  
[Procédure pas à pas : compilation d’un programme C++-CLI sur la ligne de commande](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)  
Décrit comment créer et compiler un programme C++/CLI qui utilise le .NET Framework.  
  
[Procédure pas à pas : compilation d’un programme C++-CX sur la ligne de commande](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)  
Décrit comment créer et compiler un programme C++/CX qui utilise le Windows Runtime.  
  
[Définir le chemin d’accès et les Variables d’environnement pour les versions de ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)  
Décrit comment ouvrir une fenêtre d’invite de commandes qui a les variables d’environnement requises défini pour les versions de ligne de commande qui ciblent x86, x64, les plateformes et ARM à l’aide d’un ensemble d’outils 32 bits ou 64 bits.  
  
[NMAKE, référence](../build/nmake-reference.md)  
Fournit des liens vers des articles qui décrivent l'utilitaire Microsoft Program Maintenance Utility (NMAKE.EXE).  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
Fournit des liens vers des articles qui expliquent comment utiliser MSBuild.EXE.  
  
## <a name="related-sections"></a>Rubriques connexes  

[/ MD, / MT, /LD (utiliser la bibliothèque Runtime)](../build/reference/md-mt-ld-use-run-time-library.md)  
Décrit comment utiliser ces options de compilateur pour utiliser une bibliothèque runtime Debug ou Release.  
  
[Options du compilateur C/C++](../build/reference/compiler-options.md)  
Fournit des liens vers des articles qui présentent les options de compilateur C et C++, ainsi que CL.exe.  
  
[Options de l’éditeur de liens](../build/reference/linker-options.md)  
Fournit des liens vers des articles qui présentent les options de l'éditeur de liens et LINK.exe.  
  
[Outils de génération C/C++](../build/reference/c-cpp-build-tools.md)  
Fournit des liens vers les outils de génération C/C++ inclus dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Voir aussi  

[Génération de programmes C/C++](../build/building-c-cpp-programs.md)