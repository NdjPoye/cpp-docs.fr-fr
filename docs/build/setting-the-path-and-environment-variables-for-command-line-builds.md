---
title: "D&#233;finition du chemin d&#39;acc&#232;s et des variables d&#39;environnement pour la g&#233;n&#233;ration &#224; partir de la ligne de commande | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "include"
  - "Lib"
  - "Path"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe (compilateur C++), variables d'environnement"
  - "compiler le code source (C++), à partir de la ligne de commande"
  - "variables d'environnement (C++)"
  - "variables d'environnement (C++), CL (compilateur)"
  - "INCLUDE (mot réservé)"
  - "LIB (variable d'environnement)"
  - "LINK (outil C++), variables d'environnement"
  - "LINK (outil C++), chemin"
  - "PATH (mot réservé)"
  - "fichier VCVARS32.bat"
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
caps.latest.revision: 17
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;finition du chemin d&#39;acc&#232;s et des variables d&#39;environnement pour la g&#233;n&#233;ration &#224; partir de la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les outils de génération en ligne de commande [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] requièrent plusieurs variables d'environnement personnalisées pour votre installation.  Quand [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] est installé, il crée des fichiers de commandes qui définissent les variables d'environnement requises, puis il crée des raccourcis permettant d'ouvrir une fenêtre d'invite de commandes dans laquelle ces variables sont déjà définies.  Pour utiliser ces outils en ligne de commande, vous pouvez exécuter l'un de ces raccourcis ou ouvrir une fenêtre d'invite de commandes traditionnelle puis exécuter le fichier de commandes vcvarsall.bat.  
  
 Les outils en ligne de commande [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] utilisent les variables d'environnement PATH, TMP, INCLUDE, LIB et LIBPATH, et peuvent également utiliser des variables d'environnement spécifiques aux outils.  Comme les valeurs de ces variables d'environnement sont spécifiques à votre installation et sont susceptibles d'être modifiées par des mises à niveau ou des mises à jour du produite, nous vous recommandons d'utiliser vcvarsall.bat ou un raccourci vers la fenêtre d'invite de commandes développeur au lieu de les définir vous\-même.  Pour obtenir des informations sur les variables d'environnement spécifiques utilisées par le compilateur et l'éditeur de liens, consultez [Variables d'environnement CL](../build/reference/cl-environment-variables.md) et [Variables d'environnement de LINK](../build/reference/link-environment-variables.md).  
  
> [!NOTE]
>  Plusieurs outils en ligne de commande et options d'outils exigent des autorisations d'administrateur.  Pour pouvoir les utiliser, nous vous recommandons d'ouvrir une fenêtre d'invite de commandes en utilisant l'option **Exécuter en tant qu'administrateur** \(dans le menu contextuel de la fenêtre d'invite de commandes que vous souhaitez ouvrir\).  
  
## Utilisation des raccourcis d'invite de commandes  
 Le raccourci d'invite de commandes développeur qui est inclus dans chaque édition de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ouvre une fenêtre d'invite de commandes et définit l'environnement afin d'utiliser l'ensemble d'outils 32 bits natif x86 pour cibler les processeurs x86.  Des fenêtres d'invite de commandes pour compilateurs croisés 32 bits qui ciblent les plateformes x64 et ARM sont également disponibles.  Selon votre système et l'édition de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] installée, un raccourci d'invite de commandes pour un ensemble d'outils 64 bits natif x64 qui cible les processeurs x64, et un autre pour un compilateur croisé 64 bits qui cible les processeurs x86, peuvent également être disponibles.  Ces versions de l'ensemble d'outils en ligne de commande sont disponibles dans toutes les éditions de Visual Studio :  
  
 x86 sur x86  
 Utilisez cet ensemble d'outils pour créer des fichiers de sortie pour les ordinateurs x86.  Il s'exécute en tant que processus 32 bits natif sur un ordinateur x86 et sous WOW64 sur un système d'exploitation Windows 64 bits.  
  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] sur les ordinateurs x86 \(compilateur croisé [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\)  
 Utilisez cet ensemble d'outils pour créer des fichiers de sortie pour [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Il s'exécute en tant que processus 32 bits natif sur un ordinateur x86 et sous WOW64 sur un système d'exploitation Windows 64 bits.  
  
 ARM sur les ordinateurs x86 \(compilateur croisé ARM\)  
 Utilisez cet ensemble d'outils pour créer des fichiers de sortie pour les ordinateurs ARM.  Il s'exécute en tant que processus 32 bits natif sur un ordinateur x86 et sous WOW64 sur un système d'exploitation Windows 64 bits.  
  
 Ces versions de l'ensemble d'outils en ligne de commandes sont disponibles sur les plateformes 64 bits :  
  
 x86 sur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]  
 Utilisez cet ensemble d'outils pour créer des fichiers de sortie pour les ordinateurs x86.  Il s'exécute en tant que processus natif sur un système d'exploitation Windows 64 bits.  
  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] sur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]  
 Utilisez cet ensemble d'outils pour créer des fichiers de sortie pour les ordinateurs [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Il s'exécute en tant que processus natif sur un système d'exploitation Windows 64 bits.  
  
 ARM sur les ordinateurs x64 \(compilateur croisé ARM\)  
 Utilisez cet ensemble d'outils pour créer des fichiers de sortie pour les ordinateurs ARM.  Il s'exécute en tant que processus 64 bits natif sur un système d'exploitation Windows 64 bits.  
  
#### Pour ouvrir une fenêtre d'invite de commandes développeur  
  
1.  Quand l'écran d'accueil de Windows 8 est affiché, tapez Visual Studio Tools.  Notez que les résultats de la recherche changent à mesure que vous tapez ; lorsque **Visual Studio Tools** apparaît, choisissez cette option.  
  
     Dans les versions antérieures de Windows, choisissez **Démarrer** et tapez Visual Studio Tools dans la zone de recherche.  Lorsque **Visual Studio Tools** apparaît dans les résultats de la recherche, choisissez cette option.  
  
2.  Dans le dossier **Visual Studio Tools**, ouvrez **Invite de commandes développeur** pour votre version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  \(Pour l'exécuter en tant qu'administrateur, ouvrez le menu contextuel de l'invite de commandes développeur et choisissez **Exécuter en tant qu'administrateur**.\)  
  
 L'invite de commandes développeur définit l'environnement afin d'utiliser l'ensemble d'outils 32 bits natif pour cibler les processeurs x86.  Choisissez l'**invite de commandes des outils croisés x64** afin d'utiliser l'ensemble d'outils 32 bits natif pour cibler les processeurs x64.  Choisissez l'**invite de commandes des outils croisés ARM** afin d'utiliser l'ensemble d'outils 32 bits natif pour cibler les processeurs ARM.  Choisissez l'**invite de commandes des outils natifs x64** afin d'utiliser l'ensemble d'outils 64 bits natif pour cibler les processeurs x64.  
  
## Utilisation de vcvarsall.bat dans une fenêtre d'invite de commandes  
 L'exécution de vcvarsall.bat dans une fenêtre d'invite de commandes traditionnelle vous permet de définir les variables d'environnement pour configurer la ligne de commande pour une compilation 32 bits ou 64 bits native, ou pour une compilation croisée sur des processeurs x86, x64 ou ARM.  Si aucun argument n'est fourni, vcvarsall.bat configure les variables d'environnement pour utiliser le compilateur 32 bits natif pour des cibles x86.  Vous pouvez toutefois l'utiliser pour configurer les compilateurs.  Si vous spécifiez une configuration de compilateur qui n'est pas installée ou n'est pas disponible sur l'architecture de votre ordinateur de build, un message s'affiche.  Le tableau suivant montre les arguments pris en charge.  
  
|Argument Vcvarsall.bat|Compilateur|Architecture de l'ordinateur de build|Architecture de sortie de génération|  
|----------------------------|-----------------|-------------------------------------------|------------------------------------------|  
|x86|natif 32 bits x86|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|x86|  
|x86\_amd64|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] sur x86 croisé|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|x86\_arm|ARM sur x86 croisé|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|ARM|  
|amd64|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 64 bits natif|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|amd64\_x86|x86 sur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] croisé|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|x86|  
|amd64\_arm|ARM sur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] croisé|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|ARM|  
  
 La procédure suivante illustre la configuration d'une invite de commandes dans le but d'utiliser l'ensemble d'outils 32 bits natif pour cibler les plateformes x86.  
  
#### Pour exécuter vcvarsall.bat  
  
1.  À l'invite de commandes, accédez au répertoire d'installation de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  \(Cet emplacement dépend du système et de l'installation de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], mais un emplacement standard est C:\\Program Files \(x86\)\\Microsoft Visual Studio *version*\\VC\\.\) Par exemple, entrez :  
  
     cd "\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  Pour configurer cette fenêtre d'invite de commandes pour des générations en ligne de commande x86 32 bits, à l'invite de commandes, entrez :  
  
     `vcvarsall x86`  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] fournit également vcvars32.bat pour configurer un environnement de ligne de commande.  Le fichier vcvars32.bat est limité à la définition des variables d'environnement appropriées pour permettre des générations en ligne de commande x86 32 bits.  Il est équivalent à la commande `vcvarsall x86`.  
  
 Si vous utilisez [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md) pour des générations en ligne de commande, l'environnement défini par vcvarsall.bat ou vcvars32.bat n'affecte pas vos builds, à moins que vous spécifiiez également l'option **\/useenv**.  
  
> [!CAUTION]
>  Le fichier vcvarsall.bat peut varier d'un ordinateur à l'autre.  Ne remplacez pas un fichier vcvarsall.bat manquant ou endommagé en utilisant un fichier provenant d'un autre ordinateur.  Réexécutez le programme d'installation de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour remplacer le fichier manquant.  
>   
>  Le fichier vcvarsall.bat varie également d'une version à l'autre.  Si la version actuelle de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] est installée sur un ordinateur qui possède également une version antérieure de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], n'exécutez pas vcvarsall.bat et vcvars32.bat issus des différentes versions dans la même fenêtre d'invite de commandes.  
  
## Voir aussi  
 [Génération à partir de la ligne de commande](../build/building-on-the-command-line.md)   
 [Liaison](../build/reference/linking.md)   
 [Options de l'Éditeur de liens](../build/reference/linker-options.md)   
 [Compilation d'un programme C\/C\+\+](../build/reference/compiling-a-c-cpp-program.md)   
 [Options du compilateur](../build/reference/compiler-options.md)