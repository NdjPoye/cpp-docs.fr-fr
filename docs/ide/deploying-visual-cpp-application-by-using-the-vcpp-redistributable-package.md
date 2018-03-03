---
title: "Déployer une application à l’aide du Package redistribuable (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52e3b048f896f0cfd532cb3000617756af2dca92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>Procédure pas à pas : déploiement d'une application Visual C++ à l'aide de Visual C++ Redistributable Package
Cet article décrit comment utiliser Visual C++ Redistributable Package pour déployer une application Visual C++.  
  
## <a name="prerequisites"></a>Prérequis  
 Vous devez installer ces composants pour terminer cette procédure pas à pas :  
  
-   Un ordinateur équipé de Visual Studio est installé.  
  
-   Un ordinateur supplémentaire qui n’a pas les bibliothèques Visual C++.  
  
### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Pour utiliser le Package redistribuable Visual C++ pour déployer une application  
  
1.  Créer et générer une application MFC en suivant les trois premières étapes dans [procédure pas à pas : déploiement d’un Visual C++ Application à l’aide d’un projet d’installation](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
2.  Créer un fichier, nommez-le setup.bat et ajoutez les commandes suivantes à ce dernier. Modification `MyMFCApplication` au nom de votre projet.  
  
    ```cmd
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  Créer un fichier d’installation à extraction automatique :  
  
    1.  À l’invite de commandes ou dans le **exécuter** fenêtre, exécutez iexpress.exe.  
  
    2.  Sélectionnez **créer un fichier de Directive à Extraction automatique** , puis choisissez le **suivant** bouton.  
  
    3.  Sélectionnez **extraire des fichiers et exécuter une commande d’installation** , puis **suivant**.  
  
    4.  Dans la zone de texte, entrez le nom de votre application MFC, puis choisissez **suivant**.  
  
    5.  Sur le **invite de Confirmation** page, sélectionnez **aucune invite** , puis **suivant**.  
  
    6.  Sur le **contrat de licence** page, sélectionnez **n’affichent pas d’une licence** , puis **suivant**.  
  
    7.  Sur le **les fichiers compressés** page, ajoutez les fichiers suivants, puis choisissez **suivant**.  
  
        -   Votre application MFC (fichier .exe).  
  
        -   VCRedist_x86.exe. Ce fichier se trouve dans \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\vcredist_x86\\.  
  
        -   Le fichier setup.bat que vous avez créé à l’étape précédente.  
  
    8.  Sur le **au lancement du programme d’installation** page, dans le **programme d’installation** zone de texte, entrez la ligne de commande suivante, puis choisissez **suivant**.  
  
         **cmd.exe /c « setup.bat »**  
  
    9. Sur le **afficher la fenêtre** page, sélectionnez **par défaut** , puis **suivant**.  
  
    10. Sur le **message terminé** page, sélectionnez **aucun message** , puis **suivant**.  
  
    11. Sur le **nom du Package et les Options** , entrez un nom pour votre fichier d’installation à extraction automatique, sélectionnez le **stocker des fichiers à l’aide du nom de fichier Long à l’intérieur du Package** option, puis choisissez **suivant**. La fin du nom de fichier doit être Setup.exe—for exemple, MyMFCApplicationSetup.exe.  
  
    12. Sur le **configurer le redémarrage** page, sélectionnez **aucun redémarrage** , puis **suivant**.  
  
    13. Sur le **enregistrer la Directive à Extraction automatique** page, sélectionnez **enregistrer Self Extraction fichier SED (Directive)** , puis **suivant**.  
  
    14. Sur le **créer un package** choisissez **suivant**.  
  
4.  Tester le fichier d’installation à extraction automatique sur l’autre ordinateur, ce qui n’a pas les bibliothèques Visual C++ :  
  
    1.  Sur un autre ordinateur, téléchargez une copie du fichier d’installation, puis installez-le en exécutant et en suivant les étapes qu’il fournit.  
  
    2.  Exécutez l’application MFC.  
  
         Le fichier d’installation à extraction automatique installe l’application MFC qui se trouve dans le dossier que vous avez spécifié à l’étape 2. L’application s’exécute correctement, car le programme d’installation du Package redistribuable Visual C++ est inclus dans le fichier d’installation à extraction automatique.  
  
        > [!IMPORTANT]
        >  Pour déterminer quelle version du runtime est installée, le programme d’installation vérifie les \HKLM\SOFTWARE\Microsoft\VisualStudio\11.0\VC\Runtimes clé du Registre\\[plateforme]. Si la version actuellement installée est plus récente que la version que le programme d’installation tente d’installer, le programme d’installation aboutit sans installer la version antérieure et laisse une entrée supplémentaire sur la page des programmes installés dans le panneau de configuration.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemples de déploiement](../ide/deployment-examples.md)