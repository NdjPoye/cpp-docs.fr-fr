---
title: "Redistribution des fichiers Visual&#160;C++ | Microsoft Docs"
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
  - "déploiement d'applications (C++), redistribuer des fichiers"
  - "déployer des applications (C++), redistribuer des fichiers"
  - "redistribution des fichiers (C++)"
  - "redistribuer des applications (C++)"
  - "redistribuer des applications (C++), à propos de la redistribution d'applications (C++)"
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
caps.latest.revision: 50
caps.handback.revision: 48
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Redistribution des fichiers Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous déployez une application, vous devez également déployer les fichiers qui sont requis pour sa prise en charge.  Si l'un de ces fichiers est fourni par Microsoft, vérifiez si vous êtes autorisé à le redistribuer.  Pour examiner les termes du contrat de licence logiciel Microsoft, consultez License.htm dans le répertoire où Visual Studio est installé ou sur le média d'installation Visual Studio.  Pour afficher la « liste REDIST » référencée dans la section « Code distribuable » des termes du contrat de licence logiciel Microsoft pour certaines éditions de Visual Studio, consultez [Code redistribuable pour Microsoft Visual Studio 2013 et Microsoft Visual Studio 2013 SDK](http://go.microsoft.com/fwlink/p/?LinkId=313603) sur le site web de Microsoft.  Pour plus d'informations sur les fichiers redistribuables, consultez [Détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md) et [Exemples de déploiement](../ide/deployment-examples.md).  
  
 Pour déployer des fichiers redistribuables Visual C\+\+, vous pouvez utiliser les packages redistribuables Visual C\+\+ \(VCRedist\_x86.exe, VCRedist\_x64.exe ou VCRedist\_arm.exe\) inclus dans Visual Studio.  Ces fichiers se trouvent sous le répertoire d'installation de Visual Studio, dans Program Files \[\(x86\)\]\\Microsoft Visual Studio *version*\\VC\\redist\\*locale*\\.  Une autre option consiste à utiliser des modules de fusion redistribuables \(fichiers .msm\), qui se trouvent dans Program Files \[\(x86\)\]\\Common Files\\Merge Modules\\.  Il est également possible d'installer directement les DLL Visual C\+\+ redistribuables dans le *dossier local de l'application*, qui est le dossier contenant votre fichier d'application exécutable.  Pour des raisons liées à la maintenance, il est déconseillé d'utiliser cet emplacement d'installation.  
  
 Les packages redistribuables Visual C\+\+ installent et inscrivent toutes les bibliothèques Visual C\+\+.  Si vous en utilisez un, vous devez le définir de sorte qu'il s'exécute sur le système cible en tant que condition préalable à l'installation de l'application.  Nous vous recommandons d'utiliser ces packages pour les déploiements car ils permettent une mise à jour automatique des bibliothèques Visual C\+\+.  Pour obtenir un exemple d'utilisation de ces packages, consultez [Procédure pas à pas : déploiement d'une application Visual C\+\+ à l'aide de Visual C\+\+ Redistributable Package](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
 Chaque package redistribuable Visual C\+\+ vérifie l'existence d'une version plus récente sur l'ordinateur.  Si une version plus récente est trouvée, le package n'est pas installé.  Depuis Visual Studio 2015, les packages redistribuables affichent un message d'erreur indiquant que l'installation a échoué.  Si un package est exécuté avec l'indicateur **\/quiet**, aucun message d'erreur ne s'affiche.  Dans les deux cas, une erreur est enregistrée par le programme d'installation de Microsoft, et un résultat d'erreur est retourné à l'appelant.  Depuis les packages de Visual Studio 2015, vous pouvez tester une valeur du Registre pour savoir si une version plus récente est installée.  La version actuellement installée est stockée sous la forme d'une valeur REG\_SZ de la clé Version, dans  HKEY\_LOCAL\_MACHINE\\SOFTWARE\[\\Wow6432Node\]\\Microsoft\\DevDiv\\vc\\Servicing\\14.0\\RuntimeMinimum.  Vous n'avez pas besoin d'installer votre package redistribuable si la version actuellement installée est plus récente.  
  
 Si vous utilisez un module de fusion qui contient une DLL Visual C\+\+, vous devez l'inclure dans le package Windows Installer \(ou dans un package d'installation similaire\) que vous utilisez pour déployer l'application.  Pour plus d'informations, consultez [Redistribution à l'aide de modules de fusion](../ide/redistributing-components-by-using-merge-modules.md).  Pour obtenir un exemple, consultez [Procédure pas à pas : déploiement d'une application Visual C\+\+ à l'aide d'un projet d'installation](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md), qui montre aussi comment utiliser InstallShield Limited Edition pour créer un package d'installation.  
  
## Erreurs d'exécution potentielles  
 Si une DLL de bibliothèque Visual C\+\+ n'est pas accessible et si Windows ne peut pas la charger pour votre application, le message suivant peut s'afficher : **Cette application n'a pas pu démarrer car MSVCR\<numéro\_version\>.dll est introuvable. La réinstallation de cette application peut corriger ce problème.**  
  
 Pour résoudre ce genre d'erreur, assurez\-vous que votre application se génère correctement et que les bibliothèques Visual C\+\+ sont déployées correctement sur le système cible.  Pour plus d'informations, consultez [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  
  
## Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Redistribution à l'aide de modules de fusion](../ide/redistributing-components-by-using-merge-modules.md)|Décrit comment utiliser les modules de fusion redistribuables [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] pour installer les bibliothèques Runtime Visual C\+\+ en tant que DLL partagées dans le dossier %windir%\\system32.|  
|[Redistribution de contrôles ActiveX Visual C\+\+](../ide/redistributing-visual-cpp-activex-controls.md)|Décrit comment redistribuer une application qui utilise les contrôles ActiveX.|  
|[Redistribution de fichiers de prise en charge de base de données](../ide/redistributing-database-support-files.md)|Explique comment redistribuer des fichiers de prise en charge pour les objets d'accès aux données \(DAO\) et les technologies de bases de données se trouvant dans le Kit de développement Microsoft Data Access SDK.|  
|[Redistribution de la bibliothèque MFC](../ide/redistributing-the-mfc-library.md)|Décrit comment redistribuer une application qui utilise MFC.|  
|[Redistribution d'une application ATL](../ide/redistributing-an-atl-application.md)|Décrit comment redistribuer une application qui utilise ATL.  Depuis Visual Studio 2012, aucune bibliothèque redistribuable pour ATL n'est requise.|  
|[Exemples de déploiement](../ide/deployment-examples.md)|Fournit des liens vers des exemples qui illustrent le déploiement d'applications Visual C\+\+.|  
|[Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)|Présente les concepts et les technologies de déploiement de Visual C\+\+.|