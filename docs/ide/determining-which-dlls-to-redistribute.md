---
title: "D&#233;termination des DLL &#224; redistribuer | Microsoft Docs"
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
  - "déploiement d'applications (C++), redistribution des DLL"
  - "dépendances (C++), déploiement d'applications et"
  - "déployer des applications (C++), redistribution des DLL"
  - "DLL (C++), redistribuer"
  - "redistribuer des DLL"
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# D&#233;termination des DLL &#224; redistribuer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous créez une application qui utilise les DLL fournies par Visual Studio, ces mêmes DLL doivent aussi être présentes sur les ordinateurs des utilisateurs de votre application pour que celle\-ci puisse s'exécuter.  Comme il est probable que la plupart des utilisateurs n'ont pas installé Visual Studio, vous devez les leur fournir.  Visual Studio met à disposition ces DLL sous forme de bibliothèques redistribuables que vous pouvez inclure dans le programme d'installation de votre application.  
  
 Les DLL redistribuables sont incluse dans votre installation de Visual Studio.  Par défaut, elles sont installées dans le dossier Program Files \(x86\)\\Microsoft Visual Studio version\\VC\\Redist.  Pour qu'il vous soit plus facile de les inclure dans votre programme d'installation, elles sont aussi disponibles sous forme de packages redistribuables autonomes via le Centre de téléchargement Microsoft.  Il s'agit d'exécutables qui installent les fichiers redistribuables sur l'ordinateur de l'utilisateur.  La version du package redistribuable doit correspondre à la version de l'ensemble d'outils Visual Studio qui a servi créer votre application.  Pour rechercher un package redistribuable correspondant, recherchez « Packages redistribuables Visual C\+\+ » dans le [Centre de téléchargement Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=158431).  
  
 Pour identifier les DLL à redistribuer avec votre application, collectez une liste des DLL dont dépend votre application.  Une façon de collecter la liste est d'exécuter l'outil Dependency Walker \(depends.exe\), comme indiqué dans [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  
  
 Dès que vous avez la liste de dépendances, comparez\-la à la liste contenue dans un fichier Redist.txt du répertoire d'installation de Microsoft Visual Studio ou à la « liste REDIST » des DLL redistribuables référencée dans la section « Code distribuable » des termes du contrat de licence logiciel Microsoft de votre copie de Visual Studio.  Pour Visual Studio 2013, la liste est disponible en ligne dans [Code distribuable pour Microsoft Visual Studio 2013 et Microsoft Visual Studio 2013 SDK](http://go.microsoft.com/fwlink/p/?LinkId=313603).  Vous ne pouvez pas redistribuer tous les fichiers inclus dans Visual Studio ; vous êtes uniquement autorisé à redistribuer les fichiers spécifiés dans Redist.txt ou dans la « liste REDIST » en ligne. Les versions Debug des applications et les diverses DLL de débogage Visual C\+\+ ne sont pas redistribuables.  Pour plus d'informations, consultez [Choix d'une méthode de déploiement](../ide/choosing-a-deployment-method.md).  
  
 Le tableau suivant décrit certaines des DLL Visual C\+\+ dont votre application peut dépendre.  
  
|Bibliothèque Visual C\+\+|Description|S'applique à|  
|-------------------------------|-----------------|------------------|  
|msvcr*version*.dll|Bibliothèque Runtime C \(CRT\) pour le code natif.|Applications qui utilisent les [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md).|  
|msvcp*version*.dll|Bibliothèque C\+\+ standard pour le code natif.|Applications qui utilisent la [Bibliothèque C\+\+ standard](../standard-library/cpp-standard-library-reference.md).|  
|mfc*version*.dll|Bibliothèque MFC \(Microsoft Foundation Class\).|Applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md).|  
|mfc*version*u.dll|Bibliothèque MFC avec prise en charge Unicode.|Applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) et requièrent la prise en charge Unicode.|  
|mfcmifc80.dll|Bibliothèque d'interfaces gérées MFC.|Applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) avec les [contrôles Windows Forms](../Topic/Windows%20Forms%20Controls.md).|  
|mfcm*version*.dll|Bibliothèque managée MFC.|Applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) avec les [contrôles Windows Forms](../Topic/Windows%20Forms%20Controls.md).|  
|mfcm*version*u.dll|Bibliothèque managée MFC avec prise en charge Unicode.|Applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) avec les [contrôles Windows Forms](../Topic/Windows%20Forms%20Controls.md) et qui nécessitent une prise en charge Unicode.|  
  
> [!NOTE]
>  Vous n'avez plus besoin de redistribuer Active Template Library sous forme de DLL distincte.  Sa fonctionnalité a été déplacée dans les en\-têtes et une bibliothèque statique.  
  
 Pour plus d'informations sur la redistribution de ces DLL avec votre application, consultez [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md).  Pour obtenir des exemples, consultez [Exemples de déploiement](../ide/deployment-examples.md).  
  
 En règle générale, vous n'avez pas besoin de redistribuer les DLL système, car elles font partie intégrante du système d'exploitation.  Toutefois, il peut y avoir des exceptions, par exemple, lorsque votre application doit s'exécuter sur plusieurs versions de systèmes d'exploitation Microsoft.  Dans ce cas, veillez à lire les termes du contrat de licence correspondants.  De même, essayez d'effectuer la mise à niveau des DLL système via Windows Update, les Service Packs ou les packages redistribuables proposés par Microsoft.  Vous pouvez accéder aux packages disponibles en les recherchant sur le site web [Support Microsoft](http://support.microsoft.com/) ou dans le [Centre de téléchargement Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=158431).  
  
## Voir aussi  
 [Choix d'une méthode de déploiement](../ide/choosing-a-deployment-method.md)   
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)