---
title: "Proc&#233;dure pas &#224; pas&#160;: d&#233;ploiement d&#39;une application Visual&#160;C++ &#224; l&#39;aide de Visual&#160;C++ Redistributable Package | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "procédure pas à pas, déployer une application Visual C++ à l'aide du package redistribuable"
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: d&#233;ploiement d&#39;une application Visual&#160;C++ &#224; l&#39;aide de Visual&#160;C++ Redistributable Package
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article pas \- à \- pas décrit comment utiliser Visual C\+\+ redistributable package pour déployer une application Visual C\+\+.  
  
## Composants requis  
 Vous devez disposer de ces composants pour exécuter cette procédure pas \- à \- pas :  
  
-   Un ordinateur sur lequel Visual Studio est installé.  
  
-   Un ordinateur supplémentaire qui n'a pas les bibliothèques Visual C\+\+.  
  
### Pour utiliser Visual C\+\+ redistributable package pour déployer une application  
  
1.  Créez et générez une application MFC en suivant les trois premières étapes dans [Walkthrough: Deploying a Visual C\+\+ Application By Using a Setup Project](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
2.  Créez un fichier setup.bat, nommez\-le, puis ajouter des commandes suivantes à celui\-ci.  Modifiez `MyMFCApplication` par le nom de votre projet.  
  
    ```  
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  Créez un fichier d'installation à extraction automatique :  
  
    1.  À une invite de commandes ou dans la fenêtre **Exécuter**, iexpress.exe exécuté.  
  
    2.  Sélectionnez **Créez le nouveau fichier de directive d'extraction pour individu** puis choisissez le bouton **Suivant** .  
  
    3.  Sélectionnez **Extraire les fichiers et exécuter une commande d'installation** puis choisissez **Suivant**.  
  
    4.  Dans la zone de texte, entrez le nom de votre application MFC puis choisissez **Suivant**.  
  
    5.  Sur la page **Invite de confirmation**, sélectionnez **Pas d'invite** puis choisissez **Suivant**.  
  
    6.  Dans la page **Contrat de licence**, sélectionnez **N'affichez pas une licence** puis choisissez **Suivant**.  
  
    7.  Dans la page **Fichiers empaquetés**, ajoutez les fichiers suivants puis choisissez **Suivant**.  
  
        -   Votre application MFC \(fichier .exe\).  
  
        -   vcredist\_x86.exe.  Ce fichier se trouve dans le dossier \\Program Files\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\vcredist\_x86\\.  
  
        -   Le fichier setup.bat de que vous avez créé à l'étape précédente.  
  
    8.  Sur la page **Installez le programme pour lancer**, dans la zone de texte **Installez le programme**, entrez la ligne de commande suivante puis choisissez **Suivant**.  
  
         **cmd.exe \/c "setup.bat"**  
  
    9. Dans la page **Afficher la fenêtre**, sélectionnez **Par défaut** puis choisissez **Suivant**.  
  
    10. Dans la page **Message terminé**, sélectionnez **Aucun message** puis choisissez **Suivant**.  
  
    11. Dans la page **Nom du package et options**, entrez un nom pour votre fichier d'installation à extraction automatique, sélectionnez l'option **Enregistrez les fichiers à l'aide de le nom de fichiers longs à l'intérieur de le package**, puis choisissez **Suivant**.  La fin du nom de fichier doit être l'exemple de Setup.exe\-for, MyMFCApplicationSetup.exe.  
  
    12. Dans la page **Configurez le redémarrage**, sélectionnez **Pas de redémarrage** puis choisissez **Suivant**.  
  
    13. Sur la page **Enregistrez la directive d'extraction pour individu**, sélectionnez **Enregistrez le fichier de directive \(SED\) d'extraction pour individu** puis choisissez **Suivant**.  
  
    14. Dans la page **Créer un package**, choisissez **Suivant**.  
  
4.  Testez le fichier d'installation à extraction automatique sur un autre ordinateur, qui ne dispose pas des bibliothèques Visual C\+\+ :  
  
    1.  Sur un autre ordinateur, téléchargez une copie du fichier d'installation, puis \-le la en l'exécutant l'et en suivant les étapes qu'elles fournissent.  
  
    2.  Exécutez l'application MFC.  
  
         Le fichier d'installation à extraction automatique installe l'application MFC qui se trouve dans le dossier que vous avez spécifié à l'étape 2.  L'application s'exécute correctement car le programme d'installation de Visual C\+\+ Redistributable Package est inclus dans le fichier d'installation auto\-extractible.  
  
        > [!IMPORTANT]
        >  Pour déterminer quelle version du runtime est installé, le programme d'installation la clé de Registre\\HKLM\\SOFTWARE\\Microsoft\\VisualStudio\\11.0\\VC\\Runtimes\\\[platform\].  Si la version actuellement installée est plus récente que la version que le programme d'installation tente d'installation, le programme d'installation retourne le succès sans installer la version antérieure et permet une entrée supplémentaire sur la page installée de programmes du panneau de configuration.  
  
## Voir aussi  
 [Exemples de déploiement](../ide/deployment-examples.md)