---
title: "Comment&#160;: configurer des projets Visual C++ pour cibler des plateformes 64&#160;bits | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "plateformes [C++], 64 bits"
  - "programmation 64 bits [C++], configurer des projets"
  - "configurations de projet (C++)"
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: configurer des projets Visual C++ pour cibler des plateformes 64&#160;bits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser les configurations de projet dans Visual Studio pour configurer des applications C\+\+ pour qu’elles ciblent des plateformes 64 bits. Vous pouvez également migrer des paramètres de projet Win32 dans une configuration de projet 64 bits.  
  
### Pour configurer des applications C\+\+ pour qu’elles ciblent des plateformes 64 bits  
  
1.  Ouvrez le projet C\+\+ à configurer.  
  
2.  Ouvrez les pages de propriétés de ce projet. Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md).  
  
    > [!NOTE]
    >  Pour les projets .NET, assurez\-vous que le nœud **Propriétés de configuration** ou l’un de ses nœuds enfants est sélectionné dans la boîte de dialogue **Pages de propriétés de \<nom\_projet\>** ; sinon, le bouton **Gestionnaire de configurations** n’est pas disponible.  
  
3.  Choisissez le bouton **Gestionnaire de configurations** pour ouvrir la boîte de dialogue **Gestionnaire de configurations**.  
  
4.  Dans la liste déroulante **Plateforme de la solution active**, sélectionnez l’option **\<Nouveau...\>** pour ouvrir la boîte de dialogue **Nouvelle plateforme de solution**.  
  
5.  Dans la liste déroulante **Tapez ou sélectionnez la nouvelle plateforme**, sélectionnez une plateforme 64 bits.  
  
    > [!NOTE]
    >  Dans la boîte de dialogue **Nouvelle plateforme de solution**, vous pouvez utiliser l’option **Copier les paramètres à partir de** pour copier les paramètres de projet existants dans la nouvelle configuration de projet 64 bits.  
  
6.  Sélectionnez le bouton **OK**. La plateforme que vous avez sélectionnée à l’étape précédente s’affiche sous **Plateforme de la solution active** dans la boîte de dialogue **Gestionnaire de configurations**.  
  
7.  Choisissez **Fermer** dans la boîte de dialogue  **Gestionnaire de configurations**, puis **OK** dans la boîte de dialogue **Pages de propriétés de \<nom\_projet\>**.  
  
### Pour copier des paramètres de projet Win32 dans une configuration de projet 64 bits  
  
-   Quand la boîte de dialogue **Nouvelle plateforme de solution** est ouverte pendant que vous configurez un projet pour cibler une plateforme 64 bits, dans la liste déroulante **Copier les paramètres à partir de**, sélectionnez **Win32**. Ces paramètres de projet sont mis à jour automatiquement au niveau du projet :  
  
    -   L’option [\/MACHINE](../build/reference/machine-specify-target-platform.md) de l’Éditeur de liens prend la valeur **\/MACHINE:X64**.  
  
    -   L’**Inscription de la sortie** est désactivée. Pour plus d'informations, consultez [Pages de propriétés de l'Éditeur de liens](../ide/linker-property-pages.md).  
  
    -   L’**Environnement cible** prend la valeur **\/env x64**. Pour plus d'informations, consultez [Pages de propriétés MIDL : Général](../ide/midl-property-pages-general.md).  
  
    -   L’option **Validation des paramètres** est effacée et réinitialisée à la valeur par défaut. Pour plus d'informations, consultez [Pages de propriétés MIDL : Avancé](../ide/midl-property-pages-advanced.md).  
  
    -   Si vous avez affecté la valeur **\/ZI** à l’option **Format des informations de débogage** dans la configuration de projet Win32, elle prend la valeur **\/Zi** dans la configuration de projet 64 bits. Pour plus d'informations, consultez [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../build/reference/z7-zi-zi-debug-information-format.md).  
  
    > [!NOTE]
    >  Aucune de ces propriétés de projet n’est modifiée si elle est substituée au niveau du fichier.  
  
## Voir aussi  
 [Applications 64 bits](../Topic/64-bit%20Applications.md)   
 [Configuration des programmes pour les processeurs 64 bits](../build/configuring-programs-for-64-bit-visual-cpp.md)   
 [Déboguer des applications 64 bits](../Topic/Debug%2064-Bit%20Applications.md)