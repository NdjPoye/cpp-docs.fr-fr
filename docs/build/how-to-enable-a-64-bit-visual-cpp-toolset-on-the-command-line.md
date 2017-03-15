---
title: "Comment&#160;: activer un ensemble d&#39;outils du compilateur Visual&#160;C++ 64 bits sur la ligne de commande | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur 64 bits (C++), ligne de commande (utilisation)"
  - "compilateur 64 bits (C++), activer un ensemble d'outils en ligne de commande"
  - "ligne de commande (C++), compilateur 64 bits"
  - "IPF"
  - "IPF, compilateur de ligne de commande"
  - "Itanium (C++)"
  - "Itanium (C++), compilateur de ligne de commande"
  - "x64 (C++)"
  - "x64 (C++), compilateur de ligne de commande"
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
caps.latest.revision: 30
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: activer un ensemble d&#39;outils du compilateur Visual&#160;C++ 64 bits sur la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ inclut des compilateurs permettant de créer des applications pouvant être exécutées sur un système d'exploitation Windows 32 bits, 64 bits ou ARM.  
  
> [!NOTE]
>  Pour plus d'informations sur les outils spécifiques fournis avec chaque édition Visual C\+\+, consultez [Outils et modèles Visual C\+\+ dans les éditions Visual Studio](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md).  
>   
>  Pour plus d'informations sur l'utilisation de l'IDE de Visual Studio pour créer des applications 64 bits, consultez [Comment : configurer des projets Visual C\+\+ pour cibler des plateformes 64 bits](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] inclut des compilateurs 32 bits, x86, natifs et croisés pour les cibles x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] et ARM.  Lorsque [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] est installé sur un système d'exploitation Windows 64 bits, les compilateurs 32 bits, natifs x86 et croisés, ainsi que les compilateurs 64 bits, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] natifs et croisés, sont installés pour chaque cible \(x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] et ARM\).  Les compilateurs 32 bits et 64 bits pour chaque cible génèrent un code identique, mais les compilateurs 64 bits prennent en charge davantage de mémoire pour les symboles d'en\-têtes précompilés et les options d'optimisation de l'ensemble du programme \([\/GL](../build/reference/gl-whole-program-optimization.md), [\/LTCG](../build/reference/ltcg-link-time-code-generation.md)\).  Si vous rencontrez des problèmes de mémoire lors de l'utilisation d'un compilateur 32 bits, essayez le compilateur 64 bits.  
  
 Quand Visual Studio est installé sur un système d'exploitation Windows 64 bits, des raccourcis supplémentaires d'invite de commandes pour les compilateurs natifs [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] et croisés x86 64 bits sont disponibles.  Pour accéder à ces invites de commandes sur Windows 8, sur l'écran **Démarrer**, ouvrez **Toutes les applications**.  Dans la version installée de **[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]**, ouvrez **Visual Studio Tools**, puis choisissez l'une des invites de commandes des outils natifs ou croisés.  Pour les versions antérieures de Windows, choisissez **Démarrer**, développez **Tous les programmes**, **[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]**, **Visual Studio Tools**, puis sélectionnez une invite de commandes.  
  
## Vcvarsall.bat  
 Vous pouvez utiliser n'importe quel compilateur sur la ligne de commande en exécutant le fichier de commande vcvarsall.bat afin de configurer les variables de chemin d'accès et d'environnement qui activent l'ensemble d'outils du compilateur.  Comme il n'existe pas de raccourcis d'invite de commandes pour activer un ensemble d'outils 64 bits pour plateformes x86 ou ARM, utilisez vcvarsall.bat dans une fenêtre d'invite de commandes pour utiliser plutôt l'ensemble d'outils 64 bits.  Pour plus d'informations, consultez [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Les étapes suivantes montrent comment configurer une invite de commandes pour utiliser l'ensemble d'outils natif 64 bits pour les plateformes x86, x64 et ARM.  
  
#### Pour exécuter vcvarsall.bat afin d'utiliser un ensemble d'outils 64 bits  
  
1.  À l'invite de commandes, basculez vers le répertoire d'installation de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  \(Si l'emplacement dépend du système et de l'installation de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], il s'agit très souvent de l'emplacement suivant : C:\\Program Files \(x86\)\\Microsoft Visual Studio *version*\\VC\\.\) Par exemple, entrez :  
  
     cd "\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  Pour configurer cette fenêtre d'invite de commandes pour des générations à partir de la ligne de commande 64 bits qui ciblent les plateformes x64, à l'invite de commandes, entrez :  
  
     `vcvarsall amd64`  
  
3.  Pour configurer cette fenêtre d'invite de commandes pour des générations à partir de la ligne de commande 64 bits qui ciblent les plateformes x86, à l'invite de commandes, entrez :  
  
     `vcvarsall amd64_x86`  
  
4.  Pour configurer cette fenêtre d'invite de commandes pour des générations à partir de la ligne de commande 64 bits qui ciblent les plateformes ARM, à l'invite de commandes, entrez :  
  
     `vcvarsall amd64_arm`  
  
## Voir aussi  
 [Configuration des programmes pour les processeurs 64 bits](../build/configuring-programs-for-64-bit-visual-cpp.md)